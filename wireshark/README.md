# Wireshark Lab Documentation

**Name:** Masumi Jain
**Lab Topic:** Network Traffic Analysis using Wireshark – WiFi Traffic Analysis and Educational Demonstration of Credential Exposure
**Date:** 31/01/2026


## Objective

* Capture and analyze WiFi network traffic using Wireshark
* Understand packet structure and protocol behavior
* Demonstrate (in a controlled lab environment) how unencrypted HTTP traffic can expose credentials
* Highlight the importance of HTTPS encryption in securing sensitive data


## Step-by-Step Lab Procedure

### Step 1: Setup

* Installed Wireshark on Windows/Linux/macOS
* Connected system to controlled WiFi lab network (VM environment)
* Opened Wireshark and selected active wireless interface

### Step 2: Capturing Traffic

* Clicked **Start Capturing Packets**
* Generated traffic by browsing websites and accessing a test HTTP login page
* Observed packets being captured in real time

### Step 3: Applying Filters

* `tcp` → Display only TCP packets
* `http` → Display HTTP traffic
* `ip.addr == 192.168.1.5` → Traffic to/from specific IP
* `dns` → DNS queries

### Step 4: Analyzing Packets

* Expanded Ethernet, IP, TCP, and HTTP headers
* Checked source/destination IP, ports, flags, packet size
* Used **Follow → TCP Stream** to analyze full communication
* Observed plain-text credentials in HTTP (educational lab only)
* Compared with HTTPS traffic where data appeared encrypted

### Step 5: Saving & Exporting

* Saved capture file as `.pcapng`
* Exported filtered packets for documentation


## 2. Commands Used / Filters

* Capture traffic → Start Capture
* Filter by IP → `ip.addr == [IP_ADDRESS]`
* Filter TCP traffic → `tcp`
* Filter HTTP traffic → `http`
* Filter DNS traffic → `dns`
* Follow TCP Stream → Right-click → Follow → TCP Stream
* Save capture → File → Save As → `.pcapng`
* Export packets → File → Export Specified Packets

## 3. Key Takeaways

* Wireshark provides deep visibility into WiFi network traffic
* Filters are essential for meaningful analysis
* HTTP traffic transmits data in plain text
* HTTPS encrypts communication using TLS
* Packet analysis strengthens networking and cybersecurity skills
* Traffic monitoring helps detect anomalies

## 4. Challenges Faced

* Large number of packets initially overwhelming
* Understanding TCP handshake and sequence numbers required attention
* Encrypted HTTPS traffic could not be directly interpreted

## 5. Lessons Learned

* Proper filtering simplifies packet analysis
* Encryption is critical for protecting credentials
* Hands-on practice improves protocol understanding
* Ethical use of network analysis tools is essential

## Ethical Statement

* This lab was conducted in a controlled virtual environment
* No unauthorized networks or real user data were accessed
* The purpose was educational and focused on cybersecurity awareness

## Conclusion

* Gained hands-on experience in WiFi traffic analysis
* Improved understanding of packet flow and protocols
* Understood the importance of HTTPS in protecting sensitive information

