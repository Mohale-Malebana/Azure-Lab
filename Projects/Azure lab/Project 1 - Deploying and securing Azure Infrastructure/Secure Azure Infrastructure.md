# PROJECT 1: Secure Azure Infrastructure


## Scenario

Apex Retail Group is moving one of its applications into Azure.Management hired you to deploy a secure cloud environment.

### **Goals**

```

- Deploy Linux servers

- Secure networking

- Implement least privilege

- Enable monitoring

- Configure identity security

- Document architecture

```



## Creating a resource group

Here's the resource group i've created : ARG-Production

***Region:*** South Africa North  
***Purpose:*** To hold related cloud services and resources together such as vm's, network security groups.etc

<img src="Screenshots/Resource group.png" alt="My Image" style="width: 80%; height: auto;">

An Azure resource group is a logical container that holds related cloud services and items—known as resources—for an application or a specific project.

## Creating a Virtual Network

Here's the virtual network I created : ARG-vnet  
***Purpose:*** Created to provide a secure, isolated and private network environment in the cloud.

***Key advantages:*** include enhanced security, easy scalability, and seamless on-premises integration.



<img src="Screenshots\vnet.png" alt="My Image" style="width: 80%; height: auto;">




A VNet (Virtual Network) is a secure, isolated private network hosted in the in Microsoft Azure—that allows virtual machines, databases, and other cloud components to communicate safely with each other, the internet, and on-premises data centers.


## Creating and deploying VM's

***WEB VM(UBUNTU VM)***


***VM Image:*** Ubuntu Server 24.04 LTS - Gen2  
***Size:*** Standard B2ats v2 (2 vcpus, 1 GiB memory)  
***Authentication:*** SSH public key(No password)   
***Public Ip address:*** None   
***Purpose:*** This a public facing web Virtual machine(VM). This is the where the application sits. 

<img src="Screenshots\web-vm.png" alt="My Image" style="width: 80%; height: auto;">

A virtual machine (VM) is a software program that emulates a physical computer. It runs its own operating system (like Windows or Linux) and applications but relies on the physical hardware of a "host" machine to function, behaving exactly like an independent computer.


***APP VM(UBUNTU VM)***


***VM Image:*** Ubuntu Server 24.04 LTS - Gen2  
***Size:*** Standard B2ats v2 (2 vcpus, 1 GiB memory)  
***Authentication:*** SSH public key(No password)   
***Public Ip address:*** None   
Purpose: This a app Virtual machine(VM) server. This vm  hosts the app. 

<img src="Screenshots\app-vm.png" alt="My Image" style="width: 80%; height: auto;">


***SOC VM(UBUNTU VM)***


***VM Image:*** Ubuntu Server 24.04 LTS - Gen2  
***Size:*** Standard B2ats v2 (2 vcpus, 1 GiB memory)  
***Authentication:*** SSH public key(No password)   
***Public Ip address:*** Yes  
Purpose: This a SOC Virtual machine(VM) server. This vm  caputures log, monitors and investigate logs

<img src="Screenshots\Soc-vm.png" alt="My Image" style="width: 80%; height: auto;">
    

       
        
                                                                                                                                                        
                                                                                                                                                        

         
          
---

>***NB!!!*** The production architecture includes a dedicated SOC Monitoring Server. Due to Azure Free Account resource limitations, monitoring services were deployed on the Application Server while maintaining the same security architecture and workflow.  
  
    
 ## Configuring Key Vault

I'm going to create a key vault to store SSH key for my Vm's. 

**Core Functions**  


  
> - Secrets Management: Securely holds and controls access to tokens, passwords, database connection strings, and API keys.   
> - Key Management: Creates and controls the cryptographic keys used to encrypt your data.  
> - Certificate Management: Provisions, manages, and deploys public and private SSL/TLS certificates   

\
<img src="Screenshots\Soc-vm.png" alt="My Image" style="width: 80%; height: auto;">

Azure Key Vault is a cloud-hosted Microsoft service used to securely store and manage application Secrets, Keys, and Certificates (learn.microsoft.com). It stops developers from hardcoding sensitive data like passwords and API keys directly into source code.
  

  <img src="Screenshots\keyadmin.png" alt="My Image" style="width: 50%; height: auto;"> Assigned a Key Vault user administrator  
  
  <img src="Screenshots\keyuse.png" alt="My Image" style="width: 50%; height: auto;"> Assigned a Key Vault user for my two VM's

   <img     src="Screenshots\keys.png" alt="My Image" style="width: 50%; height: auto;"> Imported VM Keys

**RATIONALE**


> I configured Azure RBAC on Azure Key Vault instead of using broad administrative permissions. My administrator account was assigned the Key Vault Administrator role to manage keys and secrets, while applications would use Managed Identities with the Key Vault Secrets User role to retrieve secrets without storing credentials. This follows the Principle of Least Privilege by ensuring each identity has only the permissions required for its function.


## Configuring NSG  
Web server Network Security Group rules


<img src="Screenshots\web-nsg.png" alt="My Image" style="width: 80%; height: auto;">



---

Soc server Network Security Group Rules

<img src="Screenshots\soc-nsg.png" alt="My Image" style="width: 80%; height: auto;">

A Network Security Group (NSG) in Azure is a built-in, stateful firewall tool used to filter network traffic to and from Azure resources like virtual machines and subnets using allow or deny rules

  
    
---
**RATIONALE**

>I configured Network Security Group Rules to enforce network-level access control for the Azure machines.Only the minimum required inbound traffic was allowed. SSH (TCP/22) was only allowed for administrative access, while HTTPS (TCP/443) was enabled only for the web server to support secure client communications.

---

## Setting up a Recovery Vault

***Purpose:*** I deployed a Recovery Vault because  Recovery Services Vault is an essential component of cloud resilience. 

***Key capabilities***

> - Azure Backup: Stores backup copies and recovery points for Azure Virtual Machines (Windows and Linux), SQL Server in Azure VMs, Azure Files shares, and on-premises servers or workstations via the Microsoft Azure Recovery Services (MARS) agent.
> - Azure Site Recovery: Orchestrates and manages replication, failover, and failback operations to protect and recover workloads running on Azure VMs or on-premises physical and virtual machines.
> - Policy Management: Acts as the interface where you configure backup schedules, retention ranges, and daily/weekly recovery policies  



<img src="Screenshots\recovery.png" alt="My Image" style="width: 80%; height: auto;">

A recovery services vault in Microsoft Azure is a cloud-based storage and management container used to house backup data, recovery points, and disaster recovery replication metadata. It primarily supports two core business continuity services: Azure Backup and Azure Site Recovery




## **Skills Learned** 

> - Learned how to create and deploy Vm's with Azure.
> - Configured a Virtual Network Vnet to secure cloud environment. Assigned a Public ip address to the Soc-Vm while the two other Vm's have private ip address.
> - Configured Network Security Groups and configured NSG rules.
> - Created Key vaults and assigned RBAC roles like Key security administartor and Key Vaults user. Also imported and stored SSH Keys.
> - Created Recovery Services.


