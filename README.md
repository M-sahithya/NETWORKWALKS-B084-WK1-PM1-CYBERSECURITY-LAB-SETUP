# 🔐 Kali Linux Cybersecurity Lab Setup

## 📖 1. Project Overview

This repository documents the installation, configuration, and setup of a **Kali Linux Cybersecurity Lab** using Oracle VirtualBox.

The project was carried out as part of my **Cybersecurity Internship at NetworkWalks**, with the objective of gaining practical exposure to Linux administration, virtualization, network configuration, and cybersecurity tools.

A properly configured virtual lab provides a controlled environment for understanding network communication, practicing security concepts, and exploring ethical hacking techniques.

The setup includes Kali Linux installation, NAT Network configuration, static IP addressing, connectivity verification, Nmap installation, shared folder integration, and virtual machine snapshot creation.

## 🎯 2. Project Objectives

The primary objectives of this project are:

- To understand virtualization and virtual machine configuration.
- To install and configure Kali Linux.
- To establish a virtual network using NAT Network.
- To understand static IP addressing and DNS configuration.
- To verify network and internet connectivity.
- To install and explore essential cybersecurity tools.
- To configure file sharing between host and guest operating systems.
- To understand virtual machine snapshots and recovery.
- To establish a foundation for future cybersecurity practical exercises.

## 🖥️ 3. System Requirements & Environment

### Host Machine

| Component               | Configuration           |
| ----------------------- | ----------------------- |
| Operating System        | Windows 11              |
| Processor               | Intel Core i5           |
| RAM                     | 16 GB                   |
| Virtualization Software | Oracle VirtualBox 7.2.4 |

### Virtual Machine

| Component              | Configuration     |
| ---------------------- | ----------------- |
| Guest Operating System | Kali Linux 2026.3 |
| Allocated RAM          | 4 GB              |
| Network Mode           | NAT Network       |
| Network Configuration  | Static IP         |
| Security Tool          | Nmap 7.95         |

## 🛠️ 4. Tools & Technologies Used

| Tool / Technology | Description                                                                |
| ----------------- | -------------------------------------------------------------------------- |
| Kali Linux        | Linux distribution designed for penetration testing and security auditing. |
| Oracle VirtualBox | Virtualization platform used to run Kali Linux on Windows.                 |
| Nmap              | Network discovery and security auditing tool.                              |
| NAT Network       | Provides network connectivity to virtual machines.                         |
| NetworkManager    | Linux utility used to manage network connections.                          |
| nmcli             | Command-line interface for configuring network settings.                   |
| Windows 11        | Host operating system.                                                     |

## ⚙️ 5. Implementation & Configuration

### Step 1: Kali Linux Installation

The first step was setting up Kali Linux as a virtual machine using Oracle VirtualBox.

Activities performed:

- Created a new virtual machine.
- Selected the Kali Linux operating system.
- Allocated 4 GB of RAM.
- Configured virtual machine settings.
- Started the virtual machine.
- Successfully accessed the Kali Linux desktop environment.

**Outcome:** Kali Linux was successfully installed and running inside VirtualBox.

### Step 2: NAT Network Configuration

A custom NAT Network was created in Oracle VirtualBox to provide network connectivity to the Kali Linux virtual machine.

Activities performed:

- Opened VirtualBox Network Manager.
- Created a new NAT Network.
- Configured the network prefix.
- Enabled DHCP support.
- Verified NAT Network configuration.
- Checked the virtual network settings.

**Outcome:** A functional NAT Network was configured for the virtual machine.

### Step 3: Static IP Address Configuration

A static IP address was assigned to the Kali Linux virtual machine using NetworkManager.

The `nmcli` command-line utility was used to configure network settings.

**Commands used:**

```bash
sudo nmcli connection modify "Wired connection 1" ipv4.method manual ipv4.addresses <STATIC_IP>/24 ipv4.gateway <GATEWAY_IP>

sudo nmcli connection modify "Wired connection 1" ipv4.dns "8.8.8.8 1.1.1.1"

sudo nmcli connection down "Wired connection 1"

sudo nmcli connection up "Wired connection 1"
```

**Configuration activities:**

- Configured IPv4 manual addressing.
- Assigned a static IP address.
- Configured the default gateway.
- Added DNS server addresses.
- Restarted the network connection.

**Outcome:** Static IP and network settings were successfully configured.

### Step 4: Network Connectivity Verification

After configuring the network, connectivity tests were performed to verify communication between Kali Linux and external networks.

**1. Gateway Connectivity**

```bash
ping -c 4 <GATEWAY_IP>
```

Verified communication between the Kali Linux virtual machine and its virtual network gateway.

**2. Internet Connectivity**

```bash
ping -c 4 8.8.8.8
```

Tested connectivity using an external IP address.

**3. DNS Resolution**

```bash
ping -c 4 google.com
```

Verified whether domain names could be resolved successfully.

**Test Results:**

| Test                     | Result            |
| ------------------------ | ----------------- |
| Gateway Connectivity     | Successful        |
| External IP Connectivity | Successful        |
| DNS Resolution           | Successful        |
| Packet Loss              | 0% during testing |

**Outcome:** Network connectivity and DNS resolution were successfully verified.

### Step 5: Nmap Installation & Verification

Nmap is a network discovery and security auditing tool commonly used in cybersecurity.

It helps identify hosts, discover open ports, and obtain service information during authorized security assessments.

The installation was verified using:

```bash
nmap --version
```

**Verified Version:** Nmap 7.95

**Outcome:** Nmap was available and successfully verified in the Kali Linux environment.

### Step 6: VirtualBox Shared Folder Configuration

A shared folder was configured to enable file exchange between the Windows host machine and Kali Linux guest operating system.

**Configuration activities:**

- Created a shared folder in Windows.
- Added the folder through VirtualBox Shared Folders settings.
- Configured the shared folder mount location.
- Added the Kali Linux user to the `vboxsf` group.
- Restarted the virtual machine.
- Verified folder accessibility.

**Mount Location:**

```bash
/media/sf_Kali_Shared
```

**Verification command:**

```bash
cd /media/sf_Kali_Shared
ls -la
```

**Outcome:** The shared folder was successfully mounted and accessible from Kali Linux.

### Step 7: Virtual Machine Snapshot Creation

A baseline snapshot was created to preserve the configured state of the Kali Linux virtual machine.

**Snapshot Name:**

```text
Kali_Cybersecurity_Lab_Baseline
```

**Purpose of the snapshot:**

- Preserve the initial lab configuration.
- Provide a recovery point.
- Help restore the virtual machine to a previous state.
- Support safe experimentation in future lab activities.

**Outcome:** A baseline snapshot was successfully created.

---

## 🌐 6. Network Configuration Overview

The lab uses a VirtualBox NAT Network to provide connectivity to the Kali Linux virtual machine.

The network configuration includes:

- NAT Network configuration.
- DHCP service configuration.
- Static IPv4 addressing.
- Default gateway configuration.
- DNS server configuration.
- Connectivity verification.

Sensitive network values have intentionally been excluded from this public repository.

## 🧪 7. Verification & Testing Summary

The following checks were completed to validate the lab environment.

| No. | Verification Activity       | Status     |
| --- | --------------------------- | ---------- |
| 1   | Kali Linux VM Setup         | Completed  |
| 2   | NAT Network Configuration   | Completed  |
| 3   | Static IP Configuration     | Completed  |
| 4   | Gateway Connectivity        | Successful |
| 5   | Internet Connectivity       | Successful |
| 6   | DNS Resolution              | Successful |
| 7   | Nmap Version Verification   | Successful |
| 8   | Shared Folder Configuration | Completed  |
| 9   | Baseline Snapshot Creation  | Completed  |

## 📸 8. Project Screenshots

Screenshots will be added to demonstrate the practical implementation and configuration of the lab.

Suggested evidence:

1. Kali Linux desktop environment.
2. VirtualBox virtual machine configuration.
3. NAT Network configuration.
4. Network connectivity verification.
5. Nmap version verification.
6. Shared folder accessibility.
7. Baseline snapshot in VirtualBox.

## 📚 9. Key Learning Outcomes

This hands-on task helped strengthen my understanding of:

**Linux Administration**

- Working with the Kali Linux environment.
- Managing network connections through terminal commands.
- Understanding Linux directory structures.

**Networking Fundamentals**

- Understanding NAT Network configuration.
- Static IP addressing.
- Default gateways and DNS servers.
- Network connectivity troubleshooting.

**Cybersecurity Tools**

- Understanding the purpose of Nmap.
- Installing and verifying cybersecurity tools.
- Exploring the Kali Linux security environment.

**Virtualization**

- Creating and configuring virtual machines.
- Sharing files between host and guest systems.
- Creating snapshots for recovery.

## 🚀 10. Future Scope

This lab environment can be extended through additional cybersecurity practical exercises.

Planned areas of exploration:

- Network reconnaissance using Nmap.
- Port scanning and service enumeration.
- Network traffic analysis using Wireshark.
- Vulnerability assessment in authorized lab environments.
- Linux security configuration.
- Basic penetration testing methodologies.
- Hands-on Capture The Flag (CTF) exercises.

## 🔒 11. Security & Responsible Usage

This project is developed strictly for educational and cybersecurity learning purposes.

All future scanning, reconnaissance, and vulnerability assessment activities will be conducted only within authorized lab environments or against systems for which explicit permission has been granted.

Sensitive IP addresses, personal information, and private system paths are intentionally excluded from this public documentation.

## 🙏 12. Internship Acknowledgement

This project was completed as part of my **Cybersecurity Internship at NetworkWalks**.

I sincerely appreciate the opportunity to gain hands-on experience and strengthen my practical understanding of Linux, networking, virtualization, and cybersecurity tools.

This task represents an important step in my continuous learning journey in cybersecurity.

---

## 📌 Project Status

**Initial Kali Linux Cybersecurity Lab Configuration: Completed**

**Domain:** Cybersecurity & Network Security

**Internship:** NetworkWalks



### 🔐 Learn • Configure • Practice • Secure

**Building practical cybersecurity skills through continuous learning and hands-on experience.**


