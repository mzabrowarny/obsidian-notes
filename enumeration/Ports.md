# Common Ports & Services Cheat Sheet

## Introduction
In computer networking, a port is a numerical label assigned to a communication endpoint. Knowing these ports is essential for network administration, troubleshooting, and cybersecurity enumeration (e.g., using Nmap).

## Common TCP/UDP Ports

| Port | Protocol | Service | Description |
| :--- | :--- | :--- | :--- |
| **20 / 21** | TCP | **FTP** (File Transfer Protocol) | Used for transferring files between a client and a server. Port 21 is used for command control, while port 20 is used for data transfer. It is unencrypted (data is sent in plain text). |
| **22** | TCP | **SSH** (Secure Shell) | Used for secure, encrypted remote login and command execution. It is the standard replacement for the insecure Telnet protocol. |
| **23** | TCP | **Telnet** | An old protocol for remote login. It sends all data, including usernames and passwords, in plain text, making it highly insecure. |
| **25** | TCP | **SMTP** (Simple Mail Transfer Protocol) | The standard protocol for **sending** emails from a client to a server or between mail servers. |
| **53** | TCP/UDP | **DNS** (Domain Name System) | Translates human-readable domain names (like `google.com`) into IP addresses (like `142.250.1.1`). Essential for internet navigation. |
| **67 / 68** | UDP | **DHCP** (Dynamic Host Config Protocol) | Automatically assigns IP addresses and network configuration to devices on a network. |
| **80** | TCP | **HTTP** (HyperText Transfer Protocol) | The foundation of the World Wide Web. Used for transmitting web pages. It is unencrypted. |
| **110** | TCP | **POP3** (Post Office Protocol v3) | Used by email clients to **retrieve** emails from a server. Typically downloads the email to the device and deletes it from the server. |
| **139 / 445** | TCP | **SMB / NetBIOS** | Primarily used in Windows networks for file sharing, printer sharing, and active directory services. Port 445 is direct SMB over TCP. |
| **143** | TCP | **IMAP** (Internet Message Access Protocol) | Used to **retrieve** emails. Unlike POP3, it syncs emails across multiple devices and keeps them on the server. |
| **161 / 162** | UDP | **SNMP** (Simple Network Management Protocol) | Used for collecting and organizing information about managed devices on IP networks (e.g., routers, switches, printers). |
| **389** | TCP/UDP | **LDAP** (Lightweight Directory Access Protocol) | Used for accessing and maintaining distributed directory information services (often used in Active Directory for user authentication). |
| **443** | TCP | **HTTPS** (HTTP Secure) | The secure version of HTTP. It uses SSL/TLS to encrypt communication between the web browser and the server. |
| **3306** | TCP | **MySQL** | The default port for MySQL database server connections. |
| **3389** | TCP | **RDP** (Remote Desktop Protocol) | A proprietary protocol developed by Microsoft that provides a user with a graphical interface to connect to another computer over a network connection. |
| **8080** | TCP | **HTTP-Proxy / Alt-HTTP** | A common alternative port for web servers, often used for testing or for servers running without root privileges. |

## Quick Summary Tips
* **Privileged Ports (0-1023):** These ports usually require root or administrator privileges to bind services to them.
* **Security Note:** Always prefer encrypted protocols (SSH, HTTPS, SFTP) over their unencrypted counterparts (Telnet, HTTP, FTP) to prevent eavesdropping.

---
