# 🛡️ Enterprise SIEM Architecture & Threat Automation Lab

## 📌 Executive Summary
Welcome to my cybersecurity portfolio. I am a highly motivated Junior SOC Analyst with a strong focus on **Threat Detection, Data Ingestion, and Security Automation**. 

This repository documents my hands-on experience engineering both on-premise and cloud-based logging architectures. It features a multi-node Windows AD/Splunk pipeline, an Azure Sentinel honeypot deployment, and custom Python automation tools designed to reduce Level 1 SOC alert fatigue.

**Certifications:**
* 🏆 CompTIA A+ (Core 1 & Core 2)
* 🏆 Google Cybersecurity Professional Certificate
* 📚 GED - High School Equivalency Diploma (Pending)

---

## 🏗️ 1. Multi-Node Enterprise Lab Architecture (On-Premise)
To demonstrate my understanding of corporate network segmentation and centralized log management, I built a hybrid lab environment featuring the following nodes:

* **Dedicated Domain Controller (Windows Server):** Running **Active Directory (AD)** on the `SOC-LAB.local` domain, managing users, policies, and authentication.
* **Target Windows Endpoints:** Multiple Windows Workstations (e.g., Windows 11 VMs) acting as end-user targets for security event simulations, all successfully joined to the domain.
* **Centralized SIEM Node (Ubuntu Linux 192.168.0.101):** Running Splunk Enterprise to securely ingest, index, and analyze the domain's traffic.

### ✅ Infrastructure Verification
Verified the core architecture by joining the workstations to the domain, ensuring the Active Directory policies were enforced across multiple endpoints.

<img width="821" height="549" alt="Screenshot 2026-03-16 155311" src="https://github.com/user-attachments/assets/9656c559-b2b0-498d-ba27-ebd6260c8cbf" />

> **Figure 1:** Verification of workstation endpoints successfully authenticated and joined to the `SOC-LAB.local` domain.

---

## ⚙️ 2. Splunk SIEM Ingestion & Log Pipeline Engineering
Leveraging my understanding of log forwarding, I configured the Splunk Universal Forwarder across the Windows endpoints. This ensures raw telemetry is securely routed to the central Ubuntu SIEM node.

### 🔍 Search Verification & Data Pipeline
Validated the ingestion pipeline using raw Splunk searches, confirming that event logs from multiple endpoints (e.g., `win11dev`) were successfully hitting the local index.

<img width="938" height="667" alt="Screenshot 2026-03-20 152442" src="https://github.com/user-attachments/assets/fcc13017-c5dc-4199-b101-520e06b28cdc" />

> **Figure 2:** Verification of the data pipeline, showing logs from the Windows endpoint (`Source: System.evtx`) arriving in the Splunk search head.

### 🛡️ Blue Team Focus: Security Log Analysis
The primary objective of this architecture was the centralized collection of security-specific events. Using the Splunk Data Summary, I confirmed that high-fidelity security logs (e.g., Event ID 4624, 4625 for successful/failed logins) were indexed and ready for correlation rules.

<img width="1024" height="771" alt="Screenshot 2026-03-20 151000" src="https://github.com/user-attachments/assets/1e4cac8c-2ed2-4a73-960c-cb49018b41d1" />

> **Figure 3:** Data Summary confirming the ingestion of Critical Security Event Logs from the AD environment.

---

## ☁️ 3. Cloud SIEM & Threat Hunting (Azure Sentinel)
In addition to my local Splunk environment, I am actively expanding my cloud security skills by building a live-fire threat intelligence lab in Microsoft Azure.
* **Architecture:** Deployed a Linux VM in Azure and exposed it to the public internet, running a custom **Python Honeypot** script to attract and log unauthorized access attempts.
* **Current Operations & Troubleshooting:** The honeypot successfully captures live attacker IPs and payloads locally. I am currently deep-diving into Azure Log Analytics Workspaces and Data Collection Rules (DCR) to troubleshoot and engineer the custom log forwarding pipeline into Microsoft Sentinel.

---

## 🐍 4. SOC Automation & Custom Tooling
*(Link to my full code repository: https://github.com/BalazsBuzasi/Network-Security-Tools)*

Beyond infrastructure, I develop Python scripts to automate tedious Level 1 triage tasks and explore network fundamentals:

* **Automated Threat Triage (Mini-SOAR):** A 130-line Python script that parses log files for IoCs, automatically queries the **VirusTotal API** for malicious reputation, and pushes real-time alerts to a **Discord Webhook**. Eliminates manual OSINT gathering.
* **Modbus OT Scanner:** Leveraging my background in electrical infrastructure, I developed a Modbus protocol scanner to identify exposed Industrial Control Systems (ICS) and PLCs, bridging physical electrical knowledge with cybersecurity.
* **TCP Packet Sniffer & Blue Team Scripts:** Built a raw socket sniffer to deeply understand TCP/IP headers, alongside custom network analysis tools.

---
*Open to work, eager to learn, and ready to defend the network. Let's connect on LinkedIn!*
