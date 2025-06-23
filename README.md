# 🔍 Cyber Security Internship - Task 1: Local Network Port Scanning

## 📝 Objective
The aim of this task is to scan the local network to detect open ports on connected devices. This helps in understanding the exposure of services and potential security risks in a network.

---

## 🛠 Tools Used
- [Nmap](https://nmap.org/) – for performing TCP SYN scans
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

📁 Files in this Repository
File Name	Description
scan_results.txt	Output of the Nmap TCP SYN scan
README.md	Task documentation and answers

✅ Conclusion
This task helped me understand the concept of port scanning, use Nmap for reconnaissance, and analyze network exposure through open ports.
