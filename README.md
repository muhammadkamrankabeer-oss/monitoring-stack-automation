# Monitoring Stack Automation

## Project Overview

Monitoring Stack Automation is a complete observability platform built using Infrastructure as Code (IaC) principles.

The project provisions a Debian 12 virtual machine using Vagrant, deploys a monitoring and logging stack with Docker Compose, and automates deployment through Ansible.

The solution provides:

* Infrastructure monitoring
* Metrics collection
* Alerting
* Log aggregation
* Dashboard visualization
* Automated deployment

---

## Features

### Infrastructure Monitoring

* Prometheus metrics collection
* Node Exporter host monitoring
* CPU monitoring
* Memory monitoring
* Disk monitoring
* Network monitoring

### Alerting

* Prometheus alert rules
* Alertmanager integration
* High CPU usage alerts
* Centralized alert management

### Logging

* Loki log aggregation
* Promtail log collection
* Grafana log exploration

### Visualization

* Grafana dashboards
* Node Exporter Full Dashboard
* Metrics visualization
* Log exploration

### Automation

* Vagrant environment provisioning
* Docker Compose deployment
* Ansible automation
* Role-based Ansible structure

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

## Technology Stack

| Category          | Technology     |
| ----------------- | -------------- |
| Virtualization    | Vagrant        |
| Operating System  | Debian 12      |
| Automation        | Ansible        |
| Container Runtime | Docker         |
| Orchestration     | Docker Compose |
| Monitoring        | Prometheus     |
| Metrics Exporter  | Node Exporter  |
| Alerting          | Alertmanager   |
| Visualization     | Grafana        |
| Logging           | Loki           |
| Log Collection    | Promtail       |

---

## Repository Structure

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
    ├── architecture/
    ├── interview/
    └── screenshots/
```

---

## Deployment Workflow

### Start Virtual Machine

```bash
vagrant up
```

### Connect to Virtual Machine

```bash
vagrant ssh
```

### Deploy Stack Using Docker Compose

```bash
cd /home/vagrant/monitoring-stack/docker

docker compose up -d
```

### Deploy Stack Using Ansible

```bash
cd ansible

ansible-playbook playbooks/deploy-monitoring.yml
```

---

## Services

| Service       | Port |
| ------------- | ---- |
| Grafana       | 3000 |
| Prometheus    | 9090 |
| Alertmanager  | 9093 |
| Node Exporter | 9100 |
| Loki          | 3100 |

---

## Screenshots

### Docker Containers Running

* stack-services-running.png

### Prometheus Targets

* prometheus-targets-up.png
* prometheus-scrape-targets.png

### Prometheus Alert Rules

* prometheus-alert-rules.png

### Active Alerts

* prometheus-alert-firing.png
* alertmanager-active-alerts.png

### Grafana

* grafana-prometheus-datasource.png
* grafana-node-exporter-dashboard.png
* grafana-loki-datasource.png
* grafana-loki-logs-visible.png

### Automation

* play-book-working.png

---

## Documentation

### Architecture

```text
docs/architecture/architecture.md
```

### Interview Preparation

```text
docs/interview/interview.md
```

---

## Learning Outcomes

This project demonstrates practical experience with:

* Infrastructure as Code
* Monitoring and Observability
* Metrics Collection
* Alerting Workflows
* Centralized Logging
* Docker Containerization
* Ansible Automation
* Vagrant-based Lab Environments
* Linux System Monitoring

---

## Author

Muhammad Kamran Kabeer

DevOps | Cloud | Linux | Automation | Observability
