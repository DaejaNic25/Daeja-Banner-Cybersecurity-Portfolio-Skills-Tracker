# IBM Hands-on Lab: Windows Defender Antivirus

## Overview

This hands-on lab focused on exploring and configuring Microsoft Windows Defender Antivirus. The exercises demonstrated how to review security settings, update threat definitions, perform antivirus scans, configure scheduled scans, and validate malware detection capabilities using the EICAR test file.

Windows Defender Antivirus is Microsoft's built-in endpoint protection platform that helps detect, prevent, and respond to malware, ransomware, and other security threats.

---

# Exercise 1: Review Windows Security Virus & Threat Protection

## Objective

Review the features available within the Windows Security Virus & Threat Protection dashboard.

### Navigation Path

1. Open **Start Menu**
2. Select **Settings**
3. Navigate to **Update & Security**
4. Select **Windows Security**
5. Open **Virus & Threat Protection**

### Features Reviewed

#### Current Threats
- View detected threats
- Review recent scan activity
- Launch Quick, Full, or Custom scans

#### Virus & Threat Protection Settings
- Manage protection settings
- Configure exclusions
- Enable or disable security features
- Submit sample files to Microsoft

#### Virus & Threat Protection Updates
- Review security intelligence updates
- Manually check for updates

#### Ransomware Protection
- Enable Controlled Folder Access
- Protect files and folders from unauthorized changes

---

## Evidence

### Picture1 - Windows Security Dashboard
![Picture1](images/Picture1.png)

### Picture2 - Virus & Threat Protection Settings
![Picture2](images/Picture2.png)

---

# Exercise 2: Update Threat Definitions

## Objective

Ensure Windows Defender Antivirus uses the latest threat intelligence definitions before scanning systems.

### Steps Performed

1. Open **Virus & Threat Protection**
2. Navigate to **Virus & Threat Protection Updates**
3. Select **Check for Updates**
4. Verify successful update of security intelligence definitions

### Importance

Keeping definitions up to date ensures Windows Defender can identify and respond to newly discovered threats.

---

## Evidence

### Picture3 - Threat Definition Updates
![Picture3](images/Picture3.png)

---

# Exercise 3: Run Antivirus Quick Scan

## Objective

Perform a quick scan to identify common malware locations and active threats.

### Steps Performed

1. Open **Virus & Threat Protection**
2. Select **Quick Scan**
3. Review scan results
4. Open **Protection History**

### Results Reviewed

- Last scan results
- Quarantined threats
- Allowed threats
- Protection history

---

## Evidence

### Picture4 - Quick Scan Execution
![Picture4](images/Picture4.png)

### Picture5 - Protection History
![Picture5](images/Picture5.png)

---

# Exercise 4: Run Antivirus Custom Scan

## Objective

Perform a custom scan targeting only the Downloads folder.

### Steps Performed

1. Open Scan Options
2. Select Custom Scan
3. Choose Downloads folder
4. Execute scan
5. Review findings

---

## Evidence

### Picture6 - Custom Scan Configuration
![Picture6](images/Picture6.png)

---

# Scenario 1: Configure Weekly Full Antivirus Scans

## Business Scenario

Roshan works remotely and requires continuous endpoint protection while accessing company resources.

The objective was to:
- Enable real-time protection
- Configure scheduled weekly full scans
- Automate threat detection

---

## Enable Antivirus Protection

### Steps Performed

1. Open Virus & Threat Protection
2. Select Manage Settings
3. Enable Real-Time Protection

---

## Schedule Weekly Full Scan

### Task Scheduler Configuration

#### General Settings

- Task Name: Weekly Full Scan
- Run whether user is logged on or not

#### Trigger Settings

- Weekly Schedule
- Sunday
- 3:00 AM

#### Action Settings

Program:

```text
C:\Program Files\Windows Defender\MpCmdRun.exe
