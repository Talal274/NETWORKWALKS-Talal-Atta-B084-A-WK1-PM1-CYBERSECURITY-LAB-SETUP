# 🔐 Cybersecurity Lab Environment Setup

<p align="center">
  <strong>Creating an Isolated Virtual Environment for Ethical Hacking and Penetration Testing</strong>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Skill-Cybersecurity-404040?style=flat-square&labelColor=C00000" />
  <img src="https://img.shields.io/badge/Ver-Virtualbox%20v7.2.6-0070C0?style=flat-square&labelColor=000000" />
  <img src="https://img.shields.io/badge/Kali%20Linux-Attacker_Machine-E87500?style=flat-square&labelColor=000000&logo=kalilinux&logoColor=white" />
  <img src="https://img.shields.io/badge/Skill-Linux-404040?style=flat-square&labelColor=C00000" />
  <img src="https://img.shields.io/badge/Network-10.0.0.0%2F24-238F89?style=flat-square&labelColor=000000" />
  <img src="https://img.shields.io/badge/Penetration%20Testing-C00000?style=flat-square&labelColor=000000&logo=kalilinux&logoColor=white" />
  <img src="https://img.shields.io/badge/Skill-Virtualization-404040?style=flat-square&labelColor=C00000" />
</p>

## 📌 Project Overview

This project demonstrates how to build a virtual cybersecurity lab using VirtualBox and Kali Linux.

The goal is to create a safe and controlled environment where security tools and penetration-testing techniques can be practised without directly affecting external systems. The lab supports activities such as network discovery, vulnerability testing, and security analysis.

A private NAT Network is configured to allow virtual machines to communicate with each other while providing internet connectivity. This setup also makes it easier to add vulnerable target machines for future cybersecurity experiments.

## 🎯 Objectives

The key objectives of this project are:

- Install and configure VirtualBox as the virtualization platform.
- Import Kali Linux and prepare it for security testing.
- Set up a private **NAT Network** using the `10.0.0.0/24` subnet.
- Assign a static IP address to Kali Linux for consistent network identification.
- Configure clipboard sharing, drag-and-drop, and shared folders.
- Identify and fix network connectivity and DNS resolution problems.
- Create a baseline snapshot to restore the virtual machine when needed.

## 🛡️ Purpose of the Lab

This virtual lab is designed for learning cybersecurity concepts and practising ethical hacking in a controlled environment.

It provides hands-on experience with:

- Network discovery and mapping
- Vulnerability scanning and analysis
- Packet inspection and traffic monitoring
- Exploitation techniques in an authorized lab
- Practical use of open-source security tools

⚠️ **Important:** Use this environment only for authorized security testing. Never test tools or techniques against systems or networks without permission.

## ⚙️ Lab Configuration

| 🧩 Component | ⚙️ Configuration |
|---|---|
| 🖥️ Host OS | Windows 10 Pro |
| 🧠 Host RAM | 8 GB |
| ⚡ Processor | Intel Core i5 |
| 🧰 Hypervisor | VirtualBox 7.2.6 |
| 🐉 Security OS | Kali Linux 2025.3 |
| 🌐 Virtual Network | NAT Network |
| 📡 Network Address | 10.0.0.0/24 |
| 🐧 Kali IP Address | 10.0.0.2/24 |
| 🌍 Connectivity | Internet access through NAT Network |

## 🪜 Lab Setup Procedure

### Step 1. Install 7-Zip

First, 7-Zip was installed on the Windows host system. This utility is used to extract compressed files, including virtual machine packages downloaded from the internet.

<img width="833" height="920" alt="1 - 7-zip Install" src="https://github.com/user-attachments/assets/24e19c35-7a7b-4bde-a710-cb12edfa853f" />

### Step 2. Install VirtualBox

VirtualBox version 7.2.6 was downloaded and installed. It provides the platform required to create, configure, and run virtual machines on the host computer.

<img width="1097" height="790" alt="2 - Installed and set up VirtualBox" src="https://github.com/user-attachments/assets/3e53ed22-182f-45b6-b94e-92c187ae6652" />

### Step 3. Create the NAT Network

A separate NAT Network was configured in VirtualBox to provide communication between virtual machines on the same private subnet while allowing them to access the internet.

**Network Configuration:**

- **Network Name:** `NatNetwork`
- **IPv4 Prefix:** `10.0.0.0/24`
- **DHCP:** Enabled
- **IPv6:** Disabled

This network will be used as the communication layer for Kali Linux and any additional lab machines.

<img width="1097" height="790" alt="3 - VB NAT Network Configuration" src="https://github.com/user-attachments/assets/0799d525-cbea-4505-b110-5f15ce0f5daf" />

### Step 4. Import and Configure Kali Linux

A pre-built Kali Linux virtual machine was downloaded from the official Kali Linux website and imported into VirtualBox. Kali Linux serves as the primary machine for performing security tests in this lab.

The following settings were configured:

1. **Network Adapter:** Connected the VM to `NatNetwork` so that it could use the `10.0.0.0/24` subnet.
2. **Clipboard and Drag-and-Drop:** Enabled bidirectional clipboard sharing and file transfer between the host and virtual machine.
3. **Shared Folders:** Configured a shared folder connected to the host's Downloads directory for convenient file exchange.

<img width="1097" height="790" alt="4 - Imported Kali Linux" src="https://github.com/user-attachments/assets/14db6bf5-df0b-42d9-ae6a-40d9fed1efe4" />

<img width="781" height="518" alt="4a - Updated Kali Linux NAT Setup" src="https://github.com/user-attachments/assets/2ec77785-50b1-469f-bb2e-148224bf2098" />

### Step 5. Configure the Kali Linux Network

A static IPv4 address was assigned to Kali Linux to make its address predictable for future lab activities. The network settings were configured as follows:

**Static IP Configuration:**

- **IP Address:** `10.0.0.2`
- **Subnet Mask:** `255.255.255.0 (/24)`
- **Gateway:** `10.0.0.1`
- **DNS Server:** `8.8.8.8`

<img width="1380" height="864" alt="5 - Kali Linux IP Configuration Setup" src="https://github.com/user-attachments/assets/1d61cbc3-e300-4c71-bf62-628787ec9c8f" />

After applying the settings, the network configuration was checked in the Kali Linux terminal using the `ifconfig` command to verify the assigned IP address.

<img width="1380" height="864" alt="5a - Checking IP Configuration" src="https://github.com/user-attachments/assets/37d9d2de-f822-4675-a9be-dbae75afdf3f" />

### Step 6. Create a Clean VM Snapshot

After completing the installation and network configuration, a snapshot of the working virtual machine was saved in VirtualBox.

This snapshot provides a recovery point. If later experiments cause configuration errors or system problems, the virtual machine can be returned to its saved state without repeating the entire setup process.

<img width="1920" height="1032" alt="6 - Snapshot Set Up" src="https://github.com/user-attachments/assets/f4556314-c3ca-4c6e-a925-28ec0787a8f2" />

## 🐞 Problems Encountered & Solutions

### Network Connection Hanging After Static IP Configuration

**Issue:**

After assigning the static IP address `10.0.0.2`, Kali Linux experienced network connectivity problems. Although the gateway and DNS settings had been entered, the system could not establish a working outbound connection.

**Solution:**

The issue was investigated as a possible Duplicate Address Detection (DAD) timeout involving NetworkManager. The following command was used to change the DAD timeout setting for the wired connection:

```bash
sudo nmcli connection modify "Wired connection 1" ipv4.dad-timeout 0
```

This changes the DAD timeout setting for that connection. Network connectivity should then be tested again to confirm whether the problem has been resolved.

## 💡 What I Learned

### 1. Understanding NAT Networks

I learned how a NAT Network allows virtual machines on the same private subnet to communicate with one another while accessing external networks through NAT. This provides a useful foundation for building a multi-machine cybersecurity lab.

### 2. Configuring Static IP Addresses in Linux

I gained practical experience configuring network settings in Kali Linux using the graphical interface and terminal tools such as `nmcli` and `ifconfig`. Assigning a static IP helps keep the lab's network configuration consistent.

### 3. Improving the Virtual Machine Workflow

I learned how to configure clipboard sharing, drag-and-drop, and shared folders to make transferring files between Windows and Kali Linux easier.

### 4. Using Virtual Machine Snapshots

Creating a snapshot taught me the importance of saving a known working state before performing security experiments. It provides a convenient way to recover from mistakes and restore the original configuration.

## 🔗 Tools & Resources

- **7-Zip:** [https://7-zip.org/download.html](https://7-zip.org/download.html)
- **VirtualBox:** [https://virtualbox.org/wiki/Downloads](https://virtualbox.org/wiki/Downloads)
- **Kali Linux:** [https://kali.org/get-kali](https://kali.org/get-kali)
- **OBS Studio:** [https://obsproject.com/](https://obsproject.com/)

## 👤 Author

**Talal Atta**  
Cybersecurity Student

LinkedIn: [https://www.linkedin.com/in/talal-atta-352369335/](https://www.linkedin.com/in/talal-atta-352369335/)  
GitHub: [https://github.com/Talal274](https://github.com/Talal274)

<br>

<div align="center">
  <a href="https://www.linkedin.com/in/talal-atta-352369335/">
    <img src="https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn" />
  </a>
  <a href="https://github.com/Talal274">
    <img src="https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white" alt="GitHub" />
  </a>
</div>

## 📌 Project Information

**Program:** Cybersecurity  
**Project:** Cybersecurity & Penetration Testing Lab Setup


