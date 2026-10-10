# AI Forensics Lab: AI System Security & Incident Response

## 📋 Table of Contents
- [About the Project](#-about-the-project)
- [Lab Setup & Solution Guide](#-lab-setup--solution-guide)
- [Architecture & Tools](#-architecture--tools)
- [Splunk Monitoring](#-splunk-monitoring)
- [Digital Forensics](#-digital-forensics)

---

## 🚀 About the Project
This project simulates a real-world cybersecurity scenario combining **AI-powered offensive security** (using the Zebbern MCP toolset) with **defensive monitoring and digital forensics**. It demonstrates how automated AI agents can execute multi-stage attacks while defenders monitor and investigate using Splunk, Autopsy, and Volatility.

---

## 📂 Lab Setup & Solution Guide
* Detailed step-by-step documentation, terminal commands, and configuration screenshots can be found in the solution PDF included in this repository:
  - **[View Full Solution Guide (PDF)](./gitdd.pdf)** 
---

## 🛠️ Architecture & Tools
* **Attacker (Kali Linux):** Runs the Zebbern MCP server (139 penetration testing tools) controlled by an AI agent.
* **Victim (Debian Server):** Hosts a vulnerable Flask web application on port `5000` with UFW firewall and SSH enabled.
* **Monitoring (Windows/Splunk):** Ingests system and application logs (`auth.log`, `syslog`, `flask_api.log`) via the Splunk Universal Forwarder.
* **Attack Workflow:** Runs through 5 phases—Reconnaissance, Exploitation, API/AI Attacks, Post-Exploitation, and Active Directory enumeration.

---

## 📊 Splunk Monitoring Queries
Key detection and monitoring queries used during the simulation:
* **User Enumeration:** `index=main whoami`
* **Privilege Escalation:** `index=main sudo`
* **API Endpoints:** `index=main /run endpoint` or `index=main graphql endpoint`
* **Attack Indicators:** Tracked via SQL queries, JWT tokens, and failed login attempts.

---

## 🔍 Digital Forensics
* **Disk Forensics (Autopsy):** Analyzes file system changes and recovery of deleted artifacts.
* **Memory Forensics (Volatility):** Investigates RAM dumps for running processes, injected code, and credentials.
