---
title: "Google Cybersecurity Activity — Analyze Network Attacks"
author: "Daeja Banner"
course: "Google Cybersecurity Professional Certificate"
activity: "Cybersecurity Incident Report — Network Attack Analysis"
date: 2025-11-16
---

# 🔐 Cybersecurity Incident Report — Analyze Network Attacks

This report is based on a scenario from the **Google Cybersecurity Professional Certificate**.  
A travel agency’s web server begins timing out, and packet capture data reveals an abnormally
high volume of TCP SYN requests from a single unfamiliar IP address. My task is to identify
the most likely type of attack, explain how it impacts the website, and summarize the attack
and remediation steps.

The analysis below is supported by the packet capture data exported to Excel:

- `data/wireshark_tcp_http_log.xlsx`

---

## 🧩 Section 1 — Identify the Type of Attack

> *Prompt:* Identify the type of attack that may have caused this network interruption.

One potential explanation for the website's connection timeout error message is:  
**an overload of packets sent to 192.0.2.1**, which is the sales domain.

The logs show that:  
There is an overwhelming amount of requests/communication coming from the IP address
**203.0.113.0** using port **54770**, which is a dynamic/private port that is not assigned to any
specific widely known service by IANA.

This event could be:  
This event can be a **DoS attack**.

---

## 🌐 Section 2 — Explain How the Attack Causes the Website Malfunction

> *Prompt:* When website visitors try to establish a connection with the web server,
> a three-way handshake occurs using the TCP protocol. Explain the three steps, and then
> describe what happens when a malicious actor sends many SYN packets at once.

### 🔁 TCP Three-Way Handshake (Normal Behavior)

**SYN (Client → Server)**  
The client sends a TCP segment with the **SYN** flag set to 1 to the server.  
This packet includes a randomly generated initial sequence number to initiate the connection.

**SYN-ACK (Server → Client)**  
The server receives the SYN packet and responds with a TCP segment that has both the **SYN**
and **ACK** flags set to 1. It acknowledges the client’s SYN by sending an ACK number that is
one greater than the client’s sequence number. It also sends its own initial sequence number
for the connection.

**ACK (Client → Server)**  
The client receives the server’s SYN-ACK and sends an ACK packet back to the server with the
**ACK** flag set to 1. The ACK number is one greater than the server’s sequence number. At this
point, both sides have acknowledged each other, and the TCP connection is established, allowing
data transfer to begin.

### 🚨 What Happens During a SYN Flood

When a malicious actor sends a large number of SYN packets, they are initiating a
**SYN flood attack**, which overwhelms a server’s resources by exploiting the TCP
three-way handshake.

The server allocates resources to each incoming SYN packet and waits for a final ACK that never arrives
(either because the source IP is spoofed or the sender ignores the response). This causes the server’s
connection table to fill up with **half-open connections**, preventing it from accepting legitimate
requests and leading to a denial of service for legitimate users.

### 📊 What the Logs Indicate

The logs are indicating a **DoS attack**, due to the overwhelming amount of packets coming in from
an outside source, which is overwhelming the server and causing it to time out.

---

## 📝 Section 3 — Type of Attack and Reasoning

> *Prompt:* Based on the evidence, what type of attack is occurring? Explain why.

Based on what I am seeing, this is considered a **DoS attack** due to the overwhelming amount of packets
coming from only one source. The reason for this answer is that a DoS attack uses a **single source**
to flood a target with traffic. In this case, **203.0.113.0** is flooding **192.0.2.1** with SYN packets,
which leads me to believe the specific type of DoS attack used is a **SYN flood attack**.

The website is taking too long to respond because it is receiving an overwhelming amount of SYN packets
and the server can no longer process normal connection requests.

---

## 🛡️ Section 4 — Impact and Remediation Steps

> *Prompt:* Summarize the attack and list steps to remediate it.

The attack is a type of **SYN flood DoS attack** that sends an overwhelming amount of SYN packets
to a targeted device, in this case **203.0.113.0 → 192.0.2.1**, which causes the server to time out
and prevents legitimate users from accessing the website.

### ✅ Steps for Remediation

**1. Identify and Confirm Malicious IP**  
- Confirm that **203.0.113.0** is the source of the abnormal SYN flood traffic.  
- Validate using packet captures and firewall/router logs.

**2. Implement IP Blacklisting**  
- Block the malicious IP at the firewall or load balancer.  
- Use firewall rules, OS-level controls, or network ACLs to drop traffic from 203.0.113.0.

**3. Implement Rate Limiting**  
- Apply rate-limiting on SYN requests per source IP.  
- Configure this at the server, firewall, or load balancer level to limit SYN requests per second.

**4. Monitor and Update Protections**  
- Continuously monitor network traffic after implementing the block to ensure the attack has ceased.  
- Watch for IP spoofing or new attacking IPs and update rules accordingly.

**5. Plan Longer-Term Mitigations**  
- Consider SYN cookies or more advanced DoS/DDoS protections.  
- Review server capacity and logging to detect DoS attempts earlier in the future.

---

