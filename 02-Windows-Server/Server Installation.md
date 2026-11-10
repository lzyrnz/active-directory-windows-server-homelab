# Windows Server 2019 Installation


## Overview

The Acer Aspire ES 14 was repurposed as a physical Windows Server 2019 lab machine.

The laptop was configured as a **dual-boot system**, allowing Windows Server 2019 to run directly on the hardware while retaining the existing Windows installation.

This setup provides hands-on experience with operating system installation, disk partitioning, boot configuration, BIOS/UEFI settings, and server deployment.

---

## Hardware

| Component | Details |
|---|---|
| Device | Acer Aspire ES 14 |
| Server OS | Windows Server 2019 |
| Existing OS | Windows |
| Installation Type | Physical / Bare Metal |
| Boot Configuration | Dual Boot |
| Network | Ethernet |

---

## Preparation

Before installing Windows Server 2019, the following preparations were completed:

- Backed up important files.
- Checked available disk space.
- Prepared Windows Server 2019 installation media.
- Verified BIOS/UEFI boot settings.
- Prepared disk space for the server installation.
- Connected the laptop to the network.
- Prepared the necessary installation and troubleshooting tools.

> **Important:** Always back up important data before modifying partitions or installing another operating system.

---

## Creating the Installation Media

Windows Server 2019 installation media was prepared using a USB flash drive.

The USB was configured as bootable installation media and verified before starting the installation.

**Screenshot:**
<img width="600" height="408" alt="image" src="https://github.com/user-attachments/assets/b2f31b0e-b755-4cbc-943b-d428345059ff" />

---

## BIOS / UEFI Configuration

The laptop was configured to boot from the Windows Server installation USB.

Depending on the system configuration, BIOS/UEFI settings may include:

- Boot order
- UEFI boot mode
- Secure Boot configuration
- USB boot support

---

## Disk Preparation

Existing disk space was prepared for the Windows Server 2019 installation.

The installation was configured so that the existing Windows installation remained available while Windows Server 2019 was installed in a separate partition.

The resulting layout allows the system to boot into either operating system.

**Screenshot:**
<img width="600" height="608" alt="image" src="https://github.com/user-attachments/assets/ca4acf74-0d94-4f02-bffc-065aa3db5394" />

---

## Windows Server Installation

The system was booted from the Windows Server 2019 installation media.

The following installation process was completed:

1. Booted from the installation USB.
2. Selected language and regional settings.
3. Selected the Windows Server 2019 edition.
4. Accepted the Microsoft Software License Terms.
5. Selected **Custom: Install Windows only**.
6. Selected the dedicated partition prepared for Windows Server.
7. Started the installation.
8. Allowed Windows Server to complete the installation.
9. Created the local Administrator password.
10. Booted into Windows Server 2019.

---

## Dual-Boot Verification

After installation, the boot process was tested to verify that both operating systems remained accessible.

The system successfully provided access to:

```text
Windows
Windows Server 2019
```

The Windows Server installation was then selected as the operating system used for the infrastructure lab.

---

## Post-Installation Checks

After logging into Windows Server 2019, the following checks were performed:

- Confirmed Windows Server version.
- Verified disk partitions.
- Verified network adapter availability.
- Connected the server to the physical network.
- Confirmed Ethernet connectivity.
- Checked Device Manager for hardware issues.
- Applied necessary Windows updates.
- Confirmed system date and time.
- Renamed the server.

Example server name:

```text
HomelabServer
```

---

## Result

The Acer Aspire ES 14 was successfully converted into a physical Windows Server 2019 lab machine while retaining the existing Windows installation through a dual-boot configuration.

The server was then ready for the next stage: configuring networking and deploying Active Directory Domain Services.
