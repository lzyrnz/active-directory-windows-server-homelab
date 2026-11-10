# `README.md`

# Windows Server 2019 Homelab

A hands-on IT infrastructure homelab that I built using a repurposed Acer Aspire ES 14, a used 5-port TP-Link 100 Mbps network switch, self-terminated Ethernet cables, and Windows Server 2019.

I built this project to gain practical experience with **networking, Windows Server administration, Active Directory, DNS, DHCP, Group Policy, backup, print management, and troubleshooting**.

I completed my **TESDA Computer Systems Servicing NC II**, and while I was unemployed, I wanted to use the equipment and tools I already had to build something practical that I could use as an IT portfolio project.

---

## Project Goals

My goals for this homelab were:

- Build a small physical network.
- Practice Ethernet cable termination.
- Repurpose an old laptop as a server.
- Install Windows Server 2019.
- Configure a dual-boot environment.
- Configure static IP networking.
- Install and configure Active Directory Domain Services.
- Configure DNS.
- Configure DHCP.
- Create users, groups, and Organizational Units.
- Implement Group Policy.
- Configure Windows Server Backup.
- Configure Print Management.
- Practice network and Windows troubleshooting.
- Document the entire project for my GitHub portfolio.

---

## Lab Hardware

| Equipment | Purpose |
|---|---|
| Acer Aspire ES 14 | Windows Server 2019 server |
| My Personal laptop | Domain/client testing |
| TP-Link 5-Port 100 Mbps Switch | Network connectivity |
| 10-meter Ethernet cable | Cable creation |
| RJ45 connectors | Ethernet cable termination |
| Crimping tool | Cable termination |
| Cable tester | Cable testing |

---

## Network Configuration

| Setting | Value |
|---|---|
| Server Name | `HomelabServer` |
| Server IP | `12.10.0.25` |
| Subnet Mask | `255.0.0.0` |
| Default Gateway | `12.10.0.20` |
| DNS Server | `12.10.0.25` |
