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

> My actual DHCP start and end addresses here.

```text
Start IP:
12.10.0.30

End IP:
21.10.0.39
```

---

## Scope Options

I configured the required DHCP options for the client network.

These included:

- Default gateway
- DNS server
- Domain name

### DHCP Manager

<img width="800" height="1000" alt="image" src="https://github.com/user-attachments/assets/92679fa7-5d3a-4182-9f36-f47d84266454" />


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
