# Mini SOAR Project – Cloud Security Automation

## 📌 Project Overview
This project presents a **mini SOAR (Security Orchestration, Automation, and Response)** pipeline implemented using open‑source tools and deployed on an AWS EC2 instance.

The objective of this mini project is to demonstrate how security events can be centralized, processed, and automatically escalated to an incident management platform using workflow automation.

This project was developed as a proof of concept for cloud security monitoring and SOAR fundamentals.

---

## 🏗️ Architecture

The solution is composed of the following components:

- **Graylog** – SIEM used for log ingestion, analysis, and alert generation  
- **n8n** – Workflow automation and orchestration engine  
- **TheHive 5** – Incident and case management platform  
- **Docker** – Containerized deployment  
- **AWS EC2** – Cloud infrastructure hosting the environment  

### High‑level workflow:
Security Events
↓
Graylog (SIEM)
↓ (Alert / Event)
Webhook
↓
n8n
↓
TheHive (Alert / Case)

---

## ⚙️ Features

- Centralized ingestion of simulated security events
- Detection of sensitive activities (e.g. IAM‑related actions)
- Automated alert forwarding using webhooks
- Conditional processing of alerts using n8n workflows
- Automatic creation of alerts or cases in TheHive
- Containerized and modular architecture

---

## 🧪 Event Simulation

Due to access limitations to real cloud audit logs, the project uses **simulated security events** to represent realistic cloud security scenarios such as:
- Suspicious access attempts
- Privilege‑related actions
- High‑risk security activities

These simulated events are sufficient to validate the SOAR pipeline logic and automation flow.

---

## 🚨 Alerting & Automation

- Alerts are generated in **Graylog** based on predefined rules
- Alerts are sent to **n8n** via HTTP webhooks
- n8n workflows evaluate event attributes (e.g. risk level)
- High‑risk events trigger automatic creation of alerts or cases in **TheHive**

---

## 🛠️ Deployment

The entire environment is deployed on a single AWS EC2 instance using Docker containers.

Main exposed services:
- Graylog Web Interface: `http://<EC2_IP>:9000`
- TheHive Web Interface: `http://<EC2_IP>:9002`
- n8n Web Interface: `http://<EC2_IP>:5678`

---

## ⚠️ Limitations

- The project does not implement a formal risk calculation model
- Risk levels are assigned directly without impact/likelihood scoring
- Events are simulated and not sourced from real cloud provider audit logs

These limitations were identified as improvement points for future work.

---

## 🚀 Future Improvements

- Implementation of a formal **risk calculation model**
- Integration with real cloud audit logs (e.g. AWS CloudTrail)
- Risk‑based decision making (LOW / MEDIUM / HIGH)
- Automated remediation actions
- Threat intelligence enrichment

---

## 🎓 Academic Context

This mini project serves as an introduction to:
- SIEM concepts
- SOAR architecture
- Security automation
- Incident management workflows

It provides a solid foundation for a more advanced, risk‑based SOAR project.

---

## 👤 Author

- **Hedir Bel arbia**

