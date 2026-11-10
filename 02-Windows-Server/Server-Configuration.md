# Windows Server 2019 Configuration

## Overview

After installing Windows Server 2019 on the Acer Aspire ES 14, I started configuring the server for my homelab.

The main goal of this stage was to prepare the server before installing and configuring Active Directory Domain Services, DNS, DHCP, Group Policy, Backup, and Print Management.

---

## Server Information

These are the main settings I used for the server:

| Setting | Configuration |
|---|---|
| Computer Name | `HomelabServer` |
| Operating System | Windows Server 2019 |
| IP Address | `12.10.0.25` |
| Default Gateway | `12.10.0.20` |
| Preferred DNS | `12.10.0.25` |
| Connection | Ethernet |

---

## 1. Server Name

I changed the computer name to:

```text
HomelabServer
```

I used this name because the laptop is being used as the main server for my homelab.

The computer name can be changed through:

```text
Server Manager
→ Local Server
→ Computer Name
→ Change
```

After changing the computer name, I restarted the server.

I then verified the hostname using Command Prompt:

```cmd
hostname
```

The result was:

```text
HomelabServer
```

---

## 2. Static IP Address

I configured a static IP address for the server.

The configuration I used was:

```text
IP Address:      12.10.0.25
Default Gateway: 12.10.0.20
DNS Server:      12.10.0.25
```

I used a static IP because the server will be providing services to other devices in the network.

These services include:

- DNS
- DHCP
- Active Directory
- Group Policy
- File/Print services
- Backup

Having a consistent IP address makes it easier for clients and other services to locate the server.

---

## 3. Configuring the Network Adapter

I opened:

```text
Control Panel
→ Network and Internet
→ Network and Sharing Center
→ Change adapter settings
```

I right-clicked the Ethernet adapter and selected:

```text
Properties
→ Internet Protocol Version 4 (TCP/IPv4)
→ Properties
```

I then entered my static network configuration.

```text
IP address:
12.10.0.25

Default gateway:
12.10.0.20

Preferred DNS server:
12.10.0.25
```

---

## 4. Verify IP Configuration

After configuring the network adapter, I used Command Prompt to verify the settings.

```cmd
ipconfig /all
```

I checked that the server showed:

```text
IPv4 Address: 12.10.0.25
Default Gateway: 12.10.0.20
DNS Server: 12.10.0.25
```

---

## 5. Test Network Connectivity

I tested connectivity to the gateway using:

```cmd
ping 12.10.0.20
```

I also tested the server's own IP address:

```cmd
ping 12.10.0.25
```

These tests helped confirm that the network adapter and basic TCP/IP configuration were working.

---

## 6. Check Windows Server Information

I also checked the Windows Server version and system information.

Using Command Prompt:

```cmd
systeminfo
```


This allowed me to verify that the system was running Windows Server 2019 and confirm the basic hardware and operating system information.

---

## 7. Windows Updates

Before continuing with the server roles, I checked for available Windows updates.

I installed the available updates and restarted the server when required.

Keeping the server updated is important before deploying additional services.

---

## 8. Server Manager

I used **Server Manager** as the main graphical administration tool for installing and managing server roles.

Some of the tools I used during this project include:

- Server Manager
- Active Directory Users and Computers
- DNS Manager
- DHCP Manager
- Group Policy Management
- Windows Server Backup
- Print Management
- Event Viewer
- Computer Management
- PowerShell

---

## 9. Basic PowerShell Checks

I also started using PowerShell to check the server configuration.

### Check computer name

```powershell
hostname
```

---

## 10. Preparation for Active Directory

After completing the basic server configuration, I prepared the server for Active Directory Domain Services.

Before installing AD DS, I verified:

- Server name was configured as `HomelabServer`
- Static IP address was configured
- Ethernet connectivity was working
- Default gateway was reachable
- DNS configuration was set
- Windows Server was updated
- System date and time were correct

The server was now ready for the next stage of the project.

---

## Result

The Acer Aspire ES 14 was successfully configured as my Windows Server 2019 homelab server.

The final basic configuration was:

```text
Computer Name : HomelabServer
IP Address    : 12.10.0.25
Gateway       : 12.10.0.20
DNS           : 12.10.0.25
```

With the basic server configuration completed, I continued with the installation and configuration of **Active Directory Domain Services (AD DS)**.
