## Introduction

Identity is how people, devices, and applications prove who or what they are when accessing digital resources. In a world where work happens from anywhere and data spans cloud and on-premises systems, identity has become the central security control organizations rely on.

This module introduces the foundational identity concepts that underpin the Microsoft security, compliance, and identity portfolio. It starts with authentication and authorization—the processes of proving identity and determining access. From there, it explores why identity has replaced the network perimeter as the primary security boundary, and why this matters for every organization. It covers how identity providers enable modern, centralized authentication and single sign-on, then looks at how directory services—from traditional Active Directory to cloud-based Microsoft Entra ID—store and manage identity information at scale. Finally, it covers how federation extends trust across organizational boundaries so users can access resources in different domains without separate accounts.

# Identity & Access Management (SC-900 Summary)

# 1. Authentication vs Authorization

## Authentication (Who are you?)
Verifies your identity before access is granted.

Examples:
- Password
- Fingerprint
- Face ID
- MFA

### Authentication Factors
- 🧠 **Something you know** → Password, PIN
- 📱 **Something you have** → Phone, Security key
- 👤 **Something you are** → Fingerprint, Face scan

> **MFA (Multi-Factor Authentication)** uses two or more factors for stronger security.

---

## Authorization (What can you do?)
Determines what an authenticated user is allowed to access.

Examples:
- Read files
- Edit documents
- Delete records

Uses:
- Roles (RBAC)
- Permissions
- Least Privilege

> **Remember:** Authentication comes **before** Authorization.

---

# 2. Identity as the Security Perimeter

## Traditional Security
Security focused on protecting the **network perimeter** (firewalls, VPNs).

## Modern Security
Identity is now the main security boundary because users work:
- ☁️ In the cloud
- 🏠 Remotely
- 📱 On personal devices (BYOD)

> **Identity = The new security perimeter**

---

## Types of Identities

- 👤 Human (Users)
- 💻 Device (Laptops, Phones)
- ⚙️ Workload (Apps, Services)
- 🤖 Agent (AI Agents)

All identities must be:
- Authenticated
- Authorized

---

## Four Identity Pillars

1. 🛠️ Administration
2. 🔐 Authentication
3. ✅ Authorization
4. 📋 Auditing

---

# 3. Identity Provider (IdP)

## What is an Identity Provider?

A centralized service that:
- Authenticates users
- Authorizes access
- Issues security tokens
- Manages identities

Examples:
- Microsoft Entra ID
- Google
- GitHub
- Amazon

---

## Benefits

- One place to manage users
- Consistent MFA policies
- Easier user management
- Better monitoring

---

## Security Tokens

| Token | Purpose |
|--------|----------|
| ID Token | Confirms identity (Authentication) |
| Access Token | Grants permissions (Authorization) |

---

## Authentication Protocols

| Protocol | Used For |
|-----------|----------|
| OpenID Connect (OIDC) | Authentication |
| OAuth 2.0 | Authorization |
| SAML | Enterprise Single Sign-On |

---

## Single Sign-On (SSO)

Sign in **once**, access **multiple applications**.

Benefits:
- Fewer passwords
- Better security
- Easier user experience

---

# 4. Directory Services & Active Directory

## Directory Service

A database that stores:
- Users
- Devices
- Groups
- Policies

It helps manage authentication and authorization.

---

## Active Directory (AD DS)

Microsoft's **on-premises** directory service.

Features:
- User management
- Group Policy
- Domain Controllers (DC)
- Kerberos & NTLM authentication

---

## Limitations of AD DS

- Not cloud-native
- Limited mobile support
- Requires VPN for remote access
- Doesn't natively support modern protocols

---

## Microsoft Entra ID

Cloud-based Identity and Access Management (IDaaS).

Supports:
- Cloud apps
- Remote work
- Mobile devices
- OAuth 2.0
- OpenID Connect
- SSO

Can work with AD DS using **Hybrid Identity**.

---

# 5. Federation

## What is Federation?

Allows users from **one organization** to access another organization's resources using their **existing credentials**.

> No need to create another account.

---

## How It Works

1. User signs in to their own Identity Provider.
2. A trusted organization accepts that authentication.
3. Access is granted.

This works through a **trust relationship**.

---

## Common Uses

- 🤝 Business-to-Business (B2B)
- 🌍 Sign in with Google, Microsoft, GitHub
- ☁️ Hybrid cloud environments

---

# Quick Exam Cheatsheet

## Authentication
- Confirms identity
- "Who are you?"
- Password, MFA, Biometrics

---

## Authorization
- Grants permissions
- "What can you access?"
- Roles & Least Privilege

---

## Identity Perimeter
- Identity replaces the traditional network perimeter.
- Every user, device, app, and AI agent must be verified.

---

## Identity Provider (IdP)
- Central authentication service
- Issues ID & Access Tokens
- Enables SSO

---

## Directory Services

**AD DS**
- On-premises
- Domain Controller
- Group Policy

**Microsoft Entra ID**
- Cloud-based
- Supports SSO
- Modern authentication
- Hybrid identity

---

## Federation
- Trust between organizations
- Use existing credentials
- No duplicate accounts

---

# One-Sentence Summary

- **Authentication:** Proves **who you are**.
- **Authorization:** Decides **what you can access**.
- **Identity:** The new security perimeter.
- **Identity Provider:** Central service for authentication and authorization.
- **Directory Service:** Stores and manages identities.
- **Active Directory:** On-premises identity management.
- **Microsoft Entra ID:** Cloud identity management.
- **Federation:** Trust between organizations for shared access.