# Active Directory Users and Groups

## Overview

After creating the domain, I created test users and security groups to practice centralized account management.

---

## Users

I created several test accounts for the lab.


```text
Renze R. Alano
User 2
User 3
IT Admin
HR User
Sales User
```


## Security Groups

I also created security groups to organize users and control access.

Example:

```text
GG-IT-Users
GG-IT-Admins
GG-HR-Users
GG-Sales-Users
```

The `GG` naming convention represents a Global Group.

---

## Group Membership

Users were added to the appropriate security groups.

For example:

```text
IT User
   │
   └── GG-IT-Users

IT Administrator
   │
   └── GG-IT-Admins
```

This allowed me to practice managing permissions through groups instead of assigning permissions individually to each user.

---
