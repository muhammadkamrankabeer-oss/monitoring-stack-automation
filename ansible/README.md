# Monitoring Stack Automation

## Project Overview

Monitoring Stack Automation is a complete observability platform that automates the deployment of monitoring, alerting, visualization, and centralized logging components using Infrastructure as Code practices.

The project provisions a reproducible Debian virtual machine using Vagrant, deploys a containerized monitoring stack with Docker Compose, and automates deployment using Ansible.

The platform provides:

* Infrastructure Monitoring
* Metrics Collection
* Alerting
* Log Aggregation
* Dashboard Visualization
* Infrastructure Automation

---

## Architecture

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

## Features

### Infrastructure Monitoring

Monitor Linux host metrics including:

* CPU Usage
* Memory Utilization
* Disk Usage
* Filesystem Metrics
* Network Statistics
* System Load

### Alerting

Prometheus alert rules generate alerts when predefined thresholds are exceeded.

Implemented alert:

* High CPU Utilization Alert

### Visualization

Grafana dashboards provide real-time visualization of infrastructure metrics.

### Centralized Logging

Loki and Promtail collect and centralize Linux system logs for troubleshooting and analysis.

### Automation

Deployment is automated using:

* Vagrant
* Ansible
* Docker Compose

---

## Technology Stack

| Category                | Technology     |
| ----------------------- | -------------- |
| Virtualization          | Vagrant        |
| Operating System        | Debian 12      |
| Automation              | Ansible        |
| Container Runtime       | Docker         |
| Container Orchestration | Docker Compose |
| Monitoring              | Prometheus     |
| Metrics Exporter        | Node Exporter  |
| Alerting                | Alertmanager   |
| Visualization           | Grafana        |
| Logging                 | Loki           |
| Log Collection          | Promtail       |

---

## Repository Structure

```text
monitoring-stack-automation/
│
├── ansible/
│   ├── inventory/
│   ├── playbooks/
│   └── roles/
│
├── configs/
│   ├── prometheus.yml
│   ├── alert_rules.yml
│   ├── alertmanager.yml
│   ├── loki-config.yml
│   └── promtail-config.yml
│
├── docker/
│   └── docker-compose.yml
│
├── docs/
│   ├── architecture/
│   ├── interview/
│   └── screenshots/
│
├── README.md
└── Vagrantfile
```

---

## Monitoring Components

### Prometheus

Prometheus collects metrics from monitored targets and evaluates alert rules.

Responsibilities:

* Metrics Collection
* Metrics Storage
* PromQL Queries
* Alert Evaluation

---

### Node Exporter

Node Exporter exposes Linux host metrics.

Collected metrics:

* CPU
* RAM
* Filesystem
* Disk
* Network
* Load Average

---

### Alertmanager

Alertmanager receives alerts from Prometheus and manages alert routing.

Responsibilities:

* Alert Routing
* Alert Grouping
* Alert Deduplication

---

### Grafana

Grafana visualizes metrics and logs through dashboards.

Capabilities:

* Infrastructure Dashboards
* Data Source Management
* Log Exploration
* Alert Visualization

---

### Loki

Loki provides centralized log aggregation.

Benefits:

* Lightweight Architecture
* Efficient Storage
* Native Grafana Integration

---

### Promtail

Promtail collects logs from Linux hosts and forwards them to Loki.

---

## Deployment Workflow

```text
Developer
     |
     v
Vagrant Up
     |
     v
Debian VM
     |
     v
Docker Installation
     |
     v
Docker Compose
     |
     v
Monitoring Stack Running
```

---

## Automation Workflow

```text
Ansible Inventory
        |
        v
Ansible Playbook
        |
        v
Docker Installation
        |
        v
Docker Service
        |
        v
Monitoring Deployment
```

---

## Metrics Flow

```text
Linux Host
     |
     v
Node Exporter
     |
     v
Prometheus
     |
     v
Grafana
```

---

## Alerting Flow

```text
Node Exporter
      |
      v
Prometheus Rules
      |
      v
Alertmanager
      |
      v
Alert Processing
```

---

## Logging Flow

```text
Linux Logs
     |
     v
Promtail
     |
     v
Loki
     |
     v
Grafana Explore
```

---

## Screenshots

### Running Monitoring Stack

![Running Stack](docs/screenshots/stack-services-running.png)

### Prometheus Targets

![Prometheus Targets](docs/screenshots/prometheus-targets-up.png)

### Prometheus Scrape Targets

![Prometheus Scrape Targets](docs/screenshots/prometheus-scrape-targets.png)

### Alert Rules

![Alert Rules](docs/screenshots/prometheus-alert-rules.png)

### Alert Firing

![Alert Firing](docs/screenshots/prometheus-alert-firing.png)

### Alertmanager

![Alertmanager](docs/screenshots/alertmanager-active-alerts.png)

### Grafana Dashboard

![Grafana Dashboard](docs/screenshots/grafana-node-exporter-dashboard.png)

### Prometheus Data Source

![Prometheus Datasource](docs/screenshots/grafana-prometheus-datasource.png)

### Loki Data Source

![Loki Datasource](docs/screenshots/grafana-loki-datasource.png)

### Loki Logs

![Loki Logs](docs/screenshots/grafana-loki-logs-visible.png)

---

## Prerequisites

Install:

* VirtualBox
* Vagrant
* Ansible
* Git

---

## Deploy the Environment

### Clone Repository

```bash
git clone https://github.com/muhammadkamrankabeer-oss/monitoring-stack-automation.git

cd monitoring-stack-automation
```

---

### Start Virtual Machine

```bash
vagrant up
```

---

### Access Virtual Machine

```bash
vagrant ssh
```

---

### Verify Containers

```bash
docker ps
```

---

## Ansible Deployment

Validate inventory:

```bash
ansible-inventory -i inventory/hosts --list
```

Check connectivity:

```bash
ansible -i inventory/hosts monitoring -m ping
```

Dry run:

```bash
ansible-playbook playbooks/deploy-monitoring.yml --check
```

Deploy:

```bash
ansible-playbook playbooks/deploy-monitoring.yml
```

---

## Access Services

| Service      | URL                   |
| ------------ | --------------------- |
| Grafana      | http://localhost:3000 |
| Prometheus   | http://localhost:9090 |
| Alertmanager | http://localhost:9093 |
| Loki         | http://localhost:3100 |

---

## Validation Commands

```bash
docker ps
```

```bash
docker compose ps
```

```bash
docker logs prometheus
```

```bash
docker logs alertmanager
```

```bash
docker logs loki
```

```bash
docker logs promtail
```

---

## Skills Demonstrated

* Infrastructure as Code
* Configuration Management
* Monitoring
* Alerting
* Log Aggregation
* Docker
* Docker Compose
* Ansible
* Linux Administration
* Observability
* Troubleshooting

---

## Lessons Learned

Through this project I gained hands-on experience with:

* Building observability platforms
* Prometheus monitoring architecture
* Grafana dashboards
* Alertmanager alert routing
* Loki log aggregation
* Promtail log collection
* Ansible automation
* Docker-based deployments
* Infrastructure troubleshooting

---

## Future Improvements

Potential enhancements:

* Email Notifications
* Slack Integration
* Multi-Host Monitoring
* Prometheus Persistent Storage
* Grafana Provisioning
* HTTPS/TLS Support
* Kubernetes Deployment
* High Availability Monitoring

---

## Interview Preparation

A complete interview preparation guide is available in:

```text
docs/interview/interview.md
```

---

## Author

Muhammad Kamran Kabeer

DevOps | Cloud | Automation | Infrastructure as Code

GitHub:

https://github.com/muhammadkamrankabeer-oss
