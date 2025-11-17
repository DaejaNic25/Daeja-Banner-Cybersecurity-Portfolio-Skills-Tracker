---
title: "TryHackMe — SOC L1 Alert Triage"
author: "Daeja Banner"
platform: "TryHackMe"
path: "SOC Level 1"
date: 2025-11-17
tags: ["SOC Analyst", "Alert Triage", "SIEM", "L1 Analyst", "Cybersecurity"]
---

# 🛡️ TryHackMe — SOC L1 Alert Triage  
### *Alert Lifecycle • Triage Workflow • L1 Analyst Skills*

This document contains my write-up and answers for the **TryHackMe SOC L1 Alert Triage** lab.  
This room teaches the fundamentals of alert handling, triage decision-making, workflow best practices, and analyst responsibilities inside a SOC.

---

# 🔹 **Task 1 — Introduction**

Alerts are essential for SOC teams. They notify analysts of suspicious or malicious activity based on specific event patterns. L1 analysts must be able to understand alert structure, fields, severity, and status.

### **Learning Objectives**
- Understand SOC alert concepts  
- Learn alert lifecycle and triage process  
- Recognize alert fields, statuses, severity, and classification  
- Build SOC L1 triage skills  
- Prepare for SOC simulator and SAL1 certification  

### **Questions**
**What is the number of alerts you see in the SOC dashboard?**  
✔️ **5**

**What is the name of the most recent alert you see?**  
✔️ **Double-Extension File Creation**

---

# 🔹 **Task 2 — Events and Alerts**

Events become alerts after logging, ingestion into SIEM/EDR, and detection rule matching.  
Alerting reduces noise by surfacing only suspicious activity.

### L1 SOC Responsibilities
- Review alerts  
- Distinguish false positives vs real threats  
- Escalate to L2 if suspicious  
- Document findings & classifications  

### **Questions**
**What was the verdict for the “Unusual VPN Login Location” alert?**  
✔️ **False Positive**

**What user was mentioned in the alert?**  
✔️ **M.Clark**

---

# 🔹 **Task 3 — Alert Properties**

Alerts typically include:
- **Alert Time**
- **Event Time**
- **Name**
- **Severity**
- **Status**
- **Verdict**
- **Assignee**
- **Description**
- **Fields / IOCs**

### **Questions**
**Should you first prioritize medium over low severity alerts?**  
✔️ **Yea**

**Should you first take the newest alerts?**  
✔️ **Nay**  
(Oldest alerts get worked first.)

**Name of the first-priority alert you assigned yourself:**  
✔️ **Potential Data Exfiltration**

---

# 🔹 **Task 4 — Alert Prioritization**

General workflow:
1. Filter by **New** & **Unassigned**
2. Sort by **Severity** (Critical → High → Medium → Low)
3. Sort by **Time** (Oldest → Newest)

---

# 🔹 **Task 5 — Alert Triage**

Triage involves:
- Assigning the alert  
- Changing status to **In Progress**  
- Reading description & indicators  
- Investigating logs  
- Searching surrounding events  
- Using threat intel  
- Deciding verdict  
- Closing ticket as TP or FP  

### **Questions: Flags Received**
You will enter your flags here (redacted for THM ToS):

- **Flag for 1st alert:**  
⬜ *(Insert your flag — do NOT include the real flag in a public repo)*  

- **Flag for 2nd alert:**  
⬜ *(Insert placeholder)*  

- **Flag for 3rd alert:**  
⬜ *(Insert placeholder)*  

---

# 🔹 **Task 6 — Conclusion**

You successfully completed L1 alert triage.  
You learned:
- Effective alert ownership  
- Prioritization logic  
- Basic SIEM triage steps  
- Investigating suspicious login alerts  
- Identifying false positives  
- Identifying potential exfiltration attempts  

This room builds core skills required for real SOC analyst roles and prepares you for the **SOC Level 1 path** and **SOC simulator**.

---

# 📁 **Recommended GitHub Folder Structure**

Place this write-up inside your repo like:

