# Organizational Units

## Overview

I created Organizational Units (OUs) to organize users and computers in Active Directory.

This is important because Group Policy can be applied to specific OUs.

---

## OU Structure

Example structure:

```text
Domain
│
├── Users
│
├── IT
│
├── HR
│
├── Sales
│
└── Computers
```


---

## Purpose

I separated users and computers into different OUs so I could later apply different Group Policies to different departments.

For example:

```text
IT
 └── IT Users

HR
 └── HR Users

Sales
 └── Sales Users
```

This gave me a more realistic structure for practicing Windows domain administration.

---
