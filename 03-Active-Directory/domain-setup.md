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

<img width="1536" height="2048" alt="image" src="https://github.com/user-attachments/assets/183b6782-327e-4386-a05e-ce2a81cd51dd" />

---

## Promoting the Server

After installing AD DS, I promoted the server to a Domain Controller.

I selected:

```text
Add a new forest
```

and configured my domain.

```text
Domain Name: <HOMELAB.ORG>
```

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




<img width="600" height="408" alt="image" src="https://github.com/user-attachments/assets/f63ee40a-52df-48ff-9063-153d04d69c99" />

---

