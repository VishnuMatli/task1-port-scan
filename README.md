# 🔍 Cyber Security Internship - Task 1: Local Network Port Scanning

## 📝 Objective
The aim of this task is to scan the local network to detect open ports on connected devices. This helps in understanding the exposure of services and potential security risks in a network.

---

## 🛠 Tools Used
- [Nmap](https://nmap.org/) – for performing TCP SYN scans
- [Wireshark](https://www.wireshark.org/) (optional) – for analyzing packets captured during scanning
- Command Prompt / Terminal – to find IP configuration

---

## 🧪 Steps Performed

### 1. Installed Nmap
- Downloaded from: https://nmap.org/download.html
- Installed on Windows using the official installer

### 2. Identified Local IP and Subnet
```bash
ipconfig
IP: 192.168.1.5

Subnet Range: 192.168.1.0/24

3. Performed a TCP SYN Scan
bash
Copy
Edit
nmap -sS 192.168.1.0/24
4. Saved Scan Results
bash
Copy
Edit
nmap -sS 192.168.1.0/24 -oN scan_results.txt
5. (Optional) Packet Capture with Wireshark
Opened Wireshark

Started packet capture during the Nmap scan

Used filter: tcp.port to analyze scan traffic

📊 Scan Results
A sample of discovered IPs and open ports:

IP Address	Open Ports	Possible Services
192.168.1.1	80, 443	HTTP, HTTPS (Router UI)
192.168.1.5	22, 8080	SSH, HTTP Alternate
192.168.1.10	445	Microsoft-DS (File Sharing)

🔒 Security Analysis
Port 80/443: Router interface; should be protected with strong password.

Port 22: SSH access; needs to be secured or disabled if unused.

Port 445: Common attack vector; should be closed if file sharing is not needed.

📚 Interview Questions & Answers
What is an open port?
An open port is a network port that is configured to accept incoming connections. It typically indicates an active service.

How does Nmap perform a TCP SYN scan?
Nmap sends a SYN packet to each target port. If it receives a SYN-ACK, the port is open. If it gets RST, the port is closed.

What risks are associated with open ports?
Open ports may expose services that are vulnerable to attacks, especially if outdated or misconfigured.

Explain the difference between TCP and UDP scanning.

TCP scanning is reliable and detects open ports by handshake responses.

UDP scanning is stealthier but harder to detect accurately since many services don't respond.

How can open ports be secured?

Close unused ports

Use firewalls and access control

Keep services up to date

Enable authentication and encryption where applicable

What is a firewall's role regarding ports?
Firewalls manage traffic to/from ports. They can block or allow access to ports based on security policies.

What is a port scan and why do attackers perform it?
A port scan checks which ports are open on a host. Attackers use it to find exploitable services or vulnerabilities.

How does Wireshark complement port scanning?
Wireshark captures the actual network packets, which helps analyze responses during scans and detect anomalies or hidden ports.

📁 Files in this Repository
File Name	Description
scan_results.txt	Output of the Nmap TCP SYN scan
README.md	Task documentation and answers

✅ Conclusion
This task helped me understand the concept of port scanning, use Nmap for reconnaissance, and analyze network exposure through open ports.
