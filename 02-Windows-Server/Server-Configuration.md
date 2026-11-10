# Windows Server 2019 Configuration

## Overview

After installing Windows Server 2019, the server was prepared for use as the infrastructure server for the homelab.

The initial configuration included server naming, static IP configuration, network verification, Windows updates, and preparation for Active Directory deployment.

---

# 1. Server Naming

The server was assigned a descriptive hostname.

```text
HomelabServer
```


### Configuration

Open:

```text
Server Manager
→ Local Server
→ Computer Name
```

Select **Computer Name → Change** and enter:

```text
HomelabServer
```

Restart the server after changing the hostname.

---

# 2. Network Configuration

Because this server will provide DNS and DHCP services, it should use a static IP address.


| Setting | Value |
|---|---|
| IP Address | `12.10.0.25` |
| Subnet Mask | `255.0.0.0` |
| Default Gateway | `12.10.0.20` |
| Preferred DNS | `12.10.0.25` |



---

## Configure Static IP

Open:

```text
Control Panel
→ Network and Internet
→ Network and Sharing Center
→ Change adapter settings
```

Right-click the Ethernet adapter and select:

```text
Properties
→ Internet Protocol Version 4 (TCP/IPv4)
→ Properties
```

Configure the static IP information.



```text
IP address:
12.10.0.25

Subnet mask:
255.0.0.0

Default gateway:
12.10.0.20

Preferred DNS server:
12.10.0.25
```

---

# 3. Verify Network Connectivity

Open Command Prompt and run:

```cmd
ipconfig /all
```

Verify that the server has the expected IP configuration.

Test the local network:

```cmd
ping 12.10.0.20
```

Test the server's own IP:

```cmd
ping 12.10.0.25
```

Network configuration can also be checked using:

```cmd
ipconfig
```

---

# 4. Configure Server Time

Correct time synchronization is important for Active Directory because Kerberos authentication is sensitive to time differences.

Verify the current time:

```cmd
time
```

Verify the date:

```cmd
date
```

The server's time zone and system time were checked before deploying Active Directory.

---

# 5. Windows Updates

Windows Server was updated before deploying additional infrastructure services.

Navigate to:

```text
Settings
→ Update & Security
→ Windows Update
```

Install available updates and restart when required.

---

# 6. Server Manager

Server Manager was used to manage server roles and features.

Common administrative tools used during this project include:

- Server Manager
- Active Directory Users and Computers
- Active Directory Domains and Trusts
- DNS Manager
- DHCP Manager
- Group Policy Management
- Event Viewer
- Computer Management
- Services
- Windows Server Backup
- Print Management
- PowerShell

---



# 7. Prepare for Active Directory

Before installing Active Directory Domain Services, the following conditions were verified:

- Server has a static IP address.
- Server has a descriptive hostname.
- Network connectivity is working.
- System time is correct.
- Windows Server is updated.
- Server is connected to the physical network.
- DNS configuration is ready for Active Directory deployment.

---

# Result

The Acer Aspire ES 14 was successfully configured as the base Windows Server 2019 infrastructure machine.

The server was ready for deployment of:

- Active Directory Domain Services
- DNS
- DHCP
- Group Policy
- File Services
- Print Services
- Backup

The next stage of the project was deploying **Active Directory Domain Services and creating the domain environment**.
