---
title: "TryHackMe — Systems as Attack Vectors"
author: "Daeja Banner"
tags: ["TryHackMe", "SOC Analyst", "System Security", "Attack Vectors"]
difficulty: "Beginner"
date: 2025-11-14
---

# 🛡️ TryHackMe: Systems as Attack Vectors

A portfolio-friendly write-up summarizing the **Systems as Attack Vectors** room on TryHackMe, aligned with your SOC analyst learning path.

---

## 📝 Task 1 — Introduction

This room continues the SOC journey and focuses on how **systems themselves** (servers, VMs, cloud platforms like Microsoft 365) become attack vectors.

**Key ideas:**  
- Attacks can target systems directly, not only users.  
- A compromised **system** can impact thousands of users at once.  

**Answers:**  
- Can cyber attacks happen without victim intervention? → **Yes**  
- Can a breach of just a single system lead to disastrous consequences? → **Yes**  

---

## 🖥️ Task 2 — Definition of a System

Systems are where critical data and services live: email servers, banking servers, admin laptops, cloud workloads, etc. Protecting systems is crucial because:

- A single compromised user = one mailbox or account.  
- A compromised system (e.g., mail server) = thousands of mailboxes, full environment impact.

**Takeaways:**  
- Systems vary in value to attackers (student laptop vs. IT admin laptop vs. industrial server).  
- High-value systems (admins, core servers) should have the strongest protections.

**Answers:**  
- Can cyber attacks happen without victim intervention? → **Yes**  
- Can a breach of a system cause serious impact? → **Yes**  

---

## 🚨 Task 3 — Attacks on Systems

Common ways attackers breach systems:

1. **Human-led attacks**  
   - Malicious USB drives  
   - Downloading malware from pirated sites  
   - Weak or reused passwords  
   - Note: ~81% of breaches involve stolen or breached passwords.

2. **Vulnerabilities**  
   - Software flaws (CVEs) in OS, apps, or services.  
   - In 2024, over 40,000 vulnerabilities were published, 300+ actively exploited.

3. **Supply chain attacks**  
   - Malware delivered through trusted software or libraries.  
   - Examples: **SolarWinds**, **3CX**.  
   - Even TryHackMe was impacted via a library (Lottie Player) used for animations.

**Answers:**  
- Term for a security flaw that can be exploited? → **Vulnerability**  
- Attack where malware comes from a trusted app/library? → **Supply chain attack**  

---

## 🛠️ Task 4 — Vulnerabilities

Every piece of software has flaws. Some important concepts:

- **Zero-day:** vulnerability known to attackers before the vendor or defenders.  
- Once public, a vulnerability is assigned a **CVE** (Common Vulnerabilities and Exposures) ID.  
- After disclosure, both attackers and defenders race:  
  - Attackers write exploits.  
  - Defenders patch and harden systems.

**Defensive response to vulnerabilities:**  
- Apply **patches** from the vendor as soon as possible.  
- For zero-days, apply temporary mitigations (restrict access, add IPS/WAF rules) and monitor for exploitation until a patch is available.

**Answers:**  
- CVE for the critical SharePoint vuln “ToolShell”? → **CVE-2025-53770**  
- How should you respond to a detected vulnerability? → **Patch**  

---

## ⚙️ Task 5 — Misconfigurations

Misconfigurations are **setup mistakes**, not software bugs. Examples:

- Weak default passwords like `123456` or `1111`.  
- Misconfigured cloud storage (e.g., open S3 buckets, open databases).  
- Insecure IoT/“smart” devices (like smart fridges) being used in botnets.

Real-world impacts:  
- McDonald’s job application chat data exposed via weak passwords.  
- Misconfigured AWS leading to breaches of millions of customer records.  

**Responding to misconfigurations:**  
- No patch is needed — just **fix the configuration**.  
- Techniques:  
  - **Penetration testing** — ethical hackers simulate attacks and report issues.  
  - **Vulnerability scans** — detect default credentials, outdated software, exposed services.  
  - **Configuration audits** — compare against CIS benchmarks and best practices.

**Answers:**  
- Can a software patch fix misconfigurations? → **Nay**  
- Which activity involves an authorized cyber attack to detect misconfigurations? → **Penetration testing**  

---

## 🧪 Task 6 — Practice

This section provides hands-on scenarios where you, as a SOC analyst, must choose mitigation/detection steps for **Systems at Risk** and define a **Remediation Plan**.

Key mitigation controls:

- **Patch Management**  
  - Track and patch vulnerable systems to reduce the attack surface.

- **Training for IT**  
  - Educate administrators about risks of weak passwords and bad configurations.

- **Network Protection**  
  - Restrict access to sensitive systems using IP allowlists, firewalls, and segmentation.

- **Antivirus / EDR**  
  - Detect and block common malware and attacker behaviors.

> Flags from the lab are not included here to comply with TryHackMe rules.

---

## 🏁 Task 7 — Conclusion

Even if SOC analysts don’t directly manage systems, they should:

- Understand how systems are attacked (vulns, misconfigs, supply chain, human actions).  
- Communicate effectively with IT/engineering teams to patch and harden systems.  
- Stay updated on the latest threats and share relevant intel (e.g., DFIR reports, CISA KEV, supply chain attack write-ups).  

This broader understanding improves:  
- Incident response quality,  
- Detection engineering, and  
- Overall security posture of the organization.

---

## 🧠 Lessons Learned / Portfolio Notes

- Systems can be **high-impact single points of failure**.  
- Vulnerabilities require **patching**; misconfigurations require **reconfiguration**.  
- Supply chain attacks show that even trusted software can become an attack vector.  
- SOC analysts must blend technical understanding with clear communication to IT teams.

---

## 📂 Extracted Images

- image_1.png
- image_2.png
- image_3.png
- image_4.png
- image_5.png

(If you keep these in the `images/` folder, you can embed them later in this markdown using standard `![alt](images/file.png)` syntax.)

---

## 📁 Recommended GitHub Structure

```text
TryHackMe/
└── Systems-as-Attack-Vectors/
    ├── tryhackme_systems_as_attack_vectors.md
    ├── images/
    │   ├── image_1.png
    │   ├── image_2.png
    │   └── ... (if more)
    └── notes/
```

