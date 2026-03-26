---
layout: default
title: Lab 04 — KQL Queries for Microsoft Sentinel
---

# Lab 04 — KQL Queries for Microsoft Sentinel 🔎📊

**Platform:** Microsoft Sentinel / Microsoft Defender XDR  
**Focus:** Log analysis, detection logic, and threat hunting using Kusto Query Language (KQL)

---

## Objective

This lab demonstrates practical use of **Kusto Query Language (KQL)** to:

- Query and filter security events
- Perform time-based analysis
- Detect suspicious activity patterns
- Aggregate and visualize data
- Build detection logic for SOC investigations

---

## Lab Environment

- Microsoft Sentinel workspace  
- SecurityEvent and custom tables  
- Simulated log dataset  

All activities were performed in a **controlled, non-production environment**.

---

# Part 1 — Basic Queries

## 1.1 Querying Custom Tables

Executed queries to retrieve data from custom tables and validate data ingestion.

![1](Images/1.1-custom-table.png)

---

## 1.2 Filtering Events by Keyword

Searched for events containing specific keywords within log descriptions.

![2](Images/1.2-keyword-filter.png)

---

## 1.3 Time-Based Filtering

Filtered events based on a defined timeframe (last 7 days).

![3](Images/1.3-time-filter.png)

---

# Part 2 — Event Filtering & Variables

## 2.1 Process Creation Filtering

Filtered events related to process creation activities within a defined timeframe.

![4](Images/2.1-process-filter.png)

---

## 2.2 Using Variables for Dynamic Queries

Defined variables to simplify query structure and improve readability.

![5](Images/2.2-variables.png)

---

# Part 3 — Threat Hunting Scenarios

## 3.1 Identifying Suspicious Accounts

Created a temporary list of accounts exhibiting suspicious activity and used it to filter related events.

![6](Images/3.1-suspicious-accounts.png)

---

## 3.2 Process Creation Analysis

Summarized process creation activity across accounts to identify anomalies.

![7](Images/3.2-process-summary.png)

---

## 3.3 Detection Rule Logic

Developed logic to detect repeated account disable failures across multiple systems.

![8](Images/3.3-detection-rule.png)

---

# Part 4 — Advanced Queries

## 4.1 Latest Event Retrieval

Queried the most recent event for a specific host.

![9](Images/4.1-latest-event.png)

---

## 4.2 User Activity Analysis

Generated a list of accounts logging into systems over a defined period.

![10](Images/4.2-user-activity.png)

---

## 4.3 Data Visualization

Rendered a bar chart to visualize event distribution across accounts.

![11](Images/4.3-barchart.png)

---

# Investigation Value

These queries support:

- Rapid filtering of large datasets
- Detection of abnormal behaviour patterns
- Creation of detection rules
- Visualization of activity trends
- Efficient SOC investigation workflows

---

# Skills Demonstrated

- KQL query development
- Log filtering and aggregation
- Time-based analysis
- Threat hunting techniques
- Detection logic creation
- Data visualization in Sentinel

---

## Disclaimer

All activities were performed in a **controlled lab environment using simulated data**.
