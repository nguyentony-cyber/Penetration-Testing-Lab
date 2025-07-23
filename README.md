# In-House Penetration Testing Lab

## 📌 Objective
This project involved setting up a virtual penetration testing lab using Kali Linux and Metasploitable2 to simulate real-world attack scenarios. The objective was to perform network reconnaissance, discover vulnerabilities, and exploit critical flaws using both automated tools and manual techniques.

## 🧠 Skills Gained
- Vulnerability scanning and assessment using tools like Nmap and Nessus
- Exploitation using Metasploit Framework
- Manual enumeration and attack execution
- Root shell access and post-exploitation validation
- Documentation of findings and remediation strategies

## 🛠️ Tools Used
- **Kali Linux** (Attacker Machine)
- **Metasploitable2** (Target Machine)
- **VirtualBox** for VM hosting
- **Nmap**, **ARP-scan** for discovery and enumeration
- **Nessus** for vulnerability scanning
- **Metasploit** for exploitation

## 🖥️ Lab Setup

| Component         | Configuration            |
|------------------|--------------------------|
| Host Machine      | Windows 11               |
| Virtualization    | VirtualBox               |
| Kali Linux IP     | 10.0.2.15                |
| Metasploitable2 IP| 10.0.2.15                |
| Network Mode      | NAT                      |



## 🔍 Scanning Phase

### Network Discovery
Tools: `Nmap`, `ARP-scan`  
Identified Open Ports:
- **22** – SSH (OpenSSH 4.7p1)
- **80** – HTTP (Apache 2.2.8)
- **139, 445** – SMB (Samba 3.0.20)

### Vulnerability Scanning
Tool: `Nessus`  
The scan revealed multiple **critical** vulnerabilities, including:
- vsftpd v2.3.4 Backdoor (CVE-2011-2523)
- UnrealIRCd 3.2.8.1 Backdoor (CVE-2010-2075)


## 🧪 Exploitation Phase

### 1. vsftpd v2.3.4 Backdoor
Exploit Used: `exploit/unix/ftp/vsftpd_234_backdoor`

Steps:
- Launched exploit in Metasploit
- Set RHOST to Metasploitable IP
- Gained root shell access

### 2. UnrealIRCd 3.2.8.1 Backdoor
Exploit Used: `exploit/unix/irc/unreal_ircd_3281_backdoor`

Steps:
- Launched exploit in Metasploit
- Set RHOST to target IP
- Gained full remote access



## 🔒 Risk Assessment
If left unpatched:
- Attackers could gain **unauthenticated root access**
- Systems exposed to the internet could be fully compromised
- Threats include data theft, malware injection, and lateral movement

## ✅ Mitigation & Recommendations
- Patch or remove outdated software (vsftpd, UnrealIRCd)
- Perform routine vulnerability assessments
- Use network segmentation and firewalls to isolate services
- Deploy IDS/IPS to monitor traffic for exploit behavior
- Limit service exposure to internal users only

## 📄 Summary
This project reinforced critical cybersecurity skills, including vulnerability discovery, exploitation, and reporting. It highlighted how quickly outdated services can be exploited and stressed the importance of secure configurations and timely patching.


