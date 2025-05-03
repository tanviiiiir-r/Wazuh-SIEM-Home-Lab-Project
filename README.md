# 🛡️ Wazuh SIEM Home Lab on Docker

A comprehensive Security Information and Event Management (SIEM) home lab environment built using Docker and Wazuh. This project demonstrates the setup, configuration, and monitoring capabilities of Wazuh in a simulated home lab environment for log monitoring and security visibility.

---

## 📌 Objective

To create a local SIEM environment using Wazuh with Docker containers to:

* Monitor a Linux host (victim container)
* Simulate log collection from system activities
* Visualize security alerts and logs in the Wazuh dashboard

This project is designed for educational and demonstration purposes, particularly for cybersecurity-focused programs like Erasmus.

---

## 🧰 Technologies Used

* 🐳 Docker + Docker Compose
* 📦 Wazuh (Manager, Dashboard, Agent)
* 🐧 Ubuntu (Victim container)

---

## 🏗️ Project Architecture

```
+-----------------+      +------------------+      +--------------------+
|  Wazuh Manager  | <--> | Wazuh Dashboard  | <--> |  Analyst (Browser) |
+-----------------+      +------------------+      +--------------------+
        ^                         ^
        |                         |
        v                         |
+------------------+              |
| Wazuh Agent on   |--------------+
| Victim Container |
+------------------+
```

---

## 🚀 Setup Steps

### 1. Clone the Repository

```bash
git clone https://github.com/yourusername/wazuh-siem-homelab.git
cd wazuh-siem-homelab
```

### 2. Start the Wazuh Environment

```bash
docker compose up -d
```

### 3. Access the Dashboard

Visit: `https://localhost:5601`
Username: `admin`
Password: `SecretPassword`

### 4. Add Wazuh Agent to Victim

Ensure that:

* The victim container has the Wazuh agent installed
* It is configured to communicate with the Wazuh manager IP

Run this inside the victim:

```bash
/var/ossec/bin/agent-auth -m <WAZUH_MANAGER_IP>
systemctl restart wazuh-agent
```

---

## 📸 Screenshots

### 🖥️ 1. Wazuh Dashboard Login

![Wazuh Dashboard](screenshots/01_dashboard.png)  
Wazuh Dashboard login page after successful installation.

---

### 🛰️ 2. Registered Agent List

![Agents List](screenshots/02_agents.png)  
This shows the connected agents including the `wazuh-victim`.

---

### 📡 3. Real-Time Logs in Discover

![Logs Stream](screenshots/03_logs_stream.png)  
Live streaming of logs from the victim container, accessible via the Discover panel.

---

### 🔐 4. Syscheck Alerts

![Syscheck Alerts](screenshots/04_syscheck_alerts.png)  
File integrity alerts detected by the Wazuh agent using Syscheck.

---

### 🛡️ 5. SCA Scan Results

![SCA Results](screenshots/05_sca_scan_result.png)  
Security Configuration Assessment (SCA) results for Ubuntu 22.04 baseline checks.

---

## 📂 Folder Structure

```
wazuh-siem-homelab/
├── docker-compose.yml
│   
├── screenshots/
│   ├── 01_dashboard.png
│   ├── 02_agents.png
│   ├── 03_logs_stream.png
│   ├── 04_syscheck_alerts.png
│   └── 05_sca_scan_result.png
└── README.md
```

---

## 📘 What You’ll Learn

* Deploying a SIEM lab using Docker
* Wazuh architecture and configuration
* Monitoring Linux system logs
* Viewing SCA, Syscheck, and general agent activity

---

## 🌍 Why This Project Matters (Academic Relevance)

This home lab setup offers hands-on experience with:

* Real-world open-source SIEM technology (Wazuh)
* Cybersecurity visibility and audit compliance tracking
* Skills in Docker, Linux, and system monitoring

It reflects capability in:

* Technical system administration
* Basic SOC monitoring skills
* Infrastructure-as-code deployments

---

## 📜 License

MIT License

---

## ✨ Author

**Md Tanvir Rana**
Cybersecurity & SIEM Enthusiast
[LinkedIn](https://www.linkedin.com/in/md-tanvir-rana-770001243/) |