# 🔍 Nmap Scan Analysis - Deepesh

**Scan Date:** 2025-06-23 21:15 +0530  
**Target IP:** 192.168.0.1  
**Scanner Used:** Nmap 7.97  
**Command:** `nmap -sS 192.168.0.1`

---

## 🖥️ Scan Output

Starting Nmap 7.97 ( https://nmap.org ) at 2025-06-23 21:15 +0530
Nmap scan report for 192.168.0.1
Host is up (0.0031s latency).
Not shown: 994 closed tcp ports (reset)
PORT STATE SERVICE
21/tcp open ftp
23/tcp filtered telnet
80/tcp open http
139/tcp open netbios-ssn
445/tcp open microsoft-ds
1900/tcp open upnp
MAC Address: 00:5F:67:F7:16:D9 (TP-Link Limited)

Nmap done: 1 IP address (1 host up) scanned in 2.26 seconds

---

## 📌 Port Summary

| Port | Service        | Description                                       | Risk Level       |
|------|----------------|---------------------------------------------------|------------------|
| 21   | FTP            | File Transfer Protocol (unencrypted)              | ⚠️ Medium–High   |
| 23   | Telnet         | Insecure remote login (filtered)                  | ⚠️ High          |
| 80   | HTTP           | Web server without encryption                     | ⚠️ Medium        |
| 139  | NetBIOS-SSN    | File/printer sharing (Windows LAN)                | ⚠️ Medium–High   |
| 445  | Microsoft-DS   | SMB protocol (known exploits)                     | ⚠️ High          |
| 1900 | UPNP           | Device discovery (potentially dangerous)          | ⚠️ High          |

---

## 🔐 Security Insights

- **FTP (21):** Should be replaced by **SFTP** or **FTPS** to ensure encrypted transfers.
- **Telnet (23):** Avoid using as it sends data in plain text. Use **SSH** instead.
- **HTTP (80):** Lacks encryption; switch to **HTTPS**.
- **NetBIOS (139) & SMB (445):** High risk of lateral movement attacks (e.g., EternalBlue).
- **UPnP (1900):** Can expose internal services unintentionally. Disable if not needed.

---

## 💾 Save & Export Commands

To save the scan output as a text file:
```bash
nmap -sS 192.168.0.1 -oN output.txt
