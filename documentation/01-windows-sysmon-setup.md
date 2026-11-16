# Windows 10 Virtual Machine and Sysmon Configuration

## Overview

The first phase of this SOC automation project involved deploying a Windows 10 virtual machine and configuring Sysmon to collect endpoint telemetry.

The purpose of this environment was to simulate a Windows endpoint that could generate security events for collection, monitoring, and investigation through Wazuh SIEM.

## Technologies Used

- Oracle VirtualBox
- Windows 10 (64-bit)
- Microsoft Sysmon
- Windows PowerShell
- Windows Event Viewer

## Step 1: Windows 10 Virtual Machine Deployment

I used Oracle VirtualBox to create a Windows 10 (64-bit) virtual machine.

The virtual machine served as the monitored endpoint within the SOC environment.

After installing Windows, I verified that the operating system was functioning correctly before proceeding with security monitoring configuration.

## Step 2: File Integrity Verification

Before installing the required software, I used PowerShell to calculate SHA-256 hashes and verify downloaded files against their expected checksums.

Example PowerShell command:

```powershell
Get-FileHash -Path "C:\Path\To\File.exe" -Algorithm SHA256
```

This process reinforced the importance of validating software integrity before installation.

## Step 3: Sysmon Installation

I installed Microsoft Sysmon to collect detailed endpoint activity.

Sysmon provides visibility into system events that can support security investigations, including process creation and network connections, depending on the active configuration.

Example installation command:

```powershell
.\Sysmon64.exe -i
```

After installation, I verified that the Sysmon service was running.

## Step 4: Verify Sysmon Event Collection

I opened Windows Event Viewer and navigated to:

```text
Applications and Services Logs
    └── Microsoft
        └── Windows
            └── Sysmon
                └── Operational
```

I confirmed that Sysmon was generating events.

This validated the endpoint monitoring configuration before integrating the Windows system with Wazuh SIEM.

## Step 5: Create a Virtual Machine Snapshot

After verifying Sysmon functionality, I created a VirtualBox snapshot named:

`Sysmon-installed`

The snapshot preserved the configured environment and provided a recovery point for future security testing.

## Results

Successfully deployed a Windows 10 virtual machine, installed Sysmon, and verified endpoint event collection.

The environment was prepared for integration with Wazuh SIEM and subsequent security detection testing.

## Screenshots

Screenshots documenting the following will be added:

1. Windows 10 virtual machine in Oracle VirtualBox.
2. Sysmon service status.
3. Sysmon Operational log in Windows Event Viewer.
4. VirtualBox snapshot configuration.

## Lessons Learned

This phase strengthened my understanding of Windows virtualization, endpoint telemetry, file integrity verification, and security monitoring preparation.
