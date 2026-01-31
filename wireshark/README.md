Wireshark Lab Documentation

Name: Masumi Jain

Lab Topic: Network Traffic Analysis using Wireshark – WiFi Traffic Analysis and Educational Demonstration of Credential Exposure

Date: 31/01/2026

Objective:
To capture and analyze WiFi network traffic using Wireshark, understand packet structure and protocol behavior, and demonstrate (in a controlled lab environment) how unencrypted HTTP traffic can expose login credentials for educational purposes. The lab also emphasizes the importance of HTTPS encryption in securing sensitive data.

1. Step-by-Step Lab Procedure
# Step 1: Setup
Installed Wireshark on [Windows/Linux/macOS].
Connected the system to a controlled WiFi lab network (VM environment).
Opened Wireshark and selected the active wireless network interface.

# Step 2: Capturing Traffic
Clicked “Start Capturing Packets.”
Generated traffic by browsing websites and accessing a test HTTP login page in the lab.
Observed packets being captured in real-time.

# Step 3: Applying Filters
Used filters to isolate relevant traffic:
tcp → Display only TCP packets
http → Display HTTP traffic
ip.addr == 192.168.1.5 → Traffic to/from specific IP
dns → DNS queries

# Step 4: Analyzing Packets
Selected individual packets and expanded headers (Ethernet, IP, TCP, HTTP).
Examined source/destination IP, ports, flags, and packet length.
Followed TCP Stream to observe full client-server communication.
In the controlled HTTP lab, observed login credentials in plain text (educational demonstration).
Compared with HTTPS traffic where data appeared encrypted and unreadable.

# Step 5: Saving & Exporting
Saved captured traffic as .pcapng file.
Exported filtered packets for documentation and analysis.

2. Commands Used / Filters
Purpose	Command / Filter
Capture traffic	Start Capture
Filter by IP	ip.addr == [IP_ADDRESS]
Filter TCP traffic	tcp
Filter HTTP traffic	http
Filter DNS traffic	dns
Follow TCP Stream	Right-click → Follow → TCP Stream
Save capture	File → Save As → .pcapng
Export packets	File → Export Specified Packets

3. Key Takeaways
Wireshark provides deep visibility into WiFi network traffic.
Filtering is essential to analyze meaningful packets.
HTTP traffic transmits data in plain text, which can expose credentials.
HTTPS encrypts communication using TLS, protecting sensitive information.
Understanding packet headers strengthens networking and cybersecurity knowledge.
Traffic analysis is useful for troubleshooting and detecting anomalies.

4. Challenges Faced & Lessons Learned
Challenges:
Large volume of packets made initial analysis overwhelming.
Understanding TCP handshake and sequence numbers required detailed observation.
Encrypted HTTPS traffic could not be directly interpreted.

Lessons Learned:
Proper filtering significantly simplifies traffic analysis.
Encryption plays a critical role in securing online communication.
Hands-on packet analysis builds practical cybersecurity skills.
Ethical handling of network data is essential in cybersecurity practice.

⚠️ Ethical Statement
This lab was conducted in a controlled virtual environment for educational purposes only. No unauthorized networks or real user data were accessed. The objective was to understand network security concepts and the importance of encryption in protecting credentials.

✅ Conclusion
This lab provided practical exposure to WiFi network traffic analysis using Wireshark. I gained hands-on experience in capturing packets, applying filters, analyzing protocols, and understanding how encryption protects sensitive data in real-world networks.
