---
title: "Google Cybersecurity Certificate — Apply OS Hardening Techniques"
author: "Daeja Banner"
course: "Google Cybersecurity Professional Certificate"
activity: "Security Incident Report — OS Hardening & Attack Analysis"
date: 2025-11-18
tags: ["OS Hardening", "Incident Response", "tcpdump", "Brute Force", "HTTP", "DNS"]
---

# 🛡️ Security Incident Report  
### *Applying OS Hardening Techniques*

This report documents an investigation into a security incident affecting **yummyrecipesforme.com**, where a disgruntled former employee compromised the website using a brute force attack, altered its source code, and redirected users to a malicious site containing malware.

The report follows the structure required in the Coursera assignment:
1. Identify the network protocol involved  
2. Document the incident  
3. Recommend a remediation for brute force attacks  

---

# 🔹 **Section 1 — Identify the Network Protocol Involved**

Analysis of the tcpdump traffic logs shows that the primary protocol involved in this incident is the **Hypertext Transfer Protocol (HTTP)**.

### **Evidence**
- The browser sends a **DNS A-record request** to resolve `yummyrecipesforme.com`.
- After DNS responds with IP **203.0.113.22**, the browser initiates an **HTTP GET request**:
