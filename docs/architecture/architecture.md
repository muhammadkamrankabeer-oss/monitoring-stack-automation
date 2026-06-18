# Monitoring Stack Architecture

## High-Level Architecture

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

## Overview

This project deploys a complete observability platform inside a Debian virtual machine provisioned by Vagrant. The entire monitoring stack is containerized using Docker Compose and can be deployed automatically using Ansible.

## Components

### Prometheus

Prometheus collects and stores metrics from monitored targets and evaluates alert rules.

### Node Exporter

Node Exporter exposes CPU, memory, disk, filesystem, and network metrics from the Linux host.

### Alertmanager

Alertmanager receives alerts from Prometheus and manages alert routing and notifications.

### Grafana

Grafana provides dashboards, visualization, and log exploration capabilities.

### Loki

Loki stores and indexes logs collected from the monitored system.

### Promtail

Promtail collects log files and forwards them to Loki.

### Docker

Docker provides containerized deployment for all monitoring components.

### Vagrant

Vagrant provisions a reproducible Debian virtual machine environment.

### Ansible

Ansible automates deployment and configuration management tasks.

---

## Metrics Flow

Node Exporter

→ Prometheus

→ Grafana Dashboards

---

## Alerting Flow

Node Exporter Metrics

→ Prometheus Alert Rules

→ Alertmanager

→ Alert Processing

---

## Logging Flow

Linux System Logs

→ Promtail

→ Loki

→ Grafana Explore

---

## Automation Flow

Ansible Inventory

→ Ansible Playbook

→ Docker Installation

→ Monitoring Stack Deployment
