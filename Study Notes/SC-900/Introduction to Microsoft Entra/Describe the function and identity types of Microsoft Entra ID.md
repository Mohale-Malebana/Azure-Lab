## Introduction

When it comes to security, your organization can no longer rely on its network boundary. To allow employees, partners, and customers to collaborate securely, organizations need to shift to an approach where identity becomes the new security perimeter. Using an identity provider helps organizations manage that shift and all the aspects of identity security.

As organizations adopt AI-powered agents and expand collaboration across organizational boundaries, managing identities becomes more complex. Microsoft Entra provides a family of identity and access management solutions to address these challenges.

In this module, you learn about Microsoft Entra and Microsoft Entra ID, Microsoft's cloud-based identity and access management service. You explore the identity types that Microsoft Entra ID supports, including agent identities for AI scenarios. You also learn about hybrid identity and how Microsoft Entra External ID enables collaboration with people outside your organization.

---


# Microsoft Entra - Student Notes

## What is Microsoft Entra?
Microsoft Entra is Microsoft's **identity and access management (IAM)** platform. It helps organizations securely control who can access apps, devices, and data using the **Zero Trust** security model.

### Main Microsoft Entra Products

| Product | Purpose |
|---------|---------|
| **Microsoft Entra ID** | Identity management, authentication, Single Sign-On (SSO) |
| **Domain Services** | Managed Active Directory services for legacy apps |
| **Private Access** | Secure access to private/internal resources without a VPN |
| **Internet Access** | Secure internet and SaaS app access with web filtering |
| **ID Governance** | Automates user access, permissions, and lifecycle management |
| **ID Protection** | Detects risky sign-ins and users, enforces MFA |
| **Verified ID** | Issues secure digital credentials (e.g., digital certificates) |
| **External ID** | Secure access for customers, guests, and partners |
| **Workload ID** | Identity management for apps, services, and containers |
| **Agent ID** | Identity and security for AI agents |

---

# Microsoft Entra ID

Microsoft Entra ID is Microsoft's **cloud-based Identity and Access Management (IAM)** service.

## What it does
- Authenticates users
- Provides **Single Sign-On (SSO)**
- Controls access to apps and resources
- Supports cloud and on-premises environments
- Enables secure collaboration with external users

## Identity Secure Score
Measures how secure your identity environment is.

- Gives a security score (%)
- Recommends improvements
- Tracks security progress

---

## Key Terms

### Tenant
- A dedicated Microsoft Entra environment for one organization.
- Contains users, groups, devices, apps, and policies.

### Directory
- The database that stores all identities and resources.
- Each tenant has **one directory**.

### Multi-tenant
- An organization with multiple Entra tenants.
- Common after mergers or across different regions.

---

## Who Uses Microsoft Entra ID?

### IT Administrators
- Manage users
- Control access
- Configure MFA and security policies

### Developers
- Add SSO to applications
- Use APIs to integrate identity into apps

### Organizations
- Included with Microsoft 365, Azure, and Dynamics 365.

---

# Microsoft Entra Agent ID

Microsoft Entra Agent ID provides **identities for AI agents**.

## Why AI Agents Need Identities
AI agents:
- Make decisions
- Access data
- Work automatically

Without proper security they can:
- Access too much information
- Become security risks
- Be difficult to manage

---

## Main Components

### Agent Identity Blueprint
A reusable template that defines:
- Agent type
- Permissions
- Security policies

### Agent Identity
An individual AI agent created from a blueprint.

Each agent has:
- Unique identity
- Display name
- Human sponsor/owner

---

## Authentication Types

### Attended
- AI acts **on behalf of a user**.

### Unattended
- AI acts independently using its own permissions.

---

## Security Features

- Conditional Access
- Identity Protection
- Identity Governance
- Agent Registry
- Least Privilege permissions

---

# Microsoft Entra External ID

Allows people **outside your organization** to securely access apps and resources.

Examples:
- Customers
- Business partners
- Vendors
- Guests

Supports:
- Google accounts
- Facebook accounts
- Microsoft accounts
- Other identity providers

---

## Two Main Scenarios

### 1. B2B Collaboration
For business partners and guests.

Features:
- Guest access
- Uses their own credentials
- Access to Microsoft 365 and business apps

---

### 2. Customer Identity (CIAM)

For customer-facing applications.

Features:
- Self-service registration
- Social logins
- Single Sign-On (SSO)
- Customer account management

---

## Tenant Types

### Workforce Tenant
Used for:
- Employees
- Internal apps
- Guest collaboration

### External Tenant
Used for:
- Customers
- Consumer apps
- Business-facing applications

---

## B2B Direct Connect

Allows two organizations to work together without creating guest accounts.

Benefits:
- Teams shared channels
- Chat
- Calls
- File sharing

---

# Microsoft Entra Identity Types

Microsoft Entra supports three main identity categories:

| Identity Type | Represents |
|--------------|------------|
| User Identity | People |
| Device Identity | Devices |
| Workload Identity | Applications and services |

---

## User Identities

Represent:
- Employees
- Customers
- Vendors
- Consultants
- Partners

### Types

- **Internal Member** → Employee
- **External Guest** → Partner or vendor
- **External Member** → Member from another tenant
- **Internal Guest** → Internal account with guest permissions

---

## Workload Identities

Used by:
- Applications
- Services
- Containers
- Virtual Machines

Purpose:
- Authenticate securely
- Access Azure resources

### Types

#### Service Principal
Identity for an application.

#### Managed Identity
Azure automatically manages credentials.

Types:
- **System-assigned** → Linked to one Azure resource
- **User-assigned** → Shared across multiple resources

---

## Agent Identities

Used specifically for AI agents.

Features:
- Conditional Access
- Governance
- Sponsors/Owners
- Autonomous or user-assisted operation

---

## Device Identities

Represents physical devices.

### Microsoft Entra Registered
- Personal devices (BYOD)

### Microsoft Entra Joined
- Company-owned devices

### Microsoft Entra Hybrid Joined
- Connected to both:
  - On-premises Active Directory
  - Microsoft Entra ID

Benefits:
- Single Sign-On (SSO)
- Centralized management
- Intune support

---

# Groups

Groups simplify permission management.

Instead of assigning permissions one by one, assign them to a group.

## Security Groups
Used for:
- Access control
- Security policies
- Conditional Access

Members can include:
- Users
- Devices
- Groups
- Service Principals
- Agent Identities

---

## Microsoft 365 Groups

Used for collaboration.

Provides access to:
- Shared mailbox
- Calendar
- SharePoint
- Teams
- Files

Members:
- Users only

---

## Dynamic Membership

Groups can be:

- **Assigned** → Members added manually.
- **Dynamic** → Members added automatically using rules.

---

# Quick Exam Tips

- **Entra ID** = Cloud Identity & Access Management (IAM)
- **SSO** = One login for multiple apps.
- **MFA** = Extra verification for better security.
- **External ID** = Customers, guests, and partners.
- **Workload ID** = Apps and services.
- **Agent ID** = AI agents.
- **Private Access** = Secure internal access without VPN.
- **Internet Access** = Secure web and SaaS access.
- **Identity Protection** = Detects risky sign-ins.
- **Identity Governance** = Automates user access and lifecycle.
- **Verified ID** = Digital credentials.
- **Security Group** = Access control.
- **Microsoft 365 Group** = Collaboration.
- **Tenant** = Your organization's Entra environment.
- **Directory** = Database of identities and resources.

  
    



 
