---
title: "Google Cybersecurity Activity — Analyze Network Layer Communication"
author: "Daeja Banner"
course: "Google Cybersecurity Certificate"
activity: "Cybersecurity Incident Report: Network Traffic Analysis"
date: 2025-11-15
---

# Cybersecurity Incident Report: Network Traffic Analysis

## Part 1: Provide a summary of the problem found in the DNS and ICMP traffic log

The UDP protocol reveals The tcpdump logs show that the browser attempted to send DNS queries using the UDP protocol to retrieve the IP address for yummyrecipesforme.com. These DNS queries were sent to the DNS server at 203.0.113.2 on UDP port 53, which is the standard port used for DNS resolution.

This is based on the results of the network analysis, which show that the ICMP echo reply returned the error message:  The error pattern confirms that DNS resolution failed, which explains why users could not load the website. Although this is commonly caused by a service outage, repeated port-unreachable responses on a critical service may also indicate possible malicious interference or unauthorized changes affecting DNS availability

The port noted in the error message is used for:  Port 53 is used for the DNS which translate human-readable websites names into machine-readable IP addresses

The most likely issue is: The DNS service on IP 203.0.113.2 is unavailable or not listening on port 53, preventing DNS queries from being resolved. This could be due to misconfiguration, a service failure, or potentially malicious disruption.



## Part 2: Explain your analysis of the data and provide at least one cause of the incident.

**Time incident occurred:** 01:24:32 

**Explain how the IT team became aware of the incident:**

Several customers of client reported that they were not able to access the client’s company website

**Explain the actions taken by the IT department to investigate the incident:**

Attempted to visit website

Was prompted with the same error

Captured a tcpdump

**Note key findings of the IT department's investigation (i.e., details related to the port affected, DNS server, etc.):**

Domain IP 203.0.113.2

Domain: yummyrecipesforme.com

Port 53 – unreachable 

**Note a likely cause of the incident:** DoS Attack 



## Part 3

After analyzing the tcpdump log, several trends become clear. The browser sent DNS queries using the UDP protocol to port 53, which is the standard port used for DNS resolution. These outgoing UDP packets were directed to the DNS server at 203.0.113.2. Immediately after each DNS request was sent, the system received ICMP “destination port unreachable” responses.

The tcpdump repeatedly shows the same pattern:

A UDP DNS query is sent from the client to 203.0.113.2:53.

The DNS server responds with ICMP port 53 unreachable.

This indicates that although DNS queries are being sent properly, UDP port 53 on the DNS server is not accepting or processing the requests. This could occur if the DNS service is down, the port is closed, the service is misconfigured, or the server is otherwise unable to respond.

The log also reveals that multiple attempts were made and each returned the same ICMP error message. This confirms that the issue is consistent, repeatable, and service-wide.

While this behavior most commonly results from a DNS service outage, repeated “port unreachable” responses for a critical network service can also indicate possible suspicious or malicious activity, such as unauthorized modifications to DNS services or unintentional disruption.



## Part 4

**When the problem was first reported:**
The first issue was identified at 01:24:32, when users reported site access failures.

**Scenario, events, and symptoms of the initial report:**
Multiple users informed the IT team that they were unable to access the client website and received a “destination port unreachable” error after attempting to load the page. This indicated a network-level or service-level issue affecting DNS or web traffic.

**Current status of the issue:**
The issue remains active. DNS resolution is still failing, and every DNS query sent to the DNS server results in ICMP error responses. Users are unable to load the website until DNS functionality is restored.

**Information discovered during investigation:**

DNS queries were properly sent via UDP to port 53.

The DNS server at 203.0.113.2 responded with ICMP “udp port 53 unreachable” to every request.

Port 53 is not accepting traffic, indicating the DNS service is unavailable.

Without DNS resolution, the web request cannot continue to the HTTPS stage.

The issue affects all users consistently, showing the DNS service outage is widespread.

The pattern also raises the possibility of unauthorized changes or malicious interference, though no direct evidence confirms this yet.

**Next steps in troubleshooting and resolving the issue:**

Verify whether the DNS service on 203.0.113.2 is running.

Confirm that UDP port 53 is open and listening.

Review recent DNS server configuration changes.

Check system logs for service crashes, reboots, or unauthorized access.

Restart the DNS service if necessary.

Escalate to network or security engineering if malicious tampering is suspected.

**Suspected root cause:**
The most likely cause is that the DNS service on the server is down, misconfigured, or no longer listening on UDP port 53, preventing DNS queries from resolving the domain. Because the service is unexpectedly unreachable and multiple users are affected simultaneously, malicious activity or unauthorized changes cannot be ruled out at this stage.
