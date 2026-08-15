# PROJECT 2: Centralized Logging & Threat Detection


## Scenario

In the prevous part of the project we deployed and secured Cloud infrastructure and resources. Now we'll look into centralising logs and detecting threats. This will touch a bit on our main goal to secure our infrastructure  using Microsoft's SIEM and SOAR which is Microsoft Sentinel. 

### Goals

```
- Create Log Analytics Workspace 

- Enable Azure Monitor and Data Collection Rules

- Enable Microsoft Sentinel

- Enable Microsoft Defender for Cloud

- Explore the Defender Portal

- Document architecture
```


##  Creating a Log Analytics Workspace

***Purpose:*** We'll create this workspace to capture data from Azure monitor.This is where all the Azure monitor logs are going to be stored.

<img src="Screenshots\LOG.png" alt="My Image" style="width: 80%; height: auto;">  

A Log Analytics workspace in Azure is a centralized data repository that acts as the foundational management unit for Azure Monitor Logs, used to collect, store, and query telemetry and log data from various cloud and on-premises resources.

## Creating Data Collection rules

***Purpose:*** We use DCR to collect data from the vm's into the Log analytics workspace, there we can query information about the vm's cpu,network, syslogs etc 





<img src="Screenshots\dcr.png" alt="My Image" style="width: 80%; height: auto;">    

Azure Data Collection Rules (DCR) define how monitoring data is collected, transformed, and routed in Azure Monitor, using three core components: Data Sources, Data Flows, and Destinations. They replace legacy collection methods and work with the Azure Monitor Agent (AMA)


## Enabling A Microsoft Sentinel Instance 

***Purpose:*** With Azure Monitor Logs ingested in the Log analytics workspace we can now use Microsoft Sentinel to create workbooks, investigate incidents, create analytics rules to detect incidents and essentially monitor our workloads.

***Microsoft Sentinel Key Capabilities:***

> - ***Data Collection:*** Gathers logs and telemetry from users, devices, applications, and infrastructure across on-premises systems, Azure, and other clouds like AWS or GCP.  
> - ***Threat Detection & AI:*** Uses built-in artificial intelligence, machine learning, and Microsoft's threat intelligence to spot malicious activity and reduce false positives.
> - ***Investigation & Graph Analytics:*** Models relationships between users, assets, and threats to help security analysts trace attack paths quickly.
> - ***Automation (SOAR):*** Responds to threats automatically using built-in playbooks and logic rules to stop active attacks fast.

---
  
<img src="Screenshots\Sentinel.png" alt="My Image" style="width: 80%; height: auto;">      

Microsoft Sentinel is a cloud-native Security Information and Event Management (SIEM) and Security Orchestration, Automation, and Response (SOAR) solution. It unifies data collection, threat detection, investigation, and automated responses across hybrid and multi-cloud environments. 

<img src="Screenshots\kql.png" alt="My Image" style="width: 80%; height: auto;">   

First KQL query to check if Microsoft Sentinel gets the logs.



## Creating custom Analytics Rules

***Purpose:*** Before we can investigate incidents, we need to create analytic rules which trigger alerts. Analytic rules are like detection rules in Microsoft Azure. We'll use these rules to trigger alerts which we'll use to investigate.

__Core Functions__  

> - Detection: Scans logs for malware, unauthorized access, data theft, and compromised accounts.   
> - Alert & Incident Creation: Turns matching data patterns into security alerts and groups them into manageable triage case files.  
> - Automation: Triggers playbooks via Logic Apps to instantly isolate devices or notify security staff.


Here are several rules I created created:

<img src="Screenshots\rules.png" alt="My Image" style="width: 80%; height: auto;">     

Microsoft Sentinel analytics rules are automated threat-detection criteria that scan security logs, generate alerts, and create actionable incidents. They use Kusto Query Language (KQL) to spot suspicious activities and trigger automated responses.

## Creating workbooks

***Purpose:*** Creating workbooks will allow us to be able to visualize,analyze and investigate data from services we deployed like Azure Monitor, Microsoft Sentinel etc.


