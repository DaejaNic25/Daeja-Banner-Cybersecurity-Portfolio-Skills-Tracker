# IBM Hands-on Lab: Windows Defender Antivirus

## Exercise 1: Review Windows Security Virus & Threat Protection

In this lab, you'll access and review Windows Security Virus & Threat Protection. Let's begin with locating and opening Windows Security Virus & Threat Protection.

### Step 1

Click the Windows Start button and select Settings.

**Picture1**  
![Picture1](images/Picture1.png)

---

### Step 2

On the Windows Settings page, select Update & Security.

**Picture2**  
![Picture2](images/Picture2.png)

---

### Step 3

Under Update & Security, select Windows Security.

**Picture3**  
![Picture3](images/Picture3.png)

---

### Step 4

Select Virus and Threat Protection.

**Picture4**  
![Picture4](images/Picture4.png)

---

### Step 5

Review the Virus & Threat Protection dashboard.

Features include:

- Current threats
- Virus & threat protection settings
- Virus & threat protection updates
- Ransomware protection

**Picture5**  
![Picture5](images/Picture5.png)

---

## Exercise 2: Update Threat Definitions

Windows Security uses security intelligence definitions to identify known threats.

### Step 1

Under Virus & Threat Protection Updates, select Check for Updates.

**Picture6**  
![Picture6](images/Picture6.png)

---

### Step 2

Review the most recent security intelligence update.

**Picture7**  
![Picture7](images/Picture7.png)

---

### Step 3

Wait for the update process to complete.

**Picture8**  
![Picture8](images/Picture8.png)

---

## Exercise 3: Run Antivirus Quick Scan

### Step 1

Select Quick Scan.

**Picture9**  
![Picture9](images/Picture9.png)

---

### Step 2

Allow the scan to complete.

**Picture10**  
![Picture10](images/Picture10.png)

---

### Step 3

Review scan results.

**Picture11**  
![Picture11](images/Picture11.png)

---

### Step 4

Open Protection History.

**Picture12**  
![Picture12](images/Picture12.png)

---

### Step 5

Review quarantined and allowed threats.

**Picture13**  
![Picture13](images/Picture13.png)

---

## Exercise 4: Run Antivirus Custom Scan

### Step 1

Open Scan Options.

**Picture14**  
![Picture14](images/Picture14.png)

---

### Step 2

Select Custom Scan.

**Picture15**  
![Picture15](images/Picture15.png)

---

### Step 3

Choose the Downloads folder.

**Picture16**  
![Picture16](images/Picture16.png)

---

### Step 4

Run the scan.

**Picture17**  
![Picture17](images/Picture17.png)

---

## Scenario 1: Schedule Weekly Full Scans

### Enable Antivirus Protection

#### Step 1

Open Virus & Threat Protection Settings.

**Picture18**  
![Picture18](images/Picture18.png)

---

#### Step 2

Enable Real-Time Protection.

**Picture19**  
![Picture19](images/Picture19.png)

---

### Open Task Scheduler

#### Step 3

Launch Task Scheduler.

**Picture20**  
![Picture20](images/Picture20.png)

---

#### Step 4

Create a New Task.

**Picture21**  
![Picture21](images/Picture21.png)

---

#### Step 5

Configure General Settings.

**Picture22**  
![Picture22](images/Picture22.png)

---

#### Step 6

Configure Triggers.

**Picture23**  
![Picture23](images/Picture23.png)

---

#### Step 7

Configure Actions.

**Picture24**  
![Picture24](images/Picture24.png)

---

#### Step 8

Configure Conditions.

**Picture25**  
![Picture25](images/Picture25.png)

---

#### Step 9

Configure Settings.

**Picture26**  
![Picture26](images/Picture26.png)

---

## Scenario 2: Test Malware Detection with EICAR

### Step 1

Enable Notifications.

**Picture27**  
![Picture27](images/Picture27.png)

---

### Step 2

Download the EICAR test file.

**Picture28**  
![Picture28](images/Picture28.png)

---

### Step 3

Observe Windows Defender detection.

**Picture29**  
![Picture29](images/Picture29.png)

---

### Step 4

Review alerts, logs, and quarantine actions.

**Picture30**  
![Picture30](images/Picture30.png)

---

## Conclusion

This lab demonstrated how to:

- Review Windows Defender Antivirus settings
- Update threat definitions
- Perform quick and custom scans
- Schedule automated weekly scans
- Validate malware detection using the EICAR test file
- Review alerts, logs, and quarantine actions
