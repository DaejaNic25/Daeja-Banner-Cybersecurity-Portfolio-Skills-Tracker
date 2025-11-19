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
- The malicious executable file was downloaded over **HTTP**, which operates at the **Application Layer** of the TCP/IP model.
- A second DNS request resolves `greatrecipesforme.com`, followed by additional **HTTP traffic** to the malicious domain.

### **Conclusion**
The website was compromised using HTTP-based delivery of malicious content. The attacker abused HTTP to distribute a fake browser update that redirected users to the malicious site **greatrecipesforme.com**.

---

# 🔹 **Section 2 — Document the Incident**

### **Initial Customer Report**
Multiple customers reported:
- Being prompted to download a file when visiting the website  
- After running the file, their browser redirected to a different URL  
- Their computers became noticeably slower  

The website owner also reported being **locked out** of their admin account.

### **Sandbox Investigation**
A cybersecurity analyst replicated the incident in a sandbox environment:
1. Executed `tcpdump` to capture live traffic  
2. Navigated to `yummyrecipesforme.com`  
3. A prompt appeared instructing the user to download an executable  
4. After running the file, the browser redirected to **greatrecipesforme.com**  

### **Network Traffic Findings (tcpdump Log)**
- **DNS request** for `yummyrecipesforme.com`
- **DNS response**: `203.0.113.22`
- **HTTP GET request** to the legitimate site  
- Immediate file download prompt  
- **DNS request** for `greatrecipesforme.com`
- **DNS response**: `192.0.2.172`
- **HTTP traffic** begins with the malicious site

### **Root Cause Analysis**
A senior analyst confirmed:
- JavaScript had been injected into the site’s source code  
- The code forced users to download a malicious file  
- The file contained a script to redirect users to `greatrecipesforme.com`  
- The attacker accessed the host using **default admin credentials** through a **brute force attack**  
- No OS hardening or brute force mitigation controls were in place  

### **Impact**
- Web server compromised  
- Malicious file executed by users  
- End-user machines potentially infected  
- Loss of administrative access to the website  
- Compromised trust and business operations  

---

# 🔹 **Section 3 — Recommend Remediation for Brute Force Attacks**

To prevent future brute force attacks, the following OS hardening actions are recommended:

### **1. Enforce Strong Password Policies**
- Require admin passwords of **15–16+ characters**  
- Use **passphrases** instead of simple passwords  
- Require uppercase, lowercase, numbers, and symbols  
- Disallow use of **default or previously-used passwords**

### **2. Implement Account Lockout Policies**
- Lock accounts after **5 failed attempts**  
- Enforce cooldown or admin-only resets  

This prevents automated tools from performing repeated login attempts.

### **3. Enable Two-Factor Authentication (2FA)**
2FA requires:
- Something the user **knows** (password)  
- Something the user **has** (one-time code delivered via email or phone)

This significantly reduces the risk of credential-based attacks, even if a password is compromised.

### **4. Harden Administrative Access**
- Restrict admin panel access to approved IP ranges  
- Enforce secure communication channels (HTTPS)  
- Monitor logs for repeated login failures or unauthorized attempts  

