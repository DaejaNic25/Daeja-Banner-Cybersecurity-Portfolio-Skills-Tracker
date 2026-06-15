# Activity: Analyze Packets with Wireshark

## Task 1. Explore data with Wireshark

In this task, you must open a network packet capture file that contains data captured from a system that made web requests to a site.

### Step 1
Open the packet capture file (`sample.pcap`) in Wireshark.

**Picture1**
![Picture1](images/Picture1.png)

### Step 2
Maximize the Wireshark application window.

**Picture2**
![Picture2](images/Picture2.png)

### Step 3
Review the packet list and packet information columns:

- No.
- Time
- Source
- Destination
- Protocol
- Length
- Info

**Picture3**
![Picture3](images/Picture3.png)

### Question

What is the protocol of the first packet in the list where the Info column starts with "Echo (ping) request"?

**Answer:** ICMP

**Picture4**
![Picture4](images/Picture4.png)

---

## Task 2. Apply a basic Wireshark filter and inspect a packet

### Step 1
Apply the following display filter:

```text
ip.addr == 142.250.1.139
```

**Picture5**
![Picture5](images/Picture5.png)

### Step 2
Open the first TCP packet and review the packet details.

**Picture6**
![Picture6](images/Picture6.png)

### Step 3
Expand the following sections:

- Frame
- Ethernet II
- Internet Protocol Version 4
- Transmission Control Protocol

**Picture7**
![Picture7](images/Picture7.png)

### Question

What is the TCP destination port of this packet?

**Answer:** Port 80

**Picture8**
![Picture8](images/Picture8.png)

---

## Task 3. Use filters to select packets

Apply the following filters:

```text
ip.src == 142.250.1.139
```

```text
ip.dst == 142.250.1.139
```

```text
eth.addr == 42:01:ac:15:e0:02
```

**Picture9**
![Picture9](images/Picture9.png)

**Picture10**
![Picture10](images/Picture10.png)

### Question

What protocol is contained in the IPv4 subtree from the first packet related to MAC address 42:01:ac:15:e0:02?

**Answer:** TCP

---

## Task 4. Use filters to explore DNS packets

Apply the following filter:

```text
udp.port == 53
```

**Picture11**
![Picture11](images/Picture11.png)

### DNS Query

Queried hostname:

```text
opensource.google.com
```

**Picture12**
![Picture12](images/Picture12.png)

### Question

Which IP address is displayed in the Answers section for opensource.google.com?

**Answer:**

```text
142.250.1.139
```

**Picture13**
![Picture13](images/Picture13.png)

---

## Task 5. Use filters to explore TCP packets

Apply the following filter:

```text
tcp.port == 80
```

**Picture14**
![Picture14](images/Picture14.png)

### Questions & Answers

**Time To Live (TTL)**

```text
64
```

**Frame Length**

```text
54 bytes
```

**Header Length**

```text
20 bytes
```

**Destination Address**

```text
169.254.169.254
```

**Picture15**
![Picture15](images/Picture15.png)

### Filter packets containing text

```text
tcp contains "curl"
```

**Picture16**
![Picture16](images/Picture16.png)

---

## Key Takeaways

- Used Wireshark to analyze packet captures
- Applied display filters to isolate network traffic
- Examined ICMP, TCP, HTTP, and DNS traffic
- Investigated packet details at multiple network layers
- Identified IP addresses, MAC addresses, ports, and DNS responses

## Skills Demonstrated

- Wireshark
- Packet Analysis
- Network Traffic Analysis
- DNS Investigation
- TCP/IP Analysis
- Protocol Analysis
- Cybersecurity Investigation
