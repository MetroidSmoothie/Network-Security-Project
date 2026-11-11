
# Exercise 2 — Exposed Service Hardening

**Difficulty:** Beginner–Intermediate  
**Estimated Completion Time:** 45–60 minutes  
**Primary Tools:** Ubuntu Server, Kali Linux, pfSense, Nmap  
**Full Task Walkthrough:** [View Exercise Walkthrough](02-walkthrough.md)

## Overview

This exercise introduces network service enumeration, attack surface reduction, and service hardening within a segmented virtual network.

Participants will identify services running on an internal Ubuntu server, assess their exposure, and implement security controls to reduce unnecessary network access while preserving legitimate functionality.

The exercise builds upon the network environment established in the [Lab Environment Setup Guide](../../Lab%20Environment%20Setup.md).

## Scenario

You are a network security administrator responsible for securing an organization's internal servers.

A routine security assessment has identified an Ubuntu server hosting multiple network services. Some services may be unnecessary, improperly configured, or accessible from network segments that do not require them.

Your task is to identify the server's exposed services, evaluate their security implications, and implement appropriate hardening measures.

You must verify that unnecessary services are no longer exposed, authorized functionality remains operational, and the server's overall attack surface has been reduced.

## Learning Objectives

Upon completing this exercise, participants should be able to:

1. Identify listening TCP and UDP services on a Linux server.
2. Enumerate network-accessible services using Nmap.
3. Distinguish between locally listening services and services accessible from remote network segments.
4. Evaluate unnecessary services and insecure network exposure.
5. Apply service-level hardening and least-privilege access restrictions.
6. Validate security improvements using before-and-after service enumeration.
7. Restore the required lab configuration after testing.

## Prerequisites

Before beginning, ensure that:

- The [Lab Environment Setup Guide](../../Lab%20Environment%20Setup.md) has been completed.
- Exercise 1 — Stateful Firewall & Network Segmentation has been completed.
- All four virtual machines are operational.
- pfSense WAN and LAN interfaces are configured correctly.
- Kali can reach the pfSense WAN interface.
- The default pfSense WAN policy blocks unauthorized access to the internal network.
- Ubuntu has an active IPv4 address on the protected LAN.
- Ubuntu's persistent return route to Kali's subnet is configured.
- Nmap is available on Kali Linux.
- Administrator access to Ubuntu and pfSense is available.

### Lab Systems

| System | Role | IPv4 Address |
|---|---|---|
| pfSense WAN | External firewall interface | `192.168.50.1/24` |
| pfSense LAN | Internal firewall interface | `172.16.77.1/24` |
| Kali Linux | External security assessment workstation | `192.168.50.10/24` |
| Ubuntu Server | Internal server undergoing hardening | DHCP (previously `172.16.77.10`) |
| Debian Linux | Additional protected endpoint | DHCP (previously `172.16.77.11`) |

> **Note:** Ubuntu and Debian use DHCP. Confirm their current IPv4 addresses before performing connectivity tests.

## Assessment Tasks

Participants will complete the following tasks:

1. **Identify Listening Services**  
   Enumerate active TCP and UDP services on Ubuntu and identify their associated ports, processes, and listening interfaces.

2. **Assess Network Service Exposure**  
   Use Nmap to identify remotely accessible services and compare the results with Ubuntu's locally listening services.

3. **Establish a Security Baseline**  
   Document existing service configurations, network accessibility, and security controls before making changes.

4. **Implement Service Hardening**  
   Disable or restrict an unnecessary service and apply appropriate configuration changes to reduce network exposure.

5. **Validate Hardening Measures**  
   Repeat service enumeration and network scans to confirm that the selected exposure has been eliminated or restricted without disrupting authorized functionality.

6. **Review Security Evidence**  
   Examine service status, listening sockets, and scan results to verify the effectiveness of the hardening measures.

7. **Cleanup & Reset**  
   Restore temporary exercise configurations as appropriate, preserve required baseline settings, and verify that the lab is ready for subsequent exercises.

## Validation & Expected Results

Successful completion requires demonstrating that:

- Active TCP and UDP services are identified and associated with their listening ports and processes.
- Network scanning distinguishes accessible services from those blocked by firewall restrictions.
- At least one unnecessary or overly exposed service is identified and appropriately hardened.
- Before-and-after testing demonstrates a measurable reduction in unnecessary service exposure.
- Required services remain operational following hardening.
- The final server and network configurations are verified and documented.

## Knowledge Check

1. What is the difference between a listening network service and a remotely accessible service?
2. Why can an unnecessary listening service increase a server's attack surface?
3. How can Nmap be used to validate whether a service is accessible from another network segment?
4. What is the difference between disabling a service and restricting access to it through a firewall?
5. Why is it important to verify legitimate service functionality after implementing hardening measures?

## Cleanup & Reset

At the conclusion of the exercise, participants should remove temporary testing configurations and verify that required services remain operational.

Any hardening changes intended to become part of the lab's security baseline should be documented and retained. Temporary firewall exceptions or other exercise-specific changes should be reversed.

Detailed cleanup instructions and final configuration verification steps are provided in the [Exercise 2 Walkthrough](02-walkthrough.md).

