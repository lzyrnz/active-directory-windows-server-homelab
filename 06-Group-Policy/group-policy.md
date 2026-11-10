# Group Policy

## Overview

I used Group Policy to practice centralized management of Windows users and computers.

Group Policy allows administrators to apply configuration and security settings to users and computers in an Active Directory environment.

---

## Group Policy Management

I opened:

```text
Server Manager
→ Tools
→ Group Policy Management
```

I created and linked Group Policy Objects to the appropriate Organizational Units.

---

## Test GPO

I created a test Group Policy for one of my Organizational Units.

Example:

```text
GPO-HR-Disable-Control-Panel
```

The policy was linked to the appropriate OU.

---

## Control Panel Restriction

I configured:

```text
User Configuration
→ Policies
→ Administrative Templates
→ Control Panel
```

I enabled:

```text
Prohibit access to Control Panel and PC settings
```

---

## Testing the GPO

On the client computer, I ran:

```cmd
gpupdate /force
```

I then logged out and back in.

I verified the applied policies using:

```cmd
gpresult /r
```

For a more detailed report:

```cmd
gpresult /h C:\gpo-report.html
```

### Group Policy

> **Mock image — replace with my actual screenshot.**

```text
![Group Policy Management](../images/group-policy.png)
```

---

## Additional GPO Practice

I plan to continue expanding the Group Policy section with:

- Password policies
- Account lockout policies
- Screen lock policies
- Windows Firewall policies
- Windows Defender policies
- Drive mapping
- Folder permissions
- Login scripts
- Software restrictions
- Removable storage restrictions

---
