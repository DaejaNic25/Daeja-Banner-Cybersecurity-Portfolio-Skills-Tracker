# Activity: Investigate a Suspicious File Hash

## Activity Overview

In this activity, I investigated a suspicious file hash to determine whether a downloaded file was malicious. The investigation involved reviewing the timeline of events, analyzing file behavior, and examining threat intelligence gathered from VirusTotal.

The goal was to determine whether the file represented a legitimate application or malicious software and document indicators of compromise (IOCs) and observed tactics, techniques, and procedures (TTPs).

---

## Scenario

An employee received an email containing a file attachment.

### Timeline of Events

| Time | Event |
|--------|---------|
| 1:11 PM | Employee receives email containing file attachment |
| 1:13 PM | Employee downloads and opens the file |
| 1:15 PM | Multiple unauthorized executable files are created |
| 1:20 PM | Intrusion Detection System (IDS) generates an alert |

**Picture1**  
![Picture1](images/Picture1.png)

---

## SHA256 File Hash

```text
54e6ea47eb04634d3e87fd7787e2136ccfbcc80ade34f246a12cf93bab527f6b
```

**Picture2**  
![Picture2](images/Picture2.png)

---

# Investigation Findings

## Question

### Has this file been identified as malicious? Explain why or why not.

### Answer

The file was identified as malicious because 52 out of 69 antivirus vendors flagged it as malware. Multiple security vendors classified the file as:

- Trojan
- Backdoor
- FlagPro
- Fragtor malware variants

Additionally, VirusTotal reported several suspicious behaviors commonly associated with malicious software, including:

- Service scanning
- Anti-debugging techniques
- Spreading capabilities

The high detection rate across numerous antivirus vendors provides strong evidence that the file is malicious.

**Picture3**  
![Picture3](images/Picture3.png)

---

# Threat Intelligence Analysis

## TTPs Identified

The following tactics, techniques, and procedures were observed during the investigation:

- Detect Debug Environment
- Service Scan
- Spreader

**Picture4**  
![Picture4](images/Picture4.png)

---

## Malware Family / Tools

The file was associated with the following malware classifications:

- FlagPro
- Fragtor

**Picture5**  
![Picture5](images/Picture5.png)

---

## Network and Host Artifacts

### Files Observed

```text
bfsvc.exe
dwm.bin
main.bin
production.bat
```

**Picture6**  
![Picture6](images/Picture6.png)

---

## Domain Names Identified

```text
adservice.google.com
apis.google.com
api.bing.com
any.edge.bing.com
a0003.a-msedge.net
```

**Picture7**  
![Picture7](images/Picture7.png)

---

## IP Addresses Identified

```text
104.115.151.81
104.117.234.151
104.125.90.151
104.86.229.106
```

**Picture8**  
![Picture8](images/Picture8.png)

---

## Indicator of Compromise (IOC)

### SHA256 Hash

```text
54e6ea47eb04634d3e87fd7787e2136ccfbcc80ade34f246a12cf93bab527f6b
```

**Picture9**  
![Picture9](images/Picture9.png)

---

# Conclusion

Based on the VirusTotal analysis, behavioral indicators, and malware detections from multiple security vendors, the file was determined to be malicious.

The investigation identified several indicators of compromise, suspicious behaviors, and malware classifications that support this conclusion. Security teams should immediately isolate affected systems, block associated indicators, and perform additional investigation to determine whether the malware successfully executed within the environment.

---

# Key Takeaways

- File hashes can be used to quickly investigate suspicious files.
- VirusTotal provides valuable threat intelligence from multiple security vendors.
- High detection rates across antivirus engines are strong indicators of malicious activity.
- Indicators of compromise such as hashes, domains, IP addresses, and artifacts should be documented and monitored.
- Threat intelligence analysis helps security teams make informed incident response decisions.

---

# Skills Demonstrated

- Threat Intelligence Analysis
- Malware Investigation
- VirusTotal Analysis
- Indicator of Compromise (IOC) Identification
- Hash Analysis
- Incident Investigation
- Security Operations (SOC)
- Threat Hunting Fundamentals
