# 🔐 Create Hash Values (Linux Lab)

## 📘 Overview
This lab focuses on using hashing techniques to verify file integrity. In cybersecurity, hash functions generate a unique identifier (hash value or digest) for a file. Even a small change in a file results in a completely different hash, making hashing essential for detecting tampering or malicious modifications.

## 🎯 Objective
The goal of this lab is to:
- Generate hash values for files
- Compare hashes to determine if files are identical or different
- Understand how hashing helps identify file integrity issues

## 🧠 Scenario
As a security analyst, you are tasked with determining whether two files are identical. Although the files appear the same when viewed, hashing is used to confirm their integrity.

---

## 🛠️ Tools & Commands Used
- `ls` – List directory contents  
- `cat` – Display file contents  
- `sha256sum` – Generate hash values  
- `cmp` – Compare files byte-by-byte  

---

## 📂 Files Used
- `file1.txt`
- `file2.txt`
- `file1hash`
- `file2hash`

---

## 🚀 Steps Performed

### 🔹 Task 1: Generate Hashes

1. List files in the directory:
   ```bash
   ls
   ```

2. Display contents of both files:
   ```bash
   cat file1.txt
   cat file2.txt
   ```

3. Generate hash values:
   ```bash
   sha256sum file1.txt
   sha256sum file2.txt
   ```

4. Save hash values to files:
   ```bash
   sha256sum file1.txt > file1hash
   sha256sum file2.txt > file2hash
   ```

---

### 🔹 Task 2: Compare Hashes

1. Display saved hash values:
   ```bash
   cat file1hash
   cat file2hash
   ```

2. Compare hash files:
   ```bash
   cmp file1hash file2hash
   ```

---

## 🔍 Results & Analysis
- Although `file1.txt` and `file2.txt` appeared identical when viewed using `cat`, their hash values were different.
- The `cmp` command identified the exact byte and line where the difference occurred.
- This confirms that even minor differences in file content result in completely different hash values.

---

## 🛡️ Key Takeaways
- Hashing ensures **data integrity**.
- Even a **single character change** alters the hash.
- Hash comparison is a reliable way to detect **file tampering or malware**.
- Security analysts use hashing to validate files and identify suspicious activity.

---

## 📸 Screenshots
_Add your images in the `/images` folder and link them below:_

- `Picture1` – File contents output  
- `Picture2` – Hash generation output  
- `Picture3` – Comparison results  

Example:
```markdown
![Picture1](images/Picture1.png)
![Picture2](images/Picture2.png)
![Picture3](images/Picture3.png)
```

---

## 📌 Conclusion
This lab demonstrates how hashing is a fundamental technique in cybersecurity. By generating and comparing hash values, analysts can efficiently verify whether files have been altered, helping to protect systems from unauthorized changes.
