# Three-part Cloud Project

## Overview 

Hi everyone, here is my three part project where I will showcase my skills.I'll walk you through tools and skills I've used.

### Scenario 
My objective is to secure the company's Azure infrastructure at the Apex Retail Group(ARG) as A *__Junior Security Analyst__* and document everything as if I work there.  
 *(This is a fictional company and this is done for the purpose of the project.)*

 ---

  ### **Company Name**

>***Apex Retail Group (ARG)***  
***Industry:*** National retail company  
***Employees:***
20-50  
***Branches:***
Johannesburg
Cape Town  
***Cloud Platform:***
Microsoft Azure  
***Operating Systems:***
Linux only (Ubuntu Server 24.04 LTS)  
***Security Team:***
SOC Analysts,
Cloud Security Engineer,
Security Administrator

# The Three Projects

Everything connects together.

Project 1: Build and Secure the Azure Infrastructure  
Project 2: Centralized Logging, Monitoring and Threat Detection   
Project 3: Incident Response and Threat Hunting


# **Infrastructure Overview**

# Apex Retail Group - Azure Cloud Security Environment

```text
Azure Subscription
│
├── Resource Group
│   └── ARG-Production
│
├── Virtual Network
│   └── 10.0.0.0/16
│
├── Subnet
│   └── Servers
│
├── Ubuntu Server 1
│   └── Web Server (ARG-Web)
│
├── Ubuntu Server 2
│   └── Application Server (ARG-App)
│
├── Ubuntu Server 3
│   └── SOC Monitoring Server (ARG-Soc)
│
├── Network Security Groups (NSGs)
│
├── Azure Key Vault
│
├── Microsoft Defender for Cloud
│
├── Azure Monitor
│
├── Azure Log Analytics Workspace
│
├── Microsoft Sentinel
│
└── Storage Account
```

## Infrastructure Overview

| Resource | Name | Purpose |
|----------|------|---------|
| **Azure Subscription** | `Apex Retail Group Subscription` | Hosts all cloud resources |
| **Resource Group** | `ARG-Production` | Logical container for production resources |
| **Virtual Network** | `ARG-VNET` | Provides secure network communication between Azure resources |
| **Address Space** | `10.0.0.0/16` | Private IP range for the production environment |
| **Subnet** | `Servers` (`10.0.1.0/24`) | Hosts all Linux virtual machines |
| **Ubuntu VM 1** | `ARG-Web` | Public-facing web server |
| **Ubuntu VM 2** | `ARG-App` | Internal application server |
| **Ubuntu VM 3** | `ARG-Soc` | Security monitoring and log collection server |
| **Network Security Groups** | `ARG-Nsg` | Controls inbound and outbound network traffic |
| **Azure Key Vault** | `ARG-Key` | Securely stores secrets, SSH keys, and certificates |
| **Microsoft Defender for Cloud** | Enabled | Provides cloud security posture management and threat protection |
| **Azure Monitor** | Enabled | Collects metrics and performance data |
| **Log Analytics Workspace** | `ARG-Log` | Central repository for logs and telemetry |
| **Microsoft Sentinel** | Enabled | SIEM and SOAR platform for security monitoring |
| **Storage Account** | `argstorage` | Stores diagnostics logs, boot diagnostics, and other security artifacts |

## Architecture Summary

This environment simulates the production infrastructure of **Apex Retail Group**, a fictional enterprise migrating its applications to Microsoft Azure. The deployment consists entirely of **Ubuntu Linux virtual machines**, secured using Azure networking, identity, monitoring, and security services.

The environment follows cloud security best practices by implementing:

- Secure network segmentation using a Virtual Network and Subnet
- Linux-only virtual machines
- Least privilege access through Azure RBAC
- Centralized log collection with Azure Monitor and Log Analytics
- Threat detection and incident monitoring using Microsoft Sentinel
- Continuous security posture assessment through Microsoft Defender for Cloud
- Secure secret management with Azure Key Vault
- Storage Account for diagnostics, logs, and backup artifacts.

This architecture serves as the foundation for three enterprise cloud security projects:

1. **Project 1 – Deploy and Secure Azure Infrastructure**
2. **Project 2 – Centralized Logging & Threat Detection**
3. **Project 3 – Incident Response & Threat Hunting**
