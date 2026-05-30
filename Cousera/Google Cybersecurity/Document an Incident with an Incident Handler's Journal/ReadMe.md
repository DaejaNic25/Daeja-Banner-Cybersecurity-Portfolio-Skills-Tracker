# Activity: Document an Incident with an Incident Handler's Journal

## Activity Overview

This activity focused on documenting a cybersecurity incident using an incident handler's journal. The purpose of the journal is to record key findings, identify attack methods, document incident details, and capture lessons learned for future response efforts.

Incident documentation is an important part of the incident response process because it helps security teams track events, identify root causes, improve response procedures, and support future investigations.

---

## Scenario

A small U.S. healthcare clinic experienced a ransomware attack on a Tuesday morning at approximately 9:00 AM.

Several employees reported that they were unable to access medical records and other critical business files. Employees also observed a ransom note on their systems indicating that company files had been encrypted by a known cybercriminal group that targets healthcare and transportation organizations.

The attackers gained access through phishing emails containing malicious attachments. Once opened, malware was installed and ransomware was deployed throughout the environment, encrypting critical files and disrupting business operations.

---


# Incident Handler's Journal

## Date

**05/29/2026**

## Entry Number

**1**

---

## Description

On a Tuesday morning around 9:00 AM, multiple employees reported that they were unable to use their computers to access files such as medical records. Business operations shut down because employees could not access the files and software required to perform their job duties.

Employees also reported that a ransom note appeared on their computers stating that all company files had been encrypted by an organized cybercriminal group. The attackers demanded a large ransom payment in exchange for the decryption key required to restore access to the files.

---

## Tools Used

### Attack Methods Identified

- Phishing emails
- Malicious email attachments
- Malware deployment
- Ransomware encryption

The attackers distributed phishing emails to several employees. The emails contained malicious attachments that installed malware when downloaded and opened.

---

## The 5 W's

### Who caused the incident?

A known organized group of cybercriminals that targets organizations in the healthcare and transportation sectors.

### What happened?

Multiple phishing emails containing malicious attachments were sent to employees. Once opened, malware was installed and ransomware encrypted company files, causing a disruption of business operations.

### When did the incident occur?

Tuesday morning at approximately 9:00 AM.

### Where did the incident happen?

A healthcare clinic's internal network and computer systems.

### Why did the incident happen?

- Phishing emails bypassed the organization's email security controls.
- Employees were susceptible to the phishing attack.
- Additional user awareness training may have been needed to improve phishing detection.

---

## Additional Notes

### Containment Actions

- Isolate infected devices from the network to prevent further spread.
- Identify additional users who received the phishing email.
- Remove malicious emails from affected mailboxes.
- Preserve evidence for investigation.

### Eradication Actions

- Reimage affected systems.
- Decommission compromised devices if necessary.
- Verify ransomware removal before reconnecting systems to the network.

### Recovery Actions

- Restore systems from clean backups.
- Validate system functionality before returning devices to production.
- Monitor systems for signs of reinfection.

### Lessons Learned

- Reinforce phishing awareness training.
- Review email security controls.
- Improve attachment filtering and malware detection.
- Conduct periodic phishing simulations.

---

## Key Findings

### Initial Attack Vector
Phishing email with malicious attachment.

### Impact
- Medical records inaccessible
- Business operations disrupted
- Critical files encrypted
- Potential risk to patient services

### Threat Type
Ransomware

### Affected Industry
Healthcare

---

## Key Takeaways

This incident demonstrates how phishing remains one of the most effective attack vectors used by threat actors. A single malicious attachment can lead to widespread ransomware infections, operational disruption, and loss of access to critical business data.

Effective incident response requires rapid containment, eradication, recovery, and ongoing user awareness training to reduce future risk.

---

## Skills Demonstrated

- Incident Documentation
- Incident Response
- Ransomware Analysis
- Phishing Investigation
- Root Cause Analysis
- Threat Identification
- Security Awareness
- Cybersecurity Reporting
- The 5 W's Incident Analysis Methodology
