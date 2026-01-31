# Nmap Lab Documentation

**Name:** Masumi Jain

**Lab Topic:** Network Scanning and Port Enumeration using Nmap

**Date:** 26/01/2026


## **Objective**

* Perform **network reconnaissance** using Nmap
* Discover **active hosts** in a network
* Identify **open ports and running services**
* Detect **service versions and operating system details**
* Understand how exposed services increase the **attack surface**



## **Lab Environment**

* **Tool Used:** Nmap
* **Platform:** Windows / Linux (VM Environment)
* **Network Type:** Controlled Local Lab Network
* **Target:** Authorized test machine inside virtual lab



## **Step-by-Step Lab Procedure**

### **1. Host Discovery**

* Performed a **ping scan** to identify live hosts
* Verified reachable systems before detailed scanning

```
nmap -sn 192.168.1.0/24
```



### **2. Basic Port Scanning**

* Scanned target machine for **open ports**
* Observed commonly open ports:

  * **22** → SSH
  * **80** → HTTP
  * **443** → HTTPS

```
nmap 192.168.1.5
```



### **3. Service Version Detection**

* Identified **versions of running services**
* Checked for potentially outdated software

```
nmap -sV 192.168.1.5
```


### **4. Operating System Detection**

* Attempted to detect the **target operating system**

```
nmap -O 192.168.1.5
```



### **5. Aggressive Scan**

* Performed an advanced scan including:

  * OS detection
  * Version detection
  * Script scanning
  * Traceroute

```
nmap -A 192.168.1.5
```



### **6. Specific Port Scanning**

* Scanned selected ports only

```
nmap -p 80,443 192.168.1.5
```



## **Commands Summary**

* **Host discovery:** `nmap -sn <network>`
* **Basic scan:** `nmap <target-ip>`
* **Version detection:** `nmap -sV <target-ip>`
* **OS detection:** `nmap -O <target-ip>`
* **Aggressive scan:** `nmap -A <target-ip>`
* **Specific ports:** `nmap -p <ports> <target-ip>`


## **Key Observations**

* Identified **active hosts** within the local network
* Detected **open ports and associated services**
* Observed **service version details**
* Understood how exposed services increase potential security risks



## **Key Takeaways**

* Nmap is a powerful **reconnaissance and auditing tool**
* Open ports represent **accessible network services**
* Version detection helps identify **outdated or misconfigured services**
* Regular scanning strengthens overall **security posture**
* Reconnaissance is the foundational phase of **ethical hacking**



## **Challenges Faced**

* Understanding different **scan flags and options**
* Interpreting **filtered vs closed ports**
* Some scans required **administrator/root privileges**



## **Lessons Learned**

* Proper scan selection improves efficiency and accuracy
* Not every open port is a vulnerability — **context matters**
* Scanning must always be performed in an **authorized environment**
* Reconnaissance provides valuable insights into system exposure



## **Ethical Statement**

* All scans were conducted in a **controlled virtual lab environment**
* No unauthorized systems were targeted
* This lab was performed strictly for **educational and cybersecurity purposes**



## **Conclusion**

* Gained practical experience in **network reconnaissance**
* Improved understanding of **port scanning and service enumeration**
* Strengthened foundational skills in **security assessment and auditing**
