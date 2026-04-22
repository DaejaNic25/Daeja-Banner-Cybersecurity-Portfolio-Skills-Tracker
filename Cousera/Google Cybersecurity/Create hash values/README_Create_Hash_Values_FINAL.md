# Activity: Create Hash Values

## Activity Overview
As a security analyst, you’ll need to implement security controls to protect organizations against a range of threats. That’s where hashing comes in.

Previously, you learned that a hash function is an algorithm that produces a code that can’t be decrypted. Hash functions are used to uniquely identify the contents of a file so that you can check whether it has been modified. This code provides a unique identifier known as a hash value or digest.

For example, a malicious program may mimic an original program. If one code line is different from the original program, it produces a different hash value. Security teams can then identify the malicious program and work to mitigate the risk.

Many tools are available to compare hashes for various scenarios. But for a security analyst it’s important to know how to manually compare hashes.

In this lab activity, we’ll create hash values for two files and use Linux commands to manually examine the differences.

---

## Scenario
In this scenario, we need to investigate whether two files are identical or different.

Here’s how you'll do this task:
- First, you’ll display the contents of two files and create hashes for each file.
- Next, you’ll examine the hashes and compare them.

---

## Task 1: Generate Hashes for Files

The lab starts in your home directory:
`/home/analyst`

This directory contains two files:
- file1.txt
- file2.txt

Both files contain the same data.

### Steps

1. List files:
```bash
ls
```

2. Display file1:
```bash
cat file1.txt
```

3. Display file2:
```bash
cat file2.txt
```

4. Review outputs (they appear identical).

5. Generate hash for file1:
```bash
sha256sum file1.txt
```

6. Generate hash for file2:
```bash
sha256sum file2.txt
```

7. Review hash outputs.

---

## Task 2: Compare Hashes

1. Save hash for file1:
```bash
sha256sum file1.txt > file1hash
```

2. Save hash for file2:
```bash
sha256sum file2.txt > file2hash
```

3. Display hashes:
```bash
cat file1hash
cat file2hash
```

4. Inspect differences.

5. Compare using cmp:
```bash
cmp file1hash file2hash
```

6. Review output showing first difference.

---

## Conclusion

Even though the files appeared identical when viewed, their hash values were different. This shows how hashing detects even the smallest changes in files.

Hashing is essential for verifying file integrity and identifying potential security risks.
