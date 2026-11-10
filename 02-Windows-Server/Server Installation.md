# Windows Server 2019 Installation

## Overview

For this homelab, I used an old **Acer Aspire ES 14** laptop from my cousin and repurposed it as my Windows Server 2019 machine.

I decided to install Windows Server 2019 directly on the laptop instead of using a virtual machine. I also configured the laptop as a **dual-boot system**, so I could still use the existing Windows installation when needed.

The purpose of this was to get hands-on experience with installing and configuring a real Windows Server environment using physical hardware.

---

## Hardware

| Component | Details |
|---|---|
| Device | Acer Aspire ES 14 |
| Server Operating System | Windows Server 2019 |
| Installation | Physical / Bare Metal |
| Boot Configuration | Dual Boot |
| Network Connection | Ethernet |

---

## Why I Used This Laptop

I had access to an old Acer Aspire ES 14 that was no longer being used regularly. Since I was interested in learning more about IT infrastructure and Windows Server administration, I decided to repurpose it for this project.

I wanted to build the lab using actual hardware instead of relying completely on virtualization.

---

## Installation Preparation

Before installing Windows Server 2019, I prepared the laptop and installation media.

The preparation included:

- Checking the available storage
- Backing up important files
- Preparing a bootable Windows Server 2019 USB
- Checking the BIOS/UEFI boot settings
- Preparing disk space for the Windows Server installation
- Connecting the laptop to the network

> **Note:** Disk partitioning and operating system installation can result in data loss. Important files should always be backed up before modifying partitions.

---

## Dual-Boot Configuration

I configured the laptop to have two operating systems.

The setup allows me to choose between the existing Windows installation and Windows Server 2019 when starting the computer.

The general configuration is:

```text
Acer Aspire ES 14
│
├── Existing Windows Installation
│
└── Windows Server 2019
```

This allowed me to keep the original Windows installation while using Windows Server 2019 for my homelab.

---

## Windows Server 2019 Installation

I booted the laptop using the Windows Server 2019 installation USB.

The installation process was:

1. Booted the laptop from the Windows Server 2019 USB.
2. Selected the required language and regional settings.
3. Selected the Windows Server 2019 edition.
4. Accepted the Microsoft Software License Terms.
5. Selected the custom installation option.
6. Selected the partition prepared for Windows Server 2019.
7. Started the installation.
8. Waited for Windows Server to complete the installation.
9. Created the Administrator password.
10. Logged into Windows Server 2019.

---

## Post-Installation

After successfully installing Windows Server 2019, I performed some basic checks before starting the server configuration.

I checked:

- Network adapter
- Ethernet connection
- Disk partitions
- Device Manager
- Windows version
- System date and time
- Available Windows updates

I also gave the server the hostname:

```text
HomelabServer
```

---

## Server Information

The initial server configuration used in my homelab is:

| Configuration | Value |
|---|---|
| Server Name | `HomelabServer` |
| Operating System | Windows Server 2019 |
| IP Address | `12.10.0.25` |
| Default Gateway | `12.10.0.20` |
| Preferred DNS | `12.10.0.25` |

The server uses a static IP address because it will later provide network infrastructure services such as DNS and DHCP.

---

## Result

The Acer Aspire ES 14 was successfully repurposed as my physical Windows Server 2019 homelab server.

The dual-boot configuration also allowed me to keep the original Windows installation while having a dedicated Windows Server environment for practicing:

- Active Directory
- DNS
- DHCP
- Group Policy
- Backup
- Print Management
- Network administration
- Troubleshooting

The next step was to configure Windows Server and prepare it for Active Directory Domain Services.
