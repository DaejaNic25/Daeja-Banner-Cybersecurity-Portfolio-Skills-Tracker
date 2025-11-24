---
title: "Applying the NIST Cybersecurity Framework (CSF) to a Security Incident"
author: "Daeja Banner"
course: "Google Cybersecurity Professional Certificate"
activity: "NIST CSF Incident Analysis"
date: 2025-11-22
tags: ["NIST CSF", "Incident Response", "DDoS", "ICMP", "Network Security"]
---

# 🛡️ Applying the NIST Cybersecurity Framework  
### *Security Incident Report & Framework Mapping*

This report analyzes a Distributed Denial of Service (DDoS) attack targeting the organization's internal network and maps the response using the **NIST Cybersecurity Framework (CSF)**.  
The structure follows Google’s exemplar and includes my full analysis from the “Use the NIST Cybersecurity Framework to Respond to a Security Incident” assignment.

---

# 📝 **Summary**

The company experienced a **DDoS attack** caused by an overload of **ICMP packets**, resulting in a two-hour outage of internal network services. Employees were unable to access applications or resources.

Key findings:

- The firewall was improperly configured and allowed unrestricted ICMP traffic.
- Attackers flooded the network using ICMP echo requests (pings).
- Services were restored only after blocking ICMP and restarting critical systems.
- Logs and analysis confirmed lack of monitoring, no rate limiting, and no alerting for abnormal ICMP activity.

The event is mapped below according to the **five NIST CSF functions: Identify, Protect, Detect, Respond, Recover**.

---

# 🔎 **Identify**

The root cause of the outage was an **unconfigured firewall**, which allowed malicious ICMP packets to overwhelm the network.

Additional risks identified:

- No firewall auditing or configuration review  
- No baseline configuration policies  
- Lack of network monitoring  
- No anomaly detection  
- No ICMP throttling or filtering  

The organization had low visibility into its network posture and no formal process for identifying misconfigurations.

---

# 🛡️ **Protect**

The following protections were implemented:

- Added a firewall rule to **rate-limit ICMP** requests  
- Added **source IP verification** to identify spoofed packets  

Additional recommended protections:

- Enforce least-privilege access to network equipment  
- Maintain firewall configuration baselines  
- Document and enforce network security policies  
- Train staff on identifying abnormal system behavior  
- Deploy tools such as IDS/IPS and secure configuration management  

These measures strengthen the network’s ability to defend against future attacks.

---

# 🔍 **Detect**

The company improved detection capabilities by implementing:

- **Network monitoring software**  
- **Intrusion detection systems (IDS/IPS)**  
- **Continuous log collection**  
- Alerts to detect ICMP-based anomalies  

These improvements provide better visibility and allow the company to identify unusual patterns before they become service-impacting.

---

# 🚨 **Respond**

Immediate response actions included:

- Blocking incoming ICMP packets  
- Shutting down unnecessary services to reduce load  
- Restoring critical systems  
- Updating firewall settings  
- Setting up monitoring tools  

Recommended long-term actions:

- Establish a formal **DDoS response playbook**  
- Conduct regular **incident response drills**  
- Improve communication channels  
- Maintain a lessons-learned log after every incident  
- Regularly test the response capabilities of the team  

---

# 🔁 **Recover**

Recovery actions:

- Restored all network services  
- Validated that the firewall rule was successfully implemented  
- Checked network logs for any lingering malicious activity  

Recommended improvements:

- Document recovery procedures  
- Conduct periodic recovery testing  
- Update policies and procedures based on lessons learned  
- Communicate recovery updates to the organization  

These actions help the organization return to normal operations while improving overall resilience.

---

# 📁 **Suggested GitHub Folder Structure**

