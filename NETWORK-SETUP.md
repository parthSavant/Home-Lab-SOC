# Home SOC Lab — Network Setup

## 1. Overview

This document records the virtual network configuration, IP addressing, VM inventory and connectivity validation for the Home SOC Lab.

The lab uses Oracle VirtualBox with two network interfaces per virtual machine:

- **NAT:** Provides internet connectivity for updates and downloading tools.
- **Host-only:** Provides an isolated network for communication between the host and lab virtual machines.

The objective is to keep lab traffic separate from the physical home network while allowing controlled internet access.

## 2. Network Architecture

The Host-only network uses the following configuration:

<img width="609" height="406" alt="image" src="https://github.com/user-attachments/assets/d30e1982-2088-4f02-a1ef-13007372301f" />

Static VM addresses are outside the DHCP pool to avoid address conflicts.

The NAT interfaces use DHCP and remain separate from the Host-only interfaces.

## 3. Virtual Machine Inventory

<img width="704" height="234" alt="image" src="https://github.com/user-attachments/assets/02d759db-b95e-43ce-a354-57a92fcf1bdf" />

All virtual disks are dynamically allocated.

## 4. IP Address Allocation

<img width="677" height="296" alt="image" src="https://github.com/user-attachments/assets/a675b78c-d41c-4eaf-a93b-025a962746c1" />

## 5. Network Interface Configuration

<img width="650" height="238" alt="image" src="https://github.com/user-attachments/assets/f6a86ec6-fe16-49f6-ae21-d030b1c476ca" />

### Static IP configuration

- Ubuntu Server: `192.168.56.10/24`
- Kali Linux: `192.168.56.20/24`
- Windows Server 2025: `192.168.56.30/24`
- Windows 11: `192.168.56.40/24`

DHCP is disabled on the Windows Host-only interfaces. The Linux Host-only interfaces use static addressing.

No default gateway was configured on the Host-only interfaces. Internet connectivity uses the NAT interfaces.

## 6. Connectivity Validation

The following tests were performed:

<img width="610" height="676" alt="image" src="https://github.com/user-attachments/assets/cd62f314-3ea4-4dfe-abeb-ac57674b2dba" />

ARP checks confirmed that the Windows host could resolve the MAC addresses of the lab machines.

### Firewall observations

Windows Defender Firewall did not respond to some inbound ICMP Echo Requests.

The inbound ICMPv4 Echo Request rules on the personal Windows host were left disabled. No broad firewall changes were made.

The ping limitations are documented rather than treated as proof of a network failure. Successful communication in the other directions confirms that the Host-only network is functioning.

## 7. Security and Network Design Decisions

- Lab virtual machines use a dedicated Host-only network.
- NAT is used for internet access.
- Static IP addresses are used for predictable lab communication.
- Host-only interfaces do not have default gateways.
- The personal Windows host firewall was not weakened to make ping tests succeed.
- Windows Server and Windows 11 are not yet configured as domain members or a Domain Controller.

## 8. Current Status

The initial virtual network configuration is complete.
The lab is ready to proceed to the next phase after final network documentation, diagram upload and clean snapshots.

## 9. Planned Next Steps

1. Deploy and configure Docker on Ubuntu Server.
2. Learn Linux administration and service management.
3. Prepare the Ubuntu VM for the Wazuh deployment in a later phase.
4. Continue documenting configuration changes and validation evidence.

---

**Project:** Home SOC Lab  
**Virtualisation:** Oracle VirtualBox 7.2.22  
**Host OS:** Windows 11  
**Network:** NAT + Host-only  
**Status:** Phase 1 — Network configuration and initial validation
