# 🛡️ Home SOC Lab Using Wazuh

## Overview

This project demonstrates the creation of a Home Security Operations Center (SOC) Lab using Wazuh, VirtualBox, Windows 11, Kali Linux, and VirusTotal.

The objective of this lab was to gain hands-on experience with SIEM deployment, endpoint monitoring, threat detection, File Integrity Monitoring (FIM), and basic threat intelligence integration.

---

## Architecture

![SOC Architecture](SOC-Architecture.png)

### Lab Components

| Component      | Purpose                 |
| -------------- | ----------------------- |
| Wazuh OVA      | SIEM Platform           |
| Windows 11 VM  | Monitored Endpoint      |
| Kali Linux VM  | Attack Simulation       |
| VirtualBox     | Virtualization Platform |
| VirusTotal API | Threat Intelligence     |

---

## Environment Setup

### Host Machine

* Windows 11
* 16 GB RAM
* VirtualBox

### Virtual Machines

#### Wazuh OVA

* Wazuh Manager
* Wazuh Dashboard
* Elasticsearch

#### Windows 11 VM

* Registered as Wazuh Agent
* Generates security events

#### Kali Linux VM

* Used for attack simulation and testing

---

## Security Monitoring Use Cases

### Failed Login Detection

Performed multiple failed login attempts on the Windows endpoint.

**Result:** Wazuh successfully detected authentication failures and generated alerts.

---

### User Account Creation

Created a new local Windows account.

```cmd
net user testuser Password123! /add
```

**Result:** Wazuh detected account creation activity.

---

### User Account Deletion

Deleted the previously created user account.

```cmd
net user testuser /delete
```

**Result:** Wazuh detected account deletion activity.

---

### File Integrity Monitoring (FIM)

Configured Syscheck to monitor:

```text
C:\SOC-Test
```

Created and deleted files within the monitored directory.

**Result:** Wazuh generated real-time file monitoring alerts.

---

### VirusTotal Integration

Integrated VirusTotal API with Wazuh to enrich file monitoring capabilities.

Configured:

```xml
<integration>
  <name>virustotal</name>
  <group>syscheck</group>
</integration>
```

**Result:** Wazuh successfully monitored file activity and was configured for threat intelligence enrichment.

---

## Screenshots

* SOC Architecture
* Agent Connected
* Failed Login Alert
* User Creation Alert
* User Deletion Alert
* File Integrity Monitoring Alert
* Threat Hunting Dashboard

---

## Key Skills Demonstrated

* SIEM Deployment
* Wazuh Administration
* Endpoint Monitoring
* Threat Detection
* File Integrity Monitoring (FIM)
* Threat Intelligence Integration
* Security Event Analysis
* Incident Investigation

---

## Lessons Learned

Through this project I learned:

* How SIEM platforms collect and analyze logs
* How Wazuh agents communicate with the manager
* Authentication monitoring and account auditing
* File Integrity Monitoring
* Security event investigation workflows
* Basic SOC operations

---

## Future Improvements

* Install Sysmon for advanced telemetry
* Monitor Linux endpoints
* Create custom Wazuh rules
* Simulate attacks using Atomic Red Team
* Perform threat hunting exercises

---

## Author

**Hemanth Taduku**

SOC Analyst | Home Lab Enthusiast | Cybersecurity Learner
