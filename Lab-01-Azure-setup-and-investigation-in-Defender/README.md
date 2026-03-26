---
layout: default
title: Lab 01 — Azure & Entra ID Setup + Microsoft Security Investigation
---

# Lab 01 — Azure & Entra ID Setup + Security Investigation 🛡️☁️

**Platform:** Microsoft Azure / Microsoft Entra ID / Microsoft Defender XDR / Security Copilot  
**Focus:** Cloud environment setup, identity configuration, and incident investigation using Microsoft security tools  

---

## Objective

This lab demonstrates:

- Initial **Azure environment configuration** and cost governance
- **Microsoft Entra ID (Azure AD)** identity and access setup
- Provisioning and usage of **Microsoft Security Copilot**
- Performing a **SOC-style investigation** using Microsoft Defender XDR
- Applying **KQL-based threat hunting** and Copilot-assisted analysis

---

## Lab Environment

- Azure subscription (trial / personal tenant)
- Microsoft Entra ID tenant
- Microsoft Defender XDR
- Microsoft Security Copilot
- Simulated incident dataset

All activities were performed in an **isolated, non-production environment**.

---

# Part 1 — Azure Setup

## 1.1 Budget Creation

Configured a cost management budget to control Azure spending and prevent unexpected charges.

![1](Images/1.1.png)

---

## 1.2 Alert Configuration

Set up budget alerts to trigger notifications when spending thresholds are reached.

![2](Images/1.2.png)

---

## 1.3 Resource Group Creation

Created a dedicated resource group to logically organize cloud resources used in the lab.

![3](Images/1.3.png)

---

## 1.4 Log Analytics Workspace Creation

Provisioned a workspace to enable centralized logging and integration with security tools.

![4](Images/1.4.png)

---

# Part 2 — Microsoft Entra ID Setup

## 2.1 Enabling Access to Azure Resources

Configured tenant settings to allow appropriate access across Azure services.

![5](Images/2.1.png)

---

## 2.2 Assigning Owner Role

Assigned **Owner role** to the user to enable full administrative control for lab configuration.

![6](Images/2.2.png)

---

# Part 3 — Microsoft Security Copilot Setup

Provisioned Microsoft Security Copilot and verified its availability for investigation workflows.

![7](Images/3.png)

---

# Part 4 — Incident Investigation (Microsoft Defender XDR)

## 4.1 Incident Selection

Selected **high severity incident #185856** for investigation.

![8](Images/4.1.png)

---

## 4.2 Suspicious RDP Investigation

Investigated suspicious Remote Desktop activity associated with the incident.

![9](Images/4.2.png)

---

## 4.3 Device Summary (Copilot)

Used Security Copilot to generate a **summary of the affected device**, improving investigation speed.

![10](Images/4.3.png)

---

## 4.4 User Investigation

Analyzed details of the user associated with the compromised asset.

![11](Images/4.4.png)

---

## 4.5 Suspicious Script Activity

Identified unexpected script execution originating from the user's device.

![12](Images/4.5.png)

---

## 4.6 PowerShell Analysis (Base64 Decoding)

Decoded a suspicious PowerShell command to reveal underlying behavior.

![13](Images/4.6.png)

---

## 4.7 Artifact Investigation

Investigated related:

- Files  
- Processes  
- Emails  
- URLs  

to understand full attack scope.

![14](Images/4.7.png)

---

## 4.8 Mimikatz Detection

Detected usage of **mimikatz.exe**, indicating credential dumping activity.

![15](Images/4.8.png)

---

## 4.9 Copilot-Assisted Investigation

Used Security Copilot to enrich findings and accelerate analysis.

![16](Images/4.9.1.png)

![16](Images/4.9.2.png)

![16](Images/4.9.3.png)

---

## 4.10 KQL Threat Hunting

Generated and executed **KQL queries** to identify additional malicious activity.

![17](Images/4.10.png)

---

## 4.11 Additional Alerts Identified

Correlated additional alerts uncovered during advanced hunting.

![18](Images/4.11.png)

---

# Skills Demonstrated

- Azure cost management and resource organization
- Microsoft Entra ID role-based access control (RBAC)
- Microsoft Defender XDR investigation workflow
- Security Copilot usage for SOC efficiency
- KQL-based threat hunting
- Detection of:
  - Suspicious RDP activity
  - PowerShell abuse
  - Credential dumping (Mimikatz)

---

## Disclaimer

All activities were performed in a **controlled lab environment using simulated data**.
