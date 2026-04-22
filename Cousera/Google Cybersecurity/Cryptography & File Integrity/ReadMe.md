# Cryptography & File Integrity Analysis

This project was completed as part of the Google Cybersecurity Certificate on Coursera.

## Objective
Demonstrate the use of cryptographic techniques to verify file integrity and analyze encrypted data.

---

## Project 1: Create Hash Values & File Integrity Verification

### Overview
Hashing is used to uniquely identify files and detect any modifications. Even a single change in a file produces a completely different hash value.

:contentReference[oaicite:0]{index=0}

---

### 🔧 Tools Used
- `sha256sum`
- `cat`
- `cmp`
- Linux CLI

---

### 📸 Evidence

**Picture1: File Contents Comparison (file1.txt vs file2.txt)**  
![Picture1](images/Picture1.png)

**Picture2: Generated SHA-256 Hash Values**  
![Picture2](images/Picture2.png)

**Picture3: Hash Comparison Output (Difference Identified)**  
![Picture3](images/Picture3.png)

---

### Process
1. Display file contents using `cat`
2. Generate hash values using `sha256sum`
3. Store hashes in separate files
4. Compare hashes manually and using `cmp`

---

### Key Findings
- Files may appear identical but still produce different hashes
- Hashing ensures **data integrity verification**
- Even minor changes are detectable

---

## Key Takeaways
- Hashing is critical for detecting tampering
- SHA-256 provides strong integrity validation
- Manual verification strengthens analyst skills

---

## Skills Demonstrated
- Cryptographic Hashing
- File Integrity Verification
- Linux Command-Line Usage
- Security Analysis Techniques
