# Windows Authentication Threat Detection Lab

**A hands-on security engineering project focused on centralized log monitoring, threat detection, and incident investigation using Wazuh SIEM.**

> **Project Status:** In Progress — Stage 1: Infrastructure Setup

## 1. Project Overview

This project aims to design, deploy, and evaluate a security monitoring environment capable of detecting suspicious Windows authentication activity.

The lab simulates a small enterprise environment where a Windows workstation forwards security telemetry to a centralized Wazuh SIEM server running on Ubuntu Linux.

This project aims to deepens my understanding for a complete detection lifecycle, from event generation and log collection to detection engineering, incident investigation, and security hardening.

## 2. Project Objectives

- Design and deploy an isolated virtualized security monitoring environment.
- Configure centralized Windows security event collection using Wazuh.
- Investigate Windows authentication events and their underlying mechanisms.
- Develop and validate custom detection rules for suspicious login activity.
- Simulate authentication-related security incidents in a controlled environment.
- Analyze security events to reconstruct incident timelines.
- Identify detection limitations and potential false positives.
- Implement and evaluate defensive security improvements.

## 3. Planned Lab Architecture

| Component | Technology | Purpose |
|---|---|---|
| Virtualization | VMware / VirtualBox / Hyper-V (TBD) | Host the lab environment |
| Monitoring Server | Ubuntu Server 24.04 LTS | Host the Wazuh security monitoring platform |
| SIEM | Wazuh | Centralized log collection, analysis, and alerting |
| Endpoint | Windows 11 | Generate and collect authentication-related security events |
| Endpoint Telemetry | Windows Event Logs / Sysmon | Provide security and system activity evidence |
| Networking | NAT and Host-only | Provide update access and private lab communication |

### Proposed Network Configuration

| System | Private IP Address |
|---|---|
| Ubuntu Monitoring Server | 192.168.56.10 |
| Windows Endpoint | 192.168.56.20 |

*The network design and addresses are provisional and will be verified during infrastructure setup.*

### Planned Data Flow

```text
Windows 11 Endpoint
        |
        | Windows Security Events
        v
    Wazuh Agent
        |
        | Event Forwarding
        v
    Wazuh Manager
        |
        | Event Analysis and Detection
        v
    Wazuh Indexer
        |
        v
    Wazuh Dashboard
        |
        v
Security Investigation
```

## 4. Planned Detection Scenarios

The lab will initially focus on Windows authentication monitoring.

| Scenario | Investigation Objective |
|---|---|
| Repeated failed logins | Identify potentially suspicious authentication attempts |
| Successful authentication | Examine login activity and contextual evidence |
| Failed followed by successful login | Investigate possible account compromise indicators |
| Detection false positives | Evaluate whether legitimate activity triggers alerts |
| Wazuh agent disconnection | Investigate monitoring and telemetry availability |

All scenarios will be simulated within an authorized lab environment.

## 5. Project Specifications

The project will follow eight stages:

1. **Infrastructure Setup** — Deploy and configure the virtualized lab environment.
2. **SIEM Deployment** — Install and configure Wazuh.
3. **Telemetry Collection** — Configure Windows auditing, event collection, and relevant endpoint telemetry.
4. **Attack Simulation** — Generate controlled authentication activity.
5. **Detection Engineering** — Develop and validate custom detection logic.
6. **Incident Investigation** — Analyze evidence and reconstruct security events.
7. **Security Hardening** — Implement defensive improvements and evaluate their effectiveness.
8. **Documentation and Review** — Consolidate findings, limitations, and lessons learned.

## 6. Validation Approach

Each detection scenario will be evaluated using:

- Expected behavior
- Actual observed behavior
- Supporting event logs and alerts
- Detection accuracy and potential false positives
- Technical limitations
- Recommendations for improvement

Results will be documented as testing progresses.

## 7. Findings and Results



## 8. Project Limitations

This is a controlled, small-scale laboratory environment and does not represent a production enterprise deployment.

Detection effectiveness in this environment may differ from real-world conditions due to limited endpoint diversity, simplified network architecture, and simulated activity.

---

**Disclaimer:** This project is conducted for my own personal educational and defensive security engineering purposes.
