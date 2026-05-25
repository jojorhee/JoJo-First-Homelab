# JoJo-First-Homelab

This is my first attempt at a cybersecurity homelab. There are Linux and Windows clients that rely on a DNS Server from a VM with Windows Active Directory, and there's a Kali Linux machine for attacking. My documentation/files in this repository isn't extensive, but I'm just trying something new. This attack-defend environment is inspired by ProjectSecurity's Enterprise 101 Lab Design, and it simulates a small enterprise network with Windows, Linux, Active Directory, a security stack, and an attacker machine for ethical testing.

# Overview

This project is my first full homelab build. The goal was to create a realistic enterprise‑style environment where I could practice:
- Active Directory administration
- Windows & Linux system management
- Networking fundamentals
- Vulnerability discovery
- Password attacks (e.g., Hydra)
- Log analysis & detectiion
  
The lab is fully virtualized using VirtualBox

# Network Topology

Network: 10.0.0.0/24
Gateway: 10.0.0.1
DHCP Range: 10.0.0.100–10.0.0.200

# Virtual Machines

Each VM is configured with lightweight specs so my one system (can't afford multiple computers in this economy HA) can run an entire environment

| VM | OS | Specs | Storage |
| --- | --- | --- | --- |
| Domain Controller | Windows Server | 2 CPU / 4GB RAM | 50GB |
| Windows Client | Windows 11 Enterprise | 2 CPU / 4GB RAM | 80GB |
| Linux Client | Ubuntu Desktop | 1 CPU / 2GB RAM | 80GB |
| Corporate Server | Ubuntu Server | 1 CPU / 2GB RAM | 25GB |
| Attacker | Kali Linux | 1 CPU / 2GB RAM | 55GB |

# Tools Used

## Defense / Monitoring
- Wazuh – SIEM & endpoint monitoring
- MailHog – Fake SMTP server for phishing simulations

## Offense / Testing
- Hydra – Password brute‑forcing
- SecLists – Wordlists for enumeration
- Evil‑WinRM – Windows remote management
- xfreerdp – RDP access

# What I’ve Done So Far

- Built the full virtual network
- Configured Active Directory + domain join
- Set up Windows & Linux clients
- Installed Wazuh
- Created a vulnerable Linux machine
- Used Hydra from Kali to successfully access the Linux VM due to a weak password
- Began simulating basic attack chains (credential harvesting, brute force, lateral movement)

# 🎯 Goals for Future Expansion

- Add a web server + database
- Implement Group Policy hardening
- Add firewall rules + segmentation
- Build detection rules in Wazuh
- Simulate phishing → credential theft → lateral movement
- Document full attack paths and defensive responses
