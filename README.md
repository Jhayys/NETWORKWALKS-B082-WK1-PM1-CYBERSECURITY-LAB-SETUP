# NETWORKWALKS-B082-WK1-PM1-CYBERSECURITY-LAB-SETUP

**Cybersecurity Lab Environment Setup**

Building a virtual lab with VirtualBox and Kali Linux for cybersecurity testing and ethical hacking practice.

## 📌 Project Overview

This project documents the setup of a virtual cybersecurity laboratory using VirtualBox and Kali Linux on a MacBook with an Apple M1 processor.

The goal is to prepare a controlled environment for learning cybersecurity, networking, reconnaissance, network scanning, and authorized security testing.

The lab uses a VirtualBox NAT Network with the intended subnet `10.0.0.0/24`. The configuration and verification steps are documented alongside the challenges encountered during setup.

## 🎯 Objectives

The main objectives of this project are to:

- Set up VirtualBox on a MacBook M1.
- Run Kali Linux as a virtual machine.
- Configure a NAT Network using the `10.0.0.0/24` subnet.
- Configure and verify Kali Linux network connectivity.
- Work toward the required Kali IPv4 address of `10.0.0.2/24`.
- Configure shared-folder access between the host and Kali Linux.
- Enable clipboard and drag-and-drop options in the VM settings.
- Test Internet connectivity.
- Create a VM snapshot for recovery.
- Document the setup process, challenges, and lessons learned.

## 🛡️ Purpose of the Lab

The lab provides an environment for learning and practising cybersecurity skills safely.

It is intended to support future activities such as:

- Network reconnaissance
- Port scanning
- Vulnerability assessment
- Packet analysis
- Security-tool experimentation
- Penetration-testing exercises in authorized lab environments

**Important:** All security testing must be limited to systems owned by the learner or systems for which explicit permission has been granted.

## 🏗️ Lab Architecture

The current setup consists of a MacBook host running VirtualBox with a Kali Linux virtual machine attached to a NAT Network.

```text
MacBook M1 Host
       |
       | VirtualBox
       |
       +---- NAT Network
              |
              | Subnet: 10.0.0.0/24
              |
              +---- Kali Linux VM
                     |
                     +---- Cybersecurity tools
                     +---- Network testing
                     +---- Future lab exercises
```

Additional virtual machines may be added to the lab in future exercises.

## ⚙️ Lab Configuration

| Component | Configuration |
|---|---|
| Host OS | macOS |
| Host processor | Apple M1 |
| Hypervisor | Oracle VirtualBox |
| Security OS | Kali Linux |
| Virtual network | NAT Network |
| Network subnet | `10.0.0.0/24` |
| Required Kali IP | `10.0.0.2/24` |
| Previously observed DHCP IPv4 | `10.0.0.3/24` |
| Current IPv4 status | Requires re-verification |
| Internet connectivity | Successful ping test recorded earlier |
| VM snapshot | Created |
| Shared folder | Configured in VirtualBox; guest access not yet verified |
| Clipboard and drag-and-drop | Options configured; functionality not yet verified |

**Note:** The required address is `10.0.0.2/24`, but the lab did not consistently retain that address during configuration. The documentation distinguishes the required address from the address observed during earlier testing.

## 🪜 Lab Setup Procedure

### Step 1. Prepare the Host Environment

A MacBook M1 was used as the host computer. VirtualBox was used to run the Kali Linux virtual machine.

Because the host uses Apple Silicon, the virtual-machine environment and networking behaviour may differ from those on a Windows PC with an Intel processor.

### Step 2. Set Up VirtualBox

VirtualBox was used as the hypervisor for the Kali Linux virtual machine.

The Kali VM was opened and its network and integration settings were configured through the VirtualBox interface.

### Step 3. Create the NAT Network

A VirtualBox NAT Network was configured for the lab.

The intended network configuration is:

- **Network type:** NAT Network
- **IPv4 subnet:** `10.0.0.0/24`
- **Purpose:** Provide network connectivity for the lab and allow future virtual machines to share the same virtual network.

The NAT Network was selected instead of configuring the VM as an isolated, host-only machine.

### Step 4. Configure the Kali Linux VM

Kali Linux was started in VirtualBox and connected to the configured NAT Network.

The VM network adapter was set to use the NAT Network. The guest network interface was identified as `eth0` during troubleshooting.

The target configuration required by the assignment is:

```text
IP Address: 10.0.0.2
Subnet Mask: 255.255.255.0
Network:    10.0.0.0/24
```

During testing, the VM previously received `10.0.0.3/24` through DHCP. Later checks did not consistently show an IPv4 address, so the required static address remains unverified.

### Step 5. Configure Shared Folder and VM Integration

A host Downloads folder was configured in the VirtualBox shared-folder settings with the name `downloads`. The options to auto-mount the folder and make it permanent were selected.

However, the folder was not successfully accessed from inside Kali Linux during this setup.

Clipboard sharing and drag-and-drop options were also configured in the VM settings, but successful transfer between macOS and Kali has not yet been confirmed.

These items remain outstanding verification tasks.

### Step 6. Test Internet Connectivity

Internet connectivity was tested from Kali Linux using a ping command.

An earlier test to `google.com` returned **0% packet loss**, indicating successful connectivity at that time.

Because the IPv4 configuration later became inconsistent, connectivity should be retested after the network address is corrected.

### Step 7. Create a Clean VM Snapshot

A VirtualBox snapshot was created for the Kali Linux VM.

A snapshot provides a recovery point that can be used if later lab activities change the VM configuration or cause problems.

The snapshot was saved as part of the lab setup process.

## 🔎 Lab Verification

| Test | Result |
|---|---|
| Kali Linux VM starts | Successful |
| NAT Network selected | Configured |
| NAT Network subnet | Set to `10.0.0.0/24` |
| Required Kali IP `10.0.0.2/24` | Not yet verified |
| Earlier DHCP address `10.0.0.3/24` | Observed |
| Internet connectivity | Earlier ping test succeeded with 0% packet loss |
| Shared-folder access inside Kali | Not yet successful |
| Clipboard and drag-and-drop transfer | Not yet verified |
| VM snapshot | Created |

### Commands Used for Verification

Check network interfaces and addresses:

```bash
ip -br addr
```

Check the active network connection:

```bash
nmcli connection show --active
```

Test Internet connectivity:

```bash
ping -c 4 google.com
```

Check the Nmap installation:

```bash
nmap --version
```

These commands are included to document the verification process. The results should be captured again after the outstanding network configuration issues are resolved.

## 🐞 Problems Encountered & Solutions

### Problem 1. Required IPv4 Address Was Not Retained

The assignment requires Kali Linux to use `10.0.0.2/24`. During configuration, the VM previously received `10.0.0.3/24` through DHCP. After changes to the network settings, subsequent checks did not consistently display an IPv4 address.

**Troubleshooting performed:**

- Checked the VirtualBox NAT Network configuration.
- Checked the Kali network interface.
- Inspected active NetworkManager connections.
- Returned to DHCP during troubleshooting.

**Current status:** The required IPv4 address still needs to be configured and verified.

### Problem 2. Shared Folder Was Not Accessible

The `downloads` shared folder was configured in VirtualBox, but it did not appear as an accessible folder inside Kali Linux.

**Troubleshooting performed:**

- Checked the VirtualBox shared-folder settings.
- Enabled auto-mount and made the folder permanent.
- Attempted to access the mounted folder from Kali Linux.
- Attempted to use the Guest Additions option.

**Current status:** The shared-folder configuration exists in VirtualBox, but access from Kali Linux remains unresolved.

### Problem 3. Host and Guest Integration Could Not Be Confirmed

Clipboard and drag-and-drop options were configured in VirtualBox. However, successful file transfer and clipboard functionality were not confirmed during the setup.

**Current status:** These features require a later functionality test.

## 💡 What I Learned

Through this project, I gained practical experience with:

1. **Virtualization:** Using VirtualBox to run Kali Linux in a virtual machine on a MacBook M1.
2. **Virtual networking:** Understanding how a NAT Network connects virtual machines and provides network address translation.
3. **IP addressing:** Checking IPv4 addresses, network interfaces, and active connections in Linux.
4. **Network troubleshooting:** Investigating differences between the intended IP configuration and the address reported by the guest operating system.
5. **VM snapshots:** Creating a recovery point before progressing to additional cybersecurity exercises.
6. **Technical documentation:** Recording configuration details, verification results, problems, and outstanding tasks honestly.

## 🔐 Security & Ethical Use

This laboratory is intended for education and authorized cybersecurity practice only.

Any future reconnaissance, scanning, vulnerability assessment, or penetration testing will be performed only against systems owned by the learner or explicitly authorized for testing.

## 🔗 Tools & Resources

- **VirtualBox:** https://www.virtualbox.org/wiki/Downloads
- **Kali Linux:** https://www.kali.org/get-kali/
- **Networkwalks:** https://www.networkwalks.com/

## 👤 Author

**Morenike Jaiyesimi**

Cybersecurity Intern — Networkwalks

GitHub: https://github.com/Jhayys

## 📌 Project Information

- **Program:** Cybersecurity Internship at Networkwalks
- **Week:** 01
- **Project:** WK1-PM1 — Cybersecurity Lab Setup
- **Repository:** `NETWORKWALKS-B082-WK1-PM1-CYBERSECURITY-LAB-SETUP`
- **Host environment:** MacBook M1
- **Virtualization platform:** VirtualBox
- **Guest operating system:** Kali Linux
