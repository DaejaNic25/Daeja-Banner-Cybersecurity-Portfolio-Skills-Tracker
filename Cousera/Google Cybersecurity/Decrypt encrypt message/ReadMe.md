# 🔓 Lab: Decrypt an Encrypted Message

**Course:** Google Cybersecurity Certificate — Coursera  
**Domain:** Cryptography | Linux CLI | Symmetric Encryption  
**Tools Used:** Linux CLI, `cat`, `ls`, `cd`, `tr`, `openssl`

---

## Overview

Encryption is one of the most critical controls for protecting data confidentiality. Security analysts must understand not only how encryption works, but how to work with encrypted files during investigations and recovery scenarios.

In this lab, I worked through a multi-step decryption challenge using two real-world cryptographic techniques: a **Caesar cipher** and **AES-256-CBC symmetric encryption**. The goal was to locate a hidden file, decode a cipher to retrieve a secret key, and then use that key to decrypt an encrypted file and recover its contents.

---

## Scenario

Starting in the `/home/analyst` directory, two files and a subdirectory were present. A `README.txt` provided instructions pointing to a hidden file containing a Caesar cipher — which, once decoded, revealed the command and key needed to decrypt the main encrypted file `Q1.encrypted`.

---

## Task 1 — Read the Contents of a File

### List the home directory
```bash
ls
```
**Output:** `Q1.encrypted  README.txt  caesar/`

---

### Read the README instructions
```bash
cat README.txt
```
> The README directed me to the `caesar` subdirectory, where a hidden file contained further instructions protected by a Caesar cipher.

---

## Task 2 — Find and Decode the Hidden File

### Navigate to the caesar subdirectory
```bash
cd caesar
```

### List all files including hidden files
```bash
ls -a
```
> In Linux, hidden files begin with a `.` (period) and are not shown by a standard `ls` command. The `-a` flag reveals them.

**Output:** `.  ..  .leftShift3`

---

### Read the hidden file
```bash
cat .leftShift3
```
> The file contents appeared scrambled — this is the result of a **Caesar cipher** with a left shift of 3. Each letter in the ciphertext is shifted 3 positions to the left of its true value (e.g., `d` = `a`, `e` = `b`).

---

### Decrypt the Caesar cipher using `tr`
```bash
cat .leftShift3 | tr "d-za-cD-ZA-C" "a-zA-Z"
```

> The `tr` command translates characters from one set to another. Here, the first parameter `"d-za-cD-ZA-C"` represents the shifted (encrypted) character set, and `"a-zA-Z"` is the original (decrypted) set. This effectively shifts every letter 3 positions back to reveal the plaintext — including the decryption command and key needed for Task 3.

---

### Return to the home directory
```bash
cd ~
```

---

## Task 3 — Decrypt the Encrypted File

### Run the OpenSSL decryption command (revealed from .leftShift3)
```bash
openssl aes-256-cbc -pbkdf2 -a -d -in Q1.encrypted -out Q1.recovered -k ettubrute
```

**Command breakdown:**

| Flag | Purpose |
|---|---|
| `aes-256-cbc` | Symmetric cipher — AES with a 256-bit key in CBC mode |
| `-pbkdf2` | Applies key stretching for added security against brute-force |
| `-a` | Specifies Base64 encoding for the output |
| `-d` | Decrypt mode |
| `-in Q1.encrypted` | Input: the encrypted file |
| `-out Q1.recovered` | Output: the recovered plaintext file |
| `-k ettubrute` | The decryption password/key |

---

### Verify the recovered file
```bash
ls
```
**Output:** `Q1.encrypted  Q1.recovered  README.txt  caesar/`

---

### Read the decrypted message
```bash
cat Q1.recovered
```
> The decrypted contents of `Q1.recovered` are now readable — the data has been successfully recovered.

---

## Key Takeaways

| Concept | Details |
|---|---|
| **Caesar Cipher** | Classical substitution cipher; shifts letters by a fixed number of positions |
| **`tr` Command** | Linux utility for character-level translation; useful for simple cipher decoding |
| **AES-256-CBC** | Industry-standard symmetric encryption; 256-bit key, Cipher Block Chaining mode |
| **`openssl`** | Linux command-line tool for encryption, decryption, and certificate operations |
| **`-pbkdf2`** | Password-Based Key Derivation Function 2 — hardens keys against brute-force attacks |
| **Hidden Files** | Linux files prefixed with `.` are hidden from standard `ls`; revealed with `ls -a` |
| **Symmetric Encryption** | Same key used to both encrypt and decrypt — key management is critical |

---

## Real-World Application

These skills directly support SOC and incident response workflows:

- **Malware Analysis** — Analysts often encounter encrypted payloads or obfuscated scripts; understanding `openssl` and encoding schemes is essential for unpacking them
- **Forensic File Recovery** — Recovering encrypted files with known keys is a common IR task, especially in ransomware investigations
- **Threat Hunting** — Recognizing Caesar ciphers and other obfuscation techniques in logs or scripts helps identify attacker tradecraft (MITRE ATT&CK: **T1027 – Obfuscated Files or Information**)
- **Evidence Handling** — Decrypting files in a controlled, documented way preserves chain of custody during investigations

---

*Completed as part of the Google Cybersecurity Certificate on Coursera.*
