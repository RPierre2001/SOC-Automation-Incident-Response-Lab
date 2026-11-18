# SOC Automation, Threat Detection & Incident Response Lab

## Project Overview

This project demonstrates the design, deployment, and implementation of an end-to-end Security Operations Center (SOC) automation environment. The lab integrates endpoint monitoring, Security Information and Event Management (SIEM), Security Orchestration, Automation and Response (SOAR), threat intelligence, and incident management technologies.

The environment was developed using Oracle VirtualBox, Windows 10, Sysmon, Wazuh SIEM, Shuffle SOAR, VirusTotal API v3, and TheHive, supported by Ubuntu 24.04 LTS cloud infrastructure, Elasticsearch, and Apache Cassandra.

To validate the environment, I executed Mimikatz in a controlled Windows 10 virtual machine and observed corresponding Sysmon security events and Wazuh alerts. These alerts were forwarded to Shuffle SOAR, where I configured an automated workflow incorporating SHA-256 file hash processing, VirusTotal threat intelligence enrichment, TheHive integration, and email notifications.

## Project Objectives

- Build and configure a virtualized Windows 10 endpoint for security monitoring.
- Deploy Sysmon to collect detailed Windows security telemetry.
- Configure Wazuh SIEM to collect, monitor, and analyze endpoint security events.
- Deploy TheHive with Elasticsearch and Apache Cassandra to support incident management.
- Develop a Shuffle SOAR workflow using webhooks and VirusTotal API v3.
- Automate threat intelligence enrichment using SHA-256 file hash indicators.
- Configure automated security notifications through email.
- Simulate suspicious endpoint activity using Mimikatz in a controlled environment.
- Validate the detection and automation pipeline through Sysmon events, Wazuh alerts, and Shuffle workflow execution.

## Technologies Used

| Technology | Purpose |
|---|---|
| Oracle VirtualBox | Virtual machine management |
| Windows 10 (64-bit) | Endpoint operating system |
| Sysmon | Windows endpoint monitoring |
| Wazuh SIEM | Security event monitoring and alert generation |
| Shuffle SOAR | Security orchestration and automation |
| VirusTotal API v3 | Threat intelligence enrichment |
| TheHive | Incident response and case management |
| Elasticsearch | Search and indexing infrastructure |
| Apache Cassandra | Database infrastructure |
| Ubuntu 24.04 LTS | Cloud server operating system |
| Vultr | Cloud infrastructure provider |
| PowerShell | File integrity verification and administration |
| Mimikatz | Controlled credential-access security testing |

## Project Architecture

The SOC environment follows a security monitoring and automation workflow:

**Windows 10 Endpoint → Sysmon → Wazuh SIEM → Shuffle SOAR → VirusTotal / TheHive / Email Notifications**

The workflow demonstrates how endpoint activity can be monitored, analyzed, and processed through automated security operations.

An architecture diagram and screenshots will be added as the documentation is developed.
## Implementation Documentation

- [Phase 1: Windows 10 VM and Sysmon Setup](documentation/01-windows-sysmon-setup.md)
- [Phase 2: Wazuh SIEM Deployment](documentation/02-wazuh-deployment.md)
- [Phase 3: TheHive Incident Response Deployment](documentation/03-thehive-deployment.md)
- [Phase 4: Shuffle SOAR Automation](documentation/04-shuffle-automation.md)
- [Phase 5: Mimikatz Detection and Security Investigation](documentation/05-mimikatz-detection.md)
