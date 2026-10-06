# Active Directory Domain Services Lab

## Project Overview

In this lab, I configured **Active Directory Domain Services (AD DS)** using Windows Server 2022 and connected a Windows 10 Enterprise client to the domain in Microsoft Azure.

The project demonstrates basic Active Directory administration, including creating users, Organizational Units (OUs), security groups, joining a computer to a domain, and managing user accounts.

## Technologies Used

- Microsoft Azure
- Windows Server 2022 Datacenter: Azure Edition
- Windows 10 Enterprise
- Active Directory Domain Services (AD DS)
- DNS
- Active Directory Users and Computers
- Command Prompt

---

## Lab Environment

```text
Microsoft Azure
│
├── Windows Server 2022
│     SERVER01
│     ├── Active Directory
│     ├── DNS
│     └── davidlab.local
│
└── Windows 10 Enterprise
      CLIENT01
          │
          └── Joined to davidlab.local
```

---

## Step 1: Verify DNS

Before configuring Active Directory, I verified that DNS was working correctly on my Windows Server.

```cmd
ipconfig
```

My existing DNS zone was:

```text
davidlab.local
```

### Screenshot
<!-- Drag your DNS Manager screenshot here -->

---

## Step 2: Install Active Directory Domain Services

Using Server Manager, I installed the **Active Directory Domain Services (AD DS)** role.

```text
Server Manager
→ Manage
→ Add Roles and Features
→ Active Directory Domain Services
→ Install
```

### Screenshot
<!-- Drag your AD DS installation screenshot here -->

---

## Step 3: Create the Active Directory Domain

After installing AD DS, I promoted the Windows Server to a **Domain Controller** and configured a new Active Directory forest.

```text
Domain: davidlab.local
```

After the server restarted, I verified the domain using **Active Directory Users and Computers**.

### Screenshot
<!-- Drag your Active Directory domain screenshot here -->

---

## Step 4: Create Organizational Units

I created Organizational Units to organize users based on their roles.

```text
davidlab.local
│
├── IT
├── HR
└── Employees
```

### Screenshot
<!-- Drag your OU screenshot here -->

---

## Step 5: Create Domain Users

I created several test user accounts and placed them into their appropriate OUs.

```text
IT
└── John Smith (jsmith)

HR
└── Sarah Johnson (sjohnson)

Employees
└── Michael Davis (mdavis)
```

### Screenshot
<!-- Drag your user accounts screenshot here -->

---

## Step 6: Create a Security Group

I created a **Global Security Group** named:

```text
IT Support
```

I then added `jsmith` as a member of the group.

This demonstrated basic Active Directory group and user management.

### Screenshot
<!-- Drag your IT Support group screenshot here -->

---

## Step 7: Join Windows 10 to the Domain

I configured my Windows 10 Enterprise VM to use the Domain Controller as its DNS server.

I then joined the computer to:

```text
davidlab.local
```

The Windows 10 computer successfully connected to the Active Directory domain.

### Screenshot
<!-- Drag your "Welcome to the davidlab.local domain" screenshot here -->

---

## Step 8: Test Domain Authentication

After restarting the Windows 10 VM, I logged in using the domain account:

```text
DAVIDLAB\jsmith
```

I verified the logged-in user with:

```cmd
whoami
```

I also verified which Domain Controller authenticated the user:

```cmd
echo %logonserver%
```

### Screenshot
<!-- Drag your whoami/logonserver screenshot here -->

---

## Step 9: Practice User Account Management

Using **Active Directory Users and Computers**, I practiced common account-management tasks such as:

- Resetting user passwords
- Disabling and enabling accounts
- Managing security group membership
- Moving users between OUs

These are common tasks performed by IT support and system administrators.

### Screenshot
<!-- Drag your account management screenshot here -->

---

## Skills Demonstrated

- Active Directory Domain Services
- Windows Server Administration
- User Account Management
- Organizational Units
- Security Groups
- Domain Controllers
- Domain Joining
- DNS
- Windows 10 Administration
- Microsoft Azure
- Identity & Access Management
- Basic Active Directory Troubleshooting

---

## What I Learned

This lab gave me hands-on experience building and managing a basic Active Directory environment.

I learned how Active Directory, DNS, Domain Controllers, users, groups, and Windows clients work together in a Windows domain environment. I also practiced common IT support tasks such as creating accounts, resetting passwords, managing group membership, and troubleshooting domain authentication.

---

## Author

**David Saint Louis**  
Cybersecurity / Information Technology Student

[LinkedIn](https://www.linkedin.com/in/david-saint-louis-)
