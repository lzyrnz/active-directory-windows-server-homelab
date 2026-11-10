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
