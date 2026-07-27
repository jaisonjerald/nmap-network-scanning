# nmap-network-scanning
Practical Nmap network scanning and enumeration in a Windows 11 lab environment.
# 1️⃣ Host Discovery

## 🎯 Objective

Identify active hosts on the local network using Nmap's host discovery feature.

---

## 🖥️ Lab Environment

| Component | Details |
|-----------|---------|
| Operating System | Kali Linux |
| Target | Windows 11 |
| Tool | Nmap |
| Network | VirtualBox Host-Only Adapter |

---

## 📌 Command Used

```bash
nmap -sn 192.168.56.103
```

---

## 📸 Screenshot

<p align="center">
  <img src="images/01-host-discovery.png" width="900">
</p>

<p align="center">
<b>Figure 1:</b> Host discovery using an Nmap Ping Scan.
</p>

---

## 📂 Scan Output

The complete scan output is available here:

- [`scans/01-host-discovery.txt`](scans/01-host-discovery.txt)

---

## 📊 Packet Analysis

| Field | Value |
|-------|-------|
| Scanner | Kali Linux |
| Target | Windows 11 |
| Target IP | 192.168.56.103 |
| Scan Type | Host Discovery |
| Nmap Option | `-sn` |

---

## 🛡️ Security Relevance

Host discovery is the first step in network reconnaissance. It helps security professionals:

- Identify active devices
- Verify network connectivity
- Build an inventory of reachable hosts
- Prepare for service enumeration and vulnerability assessment

---

## 📚 Key Takeaways

- `-sn` performs host discovery without scanning ports.
- It is useful for quickly identifying live systems.
- Host discovery is commonly performed before more detailed scans.

---

## 💡 Skills Demonstrated

- Nmap Host Discovery
- Network Enumeration
- Reconnaissance
- Network Mapping

- # 2️⃣ TCP Connect Scan

## 🎯 Objective

Identify open TCP ports on the target system using a full TCP connection scan.

---

## 🖥️ Lab Environment

| Component | Details |
|-----------|---------|
| Scanner | Kali Linux |
| Target | Windows 11 |
| Tool | Nmap |
| Scan Type | TCP Connect Scan |

---

## 📌 Command Used

```bash
nmap -sT 192.168.56.103
```

---

## 📸 Screenshot

<p align="center">
  <img src="images/02-tcp-connect-scan.png" width="900">
</p>

<p align="center">
<b>Figure 2:</b> TCP Connect Scan performed using Nmap.
</p>

---

## 📂 Scan Output

The complete scan output is available here:

- [`scans/02-tcp-connect-scan.txt`](scans/02-tcp-connect-scan.txt)

---

## 📊 Scan Analysis

| Field | Value |
|-------|-------|
| Target IP | 192.168.56.103 |
| Open Port | 80 |
| Service | HTTP |
| Scan Type | TCP Connect Scan (`-sT`) |

### Observations

The TCP Connect Scan successfully identified **TCP port 80** as **open**, indicating that the target Windows system is running an HTTP service.

The scan completed a full TCP three-way handshake to verify that the port was accepting connections.

---

## 🛡️ Security Relevance

TCP Connect Scans help security professionals:

- Identify exposed services
- Discover open ports
- Verify firewall configurations
- Prepare for service enumeration and vulnerability assessments

In this lab, Nmap successfully identified an HTTP service listening on TCP port 80, demonstrating how open ports can reveal available network services.

---

## 📚 Key Takeaways

- `-sT` completes the full TCP three-way handshake.
- It does not require raw socket privileges.
- Open ports often indicate services available on the target host.

---

## 💡 Skills Demonstrated

- TCP Port Scanning
- Service Discovery
- Network Enumeration
- Reconnaissance
# 3️⃣ Version Detection

## 🎯 Objective

Identify the services running on open ports and determine their versions using Nmap service detection.

---

## 📌 Command Used

```bash
nmap -sV 192.168.56.103
```

---

## 📸 Screenshot

<p align="center">
  <img src="images/03-version-detection.png" width="900">
</p>

<p align="center">
<b>Figure 3:</b> Service version detection using Nmap.
</p>

---

## 📂 Scan Output

- [`scans/03-version-detection.txt`](scans/03-version-detection.txt)

---

## 📊 Analysis

| Field | Value |
|-------|-------|
| Target IP | 192.168.56.103 |
| Scan Type | Service Version Detection |
| Nmap Option | `-sV` |

### Observations

Nmap probed the open ports to identify the services running on them. Service version detection helps determine the software and, when available, its version information.

---

## 🛡️ Security Relevance

Service version detection is valuable because it helps analysts:

- Identify software running on a host
- Detect outdated or vulnerable services
- Support vulnerability assessments
- Prioritize remediation efforts

---

## 📚 Key Takeaways

- `-sV` performs service detection on open ports.
- It provides additional information beyond whether a port is simply open or closed.
- Accurate service identification supports better security analysis.

---

## 💡 Skills Demonstrated

- Service Enumeration
- Version Detection
- Network Reconnaissance
- Nmap Analysis
