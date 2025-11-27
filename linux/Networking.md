---
tags:
  - linux
  - networking
  - cli
---
This note covers essential commands for network configuration, diagnostics, and connection monitoring in Linux.

## Interface & IP Configuration
* **`ip a`**: Displays detailed information about network interfaces, including IP addresses, subnet masks, and status.
* **`ip n`**: Shows the neighbor table (ARP cache), mapping IP addresses to MAC addresses for devices in the local network.

## Routing & DNS
* **`ip r`**: Displays the system routing table, showing available network routes, gateways, and interfaces.
* **`/etc/resolv.conf`**: A configuration file containing information about DNS servers used for domain name resolution.
    * *Command:* `cat /etc/resolv.conf`

## Connections (Sockets)
We use the `ss` command to investigate sockets:
* **`ss -tp`**: Lists active TCP connections with details like source/destination IPs and ports.
* **`ss -tlp`**: Lists active **listening** TCP ports, including the Process ID (PID) and the program name responsible for the socket.

## Remote Access (SSH)
* **SSH (Secure Shell)**: A protocol for secure remote login.
* **Connection**: `ssh user@ip_address` (e.g., `ssh johndoe@192.168.100.1`).
* **Keys**: SSH keys are safer than passwords. You generate them with `ssh-keygen` and copy the public key to the server using `ssh-copy-id user@hostname`.

---
