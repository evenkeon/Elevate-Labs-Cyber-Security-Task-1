
Detailed Findings and Risk Assessment

Scan Date: Mon Aug 4 20:45:26 2025
Network Range: 192.168.0.113/24
Scan Type: Aggressive scan (-A)
Duration: 269.60 seconds
Hosts Discovered: 5

Host 192.168.0.1 (Router/Gateway)

Open Port: 80/tcp (tcpwrapped)

Low risk; management interface only.

Host 192.168.0.100

All 1,000 TCP ports filtered

Likely firewalled or offline; no services exposed.

Hosts 192.168.0.106 and 192.168.0.107 (Windows devices)

No open TCP ports detected

Appear hardened or offline

Host 192.168.0.114 (Metasploitable2 VM) – Critical Risk
Open services and associated vulnerabilities:

FTP (vsftpd 2.3.4) on 21/tcp – Backdoor vulnerability (CVE-2011-2523) spawns root shell

SSH (OpenSSH 4.7p1) on 22/tcp – CBC mode weaknesses and weak key algorithms

Telnet (Linux telnetd) on 23/tcp – Cleartext credentials

SMTP (Postfix smtpd) on 25/tcp – Expired self-signed cert, unauthenticated commands

DNS (ISC BIND 9.4.2) on 53/tcp – Outdated software vulnerable to cache poisoning

HTTP (Apache 2.2.8) on 80/tcp – EOL version with known exploits

RPC/RPCBind on 111/tcp – Exposed NFS and mount services

Samba (3.0.20) on 139 & 445/tcp – “Username map script” RCE (CVE-2007-2447)

rsh/execd on 512–514/tcp – Legacy, unencrypted remote shells

Java RMI on 1099/tcp – Remote class loading risk

Bindshell on 1524/tcp – Direct root shell access

NFS on 2049/tcp – Unauthenticated file share

FTP (ProFTPD 1.3.1) on 2121/tcp – Directory traversal and shell escapes

MySQL 5.0.51a on 3306/tcp – Privilege and auth bypass (CVE-2008-4097, CVE-2012-2122)

PostgreSQL 8.3 on 5432/tcp – SQL injection via crafted filenames (CVE-2012-0868)

VNC on 5900/tcp – Weak authentication, no encryption

X11 on 6000/tcp – GUI session exposure if enabled

IRC (UnrealIRCd) on 6667/tcp – Known remote code execution flaws

AJP13 on 8009/tcp – Request smuggling and Ghostcat risks

Tomcat (Apache-Coyote/1.1) on 8180/tcp – Outdated, directory listing exploits

Overall Risk Assessment:
The Metasploitable2 host exposes multiple critical and high-risk services, making it an immediate target for exploitation. Other hosts present minimal risk