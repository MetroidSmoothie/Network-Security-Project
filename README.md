# Network Security Lab Environment

## Overview

This project simulates a small enterprise network deployed inside a controlled virtual lab environment.  
The objective is to build, validate, and secure the network infrastructure while responding to operational security tasks as if acting as an external security analyst.

The environment is intentionally resource-intensive and designed to mimic real-world enterprise troubleshooting, validation, and defensive security workflows.

_Note: Configured .ova files are maintained off GitHub_

## Project Goals

- Deploy a multi-VM enterprise network
- Validate connectivity and segmentation
- Understand firewall/NAT behavior
- Test internal vs external access paths
- Perform security configuration and remediation tasks
- Work efficiently under realistic operational constraints


## Lab Phases

### Phase 1 – Environment Preparation
- Import all provided virtual machines
- Configure networking
- Validate communication between systems
- Ensure the environment is stable and ready

### Phase 2 – Security Operations
- Receive security-related configuration or remediation tasks
- Address each issue sequentially
- Restore secure and functional network services
- Operate quickly and methodically as if supporting a production business environment



## System Requirements & Recommendations

To ensure proper performance:

- Shut down all non-lab VMs
- Close non-essential applications
- Stop background services (email, browsers, messaging apps, etc.)
- Allocate sufficient RAM (12GB+ recommended)

This lab consumes significant host resources.



## Network Scenario

Your physical host represents the **external internet**.

The provided VMs represent:
- perimeter defenses
- internal infrastructure
- internal clients
- external testing systems


## Virtual Machines

### VM1 – pfSense Firewall
Acts as the perimeter gateway between the internet and internal lab network.

Functions:
- NAT routing
- DHCP server (LAN)
- Default gateway
- Suricata IDS/IPS
- OpenVPN services

WAN receives DHCP from the host network  
LAN provides internal addressing



### VM2 – Kali Linux
Security testing workstation.

Purpose:
- scanning
- enumeration
- testing
- troubleshooting

Runs in **bridged mode** and receives an IP on the same subnet as the host.



### VM3 – Ubuntu Server
Internal service host.

Functions:
- Web services
- Internal application simulation

No configuration changes required.



### VM4 – Debian Client
Represents internal users.

Purpose:
- client testing
- connectivity validation
- remote access checks

Receives IP via DHCP from pfSense.



## Environment Workflow

1. Import appliances
2. Configure network adapters
3. Start VMs in sequence
4. Verify IP addressing
5. Confirm routing between segments
6. Validate services
7. Begin security tasks



## Skills Demonstrated

- Virtual network design
- Firewall configuration (pfSense)
- NAT and segmentation
- DHCP/DNS troubleshooting
- Host and service validation
- Security operations mindset
- Enterprise-style lab management
