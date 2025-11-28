# Network Enumeration & Nmap Cheat Sheet

### Introduction to Network Enumeration
**Network Enumeration** is the process of gathering detailed information about a computer network, its devices, and services. It is a critical, initial stage in security testing (penetration testing).

**Key Objectives:**
* Identifying active IP addresses and hostnames.
* Discovering open ports and listening services.
* Detecting Operating Systems (OS) and software versions.
* Finding potential vulnerabilities and entry points.

> **Significance:** Without understanding the network structure, it is difficult to effectively simulate an attack or assess security posture. Enumeration provides the specific targets needed for further exploitation.

---

### Nmap (Network Mapper)
**Nmap** is the industry-standard open-source tool for network discovery and security auditing. It is used to identify active devices, open ports, and running services. It is available on Linux, Windows, and macOS.

### Basic Commands & Scan Types

| Flag | Name | Description |
| :--- | :--- | :--- |
| `nmap <IP>` | **Basic Scan** | Scans a target for open ports using default settings. |
| `-sn` | **Ping Scan / Host Discovery** | Disables port scanning. Checks which hosts are "alive" in a subnet (e.g., `192.168.100.0/24`). |
| `-sS` | **TCP SYN Scan (Stealth)** | *Default mode.* Fast and unobtrusive. It does not complete the TCP handshake (half-open). Note: It does not verify service versions (e.g., may guess "telnet" just based on port 23). |
| `-sT` | **TCP Connect Scan** | Performs a full TCP handshake. Slower and more likely to be logged, but useful if you lack root privileges. |
| `-sV` | **Version Detection** | Interrogates open ports to determine the exact service name and version number. |
| `-sC` | **Script Scan** | Runs default NSE (Nmap Scripting Engine) scripts to find extra info or common misconfigurations. |
| `-O` | **OS Detection** | Attempts to identify the Operating System based on TCP/IP stack behavior. Use `--osscan-guess` to force a best guess. |
| `-A` | **Aggressive Scan** | Enables OS detection (`-O`), version detection (`-sV`), script scanning (`-sC`), and traceroute all at once. |
| `-h` | **Help** | Displays the full list of options and parameters. |


---