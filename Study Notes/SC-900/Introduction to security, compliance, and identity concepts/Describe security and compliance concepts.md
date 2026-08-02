# Introduction

As more business data is accessed from locations outside the traditional corporate network, security and compliance are critical concerns for organizations of all sizes. Organizations need to understand how to protect their data, regardless of where it's accessed from and whether it sits on a corporate network, in the cloud, or in AI-powered services. They also need to stay compliant with the growing number of industry and regulatory requirements that govern how data must be handled, stored, and protected.

This module introduces the foundational security and compliance concepts that underpin the Microsoft security, compliance, and identity portfolio. You start with the shared responsibility model, which clarifies which security responsibilities belong to you and which belong to your cloud provider. From there, you explore how a defense-in-depth strategy layers multiple controls to slow and stop attacks, and how the confidentiality, integrity, and availability (CIA) triad frames the goals of any security effort. You learn about the Zero Trust model—and why trusting the network perimeter alone is no longer sufficient in a world where work happens from anywhere. You then explore encryption and hashing as technical mechanisms for protecting data. Finally, you learn about governance, risk, and compliance (GRC) as the structured approach organizations use to manage their obligations and responsibilities.

# Shared Responsibility Model – Summary

## Overview

The **Shared Responsibility Model** defines which security responsibilities belong to the **customer** and which belong to the **cloud provider**. As organizations move from on-premises infrastructure to cloud services, more security responsibilities shift to the cloud provider.

---

# Responsibility by Service Model

| Service Model | Customer Responsibilities | Cloud Provider Responsibilities |
|---------------|-------------------|---------------------------------|
| **On-Premises** | Everything (building, hardware, network, OS, apps, identities, data) | None |
| **IaaS (Infrastructure as a Service)** | Operating systems, applications, network configuration, identities, data | Physical datacenter, servers, networking, storage, virtualization |
| **PaaS (Platform as a Service)** | Applications, application configuration, identities, data | Infrastructure, networking, storage, operating system, runtime |
| **SaaS (Software as a Service)** | Users, identities, data, tenant configuration | Entire application, platform, infrastructure, updates, maintenance |

> **Key idea:** The higher you move in the cloud stack (IaaS → PaaS → SaaS), the more security responsibilities the cloud provider assumes.

---

# Responsibilities You Always Keep

Regardless of the cloud model, you are always responsible for:

## 📁 Data
- Classifying data sensitivity
- Protecting and encrypting data
- Data governance and compliance
- Deciding who can access data

---

## 👤 Identity and Access Management (IAM)
- Managing user accounts
- Authentication (e.g., MFA)
- Authorization and permissions
- Applying the principle of least privilege

---

## 💻 Endpoints
Secure devices that connect to cloud services:
- Laptops
- Desktops
- Phones
- Tablets

Responsibilities include:
- Security updates
- Endpoint protection
- Device management
- Threat detection

---

## ⚙️ Configuration
You are responsible for:
- Service configuration
- Network security settings
- Access policies
- Resource permissions

Poor configuration can expose resources even if the cloud platform itself is secure.

---

# Benefits of Cloud Security

Cloud providers (such as Microsoft) invest heavily in:

- Physical datacenter security
- Hardware maintenance
- Infrastructure patching
- Threat intelligence
- Compliance certifications
- Continuous monitoring

This allows organizations to focus on:
- Data protection
- Identity management
- Secure configuration

instead of maintaining physical infrastructure.

---

# Key Takeaways

- Security is a **shared responsibility** between the customer and the cloud provider.
- Moving from **On-Premises → IaaS → PaaS → SaaS** shifts more infrastructure security responsibilities to the provider.
- Customers are **always responsible** for:
  - 📁 Data
  - 👤 Identities and access
  - 💻 Endpoints
  - ⚙️ Configuration
- Cloud providers handle infrastructure security, allowing organizations to focus on securing their workloads.


---  


## Quick Memory Tip

| Always Yours | Usually Cloud Provider |
|---------------|------------------------|
| Data | Physical datacenters |
| Identities | Servers |
| Endpoints | Networking |
| Configuration | Storage infrastructure |


> **Remember:** **Your data, your identities, your devices, your configuration = Your responsibility.**   
---



# 1. Defense in Depth

## What is it?
**Defense in Depth** is a security strategy that uses **multiple layers of protection** instead of relying on a single security control.

> **Think of it like an onion 🧅** — an attacker must pass through several layers before reaching your data.

---

## Defense in Depth Layers

| Layer | Purpose | Examples |
|--------|---------|----------|
| 🏢 Physical | Protect buildings and hardware | Security guards, cameras, locks |
| 👤 Identity | Verify users | MFA, passwords, RBAC |
| 🌐 Perimeter | Protect network edge | Firewalls, DDoS protection |
| 🔗 Network | Secure internal communication | Network segmentation, NSGs |
| 💻 Compute | Secure servers and VMs | Patching, antivirus, endpoint security |
| 📱 Application | Secure software | Secure coding, input validation |
| 📁 Data | Protect sensitive information | Encryption, access controls |

---

## Why it Matters

- If one layer fails, another layer protects the system.
- Slows attackers down.
- Increases chances of detecting attacks.
- Limits damage after a breach.

---

# CIA Triad

The **CIA Triad** represents the three goals of cybersecurity.

| Principle | Meaning | Example |
|------------|---------|---------|
| 🔒 Confidentiality | Only authorized users can access data | Encryption, MFA |
| ✔️ Integrity | Data remains accurate and unchanged | Hashing, digital signatures |
| ⚡ Availability | Systems and data are available when needed | Backups, load balancing, DDoS protection |

> **Memory Tip:** **CIA = Keep data Secret, Correct, and Available.**

---

# 2. Zero Trust Model

## What is Zero Trust?

**Never Trust, Always Verify.**

No user, device, or application is trusted automatically—even if it's inside the company network.

---

## Three Principles

### ✅ Verify Explicitly
Always verify using:
- Identity
- Device
- Location
- Risk level
- Data sensitivity

---

### 🔑 Use Least Privilege
Give users:
- Only the access they need
- Only for the time they need it

Examples:
- JIT (Just-In-Time access)
- JEA (Just Enough Access)

---

### 🚨 Assume Breach
Always assume attackers may already be inside.

Protect by:
- Network segmentation
- Encryption
- Monitoring
- Logging

---

## Seven Zero Trust Pillars

1. 👤 Identities
2. 💻 Devices
3. 📱 Applications
4. 📁 Data
5. 🖥️ Infrastructure
6. 🌐 Networks
7. 📊 Visibility, Automation & Orchestration (SIEM + SOAR)

---

## Memory Tip

> **Verify Everything → Least Privilege → Assume Breach**

---

# 3. Encryption & Hashing

## Encryption

Makes data unreadable unless you have the correct key.

---

## Types of Encryption

### 🔐 Symmetric Encryption
- One shared key
- Fast
- Good for large files

Example:
- AES, MD5, NTLM

---

### 🔑 Asymmetric Encryption

Uses two keys:

- Public Key → Encrypt
- Private Key → Decrypt

Used for:
- HTTPS
- SSL/TLS
- Email encryption

---

## Digital Signatures

Provide:
- ✅ Authenticity (Who sent it?)
- ✅ Integrity (Was it changed?)

---

## Encryption by Data State

| Data State | Meaning | Example |
|------------|---------|---------|
| Data at Rest | Stored data | Hard drives, databases |
| Data in Transit | Data moving across networks | HTTPS, VPN |
| Data in Use | Data being processed | Confidential Computing |

---

## Key Management Best Practices

- Store keys separately from data
- Use HSMs (Hardware Security Modules)
- Rotate keys regularly
- Restrict access to keys

Example:
- Azure Key Vault

---

# Hashing

Hashing creates a **fixed-length fingerprint** of data.

Unlike encryption:
- Cannot be reversed
- No key required

Used for:
- Password storage
- File verification

---

## Password Hashing

Instead of storing passwords:
```
Password → Hash → Store Hash
```

When users log in:
```
Entered Password → Hash → Compare
```

---

## Salting

A **salt** is a random value added before hashing.

Benefits:
- Prevents rainbow table attacks
- Same password produces different hashes

---

## Memory Tip

| Encryption | Hashing |
|------------|----------|
| Reversible | One-way |
| Uses keys | No keys |
| Protects data | Verifies data |

---

# 4. Governance, Risk & Compliance (GRC)

## What is GRC?

A framework that helps organizations:
- Manage security
- Reduce risks
- Meet legal requirements

---

# Governance

Defines:
- Policies
- Rules
- Responsibilities

Examples:
- Security policies
- Access control rules
- Data classification

**Question:** *Who makes the rules?*

---

# Risk

Risk Management Process:

1. 🔍 Identify
2. 📈 Assess
3. 🛡️ Respond
4. 🔄 Monitor

Ways to respond:
- Accept
- Mitigate
- Transfer
- Avoid

---

# Compliance

Following:
- Laws
- Regulations
- Industry standards

Examples:
- HIPAA
- ISO 27001
- SOC 2

> **Compliance ≠ Security**

Compliance means meeting the **minimum legal requirements**. Security goes beyond compliance to better protect systems and data.

---

# Important Compliance Concepts

### 🌍 Data Residency
Where data is physically stored.

---

### ⚖️ Data Sovereignty
Data follows the laws of the country where it is stored or processed.

---

### 🔐 Data Privacy
Protecting personal information and respecting individuals' privacy rights.

---

# Quick Exam Cheatsheet

## Defense in Depth
- Physical
- Identity
- Perimeter
- Network
- Compute
- Application
- Data

---

## CIA Triad
- 🔒 Confidentiality
- ✔️ Integrity
- ⚡ Availability

---

## Zero Trust Principles
- Verify Explicitly
- Least Privilege
- Assume Breach

---

## Seven Zero Trust Pillars
- Identities
- Devices
- Applications
- Data
- Infrastructure
- Networks
- Visibility, Automation & Orchestration

---

## Encryption vs Hashing

| Encryption | Hashing |
|------------|----------|
| Reversible | One-way |
| Uses keys | No keys |
| Protects confidentiality | Verifies integrity |

---

## GRC

**Governance** → Rules & policies

**Risk** → Identify → Assess → Respond → Monitor

**Compliance** → Follow laws and standards

---

# One-Sentence Summary

- **Defense in Depth:** Use multiple security layers.
- **CIA:** Protect confidentiality, integrity, and availability.
- **Zero Trust:** Never trust, always verify.
- **Encryption:** Protects data by making it unreadable without a key.
- **Hashing:** Creates a one-way fingerprint to verify data.
- **GRC:** Governance sets rules, Risk manages threats, Compliance follows laws.


