<p align="center">
  <img src="docs/banner.svg" alt="Monitoring Stack Automation banner" width="100%">
</p>

<h1 align="center">📊 Monitoring Stack Automation</h1>

<p align="center">
  A complete, self-hosted observability platform — Prometheus, Grafana, Loki and Alertmanager —
  provisioned with Vagrant and deployed hands-off with Ansible &amp; Docker Compose.
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Vagrant-1868F2?style=for-the-badge&logo=vagrant&logoColor=white" alt="Vagrant">
  <img src="https://img.shields.io/badge/Debian%2012-A81D33?style=for-the-badge&logo=debian&logoColor=white" alt="Debian 12">
  <img src="https://img.shields.io/badge/Ansible-EE0000?style=for-the-badge&logo=ansible&logoColor=white" alt="Ansible">
  <img src="https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white" alt="Docker">
  <img src="https://img.shields.io/badge/Prometheus-E6522C?style=for-the-badge&logo=prometheus&logoColor=white" alt="Prometheus">
  <img src="https://img.shields.io/badge/Grafana-F46800?style=for-the-badge&logo=grafana&logoColor=white" alt="Grafana">
  <img src="https://img.shields.io/badge/Loki-1F2937?style=for-the-badge" alt="Loki">
</p>

<p align="center">
  <a href="https://devriston.com.pk">
    <img src="https://img.shields.io/badge/Portfolio-Devriston-0ea5e9?style=for-the-badge" alt="Portfolio">
  </a>
  <a href="https://www.linkedin.com/in/kamrankabeer/">
    <img src="https://img.shields.io/badge/LinkedIn-Connect-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn">
  </a>
  <a href="https://github.com/muhammadkamrankabeer-oss">
    <img src="https://img.shields.io/badge/GitHub-Profile-181717?style=for-the-badge&logo=github&logoColor=white" alt="GitHub">
  </a>
</p>

---

## 📌 Project Overview

**Monitoring Stack Automation** is a complete observability platform built using Infrastructure as Code (IaC) principles.

The project provisions a Debian 12 virtual machine with **Vagrant**, deploys a full monitoring and logging stack with **Docker Compose**, and automates the entire rollout end-to-end with **Ansible**.

The solution provides:

- 🖥️ Infrastructure monitoring
- 📈 Metrics collection
- 🚨 Alerting
- 📜 Log aggregation
- 📊 Dashboard visualization
- ⚙️ Automated, repeatable deployment

---

## ✨ Features

### 🖥️ Infrastructure Monitoring
- Prometheus metrics collection
- Node Exporter host monitoring
- CPU, memory, disk, and network monitoring

### 🚨 Alerting
- Prometheus alert rules
- Alertmanager integration
- High CPU usage alerts
- Centralized alert management

### 📜 Logging
- Loki log aggregation
- Promtail log collection
- Grafana log exploration

### 📊 Visualization
- Grafana dashboards
- Node Exporter Full Dashboard
- Metrics visualization & log exploration

### ⚙️ Automation
- Vagrant environment provisioning
- Docker Compose deployment
- Ansible automation with a role-based structure

---

## 🏗️ Architecture

```text
Host Machine
     |
     v
Ansible
     |
     v
Vagrant VM (Debian 12)
     |
     v
Docker Engine
     |
     v
Docker Compose
     |
     +---------------------------+
     |                           |
     v                           v
Prometheus                 Alertmanager
     |
     v
Node Exporter

Promtail ---> Loki ---> Grafana
                   ^
                   |
            Prometheus Metrics
```

---

## 🧰 Technology Stack

| Category          | Technology     |
| ------------------ | -------------- |
| Virtualization      | Vagrant        |
| Operating System    | Debian 12      |
| Automation          | Ansible        |
| Container Runtime    | Docker         |
| Orchestration        | Docker Compose |
| Monitoring          | Prometheus     |
| Metrics Exporter    | Node Exporter  |
| Alerting            | Alertmanager   |
| Visualization        | Grafana        |
| Logging              | Loki           |
| Log Collection        | Promtail       |

---

## 📂 Repository Structure

```text
monitoring-stack-automation/
│
├── Vagrantfile
├── README.md
│
├── ansible/
│   ├── inventory/
│   ├── playbooks/
│   └── roles/
│
├── configs/
│   ├── prometheus.yml
│   ├── alertmanager.yml
│   ├── alert_rules.yml
│   ├── loki-config.yml
│   └── promtail-config.yml
│
├── docker/
│   └── docker-compose.yml
│
└── docs/
    ├── banner.svg
    ├── architecture/
    ├── interview/
    └── screenshots/
```

---

## 🚀 Deployment Workflow

### 1️⃣ Start the virtual machine
```bash
vagrant up
```

### 2️⃣ Connect to the virtual machine
```bash
vagrant ssh
```

### 3️⃣ Deploy the stack with Docker Compose
```bash
cd /home/vagrant/monitoring-stack/docker
docker compose up -d
```

### 4️⃣ Or deploy the stack with Ansible
```bash
cd ansible
ansible-playbook playbooks/deploy-monitoring.yml
```

---

## 🌐 Services

| Service       | Port |
| -------------- | ---- |
| Grafana        | 3000 |
| Prometheus     | 9090 |
| Alertmanager   | 9093 |
| Node Exporter  | 9100 |
| Loki           | 3100 |

---

## 📸 Screenshots

### 🐳 Stack Up & Running
![Docker containers running](docs/screenshots/stack-services-running.png)

### 🎯 Prometheus Targets
<p>
  <img src="docs/screenshots/prometheus-targets-up.png" alt="Prometheus targets up" width="48%">
  <img src="docs/screenshots/prometheus-scrape-targets.png" alt="Prometheus scrape targets" width="48%">
</p>

### 📐 Prometheus Alert Rules
![Prometheus alert rules](docs/screenshots/prometheus-alert-rules.png)

### 🚨 Active Alerts
<p>
  <img src="docs/screenshots/prometheus-alert-firing.png" alt="Prometheus alert firing" width="48%">
  <img src="docs/screenshots/alertmanager-active-alerts.png" alt="Alertmanager active alerts" width="48%">
</p>

### 📊 Grafana
<p>
  <img src="docs/screenshots/grafana-prometheus-datasource.png" alt="Grafana Prometheus datasource" width="48%">
  <img src="docs/screenshots/grafana-node-exporter-dashboard.png" alt="Grafana Node Exporter dashboard" width="48%">
  <img src="docs/screenshots/grafana-loki-datasource.png" alt="Grafana Loki datasource" width="48%">
  <img src="docs/screenshots/grafana-loki-logs-visible.png" alt="Grafana Loki logs visible" width="48%">
</p>

### ⚙️ Automation
![Ansible playbook working](docs/screenshots/play-book-working.png)

---

## 📖 Documentation

| Doc | Path |
| --- | ---- |
| 🏗️ Architecture notes | [`docs/architecture/architecture.md`](docs/architecture/architecture.md) |
| 🎤 Interview preparation | [`docs/interview/interview.md`](docs/interview/interview.md) |

---

## 🎯 Learning Outcomes

This project demonstrates practical, hands-on experience with:

- Infrastructure as Code
- Monitoring and Observability
- Metrics Collection
- Alerting Workflows
- Centralized Logging
- Docker Containerization
- Ansible Automation
- Vagrant-based Lab Environments
- Linux System Monitoring

---

## 👤 Author

<p align="center">
  <strong>Muhammad Kamran Kabeer</strong><br>
  DevOps | Cloud | Linux | Automation | Observability
</p>

<p align="center">
  <a href="https://devriston.com.pk">
    <img src="https://img.shields.io/badge/🌐 Website-devriston.com.pk-0ea5e9?style=for-the-badge" alt="Website">
  </a>
  <a href="https://www.linkedin.com/in/kamrankabeer/">
    <img src="https://img.shields.io/badge/LinkedIn-Muhammad%20Kamran%20Kabeer-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn">
  </a>
  <a href="https://github.com/muhammadkamrankabeer-oss">
    <img src="https://img.shields.io/badge/GitHub-muhammadkamrankabeer--oss-181717?style=for-the-badge&logo=github&logoColor=white" alt="GitHub">
  </a>
</p>
