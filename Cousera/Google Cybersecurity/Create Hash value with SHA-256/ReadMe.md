# 🔐 Lab: Create Hash Values with SHA-256

**Course:** Google Cybersecurity Certificate — Coursera  
**Domain:** Linux & Command Line | File Integrity | Cryptographic Hashing  
**Tools Used:** Linux CLI, `sha256sum`, `cat`, `ls`, `cmp`

---

## Overview

Hash functions are a core tool in a security analyst's toolkit. A **hash function** is a one-way algorithm that takes file contents as input and produces a fixed-length **hash value** (also called a digest). Because even a single changed byte produces a completely different hash, these values are used to verify file integrity and detect tampering — such as identifying a malicious file masquerading as a legitimate one.

In this lab, I generated SHA-256 hashes for two files that appeared identical on the surface, then used Linux commands to detect the differences between them.

---

## Scenario

Two files — `file1.txt` and `file2.txt` — were provided in a Linux environment. The task was to determine whether they were truly identical or subtly different by comparing their cryptographic hash values.

---

## Task 1 — Generate Hash Values

### Step 1: List directory contents
```bash
ls /home/analyst
```
**Output:** `file1.txt  file2.txt`

---

### Step 2: Display file contents
```bash
cat file1.txt
cat file2.txt
```
> Both files displayed identical-looking content — visually indistinguishable.

---

### Step 3: Generate SHA-256 hashes
```bash
sha256sum file1.txt
sha256sum file2.txt
```

> Despite appearing the same via `cat`, the SHA-256 hashes returned **different values**, confirming the files were not identical at the byte level.

---

## Task 2 — Compare Hashes

### Step 1: Write hashes to separate files
```bash
sha256sum file1.txt > file1hash
sha256sum file2.txt > file2hash
```

---

### Step 2: Display and visually inspect hash values
```bash
cat file1hash
cat file2hash
```
> The hash digests can be manually compared side-by-side to spot any difference.

---

### Step 3: Use `cmp` to detect byte-level differences
```bash
cmp file1hash file2hash
```

> The `cmp` command performs a **byte-by-byte comparison** and reports the exact byte and line number where the first difference occurs — confirming the files diverge at a specific position.

---

## Key Takeaways

| Concept | Details |
|---|---|
| **Hash Function** | One-way algorithm — output cannot be reversed to recover input |
| **SHA-256** | Produces a 256-bit (64-character hex) digest |
| **File Integrity** | Identical files always produce identical hashes; any modification changes the hash entirely |
| **`sha256sum`** | Linux command to generate SHA-256 hashes |
| **`cmp`** | Byte-level file comparison; identifies first point of divergence |
| **Use Case** | Detecting malicious files disguised as legitimate ones (e.g., tampered executables or config files) |

---

## Real-World Application

In a SOC environment, hash comparison is used to:
- **Validate file integrity** during incident response
- **Match indicators of compromise (IOCs)** against known malware hashes (e.g., via VirusTotal or threat intel feeds)
- **Detect unauthorized modifications** to critical system files
- **Chain of custody verification** for forensic evidence

---

*Completed as part of the Google Cybersecurity Certificate on Coursera.*
