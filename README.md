NETWORKWALKS-B082-WK1-PM1-CYBERSECURITY-LAB-SETUP

 Cybersecurity Lab Environment Setup — VirtualBox and Kali Linux

 📌 Project Overview
This project documents my Week 1 practical work for the Networkwalks Cybersecurity Internship, Batch B082. The goal is to build a virtual cybersecurity lab using VirtualBox and Kali Linux for safe, authorized security testing.

 🎯 Objectives
- Configure VirtualBox and a Kali Linux virtual machine.
- Configure a NAT Network using the `10.0.0.0/24` subnet.
- Test network and internet connectivity.
- Create a virtual machine snapshot.
- Document configuration and troubleshooting.

⚙️ Lab Configuration

| Component | Configuration 
 Host machine | MacBook M1 
 Virtualization | Oracle VirtualBox 
 Guest operating system | Kali Linux 2026.1 
 Network type | NAT Network 
 Required subnet | `10.0.0.0/24` 
 Current Kali IP | `10.0.0.3/24` 
 Required Kali IP | `10.0.0.2/24` 
 Internet connectivity | Verified 
 Ping packet loss | 0% 
 VM snapshot | Created 
 Shared folder | Configured; access not yet verified 

🪜 Work Completed

1. Opened VirtualBox and used an existing working Kali Linux virtual machine.
2. Configured the VM to use a NAT Network.
3. Restored network connectivity after troubleshooting the IP configuration.
4. Tested internet connectivity using `ping -c 4 google.com`.
5. Confirmed 0% packet loss during the test.
6. Created a VM snapshot.
7. Configured a shared folder pointing to the host computer's Downloads folder.

🔎 Verification Results

 Test | Result 
 Kali Linux starts | Successful 
 NAT Network | Configured 
 Internet connectivity | Successful 
 Ping packet loss | 0% 
 VM snapshot | Saved 
 Required IP address | Still needs adjustment 
 Shared folder access | Pending verification 
 Clipboard and drag-and-drop | Pending verification 

🐞 Troubleshooting

Network connectivity: After changing the IPv4 settings, the Kali VM temporarily lost its IP address. The connection was restored and internet connectivity was tested successfully.

Shared folder: The shared folder was configured in VirtualBox but could not yet be accessed from inside Kali. Further guest integration troubleshooting is required.

💡 What I Learned
- How virtual machines run in VirtualBox.
- How NAT Network supports virtual lab networking.
- How to inspect IPv4 configuration and test connectivity.
- Why snapshots are useful before future lab exercises.
- How to document technical issues and troubleshooting results.

 🔐 Ethical Use
This lab is intended for cybersecurity education and authorized testing only. I will test only systems I own or have explicit permission to assess.

 🔗 Tools and Resources
- [Oracle VirtualBox](https://virtualbox.org/wiki/Downloads)
- [Kali Linux](https://kali.org/get-kali)
- [Networkwalks](https://networkwalks.com)

👤 Author
Morenike Jaiyesimi

Cybersecurity Intern — Networkwalks, Batch B082

 📌 Project Information
- Week: 01
- Project: WK1-PM1 — Cybersecurity Lab Setup
- Repository: `NETWORKWALKS-B082-WK1-PM1-CYBERSECURITY-LAB-SETUP`
