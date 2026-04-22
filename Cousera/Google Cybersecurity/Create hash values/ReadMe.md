# Activity: Create hash values

## Activity overview
As a security analyst, I used hashing to verify whether two files were identical or different. Hash functions generate a unique value for file contents, which helps detect even small modifications.

This activity demonstrates how file integrity can be validated manually using Linux commands.

---

## Scenario
In this scenario, I investigated whether two files were identical or different.

To complete this task, I:
- Displayed the contents of two files
- Generated hash values for each file
- Compared the hash values
- Used Linux commands to identify differences

---

## Tools used
- `ls`
- `cat`
- `sha256sum`
- `cmp`

---

## Task 1. Generate hashes for files

The lab started in the `/home/analyst` directory. Two files were provided:
- `file1.txt`
- `file2.txt`

### Step 1
Used the `ls` command to list the directory contents.

**Picture1: Directory listing**  
![Picture1](images/Picture1.png)

### Step 2
Used the `cat` command to display the contents of `file1.txt`.

**Picture2: Contents of file1.txt**  
![Picture2](images/Picture2.png)

### Step 3
Used the `cat` command to display the contents of `file2.txt`.

**Picture3: Contents of file2.txt**  
![Picture3](images/Picture3.png)

### Step 4
Reviewed both files. Although the contents looked identical, I still needed to generate hashes to verify whether they were truly the same.

### Step 5
Used the `sha256sum` command to generate the hash for `file1.txt`.

**Picture4: SHA-256 hash for file1.txt**  
![Picture4](images/Picture4.png)

### Step 6
Used the `sha256sum` command to generate the hash for `file2.txt`.

**Picture5: SHA-256 hash for file2.txt**  
![Picture5](images/Picture5.png)

### Step 7
Reviewed the generated hashes and noted whether they matched.

---

## Task 2. Compare hashes

### Step 1
Generated the hash of `file1.txt` and redirected the output to a new file called `file1hash`.

```bash
sha256sum file1.txt > file1hash
