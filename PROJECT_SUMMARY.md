# Hybrid Cloud SIEM Lab - Quick Reference

## Project Overview
A comprehensive 6-phase security infrastructure project demonstrating enterprise-grade SIEM deployment, network security, and hybrid cloud integration.

## Architecture Components

### On-Premise (VMware)
- **Windows Server 2022** - Domain Controller with Active Directory
- **Wazuh Manager & Indexer** - SIEM for log aggregation and threat detection
- **OPNsense Firewall** - Network segmentation with IDS/IPS (Suricata)
- **Kali Linux** - Attack simulation and penetration testing

### Cloud (AWS)
- **Ubuntu Server (EC2)** - Cloud endpoint with Wazuh agent
- **CloudTrail** - API logging and monitoring
- **Security Groups** - Cloud firewall rules

### Networking
- **Tailscale VPN** - Zero-trust mesh network connecting cloud to on-premise

## Project Phases

### Phase 1: Windows Domain & Active Directory
- Domain Controller promotion
- User creation (michael.admin, user1, user2)
- Group Policy Objects (password policy, account lockout, etc.)
- Network shares and RDP configuration

### Phase 2: Network Segmentation
- OPNsense firewall deployment
- LAN and DMZ network creation
- Firewall rules (block ping to DC, allow to DMZ)
- Suricata IDS/IPS configuration

### Phase 3: SIEM Deployment
- Wazuh Manager & Indexer installation
- Sysmon installation on Windows
- Agent configuration (Windows Server, AWS Ubuntu)
- Custom detection rules
- Security event generation and analysis

### Phase 4: Attack Simulation
- Kali Linux deployment
- Network reconnaissance (Nmap)
- Brute force attacks
- Attack detection validation

### Phase 5: Cloud Integration
- AWS EC2 instance creation
- Security Group configuration
- CloudTrail monitoring
- Tailscale VPN setup
- Cloud agent to SIEM connection

### Phase 6: Documentation
- Screenshot organization
- Technical documentation
- Portfolio preparation

## Key Technical Challenges

### Challenge 1: Log Incompatibility
**Problem:** AWS Ubuntu uses journald, Wazuh agent expected syslog  
**Solution:** Configured agent to read journald socket directly  
**Impact:** Restored cloud log ingestion

### Challenge 2: Disk Failure
**Problem:** Disk hit 98% capacity, crashed Wazuh Indexer  
**Solution:** Emergency log rotation, disk expansion, service recovery  
**Impact:** Recovered SIEM without data loss

### Challenge 3: Virtualization Issues
**Problem:** Kali Linux mouse pointer integration failure  
**Solution:** Modified VMware .vmx configuration file  
**Impact:** Restored attack simulation environment

## Key Screenshots Location

- **Architecture:** `images/CLOUD/Hybrid_Cloud_Architecture_Live.jpg`
- **SIEM Dashboard:** `images/SIEM - WAZUH/Wazuh_Security_Events_Dashboard.jpg`
- **Firewall:** `images/Firewall Setup - OPNsense/OPNsense Dashboard.jpg`
- **Network Diagram:** `images/Windows Server Setup + VM + GPO/Network Diagram P1.jpeg`
- **Cloud Integration:** `images/CLOUD/Secure_Hybrid_Cloud_Tailscale_Setup_AWS.jpg`

## Technologies Used

- **SIEM:** Wazuh
- **Firewall:** OPNsense
- **IDS/IPS:** Suricata
- **Cloud:** AWS (EC2, CloudTrail)
- **VPN:** Tailscale
- **OS:** Windows Server 2022, Ubuntu 24.04, Kali Linux
- **Virtualization:** VMware
- **Windows Logging:** Sysmon

## Resume Keywords

SIEM, XDR, Active Directory, Network Segmentation, IDS/IPS, Cloud Security (AWS), Zero-Trust Networking, Incident Response, Threat Detection, Log Analysis, Vulnerability Assessment, Penetration Testing, Disaster Recovery

## Portfolio Value

This project demonstrates:
- Enterprise security architecture design
- Hybrid cloud security implementation
- Network security and segmentation
- SIEM deployment and management
- Incident response and threat detection
- Critical system troubleshooting
- Professional documentation

## GitHub Repository

https://github.com/mjajones/Hybrid-Cloud-SIEM-Lab

