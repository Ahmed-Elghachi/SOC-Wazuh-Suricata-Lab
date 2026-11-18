# 01 – SOC Laboratory Environment Preparation

## 1. Introduction

This document describes the preparation of the virtual environment used to deploy the SOC Monitoring Platform based on Wazuh SIEM and Suricata IDS.

The laboratory uses VMware Workstation to create and manage virtual machines.

## 2. Host Machine Requirements

The host machine must meet the following recommended requirements:

| Component | Recommended Configuration |
|---|---|
| Operating System | Windows 10 / Windows 11 |
| RAM | 16 GB minimum |
| Processor | Intel Core i5 / AMD Ryzen 5 |
| Storage | 100 GB free space |
| Virtualization | Intel VT-x / AMD-V |
| Hypervisor | VMware Workstation |

## 3. Technologies Required

The following technologies are used in the laboratory:

| Technology | Purpose |
|---|---|
| VMware Workstation | Virtual machine management |
| Ubuntu Server 22.04 LTS | Wazuh and Linux environment |
| Windows 10/11 | Windows monitoring endpoint |
| Wazuh | SIEM and endpoint monitoring |
| Suricata | Network Intrusion Detection System |
| Sysmon | Windows system activity monitoring |
| PowerShell | Windows administration |
| Bash | Linux administration |

## 4. Virtual Machine Architecture

The laboratory consists of three virtual machines.

| Virtual Machine | Operating System | Role |
|---|---|---|
| Wazuh-Server | Ubuntu Server 22.04 | Wazuh Manager, Indexer and Dashboard |
| Windows-Endpoint | Windows 10/11 | Wazuh Agent and Sysmon |
| Linux-Endpoint | Ubuntu Server 22.04 | Wazuh Agent and Suricata IDS |

## 5. VMware Virtual Machine Configuration

### 5.1 Wazuh Server

Recommended configuration:

- CPU: 4 cores
- RAM: 8 GB
- Disk: 50 GB
- Network: NAT or Host-only

### 5.2 Windows Endpoint

Recommended configuration:

- CPU: 2 cores
- RAM: 4 GB
- Disk: 40 GB
- Network: Same laboratory network

### 5.3 Linux Endpoint

Recommended configuration:

- CPU: 2 cores
- RAM: 2–4 GB
- Disk: 25 GB
- Network: Same laboratory network

*Note: These are recommended configurations. Actual resources depend on the host machine.*

## 6. Network Configuration

The virtual machines must communicate with each other through a common VMware virtual network.

Example network addressing:

| Machine | IP Address |
|---|---|
| Wazuh Server | 192.168.100.10 |
| Windows Endpoint | 192.168.100.20 |
| Linux Endpoint | 192.168.100.30 |

Subnet Mask:

`255.255.255.0`

Network:

`192.168.100.0/24`

*Note: These addresses are examples. They must be adapted to the actual VMware network configuration.*

## 7. VMware Network Preparation

1. Open VMware Workstation.
2. Navigate to Edit.
3. Select Virtual Network Editor.
4. Configure the required virtual network.
5. Connect all laboratory virtual machines to the same network.
6. Verify network connectivity.

## 8. Network Connectivity Verification

On Linux, execute:

```bash
ip addr
```

Check the network configuration.

Test connectivity to the Wazuh Server:

```bash
ping 192.168.100.10
```

On Windows PowerShell:

```powershell
ipconfig
```

Test connectivity:

```powershell
ping 192.168.100.10
```

Check Wazuh communication port:

```powershell
Test-NetConnection 192.168.100.10 -Port 1514
```

## 9. Environment Preparation Checklist

- [ ] VMware Workstation installed.
- [ ] Ubuntu Server ISO downloaded.
- [ ] Windows installation media prepared.
- [ ] Wazuh Server virtual machine created.
- [ ] Windows Endpoint virtual machine created.
- [ ] Linux Endpoint virtual machine created.
- [ ] VMware network configured.
- [ ] IP addresses assigned.
- [ ] Network connectivity verified.

## 10. Conclusion

The virtual environment provides the foundation for deploying the SOC monitoring platform.

After preparing the virtual machines and verifying network connectivity, the next step is to install and configure the Wazuh SIEM platform.

---

**Project:** SOC Monitoring Platform – Wazuh & Suricata  
**Author:** Ahmed ELGHACHI  
**Domain:** Cybersecurity – Blue Team / SOC Operations
