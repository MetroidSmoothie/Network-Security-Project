
# Exercise 1 — Stateful Firewall & Network Segmentation

**Difficulty:** Beginner  
**Estimated Completion Time:** 45–60 minutes  
**Primary Tools:** pfSense, Kali Linux, Ubuntu Server
**Full Task Walkthrough:** [View Exercise Walkthrough](01-walkthrough.md)

## Overview

This exercise introduces stateful firewall inspection, network segmentation, and least-privilege access control using pfSense.

Participants will configure and test firewall rules that permit authorized traffic between isolated network segments while maintaining restrictions against unauthorized connections.

The exercise builds upon the network environment established in the [Lab Environment Setup Guide](../../Lab%20Environment%20Setup.md).

## Scenario

You are a network security administrator responsible for protecting an organization's internal network.

The organization maintains an internal Ubuntu server behind a pfSense firewall. An external testing workstation requires access to a specific TCP service hosted on that server.

Your task is to implement a firewall policy that permits only the required communication while preserving network segmentation and preventing unnecessary access to internal resources.

You must verify that the authorized connection succeeds, unauthorized traffic remains blocked, and the firewall correctly tracks established connections.

## Learning Objectives

Upon completing this exercise, participants should be able to:

1. Explain the purpose of stateful firewall inspection.
2. Identify the differences between permitted, denied, and established network connections.
3. Configure a least-privilege firewall rule using source, destination, protocol, and port restrictions.
4. Validate firewall enforcement using network connectivity tests.
5. Inspect pfSense firewall logs and connection states.
6. Restore the original firewall configuration after testing.

## Prerequisites

Before beginning, ensure that:

- The [Lab Environment Setup Guide](../../Lab%20Environment%20Setup.md) has been completed.
- All four virtual machines are operational.
- pfSense WAN and LAN interfaces are configured correctly.
- Kali can reach the pfSense WAN interface.
- Kali-to-LAN traffic is blocked by the default WAN firewall policy.
- Ubuntu has an active IPv4 address on the protected LAN.
- Administrator access to pfSense and Ubuntu is available.

### Lab Systems

| System | Role | IPv4 Address |
|---|---|---|
| pfSense WAN | External firewall interface | `192.168.50.1/24` |
| pfSense LAN | Internal firewall interface | `172.16.77.1/24` |
| Kali Linux | External testing workstation | `192.168.50.10/24` |
| Ubuntu Server | Protected internal server | DHCP (previously `172.16.77.10`) |
| Debian Linux | Additional protected endpoint | DHCP (previously `172.16.77.11`) |

> **Note:** Ubuntu and Debian use DHCP. Confirm their current IPv4 addresses before performing connectivity tests.

## Assessment Tasks

Participants will complete the following tasks:

1. **Identify an Internal Service**  
   Identify a TCP service listening on the Ubuntu server and determine its associated port.

2. **Establish Baseline Connectivity**  
   Verify that the default pfSense WAN firewall policy prevents Kali from accessing the selected internal service.

3. **Configure a Least-Privilege Firewall Rule**  
   Create a rule allowing Kali to communicate with the selected service on Ubuntu without granting unrestricted access to the internal network.

4. **Validate Authorized and Unauthorized Traffic**  
   Confirm that the permitted connection succeeds while traffic outside the authorized rule remains blocked.

5. **Inspect Stateful Connections**  
   Examine pfSense connection states and determine how the firewall tracks established communication.

6. **Review Firewall Logs**  
   Identify relevant permitted or blocked traffic and correlate the entries with connectivity tests.

7. **Restore the Baseline**  
   Remove the temporary firewall exception and verify that the original restrictions are enforced.

## Validation & Expected Results

Successful completion requires demonstrating that:

- The selected Ubuntu service is reachable when the appropriate firewall exception and network routing are configured.
- Traffic outside the permitted source, destination, protocol, and port remains restricted.
- pfSense maintains connection states for authorized traffic.
- Firewall logs provide evidence of policy enforcement.
- The original WAN-to-LAN restrictions are restored after testing.

## Troubleshooting
- Common troubleshooting issues and resolutions are included at the end of each exercise walkthrough file.

## Knowledge Check

1. What distinguishes a stateful firewall from a stateless firewall?
2. Why should a firewall rule specify an exact source, destination, protocol, and destination port?
3. How does pfSense handle return traffic for an established connection?
4. What is the difference between a firewall rule and an entry in the firewall state table?
5. Why is it important to verify denied traffic after creating an allow rule?

## Cleanup & Reset

At the conclusion of the exercise, participants should restore the original firewall configuration and confirm that the default WAN-to-LAN restrictions remain effective.
