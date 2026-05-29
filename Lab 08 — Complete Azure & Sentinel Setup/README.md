---
layout: default
title: Lab 08 — Complete Azure & Sentinel Setup
---

# Lab 08 — Complete Azure & Sentinel Setup

**Platform:** Microsoft Azure / Microsoft Sentinel / Microsoft Defender  
**Focus:** Azure infrastructure, log collection, Sentinel deployment, detections, alerts, and workbooks

---

## Lab Summary

This lab demonstrates the deployment of a complete Azure security monitoring environment.

The lab starts with Azure infrastructure provisioning, including a resource group, virtual network, subnet, Network Security Group, Windows VM, and Ubuntu VM. It then continues with Log Analytics Workspace configuration, Data Collection Rules, Azure Activity logs, NSG diagnostic logs, Entra ID logs, Microsoft Defender for Cloud, Microsoft Sentinel, Defender for Endpoint onboarding, KQL investigations, custom analytics rules, alert validation, and workbook creation.

This lab represents an end-to-end Microsoft cloud security monitoring workflow relevant to SOC operations.

---

## Objective

This lab demonstrates the ability to:

1. Deploy Azure infrastructure for a security monitoring environment;
2. Configure secure access using Network Security Groups;
3. Deploy and connect Windows and Linux virtual machines;
4. Configure centralized log collection using Log Analytics Workspace;
5. Create Data Collection Rules for Windows and Linux machines;
6. Collect Azure Activity, NSG, and Entra ID logs;
7. Enable Microsoft Defender for Cloud;
8. Deploy and configure Microsoft Sentinel;
9. Onboard a Windows endpoint into Microsoft Defender for Endpoint;
10. Run KQL queries for investigation;
11. Create analytics rules for brute-force activity;
12. Validate generated alerts;
13. Create a Sentinel workbook for visualization.

---

## Lab Environment

- Microsoft Azure;
- Azure Resource Group;
- Azure Virtual Network;
- Network Security Group;
- Windows 11 VM;
- Ubuntu VM;
- Log Analytics Workspace;
- Data Collection Rules;
- Azure Monitor Agent;
- Microsoft Defender for Cloud;
- Microsoft Defender for Endpoint;
- Microsoft Sentinel.

---

# Part 1 — Azure Resource Creation

## 1. Cost Alerts Configuration

- Configured Azure cost alerts to monitor resource usage;
- Used budget alerts to reduce the risk of unexpected cloud spending.

![Cost alerts](Images/1.png)

---

## 2. Resource Group Creation

- Created a dedicated resource group for the lab;
- Selected Central India region for cost efficiency, as latency and data residency were not critical for this scenario.

![Resource group](Images/2.png)

---

## 3. Virtual Network Creation

- Created a virtual network with a subnet inside the previously created resource group;
- Prepared the network foundation for virtual machines and monitoring resources.

![Virtual network](Images/3.1.png)

![Virtual network](Images/3.2.png)

---

## 4. Network Security Group Creation

- Created a Network Security Group to control inbound and outbound traffic;
- Prepared security controls for administrative access to virtual machines.

![Network Security Group](Images/4.1.png)

![Network Security Group](Images/4.2.png)

---

## 5. Inbound Security Rules

- Configured inbound SSH and RDP rules;
- Allowed controlled administrative access to Linux and Windows virtual machines.

![Inbound rules](Images/5.1.png)

![Inbound rules](Images/5.2.png)

![Inbound rules](Images/5.3.png)

---

## 6. NSG Association with Subnet

- Associated the Network Security Group with the subnet;
- Ensured network security rules apply to resources deployed into the subnet.

![NSG association](Images/6.png)

---

# Part 2 — Virtual Machine Deployment

## 7. Windows 11 VM Deployment

- Created and deployed a Windows 11 virtual machine;
- Used the VM as a Windows endpoint for monitoring and Defender onboarding.

![Windows VM](Images/7.1.png)

![Windows VM](Images/7.2.png)

---

## 8. Windows VM Connectivity Test

- Connected to the Windows VM using RDP;
- Verified that the host was running and accessible.

![RDP connection](Images/8.png)

---

## 9. Ubuntu VM Deployment

- Created an Ubuntu virtual machine;
- Prepared the Linux host for log collection and failed authentication testing.

![Ubuntu VM](Images/9.png)

---

## 10. Ubuntu VM Connectivity Test

- Connected to the Ubuntu VM using PuTTY;
- Verified successful SSH access.

![SSH connection](Images/10.png)

---

# Part 3 — Log Analytics and Data Collection

## 11. Log Analytics Workspace Creation

- Created a Log Analytics Workspace;
- Used it as the central location for collecting and querying security logs.

![Log Analytics Workspace](Images/11.png)

---

## 12. Data Collection Rule for Windows VM

- Created a Data Collection Rule for the Windows VM;
- Configured collection of Windows security events.

![Windows DCR](Images/12.1.png)

![Windows DCR](Images/12.2.png)

![Windows DCR](Images/12.3.png)

---

## 13. Data Collection Rule for Linux VM

- Created a Data Collection Rule for the Linux VM;
- Configured collection of Linux logs.

![Linux DCR](Images/13.1.png)

![Linux DCR](Images/13.2.png)

---

## 14. VM Connection Validation

- Confirmed that both Windows and Linux virtual machines were connected;
- Verified that the monitoring configuration was active.

![Connected VMs](Images/14.png)

---

## 15. Azure Activity Logs Collection

- Configured Azure Activity logs to be sent to the Log Analytics Workspace;
- Enabled monitoring of Azure control-plane activity.

![Azure Activity logs](Images/15.png)

---

## 16. NSG Diagnostic Logs Collection

- Configured diagnostic logging for the Network Security Group;
- Forwarded NSG telemetry to the Log Analytics Workspace.

![NSG diagnostic logs](Images/16.1.png)

![NSG diagnostic logs](Images/16.2.png)

---

## 17. Entra ID Logs Collection

- Configured collection of Entra ID logs from the Azure portal;
- Enabled identity-related monitoring for sign-in and audit activity.

![Entra ID logs](Images/17.1.png)

![Entra ID logs](Images/17.2.png)

![Entra ID logs](Images/17.3.png)

---

## 18. Windows Log Ingestion Validation

- Confirmed that Windows VM logs were successfully ingested;
- Verified log availability through the Log Analytics query interface.

![Windows logs](Images/18.png)

---

## 19. Entra ID Log Ingestion Validation

- Confirmed that Entra ID logs were successfully ingested;
- Verified availability of identity-related log data.

![Entra ID ingestion](Images/19.png)

---

## 20. Linux Log Ingestion Validation

- Confirmed that Linux VM logs were successfully ingested;
- Verified availability of Linux authentication and system logs.

![Linux logs](Images/20.png)

---

# Part 4 — Defender and Sentinel Deployment

## 21. Defender for Servers Enablement

- Enabled Defender for Servers for the created environment;
- Added endpoint protection and server security monitoring capabilities.

![Defender for Servers](Images/21.png)

---

## 22. Microsoft Sentinel Deployment

- Added Microsoft Sentinel to the Log Analytics Workspace;
- Enabled SIEM capabilities for the lab environment.

![Sentinel deployment](Images/22.png)

---

## 23. Connectors and Solutions Configuration

- Added required connectors and solutions from the Defender portal;
- Prepared Microsoft Sentinel to collect and correlate security data.

![Connectors and solutions](Images/23.1.png)

![Connectors and solutions](Images/23.2.png)

![Connectors and solutions](Images/23.3.png)

---

## 24. Windows Security Events via AMA

- Created a Data Collection Rule for Windows Security Events using Azure Monitor Agent;
- Enabled collection of Windows security telemetry for Sentinel analysis.

![Windows Security Events AMA](Images/24.1.png)

![Windows Security Events AMA](Images/24.2.png)

---

## 25. Defender for Endpoint Onboarding

- Onboarded the Windows 11 workstation into Microsoft Defender for Endpoint;
- Generated a test alert by launching a suspicious script on the Windows VM.

![Defender onboarding](Images/25.1.png)

![Defender onboarding](Images/25.2.png)

![Defender onboarding](Images/25.3.png)

---

# Part 5 — KQL Queries and Detection Engineering

## 26. KQL Queries

- Ran KQL queries to investigate authentication activity;
- Queried failed logons on Windows VM;
- Queried failed logons on Linux VM.

![KQL queries](Images/26.1.png)

![KQL queries](Images/26.2.png)

![KQL queries](Images/26.3.png)

![KQL queries](Images/26.4.png)

---

## 27. Brute Force Detection Rule

- Created an analytics rule to detect brute-force attempts;
- Used Defender portal rule creation workflow.

![Brute force rule](Images/27.1.png)

![Brute force rule](Images/27.2.png)

![Brute force rule](Images/27.3.png)

![Brute force rule](Images/27.4.png)

---

## 28. Failed RDP Detection Rule

- Created a rule to detect failed RDP attempts;
- Used failed authentication events as detection logic.

![Failed RDP rule](Images/28.png)

---

## 29. Alert Validation

- Generated test authentication failures;
- Confirmed that alerts were generated by the created rules.

![Generated alerts](Images/29.png)

---

## 30. Entra ID Brute Force Detection Rule

- Created a rule to detect Entra ID brute-force activity;
- Used identity sign-in logs as the detection source.

![Entra ID brute force rule](Images/30.png)

---

## 31. Entra ID Attack Simulation

- Generated several incorrect login attempts;
- Created test data to validate the Entra ID detection rule.

![Entra ID failed logons](Images/31.png)

---

## 32. Detection Rule Validation

- Confirmed that the detection rule worked as expected;
- Verified that matching events appeared in logs.

![Detection validation](Images/32.png)

---

## 33. Analytics Rule Creation

- Created an analytics rule in Microsoft Sentinel;
- Configured rule logic, scheduling, and alert generation settings.

![Analytics rule](Images/33.png)

---

## 34. Analytics Rule Validation

- Confirmed that the analytics rule worked;
- Verified that alerts were created based on detection logic.

![Analytics validation](Images/34.png)

---

# Part 6 — Workbook Creation

## 35. Workbook Creation

- Created a Microsoft Sentinel workbook;
- Built a visual view to support monitoring and analysis of security events.

![Workbook](Images/35.1.png)

![Workbook](Images/35.2.png)

---

## Tools Used

- Microsoft Azure;
- Microsoft Sentinel;
- Microsoft Defender for Cloud;
- Microsoft Defender for Endpoint;
- Microsoft Entra ID;
- Log Analytics Workspace;
- Azure Monitor Agent;
- Kusto Query Language;
- PuTTY;
- Windows Remote Desktop.

---

## Key Skills Demonstrated

- Azure resource deployment;
- Azure networking and NSG configuration;
- Windows and Linux VM administration;
- Log Analytics Workspace configuration;
- Data Collection Rule creation;
- Azure Activity, NSG, Windows, Linux, and Entra ID log ingestion;
- Microsoft Defender for Cloud enablement;
- Microsoft Sentinel deployment;
- Defender for Endpoint onboarding;
- KQL investigation;
- Analytics rule creation;
- Alert validation;
- Workbook creation.

---

## Learning Outcomes

- Gained hands-on experience building an end-to-end Microsoft security monitoring environment;
- Improved understanding of how Azure, Defender, Sentinel, and Log Analytics integrate;
- Practised detection engineering and validation using simulated authentication attacks;
- Developed practical skills relevant to SOC Analyst and Cloud Security Analyst roles.

---

## Disclaimer

All resources were deployed in a controlled, non-production lab environment.
No real user data, credentials, or production systems were used.
