# Week 03: Enterprise Server Deployment and Operating System Installation

## Project Overview

This project, completed as part of ITEP 414 - System Administration and Maintenance, simulates the real-world task of deploying a new enterprise server. Taking on the role of a Junior System Administrator at a startup, I installed and configured an Ubuntu Server virtual machine. The objective was to not only set up the server but to also verify its functionality, document the entire process, and create professional resources like a deployment guide and an OS comparison report. This project serves as a foundational artifact in my Systems Administration portfolio, demonstrating my ability to manage and maintain core IT infrastructure.

## Learning Objectives

This project was designed to achieve the following learning outcomes:

**Knowledge:**
- Explain the purpose and function of an operating system in enterprise environments.
- Differentiate between BIOS and UEFI firmware and their respective boot processes.
- Describe the stages of the computer boot process from power-on to login.
- Compare and contrast Ubuntu Server, Windows Server, and Rocky Linux for enterprise use.

**Skills:**
- Install Ubuntu Server in a virtualized environment using Oracle VirtualBox.
- Configure essential server settings, including network, hostname, and user accounts.
- Enable and verify secure remote administration using SSH.
- Execute fundamental server verification and update commands.
- Produce professional technical documentation, including installation guides and reports.

**Professional Outcomes:**
- Successfully installed and configured a working Linux server.
- Compiled a comprehensive deployment guide for future administrators.
- Updated my professional GitHub portfolio with a detailed project.
- Published a learning reflection on LinkedIn to share my experience and insights.

## Virtual Machine Specifications

The Ubuntu Server was installed on a virtual machine with the following minimum specifications:

| Component | Specification |
| :--- | :--- |
| **Name** | Ubuntu-Server-Week03 |
| **RAM** | 4 GB |
| **CPU** | 2 Virtual Processors |
| **Storage** | 40 GB (VDI) |
| **Network** | NAT |
| **Optical Drive** | Ubuntu Server 24.04 LTS ISO |

## Installation Summary

The installation of Ubuntu Server was performed by following the guided setup wizard and configuring the following key settings:

- **Language:** English
- **Keyboard Layout:** English (US)
- **Network Configuration:** DHCP was accepted, and the assigned IP address was recorded.
- **Hostname:** `server01`
- **User Account:** A non-root administrative user was created with a strong password.
- **Disk Partition:** The "Use Entire Disk" guided option was selected, using an ext4 file system.
- **SSH Server:** The OpenSSH server was enabled during installation.
- **Additional Packages:** No additional packages were installed at this stage.

The installation completed successfully, and the virtual machine was restarted.

## Configuration Summary

After the initial installation, the server was further configured and verified through the following tasks:

1.  **Login Verification:** Successfully logged in using the created user account.
2.  **Hostname Verification:** Confirmed the hostname was correctly set to `server01` using the `hostname` command.
3.  **IP Address Verification:** Retrieved and confirmed the system's IP address using the `ip addr` command.
4.  **Internet Connectivity Verification:** Successfully pinged `google.com` to ensure network connectivity.
5.  **System Update:** The system was updated using `sudo apt update` and `sudo apt upgrade -y`.
6.  **SSH Service Verification:** Verified the SSH service was active and running using `systemctl status ssh`.

## Verification Results

All verification tasks were executed successfully, confirming the Ubuntu Server is installed, configured, and ready for its intended enterprise role.

*(Note: Screenshots of the verification process are included in the full installation manual.)*

## BIOS vs. UEFI Highlights

A key part of this project was researching and comparing the legacy BIOS (Basic Input/Output System) and the modern UEFI (Unified Extensible Firmware Interface). My key findings are:

- **UEFI** is the modern standard, designed to succeed BIOS. It offers a more secure, faster, and feature-rich boot environment.
- **BIOS** is legacy firmware that initializes hardware and performs the Power-On Self-Test (POST) before the boot loader takes over, using the Master Boot Record (MBR) partition style which is limited to 2TB disks.
- **UEFI** operates in either 32-bit or 64-bit mode, uses the GUID Partition Table (GPT), and offers a more comprehensive pre-boot environment. It includes features like Secure Boot, which prevents malicious software from loading during startup, and the Fast Boot option for quicker system startup.
- **Modern Usage:** UEFI has largely replaced BIOS in modern computers due to its enhanced security, speed, and support for larger storage devices, making it essential for today's enterprise servers and PCs.

*(A detailed comparison table is available in the full installation manual.)*

## Embedded Boot Process Flowchart

The following flowchart illustrates the detailed boot process for a Linux-based system like Ubuntu Server.

[![Ubuntu Server Boot Process Flowchart](images/week03/boot-process-flowchart.png)](images/week03/boot-process-flowchart.png)

## Challenges Encountered

During the project, a few challenges were encountered:

1.  **Network Connectivity:** Initially, the virtual machine's network was set to Bridged, which caused IP conflicts on the home network. This was resolved by switching the network adapter to NAT mode, allowing the VM to access the internet without addressing conflicts.
2.  **Disk Space:** The initial disk size was set to 20 GB. During the package update (`sudo apt upgrade`), the disk became full. The VM was re-created with a 40 GB disk to resolve the issue.
3.  **SSH Access:** A brief issue occurred when trying to SSH into the VM from the host. This was resolved by ensuring the SSH service was running and checking the host's firewall settings.

## Reflection

This project provided an invaluable, hands-on introduction to the critical role of a System Administrator. Moving from a purely theoretical understanding of Linux to physically installing, configuring, and securing a server was an immensely rewarding learning experience. I was able to apply concepts learned in lectures, such as the boot process and firmware differences, to a practical scenario, which has significantly solidified my understanding of these foundational topics.

I was particularly challenged by the need to troubleshoot issues like network configuration and disk space management, as these are real-world problems that system admins face daily. Overcoming these challenges not only improved my technical skills but also reinforced the importance of patience and methodical problem-solving. Creating the deployment guide also highlighted the importance of documentation; clear and concise documentation is often the unsung hero of a well-run IT department. This project has given me a solid foundation and confidence to tackle more complex administrative tasks in the future.

## References

- Ubuntu Server Documentation. (n.d.). Retrieved from https://ubuntu.com/server/docs

