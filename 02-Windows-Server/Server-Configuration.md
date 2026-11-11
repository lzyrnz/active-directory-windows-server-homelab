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
| Subnet Mask | `255.0.0.0` |
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

or using sysdm.cpl

Expected result:

```text
HomelabServer
```

### Computer Name

<img width="1000" height="800" alt="image" src="https://github.com/user-attachments/assets/b176ff52-9f45-4d7f-9af8-807e84ea422a" />


---

# 2. Static IP Configuration

I configured the server with a static IPv4 address.

```text
IP Address      : 12.10.0.25
Subnet Mask     : 255.0.0.0
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

<img width="800" height="1200" alt="image" src="https://github.com/user-attachments/assets/306dbb06-e984-4a3d-9577-98a94b1a1b89" />

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

<img width="1000height="800" alt="image" src="https://github.com/user-attachments/assets/5dc16048-6907-4f94-9a7d-7d2ef86adaae" />

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

# 13. Final Configuration

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
