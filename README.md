# Elevate-Labs-Cyber-Security-Task-1
This repository contains the submission for Task 1 of the Elevate Labs Cyber Security Internship. The project's objective was to scan a local network to discover open ports and understand network exposure using Nmap.

# Network Security Audit – Aggressive Nmap Scan

## Overview  
Performed an aggressive Nmap scan against 192.168.0.113/24 to identify open ports, running services, and security vulnerabilities.

## Scan Summary  
- **Date & Time:** August 4, 2025 @ 20:45  
- **Command:** `nmap -A 192.168.0.113/24 -oN AggresiveScan-Results.txt`  
- **Hosts Found:** 5  
- **Duration:** 4.5 minutes  

## Key Findings  
- One host (192.168.0.114) running Metasploitable2 exposes 23 services with multiple critical vulnerabilities (vsftpd backdoor, bindshell, Samba RCE).  
- Legacy and unencrypted protocols (Telnet, rsh, FTP, VNC) are in use.  
- Outdated database servers (MySQL 5.0, PostgreSQL 8.3) susceptible to privilege and SQL injection flaws.

## Mitigation Steps  
1. Isolate the vulnerable host immediately.  
2. Block high-risk ports using UFW or equivalent.  
3. Upgrade or replace vulnerable services with up-to-date software.  
4. Disable unnecessary protocols (Telnet, rsh).  
5. Implement network segmentation and strong firewall rules.  
6. Enforce key-based SSH with disabled root login.  
7. Deploy IDS/IPS and enable comprehensive logging.  
8. Schedule regular vulnerability scans and audits.

## Repository Contents  
- **AggresiveScan-Results.txt:** Raw scan output  
- **analysis.md:** Detailed findings and risk assessment  
- **mitigation.md:** Step-by-step remediation guide    
- **README.md:** Project overview and instructions

## Disclaimer  
This audit was conducted in a controlled, authorized environment for educational purposes. Do not scan or exploit systems without explicit permission.
By following these remediation and hardening steps, you can significantly reduce your network’s attack surface and prevent exploitation of known vulnerabilities.

