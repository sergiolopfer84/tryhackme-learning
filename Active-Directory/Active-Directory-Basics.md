# Active Directory Fundamentals

This section contains my notes and practice material related to **Active Directory** and **Windows Domains**, based mainly on the *Active Directory Basics* room from TryHackMe.

The goal of these notes is to build a solid understanding of how Active Directory works, both from a **system administration** and **security** perspective.

---

## 📌 What is Active Directory?

Active Directory (AD) is Microsoft’s directory service used to manage:

- Users and groups
- Computers and servers
- Authentication and authorization
- Policies and configurations across a Windows domain

At the center of Active Directory is the **Domain Controller (DC)**, which stores critical information such as **hashed user credentials** and enforces security policies.

---

## 🏢 Windows Domains

A **Windows Domain** allows centralized management of identities and devices.

Key characteristics:
- Centralized authentication
- Centralized policy enforcement
- Trust-based access to resources

All users and machines rely on the **Domain Controller** to validate access to domain resources.

---

## 👥 Users, Computers and OUs

Active Directory organizes objects using **Organizational Units (OUs)**.

OUs are used to:
- Organize users and computers logically
- Apply different Group Policies
- Delegate administrative permissions

### Recommended computer organization:
- **Workstations** → User PCs and laptops
- **Servers** → Machines providing services
- **Domain Controllers** → Critical infrastructure systems

Separating these into different OUs allows better security and management.

---

## ⚙️ Group Policy Objects (GPO)

**Group Policy Objects (GPOs)** are collections of settings used to configure users and computers across the domain.

- **User Configuration** → Applies to users
- **Computer Configuration** → Applies to machines

GPOs are distributed through the **SYSVOL** network share and applied automatically to linked OUs.

---

## 🔐 Authentication Methods

Windows domains mainly use two authentication protocols:

### Kerberos (default)
- Ticket-based authentication
- Uses **TGT** and **TGS**
- More secure and efficient
- Default in modern Windows domains

### NetNTLM (legacy)
- Challenge–response mechanism
- Still widely enabled for compatibility
- More vulnerable to attacks

---

## 🌳 Trees, Forests and Trusts

- **Trees**: Multiple domains sharing the same namespace
- **Forests**: Multiple trees with different namespaces
- **Trust Relationships**: Allow users from one domain to access resources in another

Trusts enable cross-domain access but **do not grant permissions automatically**.

---

## 🎯 Purpose of this Section

These notes are meant to:
- Reinforce my understanding of Active Directory fundamentals
- Serve as documentation for learning and revision
- Act as a foundation for future topics such as:
  - Active Directory hardening
  - AD exploitation and pentesting techniques

---

## 🚀 Next Steps

- Active Directory Hardening
- Compromising Active Directory
- Kerberos and NTLM attacks
- Privilege escalation in AD environments
