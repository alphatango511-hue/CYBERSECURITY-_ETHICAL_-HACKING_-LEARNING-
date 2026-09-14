# Week 2 PM1 - Cybersecurity & Ethical Hacking Learning Environment

## Overview

This repository documents my hands-on cybersecurity and ethical hacking learning environment as part of Week 2 Practical Milestone 1 (PM1). It includes practical work related to virtualization, Kali Linux setup, networking fundamentals, reconnaissance, and security testing in an isolated lab environment.

**Purpose:** Develop practical cybersecurity skills in an isolated, authorized environment.

---

## Lab Objectives
# IMG-20260912-WA0012(1).jpg
- Build an isolated cybersecurity practice environment
- Configure virtual machines for security testing
- Install and configure Kali Linux
- Configure virtual networking (NAT/Host-Only)
- Understand IP addressing and connectivity
- Practice reconnaissance and enumeration
- Perform vulnerability assessment in authorized labs
- Create snapshots for safe experimentation and rollback

---

## Lab Environment & Specifications

### Virtualization

| Component | Details |
|-----------|---------|
| Hypervisor | Oracle VirtualBox |
| Host OS | Windows |
| Security Testing OS | Kali Linux |
| Network Type | NAT / Host-Only Network |
| Purpose | Isolated cybersecurity laboratory |

### Tools Installed

- Kali Linux
- Nmap
- Wireshark
- Burp Suite
- Metasploit Framework
- Gobuster
- Netcat
- Python

### Network Configuration

Example private laboratory network:

| Machine | Example IP |
|---------|------------|
| Kali Linux | 10.0.0.2 |
| Target VM | 10.0.0.10 |
| Test VM | 10.0.0.11 |

> **Note:** These addresses are examples for an isolated lab environment only.

---

## Phase 1 — Kali Linux Setup

### Step 1: Install VirtualBox

Oracle VirtualBox was installed and configured as the virtualization platform for the cybersecurity laboratory.

### Step 2: Install Kali Linux

Kali Linux was installed inside a virtual machine and configured for security testing and cybersecurity practice.

### Step 3: Configure Network Connection

The virtual machine network adapter was configured using an isolated laboratory network.

### Step 4: Verify Network Configuration

Network configuration was verified using standard Linux networking commands:

```bash
ip addr
```

The assigned IP address and network interface were checked to confirm that the virtual machine was connected correctly.

### Step 5: Test Connectivity

Connectivity between authorized laboratory machines was tested:

```bash
ping 10.0.0.10
```

The test was used to verify communication between machines inside the controlled lab environment.

---

## Virtual Machine Snapshots

Snapshots were created after major configuration stages:

- ✅ Fresh OS installation
- ✅ Network configuration completed
- ✅ Kali Linux configured
- ✅ Target machine configured
- ✅ Pre-testing state

Snapshots allow the laboratory environment to be restored to a known working state after experiments.

---

## Reconnaissance & Enumeration

Authorized laboratory systems can be examined using tools such as Nmap:

```bash
nmap -sV 10.0.0.10
```

**Purpose:** Understand network discovery, service enumeration, and basic security assessment techniques.

---

## Web Security

The laboratory can also be used to study common web application security concepts:

- Authentication security
- Input validation
- SQL Injection concepts
- Cross-Site Scripting (XSS)
- Access control
- Security headers

> All testing is performed only against intentionally vulnerable applications or systems for which authorization has been provided.

---

## Week 2 PM1 — Practical Work Completed

### Tasks Accomplished

| Task | Status |
|------|--------|
| VirtualBox installation | ✅ Complete |
| Kali Linux VM setup | ✅ Complete |
| Network adapter configuration | ✅ Complete |
| IP address verification | ✅ Complete |
| Connectivity testing | ✅ Complete |
| VM snapshots created | ✅ Complete |
| Initial reconnaissance practice | ✅ Complete |

### Commands Used

```bash
# Check network interface and IP
ip addr

# Test connectivity to target
ping 10.0.0.10

# Basic service scan
nmap -sV 10.0.0.10
```

### Key Learnings

1. **Virtualization:** Understanding how to set up and manage virtual machines
2. **Networking:** Configuring NAT and Host-Only networks for isolation
3. **Linux Basics:** Using terminal commands for network verification
4. **Security Tools:** Introduction to Nmap for reconnaissance
5. **Documentation:** Recording findings and configurations

---

## Project Structure

```text
cybersecurity_ethical_hacking_learning/
│
├── README.md
├── week2-pm1/
│   ├── screenshots/
│   │   ├── virtualbox_setup.png
│   │   ├── kali_installation.png
│   │   ├── network_config.png
│   │   └── connectivity_test.png
│   ├── commands.md
│   └── notes.md
│
└── resources/
    └── references.md
```

---

## Learning Outcomes

Through this laboratory I aim to develop practical skills in:

- Linux
- Networking
- Cybersecurity
- Ethical Hacking
- Vulnerability Assessment
- Web Security
- Network Security
- Security Tools
- Technical Documentation

---

## Git Commands Used

```bash
# Initialize repository
git init

# Add files
git add .

# Commit changes
git commit -m "Week 2 PM1 - Kali Linux setup and network configuration"

# Push to remote
git push origin main
```

---

## Disclaimer

This repository is intended for **educational and authorized cybersecurity testing only**.

All security testing must be performed against systems, applications, networks, CTFs, or laboratories where **explicit permission** has been provided.

I do not support unauthorized access, disruption, data theft, or illegal activity.

---

## Author

**Bishamakhan**

Cybersecurity Enthusiast | Interested in Cybersecurity, Ethical Hacking, Networking and Security Research

---

## References

- [OWASP Web Security Resources](https://owasp.org/)
- [Kali Linux Documentation](https://www.kali.org/docs/)
- [Nmap Documentation](https://nmap.org/book/)
- [Wireshark Documentation](https://www.wireshark.org/docs/)
- [VirtualBox Documentation](https://www.virtualbox.org/wiki/Documentation)

---

*Last Updated: Week 2 PM1*
