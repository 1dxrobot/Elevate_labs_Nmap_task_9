# Elevate_labs_Nmap_task_9

### 1. Prepare your environment
1.1 Install Nmap on your system Kali.
- sudo apt update && sudo apt install nmap -y
- nmap --version   
1.2 Make sure you are scanning only your own/home lab network or systems you have permission for.
 ``` /usr/lib/nmap/nmap -A -oA scan_results 192.168.1.1 ```
1.3 Decide where you will save outputs and screenshots for later upload to GitHub.
  - mkdir ~/nmap-scans && cd ~/nmap-scans
  - sudo nmap -A 192.168.1.1 -oA scan_results
<ol> Reports  
  - Nmap 7.98 scan initiated Thu Jan 29 01:06:49 2026 as: /usr/lib/nmap/nmap -A -oA scan_results 192.168.1.1
  - Nmap done at Thu Jan 29 01:06:53 2026 -- 1 IP address (0 hosts up) scanned in 3.26 seconds </ol>
       
### 2. Scan the local network
2.1 Find your IP and network range (192.168.1.0/24).

- ip a
   - 192.168.21.129/24 

2 .2 Run a basic ping scan to discover live hosts, for example: nmap -sn 192.168.1.0/24.

```└─$ nmap -sn 192.168.21.129/24 
Starting Nmap 7.98 ( https://nmap.org ) at 2026-01-29 01:25 -0500
Nmap scan report for 192.168.21.1
Host is up (0.00027s latency).
MAC Address: 00:50:56:C0:00:08 (VMware)
Nmap scan report for 192.168.21.2
Host is up (0.00019s latency).
MAC Address: 00:50:56:FA:73:56 (VMware)
Nmap scan report for 192.168.21.254
Host is up (0.00024s latency).
MAC Address: 00:50:56:FF:F8:7E (VMware)
Nmap scan report for 192.168.21.129
Host is up.
Nmap done: 256 IP addresses (4 hosts up) scanned in 4.05 seconds
```

2.3 Note which IPs are up; you can screenshot this result.

IMAGE --> Result

### 3. Identify open ports

3.1 Choose 1–3 target IPs from the discovered hosts.
- 192.168.21.129/24
- 
3.2 Run a port scan, for example: nmap -p- 192.168.1.10 or nmap -sS 192.168.1.10.
sudo nmap -p- 192.168.21.129/24

3.3 Record which ports are open (e.g., 22, 80, 443). Screenshot or save output
Result --> IMAGE 

### 4. Detect services and versions

4.1 For the same IP, run service scan: nmap -sV 192.168.1.10.
nmap -sV 192.168.21.129/24 

4.2 This will show which service is running on each open port and sometimes the version (e.g., Apache httpd 2.4.x).
RESULT ---> image 

#### 5. Identify OS

Run OS detection: nmap -O 192.168.1.10 (you can combine options like nmap -sV -O 192.168.1.10).
-- sudo nmap -sV -O 192.168.21.129/2

