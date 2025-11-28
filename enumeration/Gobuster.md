# Gobuster Cheat Sheet

### Introduction
**Gobuster** is a high-speed, brute-force tool written in Go. It is used to discover hidden URIs (directories and files), DNS subdomains, and Virtual Host names on web servers.

**Key Modes:**
* `dir`: Enumerating directories and files.
* `vhost`: Enumerating virtual hosts (VHosts).
* `fuzz`: Fuzzing values (e.g., parameters).

---

### Prerequisites: Wordlists
Gobuster requires a wordlist to operate. In Kali Linux, the **SecLists** collection is standard (located at `/usr/share/seclists/`).

**Common Wordlists used in these exercises:**
* **Directories:** `/usr/share/seclists/Discovery/Web-Content/raft-small-directories.txt`
* **Files:** `/usr/share/seclists/Discovery/Web-Content/raft-small-files.txt`
* **Virtual Hosts:** `/usr/share/seclists/Discovery/DNS/fierce-hostlist.txt`
* **Subdomains:** `/usr/share/seclists/Discovery/DNS/subdomains-top1million-5000.txt`
* **Passwords:** `/usr/share/seclists/Passwords/xato-net-10-million-passwords-100000.txt`

---

### Directory Enumeration
**Goal:** Discover hidden directories on the target server.
**Mode:** `dir`

```bash
gobuster dir -u http://<target_ip>/ -w /usr/share/seclists/Discovery/Web-Content/raft-small-directories.txt
```

---

### File Enumeration
**Goal:** Discover hidden files (e.g., `.php`, `.txt`, `.html`).
**Mode:** `dir`

You can use a specific file wordlist or append extensions to a directory wordlist.

**Option A: Using a file-specific wordlist**
```bash
gobuster dir -u http://<target_ip>/_private/ -w /usr/share/seclists/Discovery/Web-Content/raft-small-files.txt
```

**Option B: Using extensions (`-x`)**
```bash
gobuster dir -u http://<target_ip>/ -w <wordlist> -x php,html,txt
```

---

### Virtual Host Enumeration
**Goal:** Find hidden Virtual Hosts on a single IP address (checking if the server content changes based on the `Host` header).
**Mode:** `vhost`

```bash
gobuster vhost -u http://<target_ip>/ -w /usr/share/seclists/Discovery/DNS/fierce-hostlist.txt
```

---

### Subdomain Enumeration
**Goal:** Find subdomains associated with a specific base domain (e.g., `secret.business`).
**Mode:** `vhost`

This uses `vhost` mode but appends the domain to the wordlist entries.

```bash
gobuster vhost -u http://<target_ip>/ -w /usr/share/seclists/Discovery/DNS/subdomains-top1million-5000.txt --domain business --append-domain
```
* `--domain`: Specifies the base domain.
* `--append-domain`: Appends the base domain to every word in the list (e.g., checking `word.business`).

---

### Parameter Fuzzing
**Goal:** Find hidden GET parameters (e.g., `?password=...`).
**Mode:** `fuzz`

This brute-forces a specific part of the URL defined by the keyword `FUZZ`.

```bash
gobuster fuzz -u "http://<target_ip>/page.php?password=FUZZ" -w /usr/share/seclists/Passwords/xato-net-10-million-passwords-100000.txt
```
* `FUZZ`: The placeholder that Gobuster replaces with words from the list.
* `-fs <size>`: (Optional but recommended) Filter by file size to hide invalid responses if they all have the same size.

---

### Common Flags Reference

| Flag | Description |
| :--- | :--- |
| `-u` | **URL:** The target web address. |
| `-w` | **Wordlist:** Path to the dictionary file. |
| `-t` | **Threads:** Number of concurrent threads (default is 10). |
| `-x` | **Extensions:** Extensions to search for (only in `dir` mode). |
| `-k` | **Skip SSL:** Ignore SSL certificate errors. |
| `--domain` | Base domain for VHost scanning. |
| `--append-domain` | Append the base domain to wordlist entries. |
| `-z` | **No Progress:** Hide the progress bar. |
| `-o` | **Output:** Save results to a file. |

---