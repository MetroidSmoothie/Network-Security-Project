# Network Security Lab

_**Project Status:** Enhancements in progress. The existing virtual network environment is being expanded with additional firewall security assessments, incident investigation scenarios, Suricata detection engineering, and security control validation._

## Overview

A virtualized network security lab built with Oracle VirtualBox, pfSense, Suricata, and Linux systems. The environment simulates a small enterprise network for practicing firewall administration, network traffic analysis, intrusion detection, incident investigation, and security control validation.

**The goal of this project is to provide aspiring and entry-level cybersecurity professionals with an accessible, reproducible lab environment and structured security assessments they can complete to develop practical, hands-on skills.**

## Network Topology

![Network Security Lab Topology](images/simple-topology.png)

The environment consists of four virtual machines:

| System | Role |
|---|---|
| pfSense | Perimeter firewall, routing, NAT, and Suricata intrusion detection |
| Kali Linux | External security testing and attack simulation |
| Ubuntu Server | Internal server hosting network services |
| Debian Linux | Internal workstation for connectivity and access testing |

## Security Lab Scenarios

The lab includes simulated security tasks covering:

- Firewall rule configuration, auditing, and hardening
- NAT and network access control
- SSH brute-force detection and incident investigation
- Suricata detection engineering and rule tuning
- Network traffic analysis and threat hunting
- Security control validation and regression testing

## Documentation

- [Lab Environment Setup - Currently being updated]
- [Project Tasks - In progress]

Additional investigation, detection engineering, and validation documentation will be added as the lab develops.
