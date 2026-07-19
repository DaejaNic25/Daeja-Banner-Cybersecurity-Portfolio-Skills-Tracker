# Activity: Use a Playbook to Respond to a Phishing Incident

## Activity Overview

In this activity, I reviewed a phishing incident alert and documented the appropriate response using a Security Operations Center (SOC) playbook.

The objective was to evaluate the alert, identify indicators of compromise (IOCs), determine the severity of the incident, and document why the alert required escalation.

---

## Scenario

A phishing alert was generated after a user received an email that may have contained malware.

### Ticket Information

| Field | Value |
|--------|--------|
| Ticket ID | A-2703 |
| Severity | Medium |
| Status | Escalated |

Alert Message:

> SERVER-MAIL — Phishing attempt, possible malware download.

---

## Ticket Analysis

After reviewing the alert, the incident was escalated to a Level 2 SOC analyst.

### Reason for Escalation

The email contained several indicators commonly associated with phishing attacks, including:

- Suspicious sender email
- Malicious IP address
- Spelling and grammar errors
- Password-protected executable attachment
- Known malicious SHA-256 file hash

---

## Indicators of Compromise (IOCs)

### Known Malicious SHA-256

```text
54e6ea47eb04634d3e87fd7787e2136ccfbcc80ade34f246a12cf93bab527f6b
```

---

### Suspicious Sender

```text
Def Communications
76tguyhh6tgftrt7tg.su
114.114.114.114
```

---

### Recipient

```text
hr@inergy.com
176.157.125.93
```

---

### Attachment

```text
bfsvc.exe
```

---

## Email Analysis

Several phishing indicators were identified:

- Misspelled subject line ("Infrastructure Egnieer role")
- Poor grammar within the email body
- Password-protected executable attachment
- Sender domain inconsistent with a legitimate business
- Known malicious file hash

---

## Evidence

**Picture1**  
![Picture1](images/Picture1.png)

---

# Recommended Response

According to the SOC playbook:

- Escalate to Tier 2 SOC
- Block sender IP address
- Block malicious file hash
- Quarantine affected endpoint
- Search environment for additional recipients
- Notify the user
- Preserve evidence for investigation

---

# Key Takeaways

- Identified multiple phishing indicators.
- Validated malicious indicators of compromise.
- Applied an incident response playbook.
- Escalated the incident appropriately.

---

# Skills Demonstrated

- Phishing Analysis
- Email Security
- SOC Alert Triage
- Incident Response
- IOC Identification
- Threat Analysis
- Security Operations
