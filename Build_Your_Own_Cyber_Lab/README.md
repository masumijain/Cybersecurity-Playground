# 🔐 Cybersecurity Lab Setup (pfSense + Ubuntu + Kali)

---

## 1️⃣ Download Required Tools

### ✅ Install Hypervisor

Download & install:

* **VirtualBox** (recommended)
  or
* VMware

---

### ✅ Download ISOs

* **pfSense ISO** → from official website
* **Ubuntu Desktop ISO**
* **Kali Linux ISO**

---

## 2️⃣ Create pfSense VM (Most Important)

### ➤ Create New VM

* Type: BSD
* Version: FreeBSD (64-bit)
* RAM: 2GB minimum
* CPU: 2 cores

### ➤ Network Setup (Very Important)

Adapter 1:

* Attached to: **Bridged Adapter**
* This is **WAN**

Adapter 2:

* Attached to: **Internal Network**
* Name: `labnet`
* This is **LAN**

---

## 3️⃣ Install pfSense

* Boot from ISO
* Choose default installation
* Reboot

After installation, assign interfaces:

* WAN → em0
* LAN → em1

Set LAN IP:

```
192.168.10.1 /24
```

Enable DHCP on LAN (easier).

Now pfSense LAN IP =
👉 `192.168.10.1`

---

## 4️⃣ Create Ubuntu VM

* Type: Linux → Ubuntu (64-bit)
* RAM: 2GB
* CPU: 2 cores

### Network:

Adapter 1:

* Attached to: **Internal Network**
* Name: `labnet`

Start VM.

Ubuntu should auto-get IP from pfSense DHCP.

Check:

```bash
ip a
```

Should show:

```
192.168.10.x
```

Open browser:

```
https://192.168.10.1
```

pfSense login page should open ✅

---

## 5️⃣ Create Kali VM

* Type: Linux → Debian (64-bit)
* RAM: 2GB
* CPU: 2 cores

### Network:

Adapter 1:

* Attached to: **Internal Network**
* Name: `labnet`

Start Kali.

Check:

```bash
ip a
```

Should get:

```
192.168.10.x
```

Now Kali & Ubuntu are inside LAN behind pfSense.

---

## 6️⃣ Test Internet Access

From Ubuntu or Kali:

```bash
ping 8.8.8.8
```

If not working:

* Check pfSense → Firewall Rules → LAN → Allow LAN to Any

---

#  Final Lab Architecture

```
Internet
   ↓
Home Router
   ↓
pfSense (WAN)
   ↓
pfSense (LAN 192.168.10.1)
   ↓
Ubuntu & Kali (192.168.10.x)
```

---

# What You Can Do Now

* Packet capture
* Nmap scanning
* Firewall rule testing
* IDS/IPS practice
* Traffic monitoring
* VLAN experiments
