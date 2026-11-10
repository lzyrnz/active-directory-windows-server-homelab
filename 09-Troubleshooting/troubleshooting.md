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
( I will use this for future refernces... )
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
