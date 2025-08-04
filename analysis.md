Vulnerability Assessment Summary of Network Scan

1.Router/Gateway (192.168.0.1)
  – Open Port: 80/tcp (tcpwrapped)
  – Risk Level: Low (management interface only)

2.Host 192.168.0.100
  – All 1,000 TCP ports filtered
  – Status: Likely firewalled or offline; no services exposed

3.Windows Devices (192.168.0.106 & 192.168.0.107)
  – No open TCP ports detected
  – Status: Appear hardened or offline

4.Metasploitable2 VM (192.168.0.114)
  – Overall Risk: Critical
  – Key Vulnerable Services:

FTP (vsftpd 2.3.4) on port 21/tcp – backdoor vulnerability (CVE-2011-2523) allowing root shell access

SSH (OpenSSH 4.7p1) on port 22/tcp – CBC mode weaknesses and weak key algorithms

Telnet on port 23/tcp – cleartext credentials transmission

SMTP (Postfix) on port 25/tcp – expired self-signed certificate and unauthenticated commands

DNS (ISC BIND 9.4.2) on port 53/tcp – outdated software vulnerable to cache poisoning

HTTP (Apache 2.2.8) on port 80/tcp – end-of-life version with known exploits

RPC/RPCBind on port 111/tcp – exposed NFS and mount services

Samba (3.0.20) on ports 139 and 445/tcp – remote code execution via the “username map script” (CVE-2007-2447)

rsh/execd on ports 512–514/tcp – legacy unencrypted remote shells

Java RMI on port 1099/tcp – remote class loading risk

Bindshell on port 1524/tcp – direct root shell access

NFS on port 2049/tcp – unauthenticated file share

FTP (ProFTPD 1.3.1) on port 2121/tcp – directory traversal and shell escape vulnerabilities

MySQL (5.0.51a) on port 3306/tcp – privilege and authentication bypass (CVE-2008-4097, CVE-2012-2122)

PostgreSQL (8.3) on port 5432/tcp – SQL injection via crafted filenames (CVE-2012-0868)

VNC on port 5900/tcp – weak authentication and no encryption

X11 on port 6000/tcp – potential GUI session exposure

IRC (UnrealIRCd) on port 6667/tcp – known remote code execution flaws

AJP13 on port 8009/tcp – request smuggling and Ghostcat vulnerabilities

Tomcat (Apache-Coyote/1.1) on port 8180/tcp – outdated version allowing directory listing exploits

Immediate mitigation is required for the Metasploitable2 VM to prevent exploitation.



