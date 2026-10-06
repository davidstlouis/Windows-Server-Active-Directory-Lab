
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

<img width="1470" height="956" alt="Screenshot 2026-10-06 at 6 32 11 PM" src="https://github.com/user-attachments/assets/73d0ea0f-5973-4cce-8e38-f9669b4a6ba5" />

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
<img width="1470" height="956" alt="Screenshot 2026-10-06 at 6 33 49 PM" src="https://github.com/user-attachments/assets/03f8d624-e430-40fa-b479-a94f34f2f012" />


---

## Step 3: Create the Active Directory Domain

After installing AD DS, I promoted the Windows Server to a **Domain Controller** and configured a new Active Directory forest.

```text
Domain: my domain.com

```

After the server restarted, I verified the domain using **Active Directory Users and Computers**.

<img width="1470" height="956" alt="Screenshot 2026-10-06 at 6 37 25 PM" src="https://github.com/user-attachments/assets/4798c8cd-074d-4d6d-99cd-6b18269622d1" />

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

<img width="1470" height="956" alt="Screenshot 2026-10-06 at 6 42 11 PM" src="https://github.com/user-attachments/assets/cb43eb7c-cf7f-4cd2-83b0-ce2c4eb93b5d" />

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

<img width="1470" height="956" alt="Screenshot 2026-10-06 at 6 48 27 PM" src="https://github.com/user-attachments/assets/c51fc29f-b693-40f2-87ff-8ad4afa6e792" />
<img width="1470" height="956" alt="Screenshot 2026-10-06 at 6 49 15 PM" src="https://github.com/user-attachments/assets/aa7680d8-8e9d-473b-a8bd-a2c26357a5c7" />
<img width="1470" height="956" alt="Screenshot 2026-10-06 at 6 48 56 PM" src="https://github.com/user-attachments/assets/1499a911-fef7-47f4-8da5-58a8361aab5f" />

---

## Step 6: Create a Security Group

I created a **Global Security Group** named:

```text
IT Support
```

I then added `jsmith` as a member of the group.

This demonstrated basic Active Directory group and user management.

<img width="1470" height="956" alt="Screenshot 2026-10-06 at 6 52 41 PM" src="https://github.com/user-attachments/assets/e1c1ebfe-b1df-4ba7-a825-b7399d8a9ba2" />

---

## Step 7: Join Windows 10 to the Domain

I configured my Windows 10 Enterprise VM to use the Domain Controller as its DNS server.

I then joined the computer to:

```text my domain.com```

The Windows 10 computer successfully connected to the Active Directory domain.

<img width="1470" height="956" alt="Screenshot 2026-10-06 at 7 01 49 PM" src="https://github.com/user-attachments/assets/53677def-f688-4454-861c-2b6cb898df54" />


---

## Step 8: Test Domain Authentication

After restarting the Windows 10 VM, I logged in using the domain account:

```text
mydomain.com\Jane_admin

```

I verified the logged-in user with:

```cmd
whoami
```

I also verified which Domain Controller authenticated the user:

```cmd
echo %logonserver%
```

<img width="1470" height="956" alt="Screenshot 2026-10-06 at 7 06 00 PM" src="https://github.com/user-attachments/assets/d8a446dd-5d67-42b5-8448-105678375620" />

---

## Step 9: Practice User Account Management

Using **Active Directory Users and Computers**, I practiced common account-management tasks such as:

- Resetting user passwords
- Disabling and enabling accounts
- Managing security group membership
- Moving users between OUs

These are common tasks performed by IT support and system administrators.

<img width="1470" height="956" alt="Screenshot 2026-10-06 at 7 11 32 PM" src="https://github.com/user-attachments/assets/5fe19c1b-fed1-4320-a7ff-7942d73ffa77" />

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

