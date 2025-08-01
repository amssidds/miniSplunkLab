# miniSplunkLab

A self-contained lab environment for exploring log collection, analysis, and detection using **Splunk**, **Windows Event Forwarding**, **Sysmon**, and **Active Directory**.

---

## Project Overview

The **miniSplunkLab** project simulates a small enterprise network to explore how logs can be collected, forwarded, and analyzed in a central SIEM (Splunk).  
It involves setting up multiple virtual machines, forwarding logs from endpoints, simulating attacks, and analyzing results.

---

## Lab Architecture

<img width="500" alt="Screenshot 2025-07-31 170618" src="https://github.com/user-attachments/assets/8b0809dc-9b71-4bf1-84f7-03122568641b" />


- **Proxmox** as the hypervisor
- **Ubuntu VM** running Splunk Enterprise
- **Windows Server (Domain Controller)**
- **Windows Client (joined to the domain)**
- **Kali Linux** for adversary simulation
- **Sysmon** and **Splunk Universal Forwarder** for detailed endpoint logging
- **Atomic Red Team** for safe adversary emulation

---

## Implementation Steps

1. **Provisioned VMs on Proxmox** for Splunk, Active Directory, Windows Client, and Kali Linux.  
2. **Installed Splunk Enterprise** on Ubuntu and configured it to auto-start.  
3. **Deployed Splunk Universal Forwarder** on Windows endpoints for log forwarding.  
4. **Installed Sysmon** with a custom configuration for detailed Windows event logging.  
5. **Created indexes** in Splunk to organize forwarded logs.  
6. **Configured inputs.conf** to collect Application, Security, System, and Sysmon event logs.  
7. **Promoted a Windows Server to Domain Controller** and created test users and groups.  
8. **Joined a Windows client to the domain** for centralized log collection.  
9. **Simulated adversary activity** using Atomic Red Team to generate test logs.  
10. **Queried Splunk** for collected logs, confirming event visibility and successful detection.

---

## Screenshots

All step-by-step screenshots documenting the lab setup and testing process are included in [`screenshots.pdf`](./screenshots.pdf).  

---

## Source

- [Splunk](https://www.splunk.com/)
- [Sysmon](https://learn.microsoft.com/en-us/sysinternals/downloads/sysmon)
- [Atomic Red Team](https://github.com/redcanaryco/atomic-red-team)
