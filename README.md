# 🛡️ SOC Monitoring Platform | Wazuh & Suricata

<p align="center">
  <img src="https://img.shields.io/badge/Domain-Cybersecurity-blue" />
  <img src="https://img.shields.io/badge/Focus-SOC%20%7C%20Blue%20Team-green" />
  <img src="https://img.shields.io/badge/SIEM-Wazuh-orange" />
  <img src="https://img.shields.io/badge/IDS-Suricata-red" />
  <img src="https://img.shields.io/badge/Platform-Linux-lightgrey" />
</p>

<p align="center">
  <b>A Practical Security Operations Center (SOC) Laboratory</b>
</p>

---

## 📌 1. Project Overview

This project demonstrates the deployment and configuration of a defensive Security Operations Center (SOC) laboratory using **Wazuh SIEM** and **Suricata IDS**.

The main objective is to build a centralized security monitoring environment capable of collecting endpoint events, monitoring system activities, detecting suspicious network traffic, and supporting security investigations.

The laboratory integrates Windows and Linux endpoints with centralized security monitoring components to provide visibility into endpoint and network activities.

## 🎯 2. Project Objectives

- Deploy and configure a centralized Wazuh SIEM platform.
- Integrate Windows and Linux endpoints.
- Monitor security events across multiple operating systems.
- Configure File Integrity Monitoring (FIM).
- Collect and analyze Windows security events.
- Integrate Sysmon for enhanced Windows event visibility.
- Deploy Suricata for network intrusion detection.
- Analyze security alerts and investigate suspicious activities.
- Develop practical SOC monitoring and incident investigation skills.

## 🏗️ 3. SOC Architecture

The laboratory is designed around centralized security monitoring.

### Main Components

| Component | Description |
|---|---|
| Wazuh Manager | Receives and analyzes endpoint security events. |
| Wazuh Indexer | Stores and indexes security information. |
| Wazuh Dashboard | Provides security monitoring and visualization. |
| Windows Endpoint | Generates Windows security events. |
| Linux Endpoint | Generates Linux system and security events. |
| Wazuh Agents | Forward endpoint events to the Wazuh Manager. |
| Sysmon | Provides detailed Windows system activity events. |
| Suricata IDS | Monitors network traffic and generates intrusion detection alerts. |

### Architecture Diagram

Add your architecture diagram here:

```text
                 SECURITY OPERATIONS CENTER
                            |
                   +------------------+
                   |  Wazuh Dashboard |
                   +------------------+
                            |
                   +------------------+
                   |   Wazuh Manager  |
                   +------------------+
                            |
                   +------------------+
                   |  Wazuh Indexer   |
                   +------------------+
                            |
             +--------------+--------------+
             |                             |
      +-------------+               +-------------+
      |   Windows   |               |    Linux    |
      |   Endpoint  |               |   Endpoint  |
      +-------------+               +-------------+
      | Wazuh Agent |               | Wazuh Agent |
      |   Sysmon    |               | System Logs |
      +-------------+               +-------------+

                   +------------------+
                   |   Suricata IDS   |
                   +------------------+
                            |
                     Network Monitoring
```

*Note: This is a conceptual diagram. The actual network topology and Suricata integration depend on the laboratory configuration.*

## 🛠️ 4. Technologies & Tools

| Technology | Purpose |
|---|---|
| Wazuh | Security Information and Event Management (SIEM) |
| Suricata | Network Intrusion Detection System (IDS) |
| Sysmon | Windows system activity monitoring |
| Linux | Server administration and monitoring |
| Windows | Endpoint security monitoring |
| VirtualBox | Virtual laboratory environment |
| PowerShell | Windows administration |
| Bash | Linux administration |

## ⚙️ 5. Implementation

### 5.1 Wazuh SIEM Deployment

Deployment of the Wazuh platform, including:

- Wazuh Manager installation.
- Wazuh Indexer installation.
- Wazuh Dashboard configuration.
- Verification of Wazuh services.
- Access to the centralized monitoring interface.

### 5.2 Windows Endpoint Integration

Integration of a Windows endpoint with the Wazuh Manager.

Activities:

- Installation of the Wazuh Agent.
- Configuration of the Wazuh Manager address.
- Agent registration and connection verification.
- Windows security event collection.
- Security policy auditing.

### 5.3 Linux Endpoint Integration

Integration of a Linux endpoint with the Wazuh Manager.

Activities:

- Wazuh Agent installation.
- Manager address configuration.
- Agent service management.
- Linux system log monitoring.
- Agent connection verification.

### 5.4 Windows Security Monitoring

Configuration of Windows auditing policies to improve security event visibility.

Monitored categories include:

- Account Logon Events.
- Logon Events.
- Account Management.
- Process Management.
- Policy Change.
- Privilege Use.

### 5.5 File Integrity Monitoring (FIM)

File Integrity Monitoring is configured to monitor selected directories.

Monitored paths:

**Windows:**
```text
C:\SOC-Test\
```

**Linux:**
```text
/home/user/SOC-Test/
```

The objective is to identify file integrity changes and generate security events for investigation.

### 5.6 Sysmon Integration

Sysmon provides detailed information about Windows system activity.

It can complement Windows event collection by providing additional information about processes and system events.

The collected events can be used for security monitoring and investigation.

### 5.7 Suricata IDS Deployment

Suricata is deployed as a network intrusion detection component.

Main activities:

- Suricata installation.
- Network interface configuration.
- Service management.
- Configuration of network monitoring.
- Analysis of generated alerts.

Suricata event information can be found in:

```text
/var/log/suricata/eve.json
```

## 📊 6. Security Monitoring & Investigation

The laboratory focuses on defensive security monitoring through:

- Endpoint security event collection.
- Windows and Linux log analysis.
- File integrity monitoring.
- Network intrusion detection.
- Security alert investigation.
- Identification of suspicious activities.

## 📸 7. Screenshots & Evidence

Screenshots will document the actual deployment and configuration.

| Screenshot | Description |
|---|---|
| `wazuh-install.png` | Wazuh platform installation |
| `agent_windows.png` | Windows Wazuh Agent |
| `agent_linux.png` | Linux Wazuh Agent |
| `audit_windows.png` | Windows audit policy |
| `fim_config.png` | File Integrity Monitoring configuration |
| `suricata_install.png` | Suricata installation |
| `wazuh-dashboard.png` | Wazuh Dashboard |

*Add the corresponding screenshots to a `screenshots/` directory as they become available.*

## 📁 8. Repository Structure

```text
SOC-Wazuh-Suricata-Lab/
│
├── README.md
│
├── architecture/
│   └── soc-architecture.png
│
├── screenshots/
│   ├── wazuh-install.png
│   ├── agent_windows.png
│   ├── agent_linux.png
│   ├── audit_windows.png
│   ├── fim_config.png
│   ├── suricata_install.png
│   └── wazuh-dashboard.png
│
├── configuration/
│   ├── wazuh/
│   ├── suricata/
│   └── sysmon/
│
└── documentation/
    ├── installation-guide.md
    └── configuration-guide.md
```

## 📚 9. Skills Demonstrated

This project demonstrates practical knowledge in:

- SIEM Deployment and Administration.
- SOC Operations.
- Blue Team Security.
- Security Event Monitoring.
- Log Analysis.
- Endpoint Monitoring.
- File Integrity Monitoring.
- Network Intrusion Detection.
- Windows Security Auditing.
- Linux System Administration.
- Security Event Investigation.

## 🔮 10. Future Improvements

Potential improvements for the laboratory include:

- Advanced Wazuh detection rules.
- MITRE ATT&CK mapping.
- Additional Windows event monitoring.
- Enhanced Suricata event integration.
- Automated security alert analysis.
- Incident response documentation.
- Security dashboards and reporting.

## 👨‍💻 11. Author

**Ahmed ELGHACHI**

Master's Graduate in Cybersecurity

Focus: Cyber Defense | SOC Operations | Blue Team | Cloud Security

**GitHub:** [Ahmed-Elghachi](https://github.com/Ahmed-Elghachi)

**Credly:** [Ahmed Elghachi](https://www.credly.com/users/ahmed-elghachi)

---

## ⚠️ Disclaimer

This project is developed for educational purposes and defensive cybersecurity learning in a controlled laboratory environment.

All monitoring and security testing activities must be conducted on systems and networks for which proper authorization has been obtained.

---

<p align="center">
  <b>Building practical cybersecurity skills through defensive security engineering.</b>
</p>
