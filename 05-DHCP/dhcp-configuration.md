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
