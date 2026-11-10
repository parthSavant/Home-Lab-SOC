# Home-Lab-SOC
This is a home lab for attack simulation, endpoint telemetry collection, KQL detection engineering, security alert investigation, and incident response.

# Home SOC Lab | Security Operations & Detection Engineering

## Overview

This project is a hands-on Security Operations Centre (SOC) lab designed to develop practical skills in cybersecurity, security monitoring, detection engineering, threat investigation and incident response.

The lab uses virtual machines to simulate a small enterprise environment containing Windows and Linux systems, Active Directory, security monitoring tools and controlled attack scenarios.

The main objective is to understand the complete security operations lifecycle:

**Attack → Telemetry → Detection → Investigation → Response → Remediation**

The project focuses on building strong cybersecurity fundamentals while gaining practical experience with modern security tools and techniques.

## Project Objectives

- Build an isolated virtual cybersecurity lab.
- Develop practical Linux and Windows administration skills.
- Configure Active Directory and understand identity and access management.
- Generate controlled attack activity against lab systems.
- Collect and analyse Windows and Linux security telemetry.
- Deploy and configure Wazuh as the primary SIEM.
- Develop and test security detection rules.
- Investigate alerts and suspicious activity.
- Analyse network traffic and endpoint forensic evidence.
- Understand Active Directory attack paths and privilege escalation.
- Practise security searches and analysis using Splunk SPL.
- Document findings, remediation and lessons learned.

## Lab Environment

<img width="506" height="629" alt="image" src="https://github.com/user-attachments/assets/7c170a23-5f6d-465d-939a-ef95916f82f5" />

Tool versions and deployment configurations will be documented as the lab is implemented.

## Lab Architecture

The environment will contain the following virtual machines:

1. **Kali Linux** — security testing and controlled attack simulation.
2. **Ubuntu Server** — Linux administration, Docker and Wazuh deployment.
3. **Windows Server 2025** — Active Directory, DNS and Group Policy.
4. **Windows 11** — domain-joined monitored endpoint.

The virtual machines will communicate over a controlled VirtualBox network.

Additional security applications, including Splunk, Velociraptor and BloodHound CE, will be deployed in later stages.

## Project Workflow

### Phase 1 — Virtualisation and Networking
- Configure VirtualBox and isolated lab networking.
- Deploy Kali Linux and Ubuntu Server.
- Configure IP addressing and test connectivity.
- Document the network architecture.

### Phase 2 — Linux Fundamentals and Docker
- Practise Linux users, groups, permissions and services.
- Configure SSH, firewall rules and system logging.
- Learn Bash and Linux administration.
- Install Docker and Docker Compose.

### Phase 3 — Windows and Active Directory
- Deploy Windows Server 2025.
- Configure Active Directory Domain Services.
- Create users, groups and organisational units.
- Configure Group Policy.
- Join Windows 11 to the domain.
- Practise PowerShell and Windows event analysis.

### Phase 4 — Wazuh SIEM Deployment
- Deploy Wazuh on Ubuntu.
- Configure Windows and Linux agents.
- Enable Sysmon and relevant audit logging.
- Validate security telemetry collection.
- Investigate generated alerts.

### Phase 5 — Attack Simulation and Detection Engineering
- Perform network discovery and scanning.
- Simulate suspicious authentication activity.
- Generate controlled endpoint attack activity.
- Use Atomic Red Team to test selected ATT&CK techniques.
- Develop and test Wazuh detection rules.
- Analyse detection accuracy and false positives.

### Phase 6 — Network and Endpoint Investigation
- Analyse network traffic using Wireshark.
- Deploy Velociraptor for endpoint investigations.
- Collect and examine forensic artefacts.
- Build incident timelines.
- Document investigation findings and remediation.

### Phase 7 — Active Directory Security
- Deploy BloodHound Community Edition.
- Collect Active Directory relationship data.
- Identify excessive permissions and attack paths.
- Investigate privilege escalation risks.
- Implement and document remediation.

### Phase 8 — Splunk and SPL
- Deploy Splunk Enterprise Free.
- Ingest selected security logs.
- Develop SPL searches.
- Analyse authentication and endpoint events.
- Compare selected investigations between Wazuh and Splunk.

### Phase 9 — Documentation and Portfolio Completion
- Publish detection rules and scripts.
- Document attack scenarios and investigations.
- Include screenshots, architecture diagrams and evidence.
- Record lessons learned and project limitations.
- Finalise the project documentation.

## Security and Lab Safety

- All attack simulations will take place within the authorised lab environment.
- Virtual networks will be configured to reduce exposure to external systems.
- Vulnerability testing and exploitation will only target systems I own or have explicit permission to test.
- VM snapshots will be used before significant configuration changes.
- Credentials and sensitive information will not be committed to GitHub.

## Project Status

**Status:** In Development

The project will be implemented incrementally. Each phase will include practical configuration, testing, evidence and documentation.

## Skills Demonstrated

- Security Operations Centre (SOC) fundamentals
- SIEM deployment and log analysis
- Detection engineering
- Windows and Linux administration
- Active Directory and identity security
- Network analysis and troubleshooting
- Endpoint monitoring and investigation
- Vulnerability assessment
- Attack simulation
- Incident response
- PowerShell, Python and Bash
- Docker and virtualisation
- MITRE ATT&CK mapping

## Learning Approach

This project prioritises practical understanding over simply installing security tools.

Each scenario will follow a structured process:

1. Understand the technology or security concept.
2. Generate or reproduce controlled activity.
3. Identify the resulting telemetry.
4. Develop or apply a detection.
5. Investigate the resulting alert.
6. Document the findings and remediation.

The aim is to build practical skills that can be demonstrated in cybersecurity, SOC, security engineering and IAM-related roles.
