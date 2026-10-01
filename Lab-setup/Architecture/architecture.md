# Home SOC Lab Architecture

## 1. Project Objective

The Home SOC Lab is a controlled cybersecurity environment designed to demonstrate the complete security monitoring and incident response lifecycle.

The core workflow is:

Attack
  ↓
Target
  ↓
Telemetry
  ↓
SIEM
  ↓
Detection
  ↓
Alert
  ↓
Analyst Triage
  ↓
Investigation
  ↓
Evidence Collection
  ↓
Severity Assessment
  ↓
Response
  ↓
Incident Documentation

The goal is to demonstrate practical SOC skills rather than simply installing security tools.

---

## 2. Lab Architecture

The lab will use Oracle VirtualBox to host the virtual machines and Docker to provide containerized services.

### Core Components

Component -	Role
Kali Linux -	Attacker and security testing workstation
Windows -	Windows endpoint and primary endpoint telemetry source
Ubuntu -	Linux endpoint and security infrastructure
Metasploitable2 -	Intentionally vulnerable target
bWAPP -	Intentionally vulnerable web application
Wazuh -	Primary local security monitoring and SIEM platform
Docker -	Container platform for vulnerable applications, security services, automation and future tooling
Sysmon -	Detailed Windows endpoint telemetry
KQL -	Detection/query language practice and future SIEM portability
Oracle VirtualBox -	Virtualization platform

---

## 3. Attack Layer

Kali Linux will be used to generate controlled security activity against isolated lab targets.

Planned activity includes:

* Authentication attacks
* Network reconnaissance
* Vulnerability scanning
* Exploitation of intentionally vulnerable systems
* Web application attacks against bWAPP
* Suspicious PowerShell activity
* Other controlled attack scenarios added as the lab develops

All offensive activity will remain inside the isolated lab environment.

---

## 4. Target Layer

The lab will contain multiple target systems so that different types of telemetry and attack techniques can be investigated.

### Windows

Used to demonstrate:

* Windows authentication events
* Process execution
* PowerShell activity
* Sysmon telemetry
* Endpoint detection and investigation

### Ubuntu

Used to demonstrate:

* Linux authentication activity
* System logs
* Process activity
* Network activity
* Linux security monitoring

### Metasploitable2

Used as an intentionally vulnerable target for:

* Vulnerability assessment
* Exploitation
* Attack simulation
* Detection engineering

### bWAPP

bWAPP will run as a Docker-based vulnerable web application.

It will be used for:

* Web attack simulation
* Web log analysis
* Detection development
* Investigation exercises

---

## 5. Telemetry Layer

The lab will generate security-relevant telemetry from multiple sources.

Planned telemetry sources include:

* Windows Event Logs
* Sysmon
* Linux system and authentication logs
* Web application logs
* Network-related events
* Wazuh agent telemetry

Telemetry will provide the evidence required to detect and investigate simulated attacks.

---

## 6. SIEM and Monitoring Layer

Wazuh will be the primary local security monitoring and SIEM platform.

The initial goal is to build a working local monitoring pipeline:


Endpoint / Application
        ↓
      Logs
        ↓
   Wazuh Agent
        ↓
   Wazuh Server
        ↓
   Detection / Alert
        ↓
   Analyst Investigation

Wazuh will be used for:

* Log collection
* Security monitoring
* Alert generation
* Detection rules
* Searching and investigation
* Endpoint visibility

The SIEM environment will be built locally rather than relying on a paid cloud SIEM subscription.

---

## 7. KQL

KQL will be developed as a separate detection-engineering skill.

The project will use Microsoft's available KQL practice/demo environment for learning and developing queries.

The project will **not** claim that lab telemetry is being ingested into Microsoft Sentinel unless a real Sentinel environment is later configured.

Where appropriate, detection concepts developed in the local lab can be translated into KQL to demonstrate transferable detection-engineering skills.

---

## 8. Detection Layer

Detection engineering will follow this process:

Attack Technique
      ↓
Expected Behaviour
      ↓
Telemetry Source
      ↓
Detection Logic
      ↓
Detection Rule / Query
      ↓
Controlled Test
      ↓
False Positive Analysis
      ↓
Documentation

Each detection should have a clear relationship between the attack, the telemetry it produces, and the logic used to identify it.

---

## 9. Analyst Workflow

The analyst is the final decision-maker in the SOC workflow.

Automation and AI may assist with analysis, enrichment and prioritisation, but they will not replace the analyst's final assessment.

The investigation process will include:

1. Alert triage
2. Initial validation
3. Evidence collection
4. Timeline construction
5. Indicator identification
6. Attack reconstruction
7. Severity assessment
8. Response decision
9. Incident documentation
10. Lessons learned

---

## 10. Docker Strategy

Docker will be used as a broader security engineering platform rather than only for bWAPP.

Planned uses include:

* Vulnerable applications
* Security services
* Log collection components
* Python security tools
* APIs
* Automation services
* Dashboards
* Docker Compose-based lab services
* Future local AI services

Docker will be introduced where it provides a practical security or engineering benefit.

---

## 11. Automation

Python will eventually be used to automate repetitive SOC and security engineering tasks.

Potential capabilities include:

* SIEM API interaction
* Alert retrieval
* IOC extraction
* Threat intelligence enrichment
* Log processing
* Investigation support
* Report generation
* Security validation and auditing

Automation will be introduced after the manual investigation workflow is functional.

---

## 12. Future AI Integration

AI will be introduced only after the underlying detection and investigation workflow works manually.

The planned AI-assisted SOC workflow is:

SIEM Alert
    ↓
Context Gathering
    ↓
Python Automation
    ↓
Local AI Model
    ↓
Suggested Analysis
    ↓
Analyst Review
    ↓
Final Decision

Potential future capabilities include:

* Alert summarisation
* Investigation assistance
* Log analysis
* IOC extraction
* Investigation context gathering
* Suggested next investigative steps
* Draft incident reports

The AI system will remain an analyst-assistance layer rather than the final authority.

---

## 13. Project Philosophy

The project combines modern security technologies with fundamental cybersecurity skills.

Each technology should support a specific security objective:

| Technology      | Security Objective                              |
| --------------- | ----------------------------------------------- |
| VirtualBox      | Virtualisation and lab isolation                |
| Kali Linux      | Offensive security and attack simulation        |
| Windows         | Endpoint security and telemetry                 |
| Sysmon          | Detailed endpoint visibility                    |
| Ubuntu          | Linux security monitoring                       |
| Metasploitable2 | Vulnerability assessment and exploitation       |
| Docker          | Reproducible security services and applications |
| Wazuh           | Security monitoring and SIEM                    |
| KQL             | Detection engineering and query skills          |
| Python          | Security automation                             |
| APIs            | Security tool integration                       |
| Local AI        | Analyst assistance and advanced experimentation |

The project prioritises understanding the security workflow over collecting tools.

---

## 14. Project Development Approach

The lab will be developed incrementally.

The development sequence is:

Architecture
    ↓
Networking
    ↓
Telemetry
    ↓
SIEM
    ↓
Attack Scenarios
    ↓
Detection Engineering
    ↓
Investigation
    ↓
Automation
    ↓
AI-Assisted Triage

Each stage should produce a working, documented artifact before moving to the next stage.

The lab itself is not the final product.

The final portfolio evidence should demonstrate the ability to:

* Generate security events
* Collect telemetry
* Detect suspicious activity
* Investigate alerts
* Gather evidence
* Assess severity
* Respond to incidents
* Document findings
* Automate repetitive tasks
* Apply AI responsibly to security workflows
