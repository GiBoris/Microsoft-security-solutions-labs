---
layout: default
title: Lab 05 — Detections & Incident Response in Microsoft Sentinel
---

# Lab 05 — Detections & Incident Response in Microsoft Sentinel 🚨🛡️

**Platform:** Microsoft Sentinel / Microsoft Defender XDR  
**Focus:** Detection engineering, automation (SOAR), UEBA, and incident response  

---

## Objective

This lab demonstrates end-to-end **SOC detection and response workflow** in Microsoft Sentinel:

- Creating playbooks for automated response
- Building detection rules from queries
- Enabling UEBA (User & Entity Behaviour Analytics)
- Simulating attacks and validating detections
- Investigating and resolving incidents

---

## Lab Environment

- Microsoft Sentinel workspace  
- Microsoft Defender XDR  
- Windows virtual machine  
- Simulated attack scenarios  

All activities were performed in a **controlled, non-production environment**.

---

# Part 1 — Playbook & Automation (SOAR)

## 1.1 Sentinel SOAR Setup

Installed Sentinel SOAR Essentials to enable automation capabilities.

![1](Images/1.1-soar.png)

---

## 1.2 Playbook Creation

Created a playbook to automate incident response actions.

![2](Images/1.2-playbook.png)

---

## 1.3 Playbook Configuration

Configured connections and permissions required for playbook execution.

![3](Images/1.3-playbook-config.png)

---

## 1.4 Automation Rule

Created an automation rule to trigger the playbook upon incident creation.

![4](Images/1.4-automation-rule.png)

---

# Part 2 — Scheduled Analytics Rules

## 2.1 Rule Creation

Created a scheduled query rule to detect suspicious activity.

![5](Images/2.1-rule.png)

---

## 2.2 Rule Validation

Verified that the rule is active and running.

![6](Images/2.2-rule-running.png)

---

# Part 3 — UEBA Enablement

## 3.1 Enabling UEBA

Enabled User and Entity Behaviour Analytics to enhance detection capability.

![7](Images/3.1-ueba.png)

---

## 3.2 UEBA Rules Activation

Confirmed that UEBA-related analytic rules are enabled.

![8](Images/3.2-ueba-rules.png)

---

# Part 4 — Attack Simulation

## 4.1 Persistence Simulation

Simulated persistence via registry modification.

![9](Images/4.1-persistence.png)

---

## 4.2 Privilege Escalation Simulation

Simulated user creation and privilege escalation activity.

![10](Images/4.2-privilege.png)

---

## 4.3 Command & Control (C2) Simulation

Simulated DNS-based C2 communication.

![11](Images/4.3-c2.png)

---

# Part 5 — Detection Engineering

## 5.1 Persistence Detection Query

Developed a query to detect registry-based persistence.

![12](Images/5.1-registry-query.png)

---

## 5.2 Detection Rule Creation

Created an analytic rule based on the persistence detection query.

![13](Images/5.2-detection-rule.png)

---

## 5.3 Privilege Escalation Query

Developed a query to detect group membership changes.

![14](Images/5.3-privilege-query.png)

---

## 5.4 Privilege Escalation Detection Rule

Created detection rule to alert on privilege escalation activity.

![15](Images/5.4-privilege-rule.png)

---

# Part 6 — Incident Investigation & Response

## 6.1 Incident Overview

Reviewed generated incidents in Microsoft Defender portal.

![16](Images/6.1-incidents.png)

---

## 6.2 Playbook Execution

Executed playbook on selected incident.

![17](Images/6.2-playbook-run.png)

---

## 6.3 Task Creation

Created investigation task within the incident.

![18](Images/6.3-task.png)

---

## 6.4 Incident Resolution

Updated incident status to resolved after investigation.

![19](Images/6.4-resolved.png)

---

# Investigation Value

This lab demonstrates a complete SOC workflow:

1. Detection via analytics rules  
2. Alert correlation into incidents  
3. Automated response via playbooks  
4. Investigation and validation  
5. Incident closure  

---

# Skills Demonstrated

- Detection engineering in Microsoft Sentinel  
- KQL-based analytics rule creation  
- SOAR automation with playbooks  
- UEBA integration  
- Incident investigation and response  
- End-to-end SOC workflow  

---

## Disclaimer

All activities were performed in a **controlled lab environment using simulated attack scenarios**.
