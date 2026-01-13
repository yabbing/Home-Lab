# Enterprise Security Homelab

## Overview

This repository documents the design, build, and ongoing development of an enterprise style cybersecurity homelab.

The lab is designed to simulate real world infrastructure used in corporate environments, with a strong focus on networking, segmentation, monitoring, detection, and attack and defense scenarios.

The primary purpose of this lab is hands on learning and skill development for:
- SOC Analyst roles
- Junior Security Engineer roles
- Penetration Testing roles

---

## Objectives

The core objectives of this homelab include:

- Build a realistic enterprise style network environment
- Gain hands on experience with VLANs, firewalls, and network segmentation
- Deploy and manage Proxmox virtualization infrastructure
- Create an Active Directory attack and defense lab
- Practice SOC workflows including monitoring, detection, and investigation
- Develop troubleshooting and documentation skills aligned with real world IT and security roles

---

## Lab Architecture Overview

### Virtualization Platform

- Proxmox VE used as the primary hypervisor platform
- Multiple Proxmox nodes planned for clustering
- Linux bridges used for VM networking
- Static IP addressing for management interfaces
- Flat network implemented prior to VLAN segmentation to support clustering

---

### Network Design

- Base LAN subnet: `192.168.1.0/24`
- Managed switch with VLAN capability
- VLAN segmentation designed for:
  - Management network
  - Production services
  - Security lab and attack testing
- Manual configuration of access and trunk ports
- Real world networking issues encountered and resolved:
  - Incorrect PVID assignments
  - Untagged traffic failures
  - Misconfigured trunk ports
  - Loss of connectivity due to VLAN mismatch

---

### Firewall and Routing

- OPNsense deployed as a virtual firewall appliance
- Firewall responsibilities include:
  - Inter VLAN routing
  - Traffic filtering and security policy enforcement
  - Acting as the default gateway for lab networks
- WAN and LAN interfaces configured and tested
- Firewall rule validation performed to confirm segmentation and isolation

---

## Proxmox Infrastructure

### Node Configuration

- Primary Proxmox node deployed with static IP configuration
- Second Proxmox node prepared for cluster integration
- Proxmox web interface accessible on port 8006
- Linux bridge `vmbr0` used for host and VM networking

### Networking Considerations

- Physical NICs bridged directly to Proxmox
- VLAN tagging planned after cluster creation
- VLAN aware bridging evaluated for future segmentation
- Emphasis placed on maintaining reliable management connectivity

---

## Active Directory Lab

- Windows Server deployed as Active Directory Domain Services
- Domain users, groups, and organizational units configured
- Group Policy Objects created to simulate enterprise controls
- Multiple Windows client systems joined to the domain
- Environment designed to support:
  - Credential attacks
  - Privilege escalation testing
  - Lateral movement scenarios
- Both hardened and intentionally vulnerable configurations tested

---

## Security Tooling

The following security tools are deployed or planned within the lab:

- Wazuh for host based monitoring and security event collection
- Elastic Stack for log aggregation, visualization, and analysis
- Snort for network based intrusion detection
- OpenVAS and Nessus for vulnerability scanning and exposure analysis
- Kali Linux for controlled attack simulation and testing

---

## SOC and Detection Use Cases

This lab supports realistic Security Operations workflows, including:

- Centralized log collection from servers, endpoints, and network devices
- Detection of suspicious authentication behavior
- Monitoring lateral movement and privilege escalation attempts
- Investigation of alerts using SIEM dashboards and raw log analysis
- Validation of firewall rules and network segmentation effectiveness

---

## Troubleshooting and Lessons Learned

Throughout the build process, several real world issues were encountered and resolved:

- Proxmox nodes inaccessible due to switch VLAN misconfiguration
- Loss of network connectivity caused by incorrect firewall gateway settings
- VLAN aware bridging misconfigurations in Proxmox
- Importance of maintaining a flat network prior to cluster formation

Each issue was documented to reinforce troubleshooting methodology and networking fundamentals.

---

## Current Status

- Primary Proxmox node operational
- Secondary node prepared for cluster join
- Flat network validated for clustering
- Firewall partially inline
- VLAN segmentation staged for incremental rollout

---

## Planned Enhancements

- Full Proxmox cluster configuration
- Dedicated management VLAN
- Dedicated Corosync or cluster communication network
- Firewall enforced segmentation for all lab traffic
- Expanded detection rules and alert tuning
- Automated attack simulation for detection validation
- Detailed network diagrams and architecture visuals

---

## Repository Structure

Planned repository organization:

- `/docs`  
  Design documentation and written walkthroughs

- `/diagrams`  
  Network diagrams and architecture visuals

- `/configs`  
  Firewall rules, switch configurations, and system settings

- `/notes`  
  Troubleshooting logs, lessons learned, and observations

---

## Why This Lab Matters

This homelab is intentionally designed to mirror real enterprise environments.

The focus is placed on:
- Architecture and network design
- Security boundaries and segmentation
- Monitoring and detection workflows
- Real world troubleshooting and problem solving

The skills developed through this lab directly translate to entry level and junior roles in:
- Security Operations
- Network and Systems Administration
- Penetration Testing
- Vulnerability Management

---

## Author

Built and maintained by an aspiring cybersecurity professional focused on continuous learning, hands on experience, and real world skill development.
