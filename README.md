# Project Overview #

This project demonstrates a practical, end-to-end approach to improving cybersecurity within a modern healthcare organization. It combines research, real-world threat analysis, and a virtualized proof-of-concept environment to showcase how healthcare providers can strengthen security, protect sensitive patient data, and meet regulatory compliance standards.

The work addresses both the technical vulnerabilities in healthcare systems and the human factors—such as phishing susceptibility—that continue to be exploited by attackers.

# Objectives #

The primary goals of this project were:

Analyze vulnerabilities in a telemedicine-focused healthcare environment.

Implement key security controls including:

VPN-based secure remote access

Multi-factor authentication (MFA)

Network segmentation

Access control policies

Logging & intrusion detection

Simulate real cyberattacks (phishing, port scanning) to evaluate defenses.

Train healthcare staff using a custom-built cybersecurity awareness manual.

Document results proving the need for long-term cybersecurity investment.

# Background #

Healthcare organizations have become one of the most targeted industries for cybercrime due to:

High-value patient data

Increasing digital transformation (EHR, IoT, remote care)

Outdated systems or weak access control

Strict laws such as GDPR and HIPAA

Even a small breach can risk patient safety, cause financial loss, and lead to regulatory penalties.

# Technical Implementation #
Virtual Environment Setup

A VMware-based environment was created containing:

Server 1: Windows Server 2022 (Domain Controller + DNS)

Server 2: Windows Server 2022 (Tailscale VPN host)

Windows 10 Client: Domain-joined workstation

Kali Linux: Attacker system for phishing & reconnaissance

Active Directory & DNS

AD DS installed and promoted to a domain controller

Domain created: TMedicine.local

Organizational Units (Medical Staff, IT Staff)

Group Policies for:

Password complexity

RDP restrictions

Auto-lock timers

Account lockout

Login warnings

Secure Remote Access (VPN)

Tailscale VPN deployed on Server 2 and Windows Client

Encrypted tunnels established for remote access

Validated through RDP login over VPN

Multi-Factor Authentication

Google 2-Step Verification added to VPN login

Ensures only authorized staff can access internal systems

Network Segmentation & Access Control

Windows Firewall rules restricting RDP (port 3389) to internal IPs

Blocking attacker IP (Kali Linux)

Job-based access policies enforcing the Principle of Least Privilege

Aligns with Zero Trust Architecture principles

Phishing Simulation (Gophish)

A phishing campaign was launched targeting simulated medical staff.

Results:

3/5 users clicked the link

1 user entered credentials

This demonstrated the high risk posed by human factors in healthcare environments.

Intrusion Detection & Monitoring

Nmap port scanning used to simulate reconnaissance

Firewall logs captured blocked intrusion attempts

Confirmed segmentation and filtering worked as intended

# Key Results #
Area	Outcome
VPN Security	Encrypted remote access successfully implemented
MFA	Prevented unauthorized logins even with password compromise
Firewall & Segmentation	Blocked external IP scanning & lateral movement
Phishing Test	60% click rate showed strong need for staff training
Monitoring	Logs detected and recorded attacks accurately

Together, these controls significantly increased security across the simulated healthcare infrastructure.

# Cybersecurity Training Manual #

A complete training manual for healthcare staff was developed covering:

Recognizing phishing & social engineering

Safe password practices & MFA

Zero Trust & least-privilege principles

Data handling, GDPR/HIPAA awareness

Reporting suspicious activity

This emphasizes that technology alone is not enough—education is crucial.

# Conclusion #

This project proves that:

A realistic healthcare cybersecurity environment can be simulated and secured using industry best practices.

Technical defenses like MFA, segmentation, and VPNs greatly reduce attack surface.

Human error remains one of the largest threats.

Ongoing cybersecurity awareness training is essential to ensuring patient safety and compliance.

The work aligns with recommendations from NIST, HHS, GDPR, and other major security frameworks.
