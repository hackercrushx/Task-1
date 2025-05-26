# Task-1
Elevate Labs Internship 

Task 1:  Scan Your Local Network for Open Ports

Objective: Learn to discover open ports on devices in your local network to understand network exposure.

 I open up virtual machine beacuse i am more comfortable with Kali Linux than WIndows. So firstly figure out IP address then Run: nmap -sS 192.168.1.0/24 to perform TCP SYN scan, open wireshark filter out with ports and services.

# Internship Task Report - Nmap Scanning
Date: 26 May 2025  
Tool Used: Nmap 7.94SVN , Wireshark
Platform: Kali Linux

## Objective:
Perform a TCP SYN scan on the local network and identify active hosts, open ports, running services, and potential security risks.

## Local Network:
- IP Address: 10.0.2.15
- Subnet: 10.0.2.0/24

## Scan Command:
sudo nmap -sS 10.0.2.0/24 -oN scan.txt

## Results:
- Active Hosts and Open Ports:
- Host IP	Open Ports
- 10.0.2.2	80, 135, 443, 445, 902, 912, 1433, 3306
- 10.0.2.3	80, 135, 443, 445, 902, 912, 1433, 3306
- 10.0.2.4	80, 135, 443, 445, 902, 912, 1433, 3306
- 10.0.2.15	No open ports (Kali system)

## Common Services:
- HTTP/HTTPS (Web servers)
- Microsoft RPC and SMB (Windows)
- MySQL and MSSQL (Databases)
- VMware ports (902, 912)

## Security Risks Identified:
- SMB (445) may be exploited via EternalBlue.
- Exposed databases (1433, 3306) vulnerable to brute-force or SQL attacks.
- RPC (135) commonly exploited in Windows vulnerabilities.
- VMware ports may allow remote access if unpatched.

## Recommendations:
- Disable unused services.
- Apply firewall rules to restrict access.
- Keep all systems updated.
- Avoid exposing database ports to public networks.
