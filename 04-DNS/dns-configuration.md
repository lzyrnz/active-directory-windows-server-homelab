# DNS Configuration

## Overview

DNS is an important part of Active Directory because domain clients use DNS to locate domain services.

After installing AD DS, DNS was installed and configured as part of the domain controller setup.

---

## DNS Server

```text
Server: HomelabServer
IP: 12.10.0.25
```

The server uses itself as the DNS server.

---

## DNS Manager

I opened:

```text
Server Manager
→ Tools
→ DNS
```

I checked the forward lookup zone created for the domain.

### DNS Manager

<img width="800" height="1548" alt="image" src="https://github.com/user-attachments/assets/6a7af1b6-35ef-411b-b346-87c08b3748ea" />


---

## DNS Testing

I used:

```cmd
nslookup
```

I also tested DNS resolution using:

```cmd
nslookup <domain-name>
```

and:

```cmd
ping <domain-name>
```

---

## Result

DNS was successfully configured and working with the Active Directory environment.

---
