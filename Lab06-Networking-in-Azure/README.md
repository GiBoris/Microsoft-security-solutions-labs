---
layout: default
title: Lab 06 — Azure Networking & Security
---

# Lab 06 — Azure Networking & Security 🌐🔐

**Platform:** Microsoft Azure  
**Focus:** Virtual networking, connectivity, network security, and firewall configuration  

---

## Lab Summary

This lab demonstrates the design and implementation of a **secure Azure network architecture** across multiple virtual networks.

The work includes:

- Creating multiple Virtual Networks (VNets) and subnets  
- Deploying and connecting virtual machines  
- Configuring private DNS resolution  
- Establishing connectivity using **VNet peering and VPN gateways**  
- Implementing **Virtual WAN architecture**  
- Enabling **DDoS protection**  
- Deploying and configuring **Azure Firewall (network + DNAT rules)**  

This lab reflects real-world cloud networking scenarios used in enterprise environments.

---

## Objective

The goal of this lab is to:

- Build segmented Azure network environments  
- Enable secure communication between networks  
- Implement layered network security controls  
- Understand enterprise-grade Azure networking components  

---

## Lab Environment

- Multiple Azure Virtual Networks:
  - CoreServicesVnet  
  - ManufacturingVnet  
  - ResearchVnet  
- Windows virtual machines  
- Azure Virtual WAN  
- Azure Firewall  
- Azure DDoS Protection  

All activities were performed in a **controlled, non-production environment**.

---

# Part 1 — Virtual Networks & DNS

## 1.1 Creating Virtual Network with Subnets

Created a primary virtual network with segmented subnets.

![1.1](Images/1.1.1.png)

![1.1](Images/1.1.2.png)

---

## 1.2 Additional Networks

Created additional VNets for:

- Manufacturing (sensors + internal systems)  
- Research environment  

![1.2](Images/1.2.1.png)

![1.2](Images/1.2.2.png)

---

## 1.3 Private DNS Configuration

Configured a private DNS zone and linked it to all VNets.

![1.3](Images/1.3.1.png)

![1.3](Images/1.3.2.png)

---

# Part 2 — Virtual Machines Deployment

## 2.1 VM Deployment

Deployed testvm1 and testvm2 virtual machines in CoreServicesVnet.

![2.1](Images/2.1.1.png)

![2.1](Images/2.1.2.png)

![2.1](Images/2.1.3.png)

![2.1](Images/2.1.4.png)

---

## 2.2 Connectivity Verification

Verified VM connectivity via RDP.

![2.2](Images/2.2.1.png)

![2.2](Images/2.2.2.png)

---

## 2.3 Cross-Network VM

Deployed VM in ManufacturingVnet and validated access.

![2.3](Images/2.3.png)

---

# Part 3 — Network Connectivity

## 3.1 VNet Peering

Configured peering between CoreServicesVnet and ManufacturingVnet.

![3.1](Images/3.1.png)

---

## 3.2 Connectivity Testing

Verified communication between VMs across VNets.

![3.2](Images/3.2.png)

---

## 3.3 VPN Gateway Setup

Deployed gateways for both VNets.

![3.3](Images/3.3.png)

---

## 3.4 Peering Removal Validation

Removed peering and confirmed connectivity via gateways.

![3.4](Images/3.4.png)

---

## 3.5 Virtual WAN

Configured Virtual WAN and hub.

![3.5](Images/3.5.png)

---

## 3.6 VNet to Virtual WAN Connection

Connected ResearchVnet to Virtual WAN.

![3.6](Images/3.6.1.png)

![3.6](Images/3.6.2.png)

---

# Part 4 — DDoS Protection

## 4.1 DDoS Protection Plan

Created a DDoS protection plan.

![4.1](Images/4.1.png)

---

## 4.2 Network Protection

Applied DDoS protection to the network.

![4.2](Images/4.2.png)

---

## 4.3 Monitoring & Alerts

Configured:

- Telemetry  
- Diagnostic logs  
- Alert rules  

![4.3](Images/4.3.1.png)

![4.3](Images/4.3.2.png)

![4.3](Images/4.3.3.png)
---

# Part 5 — Azure Firewall Configuration

## 5.1 Deploy and configure Azure Firewall

Created AzureFirewallSubnet.

![5.1](Images/5.1.png)

---

## 5.2 Firewall Deployment

Deployed Azure Firewall.

![5.2](Images/5.2.1.png)

![5.2](Images/5.2.1.png)

---

## 5.3 Routing Configuration

Configured route tables for traffic control.

![5.3](Images/5.3.1.png)

![5.3](Images/5.3.2.png)

---

## 5.4 Firewall Policy (Application Rule)

Allowed outbound access to external resources (e.g. web access).

![5.4](Images/5.4.png)

---

## 5.5 Network Rule (DNS)

Configured rule to allow DNS communication.

![5.5](Images/5.5.png)

---

## 5.6 DNAT Rule

Configured Destination NAT rule for inbound access.

![5.6](Images/5.6.png)

---

# Investigation Value

This lab demonstrates:

- Enterprise-level Azure network architecture  
- Secure connectivity design between environments  
- Multi-layer network security controls  
- Real-world cloud networking patterns used in SOC environments  

---

# Skills Demonstrated

- Azure Virtual Networks & Subnetting  
- VNet Peering & VPN Gateways  
- Virtual WAN architecture  
- Azure Firewall configuration (Application + Network + DNAT)  
- DDoS protection and monitoring  
- Cloud network troubleshooting and validation  

---

## Disclaimer

All activities were performed in a **controlled lab environment using simulated infrastructure**.
