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

### SOC Architecture Diagram

![SOC Automation and Incident Response Architecture](soc-architecture.png)
## Implementation Documentation

- [Phase 1: Windows 10 VM and Sysmon Setup](documentation/01-windows-sysmon-setup.md)
- [Phase 2: Wazuh SIEM Deployment](documentation/02-wazuh-deployment.md)
- [Phase 3: TheHive Incident Response Deployment](documentation/03-thehive-deployment.md)
- [Phase 4: Shuffle SOAR Automation](documentation/04-shuffle-automation.md)
- [Phase 5: Mimikatz Detection and Security Investigation](documentation/05-mimikatz-detection.md)
## Project Results

This SOC automation lab demonstrated the integration of endpoint monitoring, security event detection, and automated incident notification within a controlled environment.

### Key Accomplishments

- **Endpoint Monitoring:** Deployed a Windows 10 virtual machine with Sysmon and a Wazuh agent to collect and forward endpoint security telemetry.
- **SIEM Deployment:** Configured Wazuh on an Ubuntu 24.04 LTS cloud server to monitor endpoint activity and generate security alerts.
- **Threat Detection:** Executed Mimikatz in an isolated testing environment and observed corresponding security events and Wazuh alerts.
- **Security Automation:** Configured a Shuffle SOAR workflow to receive Wazuh alerts through a webhook and process SHA-256 file hashes.
- **Threat Intelligence:** Integrated VirusTotal API v3 into the Shuffle workflow to support file-hash reputation lookups.
- **Incident Management:** Deployed TheHive with Elasticsearch and Apache Cassandra and configured its integration with Shuffle.
- **Automated Notifications:** Verified that Shuffle successfully delivered an email notification associated with the security alert.

### Skills Demonstrated

- Security Information and Event Management (SIEM)
- Security Orchestration, Automation, and Response (SOAR)
- Endpoint Monitoring and Log Analysis
- Security Alert Investigation
- Threat Intelligence Integration
- Incident Response Workflows
- Linux Server Administration
- Cloud Infrastructure Deployment
- Windows Event Analysis
- Technical Troubleshooting and Documentation

### Project Scope

This project was developed as a personal cybersecurity home lab for educational and professional development purposes.

All security testing was performed within an isolated, authorized environment. The project demonstrates detection, alert processing, threat intelligence integration, and notification workflows rather than a production SOC deployment.
## Project Highlights

The following screenshots demonstrate key components of the SOC automation environment, including endpoint monitoring, security detection, and automated alert processing.

### 1. Wazuh SIEM Dashboard

The Wazuh dashboard provides centralized visibility into security activity collected from the Windows 10 endpoint.

![Wazuh SIEM Dashboard](screenshots/Wazuh-agent-dashboard.png)

### 2. Mimikatz Security Detection

Wazuh generated security alerts associated with controlled Mimikatz testing inside the Windows 10 virtual machine.

![Mimikatz Detection](screenshots/Wazuh-Mimikatz-alerts.png)

### 3. Shuffle SOAR Automation Workflow

The Shuffle workflow connects alert processing with SHA-256 hash handling, VirusTotal threat intelligence, and incident response integrations.

![Shuffle SOAR Workflow](screenshots/shuffle-workflow.png)

### 4. TheHive Incident Response Integration

TheHive was configured as an incident management platform within the automated workflow.

![TheHive Integration](screenshots/Thehive-integration.png)

### 5. Automated Email Notification

Shuffle successfully delivered an automated email notification associated with the security alert.

![Automated Security Alert](screenshots/shuffle-email-notification.png)
## Challenges, Troubleshooting, and Lessons Learned

Throughout the development of this SOC automation lab, I encountered and resolved several technical challenges involving security tool deployment, configuration, and integration.

### 1. TheHive Deployment and Service Configuration

**Challenge:** Encountered configuration issues involving Elasticsearch while deploying TheHive on an Ubuntu cloud server.

**Resolution:** Investigated service configuration files, identified conflicting Elasticsearch cluster initialization settings, corrected the configuration, and verified that the required services were running.

**Skills Demonstrated:** Linux administration, service troubleshooting, configuration management, and log analysis.

### 2. Wazuh Manager Configuration Error

**Challenge:** Wazuh Manager failed to restart after modifications to the Shuffle webhook integration in `ossec.conf`.

**Resolution:** Examined Wazuh error logs, identified an XML formatting issue involving the webhook configuration, corrected the affected XML tags, and validated the configuration before restarting the service.

**Result:** Successfully restored Wazuh Manager to an active and running state.

**Skills Demonstrated:** XML configuration troubleshooting, Linux command-line administration, service management, and log analysis.

### 3. Shuffle Webhook Replacement

**Challenge:** Needed to replace an existing Shuffle webhook URL without rebuilding the SOC automation workflow.

**Resolution:** Created a replacement webhook, updated the Wazuh Manager integration, restarted Wazuh, and verified that Shuffle received new executions.

**Result:** Confirmed successful workflow executions and disabled the original webhook.

**Skills Demonstrated:** SIEM-to-SOAR integration, webhook management, automation troubleshooting, and security configuration maintenance.

### Key Lessons Learned

- Security monitoring depends on accurate endpoint telemetry collection and properly configured detection rules.
- Custom SIEM rules can improve visibility into specific adversary techniques.
- XML configuration errors can prevent critical security services from starting.
- SIEM-to-SOAR integrations require validation of both alert forwarding and downstream automation.
- Troubleshooting security infrastructure requires examining logs, testing configurations, and verifying service health.
- Protecting webhook URLs and API credentials is an important part of maintaining secure automation workflows.
