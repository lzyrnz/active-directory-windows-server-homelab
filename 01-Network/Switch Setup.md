# Network Switch Setup

## Overview

I used a second-hand **TP-Link 5-port 100 Mbps network switch** that I had purchased a few months earlier.

Although the switch is limited to 100 Mbps, it is sufficient for this homelab because the main purpose is to practice networking and Windows Server administration.

---

## Switch

```text
Manufacturer: TP-Link
Ports: 5
Speed: 100 Mbps
Type: Ethernet Switch
```

### Switch Setup


![TP-Link Switch Setup](switch-setup.jpg)

---

## Connections

The switch was used to connect:

- Windows Server 2019
- Windows client
- Other network devices

The server and client devices were connected using the Ethernet cables that I terminated myself.

---

## Result

The switch provided the physical network connectivity required for the Windows Server 2019 homelab.

---

# `02-windows-server/server-installation.md`

# Windows Server 2019 Installation

## Overview

For this project, I used an old **Acer Aspire ES 14** laptop from my cousin and repurposed it as my Windows Server 2019 machine.

Instead of running Windows Server inside a virtual machine, I installed it directly on the laptop.

I also configured the laptop as a **dual-boot system**, allowing me to keep the existing Windows installation while having Windows Server 2019 available for the homelab.

---

## Hardware

| Component | Details |
|---|---|
| Device | Acer Aspire ES 14 |
| Server OS | Windows Server 2019 |
| Installation | Physical/Bare Metal |
| Boot Configuration | Dual Boot |
| Network | Ethernet |

---

## Installation Media

I used **Rufus** to create the bootable Windows Server 2019 USB installer.

The general process was:

1. Prepared a USB flash drive.
2. Opened Rufus.
3. Selected the Windows Server 2019 ISO.
4. Selected the USB device.
5. Configured the appropriate boot options.
6. Started the USB creation process.
7. Waited for Rufus to finish.
8. Used the USB to boot the Acer Aspire ES 14.

### Rufus

> **Mock image — replace with my actual screenshot.**

```text
![Rufus Windows Server USB](../images/rufus-server-usb.png)
```

---

## Dual-Boot Setup

I prepared disk space for Windows Server 2019 while keeping the existing Windows installation.

The final configuration allowed the laptop to boot into either operating system.

```text
Acer Aspire ES 14
│
├── Existing Windows
│
└── Windows Server 2019
```

### Disk Partition

> **Mock image — replace with my actual screenshot.**

```text
![Disk Partition](../images/disk-partition.png)
```

---

## Windows Server Installation

I booted the laptop from the Windows Server 2019 USB created using Rufus.

The installation process included:

1. Booting from the USB.
2. Selecting language and regional settings.
3. Selecting Windows Server 2019.
4. Accepting the license terms.
5. Selecting Custom Installation.
6. Selecting the partition prepared for Windows Server.
7. Starting the installation.
8. Waiting for the installation to finish.
9. Creating the Administrator password.
10. Logging into Windows Server.

---

## Server Name

After installation, I changed the computer name to:

```text
HomelabServer
```

I used this name because the Acer Aspire ES 14 is being used as the main server for my homelab.

---

## Result

Windows Server 2019 was successfully installed on the Acer Aspire ES 14 and configured as a dual-boot system.

The server was ready for the initial Windows Server configuration.

---

# `02-windows-server/server-configuration.md`

# Windows Server 2019 Configuration

## Overview

After installing Windows Server 2019, I performed the initial configuration before installing the server roles.

This included configuring the computer name, static IP address, subnet mask, gateway, DNS, Windows services, firewall settings, network discovery, and file sharing.

---

## Server Information

| Setting | Value |
|---|---|
| Computer Name | `HomelabServer` |
| Operating System | Windows Server 2019 |
| IP Address | `12.10.0.25` |
| Subnet Mask | `255.255.255.0` |
| Default Gateway | `12.10.0.20` |
| DNS Server | `12.10.0.25` |
| Connection | Ethernet |

---

# 1. Computer Name

I changed the computer name to:

```text
HomelabServer
```

I configured this through:

```text
Server Manager
→ Local Server
→ Computer Name
→ Change
```

After changing the computer name, I restarted the server.

I verified the name using:

```cmd
hostname
```

Expected result:

```text
HomelabServer
```

### Computer Name

> **Mock image — replace with my actual screenshot.**

```text
![Computer Name](../images/server-computer-name.png)
```

---

# 2. Static IP Configuration

I configured the server with a static IPv4 address.

```text
IP Address      : 12.10.0.25
Subnet Mask     : 255.255.255.0
Default Gateway : 12.10.0.20
DNS Server      : 12.10.0.25
```

I configured this through:

```text
Control Panel
→ Network and Internet
→ Network and Sharing Center
→ Change Adapter Settings
→ Ethernet
→ Properties
→ Internet Protocol Version 4 (TCP/IPv4)
```

### IPv4 Configuration

> **Mock image — replace with my actual screenshot.**

```text
![IPv4 Configuration](../images/ipv4-configuration.png)
```

---

# 3. Verify IP Configuration

After configuring the static IP, I used:

```cmd
ipconfig /all
```

I checked that the server displayed the correct:

- IPv4 address
- Subnet mask
- Default gateway
- DNS server

### IP Configuration

> **Mock image — replace with my actual screenshot.**

```text
![IP Configuration](../images/ipconfig-all.png)
```

---

# 4. Test Network Connectivity

I tested the gateway:

```cmd
ping 12.10.0.20
```

I also tested the server's own address:

```cmd
ping 12.10.0.25
```

These tests helped verify that the network adapter and TCP/IP configuration were working.

---

# 5. Windows Updates

I checked for Windows Server updates before continuing with the server roles.

I installed the available updates and restarted the server when necessary.

---

# 6. Services.msc

I also checked the Windows services using:

```text
services.msc
```

I reviewed the services related to network discovery and device discovery.

The services I configured/checked included:

- Function Discovery Provider Host
- Function Discovery Resource Publication
- SSDP Discovery
- UPnP Device Host

These services can help with network discovery and visibility of devices and shared resources.

### Services

> **Mock image — replace with my actual screenshot.**

```text
![Windows Services](../images/services-network-discovery.png)
```

---

# 7. Function Discovery Services

I checked the following services:

### Function Discovery Provider Host

This service supports the discovery of network devices and resources.

### Function Discovery Resource Publication

This service publishes the computer and its resources so they can be discovered by other computers on the network.

I checked their startup configuration and made sure they were running as required for my lab.

---

# 8. SSDP Discovery

I checked the **SSDP Discovery** service.

SSDP is used to discover network devices that use the Simple Service Discovery Protocol.

I enabled/configured the service as required for my network discovery testing.

---

# 9. UPnP Device Host

I also checked the **UPnP Device Host** service.

This service allows the computer to host UPnP devices.

I reviewed the service configuration as part of my network discovery setup.

---

# 10. Windows Firewall

I checked the Windows Firewall configuration through:

```text
Control Panel
→ System and Security
→ Windows Defender Firewall
```

I also used:

```text
firewall.cpl
```

to quickly access the Windows Firewall configuration.

### Windows Firewall

> **Mock image — replace with my actual screenshot.**

```text
![Windows Firewall](../images/windows-firewall.png)
```

I verified that the required network functionality was allowed through the firewall.

---

# 11. Advanced Sharing Settings

I configured Windows network sharing through:

```text
Control Panel
→ Network and Sharing Center
→ Change advanced sharing settings
```

I reviewed the settings for:

- Network discovery
- File and printer sharing
- Public folder sharing
- Password protected sharing

I enabled the required settings for my lab so that Windows clients could discover the server and access shared resources.

### Advanced Sharing

> **Mock image — replace with my actual screenshot.**

```text
![Advanced Sharing Settings](../images/advanced-sharing-settings.png)
```

---

# 12. Peer-to-Peer File Sharing

I tested basic Windows peer-to-peer file sharing between devices on the local network.

The purpose was to verify that the server and client could discover each other and communicate over the network before deploying the domain environment.

I checked:

```text
Network Discovery
File and Printer Sharing
Windows Firewall Rules
Network Connectivity
```

---

# 13. PowerShell Network Checks

I also used PowerShell to inspect the network configuration.

### Network configuration

```powershell
Get-NetIPConfiguration
```

### Network adapters

```powershell
Get-NetAdapter
```

### Computer name

```powershell
hostname
```

### Windows information

```powershell
Get-ComputerInfo | Select-Object WindowsProductName, WindowsVersion, OsBuildNumber
```

---

# 14. Final Configuration

At the end of the initial server configuration, my server was configured as:

```text
Computer Name : HomelabServer
IP Address    : 12.10.0.25
Subnet Mask   : 255.255.255.0
Gateway       : 12.10.0.20
DNS           : 12.10.0.25
```

Network discovery and file/printer sharing were also configured for the lab environment.

---

# Result

The basic Windows Server 2019 configuration was completed successfully.

The server was ready for the next stage of the project:

- Active Directory Domain Services
- DNS
- DHCP
- Group Policy
- Backup
- Print Management

---

# `03-active-directory/domain-setup.md`

# Active Directory Domain Services Setup

## Overview

After completing the initial Windows Server configuration, I installed **Active Directory Domain Services (AD DS)**.

The goal was to create a domain environment where users and computers could be centrally managed.

---

## Server

```text
Server Name : HomelabServer
IP Address  : 12.10.0.25
```

---

## Installing AD DS

I opened:

```text
Server Manager
→ Add Roles and Features
```

I selected:

```text
Active Directory Domain Services
```

I installed the required features and completed the installation.

### AD DS Installation

> **Mock image — replace with my actual screenshot.**

```text
![AD DS Installation](../images/ad-ds-installation.png)
```

---

## Promoting the Server

After installing AD DS, I promoted the server to a Domain Controller.

I selected:

```text
Add a new forest
```

and configured my domain.

```text
Domain Name: <MY-DOMAIN>
```

> Replace `<MY-DOMAIN>` with the actual domain name used in my lab.

I then configured the Directory Services Restore Mode password and completed the domain controller installation.

---

## Verification

After restarting, I checked that the server was functioning as a domain controller.

I used:

```text
Active Directory Users and Computers
```

and:

```text
DNS Manager
```

to verify the installation.

### Active Directory

> **Mock image — replace with my actual screenshot.**

```text
![Active Directory](../images/ad-domain.png)
```

---

# `03-active-directory/users-and-groups.md`

# Active Directory Users and Groups

## Overview

After creating the domain, I created test users and security groups to practice centralized account management.

---

## Users

I created several test accounts for the lab.

Example:

```text
User 1
User 2
User 3
IT Admin
HR User
Sales User
```

I used test accounts rather than personal accounts.

### AD Users

> **Mock image — replace with my actual screenshot.**

```text
![Active Directory Users](../images/ad-users.png)
```

---

## Security Groups

I also created security groups to organize users and control access.

Example:

```text
GG-IT-Users
GG-IT-Admins
GG-HR-Users
GG-Sales-Users
```

The `GG` naming convention represents a Global Group.

---

## Group Membership

Users were added to the appropriate security groups.

For example:

```text
IT User
   │
   └── GG-IT-Users

IT Administrator
   │
   └── GG-IT-Admins
```

This allowed me to practice managing permissions through groups instead of assigning permissions individually to each user.

---

# `03-active-directory/organizational-units.md`

# Organizational Units

## Overview

I created Organizational Units (OUs) to organize users and computers in Active Directory.

This is important because Group Policy can be applied to specific OUs.

---

## OU Structure

Example structure:

```text
Domain
│
├── Users
│
├── IT
│
├── HR
│
├── Sales
│
└── Computers
```

### Organizational Units

> **Mock image — replace with my actual screenshot.**

```text
![Organizational Units](../images/organizational-units.png)
```

---

## Purpose

I separated users and computers into different OUs so I could later apply different Group Policies to different departments.

For example:

```text
IT
 └── IT Users

HR
 └── HR Users

Sales
 └── Sales Users
```

This gave me a more realistic structure for practicing Windows domain administration.

---

# `04-dns/dns-configuration.md`

# DNS Configuration

## Overview

DNS is an important part of Active Directory because domain clients use DNS to locate domain services.

After installing AD DS, DNS was installed and configured as part of the domain controller setup.

---

## DNS Server

```text
Server: HomelabServer
IP: 12.10.0.25
```

The server uses itself as the DNS server.

---

## DNS Manager

I opened:

```text
Server Manager
→ Tools
→ DNS
```

I checked the forward lookup zone created for the domain.

### DNS Manager

> **Mock image — replace with my actual screenshot.**

```text
![DNS Manager](../images/dns.png)
```

---

## DNS Testing

I used:

```cmd
nslookup
```

I also tested DNS resolution using:

```cmd
nslookup <domain-name>
```

and:

```cmd
ping <domain-name>
```

---

## Result

DNS was successfully configured and working with the Active Directory environment.

---

# `05-dhcp/dhcp-configuration.md`

# DHCP Configuration

## Overview

I configured DHCP on Windows Server 2019 to automatically provide IP configuration to client devices.

---

## DHCP Installation

I installed the DHCP Server role using:

```text
Server Manager
→ Add Roles and Features
→ DHCP Server
```

---

## DHCP Scope

I created a DHCP scope for the lab network.

The exact scope configuration used in my lab is documented below.

```text
Network:
12.10.0.0/24

Server:
12.10.0.25
```

> Add my actual DHCP start and end addresses here.

```text
Start IP:
<START-IP>

End IP:
<END-IP>
```

---

## Scope Options

I configured the required DHCP options for the client network.

These included:

- Default gateway
- DNS server
- Domain name

### DHCP Manager

> **Mock image — replace with my actual screenshot.**

```text
![DHCP Manager](../images/dhcp.png)
```

---

## Testing

On a Windows client, I used:

```cmd
ipconfig /release
```

followed by:

```cmd
ipconfig /renew
```

Then:

```cmd
ipconfig /all
```

I checked that the client received an IP address from the DHCP server.

---

## Result

DHCP successfully provided IP configuration to clients on the lab network.

---

# `06-group-policy/group-policy.md`

# Group Policy

## Overview

I used Group Policy to practice centralized management of Windows users and computers.

Group Policy allows administrators to apply configuration and security settings to users and computers in an Active Directory environment.

---

## Group Policy Management

I opened:

```text
Server Manager
→ Tools
→ Group Policy Management
```

I created and linked Group Policy Objects to the appropriate Organizational Units.

---

## Test GPO

I created a test Group Policy for one of my Organizational Units.

Example:

```text
GPO-HR-Disable-Control-Panel
```

The policy was linked to the appropriate OU.

---

## Control Panel Restriction

I configured:

```text
User Configuration
→ Policies
→ Administrative Templates
→ Control Panel
```

I enabled:

```text
Prohibit access to Control Panel and PC settings
```

---

## Testing the GPO

On the client computer, I ran:

```cmd
gpupdate /force
```

I then logged out and back in.

I verified the applied policies using:

```cmd
gpresult /r
```

For a more detailed report:

```cmd
gpresult /h C:\gpo-report.html
```

### Group Policy

> **Mock image — replace with my actual screenshot.**

```text
![Group Policy Management](../images/group-policy.png)
```

---

## Additional GPO Practice

I plan to continue expanding the Group Policy section with:

- Password policies
- Account lockout policies
- Screen lock policies
- Windows Firewall policies
- Windows Defender policies
- Drive mapping
- Folder permissions
- Login scripts
- Software restrictions
- Removable storage restrictions

---

# `07-backup/backup-and-recovery.md`

# Windows Server Backup

## Overview

I configured Windows Server Backup to practice server backup and recovery.

The purpose was to understand how backups can be used to recover important server data and configurations.

---

## Installing Windows Server Backup

I installed the Windows Server Backup feature through:

```text
Server Manager
→ Add Roles and Features
→ Features
→ Windows Server Backup
```

---

## Backup Configuration

I configured a backup job according to the available storage in my lab.

The backup configuration included the required server data and system components.

### Windows Server Backup

> **Mock image — replace with my actual screenshot.**

```text
![Windows Server Backup](../images/backup.png)
```

---

## Backup Testing

After creating a backup, I verified that the backup completed successfully.

I also explored the available recovery options to understand how the server could be restored after a failure.

---

## Result

Windows Server Backup was successfully configured and tested as part of the homelab.

---

# `08-print-server/print-management.md`

# Print Server and Print Management

## Overview

I configured Print Management on Windows Server 2019 to practice centralized printer administration.

---

## Print Management

I opened:

```text
Server Manager
→ Tools
→ Print Management
```

I used Print Management to manage printers and print queues.

### Print Management

> **Mock image — replace with my actual screenshot.**

```text
![Print Management](../images/print-management.png)
```

---

## Printer Sharing

I practiced configuring a printer as a shared network printer.

The goal was to allow clients on the network to access the printer through the server.

Example:

```text
\\HomelabServer\<PrinterName>
```

---

## Result

I successfully configured and explored Windows Print Management as part of the server administration lab.

---

# `09-troubleshooting/troubleshooting.md`

# Troubleshooting

## Overview

An important part of this homelab was not only configuring the services but also learning how to troubleshoot problems when something did not work.

I used built-in Windows tools and command-line utilities to diagnose network and server issues.

---

# Network Troubleshooting

## `ipconfig`

I used:

```cmd
ipconfig /all
```

to check:

- IP address
- Subnet mask
- Default gateway
- DNS server
- DHCP status

---

## `ping`

I used:

```cmd
ping 12.10.0.20
```

to test connectivity to the gateway.

I also tested:

```cmd
ping 12.10.0.25
```

to verify connectivity to the server.

---

## DNS Troubleshooting

I used:

```cmd
nslookup
```

to test DNS resolution.

I also checked DNS Manager on the server.

---

## DHCP Troubleshooting

On the client, I used:

```cmd
ipconfig /release
```

and:

```cmd
ipconfig /renew
```

Then:

```cmd
ipconfig /all
```

to verify that the client received an IP address.

---

# Group Policy Troubleshooting

I used:

```cmd
gpupdate /force
```

to force the client to refresh its Group Policy.

I used:

```cmd
gpresult /r
```

to determine which policies were applied.

For a detailed report:

```cmd
gpresult /h C:\gpo-report.html
```

---

# Service Troubleshooting

I used:

```text
services.msc
```

to check whether required Windows services were running.

Services I checked included:

- Function Discovery Provider Host
- Function Discovery Resource Publication
- SSDP Discovery
- UPnP Device Host
- DHCP Server
- DNS Server
- Active Directory-related services

---

# Firewall Troubleshooting

I used:

```text
firewall.cpl
```

to check Windows Firewall configuration.

I also reviewed firewall rules when troubleshooting network discovery and file/printer sharing.

---

# File Sharing Troubleshooting

When testing file sharing, I checked:

1. Network connectivity.
2. Network discovery.
3. File and printer sharing.
4. Windows Firewall.
5. Sharing permissions.
6. NTFS permissions.
7. Required Windows services.

---

# Useful Troubleshooting Commands

```cmd
ipconfig /all
```

```cmd
ping <IP-address>
```

```cmd
nslookup <domain>
```

```cmd
tracert <destination>
```

```cmd
arp -a
```

```cmd
gpupdate /force
```

```cmd
gpresult /r
```

---

# Troubleshooting Documentation Template

When I encounter a problem in the lab, I document it using this format:

## Problem

Describe what was not working.

## Symptoms

Describe what I observed.

## Investigation

List the commands, tools, and settings I checked.

## Cause

Explain what caused the problem.

## Solution

Describe how I fixed it.

## Verification

Explain how I confirmed that the problem was resolved.

---

# Lessons Learned

Through this project, I gained practical experience with:

- Physical Ethernet networking
- Ethernet cable termination
- Windows Server installation
- Dual-boot configuration
- Static IP configuration
- DNS
- DHCP
- Active Directory
- Organizational Units
- Users and security groups
- Group Policy
- Windows Firewall
- Network discovery
- File and printer sharing
- Windows Server Backup
- Print Management
- PowerShell
- Network troubleshooting

I also learned that configuring a service is only one part of system administration. Being able to **verify, troubleshoot, and document the configuration** is equally important.
