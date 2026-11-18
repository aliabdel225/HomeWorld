# Welcome to My HomeWorld Project.

# 🛡️ PROJECT HOMEWORLD
### Building a Real-World Home IT Department

**Project Owner:** Ali Abdelghani  
**Project Type:** IT Infrastructure | Systems Administration | Network Security | Cybersecurity  
**Environment:** Physical Hardware + Virtualized Server Infrastructure  
**Status:** Active Development  
**Started:** November 2026

---

## 1. Project Overview

**HOMEWORLD** is a hands-on IT infrastructure and cybersecurity project designed to transform a residential network into a professionally managed IT environment.

The objective is to build, configure, secure, monitor, and maintain an operational IT department using actual household devices and enterprise technologies.

Rather than relying entirely on isolated virtual machines, HOMEWORLD integrates physical endpoints, a Windows Server domain controller, Linux administration, centralized authentication, network management, and security monitoring.

The project simulates the responsibilities of an IT Support Technician, Systems Administrator, Network Administrator, and Security Analyst.

### Mission

> Design and operate a secure, reliable, documented, and manageable home infrastructure that demonstrates practical enterprise IT and cybersecurity skills.

## 2. Project Objectives

HOMEWORLD has seven primary objectives:

1. **Centralized Identity Management:** Implement Active Directory for compatible Windows and Linux endpoints.
2. **Endpoint Administration:** Manage physical household computers, user accounts, software, updates, and configurations.
3. **Network Security:** Improve visibility, segmentation, access control, and protection of the home network.
4. **IT Support Operations:** Establish asset inventory, help desk tickets, troubleshooting procedures, and maintenance documentation.
5. **Security Monitoring:** Collect and analyze relevant endpoint, authentication, and network security logs.
6. **Infrastructure Reliability:** Develop monitoring, backup, recovery, and safe shutdown procedures.
7. **Professional Documentation:** Publish sanitized technical reports, diagrams, and troubleshooting case studies.

---

## 3. Current Infrastructure

### Hardware Environment

The planned environment includes:

| Device Category | Purpose |
|---|---|
| Primary Kali Linux computer | Administration workstation and virtualization host |
| Windows Server 2025 VM | Active Directory Domain Controller |
| Windows laptops | Potential domain-managed endpoints |
| macOS laptop | Household endpoint and potential centralized management |
| Work laptop | Restricted endpoint; subject to employer policies |
| iPhones | Mobile device inventory and network security |
| Smart TVs | IoT network security and segmentation |
| Wall-mounted tablet | IoT inventory and network management |
| ISP router/firewall | Internet gateway and existing network infrastructure |

Not every household device can join Active Directory. Devices such as iPhones, smart TVs, and most tablets will be managed through appropriate network controls and supported device-management methods.

Employer-owned and school-managed devices will not be enrolled or reconfigured without authorization.

### Core Technologies

- Windows Server 2025
- Active Directory Domain Services
- DNS and Kerberos
- Kali Linux
- Samba Winbind
- PAM / LightDM
- Oracle VirtualBox
- systemd
- PowerShell and Bash
- Linux and Windows troubleshooting utilities

Additional tools will be selected during later implementation phases.

---

## 4. Infrastructure Architecture

### Current Logical Architecture

```text
                 INTERNET
                    |
             ISP ROUTER/FIREWALL
                    |
               HOME NETWORK
                    |
        +-----------+-----------+
        |                       |
  KALI LINUX HOST        HOUSEHOLD DEVICES
  Physical Computer      Windows / macOS / IoT
        |
        |
  ORACLE VIRTUALBOX
  Bridged Networking
        |
        |
  WINDOWS SERVER 2025
  HOMEWORLD DOMAIN CONTROLLER
        |
        +-- Active Directory
        +-- DNS
        +-- Kerberos
        +-- Domain Users
        +-- Security Groups
        |
        |
  LINUX DOMAIN AUTHENTICATION
        |
        +-- Samba Winbind
        +-- PAM
        +-- LightDM
        +-- XFCE
```

**Architecture note:** The domain controller currently depends on the primary Kali Linux computer. Future planning will evaluate a dedicated always-on server and appropriate redundancy.

---

## 5. Completed Work

### Phase 0 — Initial Infrastructure Deployment

**Status: Initial objectives completed; operational hardening ongoing.**

The following capabilities have been implemented and validated:

- Configured a Windows Server 2025 Active Directory domain controller in VirtualBox.
- Integrated the domain controller with the home network using bridged networking.
- Configured domain DNS resolution for the Kali Linux host.
- Integrated Linux authentication with Active Directory using Samba Winbind and Kerberos.
- Validated domain account and group resolution.
- Obtained a valid Kerberos authentication ticket.
- Successfully logged into the Kali Linux graphical desktop using an Active Directory domain account.
- Configured the domain controller to run headlessly under a systemd user service.
- Enabled systemd user lingering so the VM can remain running after the local desktop user logs out.
- Investigated authentication failures, domain discovery problems, and VirtualBox startup conflicts.
- Preserved separation between standard domain users and local Linux administrative privileges.

### Remaining Validation

The following items are **not yet considered complete**:

- Reliable guest shutdown during host shutdown
- Automatic startup and recovery after a full host reboot
- Tested Active Directory backup and recovery
- Production-style monitoring and alerting
- Documented infrastructure recovery procedures

---

## 6. HOMEWORLD Development Roadmap

### Phase 1 — Infrastructure Documentation and Assessment

**Goal:** Establish a complete understanding of the environment before expanding management capabilities.

Planned activities:

- Inventory physical and virtual devices.
- Document operating systems, device types, and ownership.
- Record network addressing and infrastructure dependencies.
- Create a physical network topology diagram.
- Create a logical infrastructure architecture diagram.
- Document the Active Directory authentication flow.
- Create a systemd and VirtualBox service architecture diagram.
- Identify security weaknesses and single points of failure.

**Deliverables:**
- IT Asset Inventory
- Network Topology Diagram
- Infrastructure Architecture Diagram
- Initial Risk Assessment
- Configuration Baseline

### Phase 2 — Active Directory and Identity Management

**Goal:** Establish a manageable identity infrastructure.

Planned activities:

- Review organizational units and security groups.
- Define standard and administrative user roles.
- Establish account naming conventions.
- Review password and account-lockout policies.
- Implement least-privilege access.
- Document account provisioning and deprovisioning.
- Configure Group Policy for compatible Windows devices.
- Test Linux domain authentication and authorization policies.
- Document domain-controller dependencies and recovery.

**Deliverables:**
- Active Directory Structure
- Identity and Access Management Policy
- User Provisioning Procedure
- Group Policy Documentation
- Authentication Test Report

### Phase 3 — Physical Endpoint Management

**Goal:** Extend management from the server lab to authorized household computers.

Planned activities:

- Assess Windows editions and domain-join compatibility.
- Enroll compatible Windows devices where appropriate.
- Evaluate Linux and macOS identity integration.
- Configure supported endpoint security policies.
- Establish patch management procedures.
- Document remote troubleshooting and support.
- Develop endpoint maintenance checklists.

**Deliverables:**
- Endpoint Deployment Guide
- Endpoint Configuration Baseline
- Patch Management Procedure
- Endpoint Troubleshooting Runbook

### Phase 4 — Network Security and Segmentation

**Goal:** Improve network isolation and reduce unnecessary access between devices.

Planned activities:

- Assess existing ISP router/firewall capabilities.
- Identify trusted, guest, and IoT devices.
- Evaluate VLAN support and alternative isolation methods.
- Design a secure network segmentation plan.
- Define firewall and access-control requirements.
- Review DNS, DHCP, and wireless security.
- Validate authorized connectivity and isolation.

**Deliverables:**
- Network Segmentation Design
- Firewall Rule Matrix
- Network Security Assessment
- Connectivity Validation Report

### Phase 5 — Home IT Help Desk

**Goal:** Simulate real IT support operations using the HOMEWORLD environment.

Planned activities:

- Establish a help desk ticketing workflow.
- Create incident and service-request categories.
- Define ticket priorities and escalation criteria.
- Record troubleshooting steps and resolutions.
- Create a technical knowledge base.
- Document common Windows, Linux, and network issues.
- Build realistic support case studies.

**Deliverables:**
- Help Desk Ticket Templates
- Incident Response Workflow
- IT Knowledge Base
- Troubleshooting Case Studies

### Phase 6 — Security Monitoring and Detection

**Goal:** Introduce centralized visibility and defensive security operations.

Planned activities:

- Evaluate centralized logging technologies.
- Collect Windows authentication and security events.
- Collect relevant Linux system and authentication logs.
- Monitor suspicious authentication activity.
- Develop security detection rules.
- Investigate controlled security events.
- Create incident investigation reports.

**Potential Technologies:**
- Windows Event Logs
- Sysmon
- Elastic Stack
- Wazuh
- PowerShell
- Linux audit and system logs

**Deliverables:**
- Security Monitoring Architecture
- Detection Use Cases
- Security Investigation Reports
- Incident Response Playbooks

### Phase 7 — Backup, Recovery, and Reliability

**Goal:** Make HOMEWORLD resilient and recoverable.

Planned activities:

- Validate graceful virtual machine shutdown.
- Test controlled host reboot and service recovery.
- Develop supported Active Directory backup procedures.
- Document recovery point and recovery time objectives.
- Test recovery in an isolated environment.
- Implement service health monitoring.
- Establish maintenance and change-control procedures.

**Deliverables:**
- Backup and Recovery Plan
- Shutdown and Startup Runbook
- Disaster Recovery Test Report
- Infrastructure Monitoring Checklist

**Priority:** Some of these activities must be completed before expanding the environment. Backup and shutdown safety are prerequisites for broader deployment, even though they are documented as a dedicated phase.

---

## 7. Security Principles

HOMEWORLD follows these operating principles:

**Least Privilege:** Users receive only the permissions required for their responsibilities.

**Defense in Depth:** Identity controls, endpoint protection, network restrictions, and monitoring work together.

**Change Management:** Significant configuration changes are documented, validated, and reversible where possible.

**Availability:** Infrastructure dependencies and failure scenarios are identified before expanding services.

**Privacy:** Personal information, credentials, internal addresses, and sensitive configuration details are excluded from public reports.

**Authorized Administration:** Only personally owned or explicitly authorized devices are managed.

**Safe Testing:** Offensive security experiments are restricted to isolated or explicitly authorized lab environments.

---

## 8. Documentation Standards

Every major HOMEWORLD implementation will include:

- Objective and business justification
- Technologies and prerequisites
- Infrastructure diagram where appropriate
- Step-by-step implementation
- Windows and Linux commands where applicable
- Validation results
- Troubleshooting and lessons learned
- Security implications
- Screenshots or sanitized evidence
- Recommendations and next actions

Reports will distinguish between completed work, validated results, planned activities, and unresolved issues.

---

## 9. Project Success Criteria

HOMEWORLD will be considered operationally mature when:

- Compatible authorized endpoints can use centrally managed identities.
- Administrative privileges are clearly separated from standard user access.
- Core services can recover from routine host restarts.
- Backups and recovery procedures have been tested.
- Endpoint inventory and support documentation are maintained.
- Security monitoring provides useful visibility into infrastructure activity.
- Network access controls appropriately separate trusted and untrusted devices.
- Configuration changes and incidents are documented.
- The environment can be maintained without relying on undocumented knowledge.

---

## 10. Portfolio and Professional Development

HOMEWORLD demonstrates hands-on experience relevant to:

- IT Support Technician
- Help Desk Analyst
- Junior Systems Administrator
- Network Support Technician
- Security Operations Center Analyst
- Junior Cybersecurity Analyst

The project emphasizes practical problem-solving, technical documentation, troubleshooting, security awareness, and infrastructure operations.

### Project Reports

[HOMEWORLD Infrastructure Progress Report](https://aliabdel225.github.io/homeworld-infrastructure-progress-report.html)

[Cybersecurity Portfolio](https://aliabdel225.github.io/)

---

## 11. Current Project Status

| Workstream | Status |
|---|---|
| Windows Server AD deployment | Completed |
| Kali Linux domain integration | Completed |
| Graphical domain login | Verified |
| Headless domain-controller operation | Verified after logout |
| Safe shutdown validation | In progress |
| Host reboot recovery | Pending |
| Asset inventory | Planned |
| Infrastructure diagrams | Planned |
| Physical endpoint onboarding | Planned |
| Network segmentation | Planned |
| Help desk implementation | Planned |
| Security monitoring | Planned |
| Backup and disaster recovery | Pending validation |

---

## Final Vision

HOMEWORLD is more than an Active Directory lab.

It is an evolving infrastructure project designed to demonstrate how enterprise IT principles can be applied to a real environment with real devices, operational constraints, security requirements, and maintenance responsibilities.

**The goal is not simply to make systems work. It is to make them secure, manageable, observable, documented, and recoverable.**

---

**Maintained by:** Ali Abdelghani  
**Project:** HOMEWORLD  
**Last Updated:** November 18, 2026  
**Status:** Active Development
