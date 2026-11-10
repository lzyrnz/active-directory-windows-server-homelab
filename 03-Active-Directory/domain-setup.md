# Active Directory Domain Services Setup

## Overview

After completing the initial Windows Server configuration, I installed **Active Directory Domain Services (AD DS)**.

The goal was to create a domain environment where users and computers could be centrally managed.

---

## Server

```text
Server Name : HomelabServer
IP Address  : 12.10.0.25
```

---

## Installing AD DS

I opened:

```text
Server Manager
→ Add Roles and Features
```

I selected:

```text
Active Directory Domain Services
```

I installed the required features and completed the installation.

### AD DS Installation

> **Mock image — replace with my actual screenshot.**

```text
![AD DS Installation](../images/ad-ds-installation.png)
```

---

## Promoting the Server

After installing AD DS, I promoted the server to a Domain Controller.

I selected:

```text
Add a new forest
```

and configured my domain.

```text
Domain Name: <MY-DOMAIN>
```

> Replace `<MY-DOMAIN>` with the actual domain name used in my lab.

I then configured the Directory Services Restore Mode password and completed the domain controller installation.

---

## Verification

After restarting, I checked that the server was functioning as a domain controller.

I used:

```text
Active Directory Users and Computers
```

and:

```text
DNS Manager
```

to verify the installation.

### Active Directory

> **Mock image — replace with my actual screenshot.**

```text
![Active Directory](../images/ad-domain.png)
```

---

