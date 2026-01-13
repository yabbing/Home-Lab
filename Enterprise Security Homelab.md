Overview

This repository documents the design, build, and ongoing development of an enterprise style cybersecurity homelab. The lab is designed to simulate real world infrastructure used in corporate environments, with a strong focus on networking, segmentation, monitoring, detection, and attack and defense scenarios.

The primary purpose of this lab is hands on learning and skill development for SOC Analyst, Junior Security Engineer, and Penetration Testing roles.

Objectives

Build a realistic enterprise style network environment

Gain hands on experience with VLANs, firewalls, and segmentation

Deploy and manage Proxmox virtualization infrastructure

Create an Active Directory attack and defense lab

Practice SOC workflows including monitoring, detection, and investigation

Develop troubleshooting and documentation skills aligned with real world IT and security roles

Lab Architecture Overview
Virtualization Platform

Proxmox VE used as the primary hypervisor platform

Multiple Proxmox nodes planned for clustering

Linux bridges used for VM networking

Static IP addressing for management interfaces

Cluster ready flat network implemented before VLAN segmentation

Network Design

Base LAN subnet: 192.168.1.0/24

Managed switch with VLAN capability

VLAN segmentation designed for:

Management

Production services

Security lab and attack testing

Trunk and access ports configured manually

Common enterprise networking issues encountered and resolved:

Incorrect PVID assignments

Untagged traffic failures

Misconfigured trunk ports

Firewall and Routing

OPNsense deployed as a virtual firewall appliance

Intended roles:

Inter VLAN routing

Traffic filtering and firewall policy enforcement

Gateway for lab networks

WAN and LAN interfaces configured

Firewall rule testing performed to validate segmentation and isolation

Active Directory Lab

Windows Server deployed as Active Directory Domain Services

Domain users, groups, and policies configured

Multiple Windows client systems joined to the domain

Group Policy Objects used to simulate real enterprise environments

Environment designed to support:

Credential attacks

Privilege escalation testing

Lateral movement scenarios

Both hardened and intentionally vulnerable configurations tested

Security Tooling

The following tools are deployed or planned within the lab:

Wazuh for host based monitoring and security event collection

Elastic Stack for log aggregation, visualization, and analysis

Snort for network based intrusion detection

OpenVAS and Nessus for vulnerability scanning and exposure analysis

Kali Linux for controlled attack simulation and testing

SOC and Detection Use Cases

This lab supports realistic SOC workflows, including:

Centralized log collection from servers, endpoints, and network devices

Detection of suspicious authentication activity

Monitoring lateral movement and privilege escalation attempts

Investigating alerts using SIEM dashboards and raw log analysis

Validating firewall rules and segmentation effectiveness

Troubleshooting and Lessons Learned

Throughout the build process, several real world issues were encountered and resolved:

Proxmox nodes inaccessible due to switch VLAN misconfiguration

Loss of connectivity caused by incorrect firewall gateway assignment

VLAN aware bridging considerations in Proxmox

Importance of flat networking prior to cluster creation

Each issue was documented to reinforce troubleshooting methodology and networking fundamentals.

Current Status

Proxmox primary node operational

Second Proxmox node prepared for cluster join

Flat network validated for clustering

Firewall partially inline

VLAN segmentation in staged rollout

Planned Enhancements

Full Proxmox cluster configuration

Dedicated management VLAN

Dedicated Corosync or cluster network

Full firewall enforcement for all lab traffic

Expanded detection rules and alert tuning

Automated attack simulation for detection validation

Detailed network diagrams and architecture visuals

Why This Lab Matters

This homelab is intentionally designed to mirror real enterprise environments. Rather than focusing only on tools, the emphasis is placed on architecture, networking fundamentals, security boundaries, and operational troubleshooting.

The skills developed through this lab directly translate to entry level and junior roles in:

Security Operations

Network and Systems Administration

Penetration Testing

Vulnerability Management

Author

Built and maintained by an aspiring cybersecurity professional focused on continuous learning, hands on experience, and real world skill development.
