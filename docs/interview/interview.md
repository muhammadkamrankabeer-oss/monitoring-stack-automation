# Monitoring Stack Automation – Interview Questions & Answers

## 1. What problem does this project solve?

This project provides a complete observability platform that collects metrics, visualizes infrastructure health, generates alerts, and centralizes logs using Prometheus, Grafana, Alertmanager, Loki, and Promtail.

---

## 2. What tools are used in this project?

* Vagrant
* Debian Linux
* Docker
* Docker Compose
* Ansible
* Prometheus
* Node Exporter
* Alertmanager
* Grafana
* Loki
* Promtail

---

## 3. Why did you use Vagrant?

Vagrant provides a reproducible virtual machine environment that can be created and destroyed consistently.

---

## 4. Why did you use Docker?

Docker simplifies deployment and ensures all monitoring components run consistently across environments.

---

## 5. What is Infrastructure as Code?

Infrastructure as Code (IaC) is the practice of managing infrastructure through code instead of manual configuration.

---

## 6. What is Ansible?

Ansible is an agentless automation tool used for configuration management and application deployment.

---

## 7. What is an Ansible Inventory?

An inventory defines the target hosts that Ansible manages.

---

## 8. What is an Ansible Playbook?

A playbook is a YAML file containing automation tasks executed against managed hosts.

---

## 9. What is an Ansible Role?

Roles organize automation code into reusable components.

---

## 10. What is Docker Compose?

Docker Compose manages multi-container applications using a single YAML file.

---

## 11. What is Prometheus?

Prometheus is an open-source monitoring and metrics collection system.

---

## 12. How does Prometheus collect metrics?

Prometheus periodically scrapes HTTP endpoints exposed by exporters.

---

## 13. What is a Prometheus Target?

A target is an endpoint Prometheus scrapes for metrics.

---

## 14. What is Node Exporter?

Node Exporter exposes Linux system metrics to Prometheus.

---

## 15. Which metrics can Node Exporter provide?

* CPU
* Memory
* Disk
* Filesystem
* Network
* Load Average

---

## 16. What is a Prometheus Job?

A job groups targets that perform the same function.

---

## 17. What is a Prometheus Rule?

Rules evaluate metrics and can generate alerts.

---

## 18. What is PromQL?

PromQL is the Prometheus Query Language used to analyze metrics.

---

## 19. What is Alertmanager?

Alertmanager receives alerts from Prometheus and manages routing, grouping, and notifications.

---

## 20. What is alert routing?

Routing determines where alerts should be sent.

---

## 21. What is alert grouping?

Grouping combines similar alerts to reduce noise.

---

## 22. What alert was implemented in this project?

High CPU utilization alert.

---

## 23. How was the CPU alert configured?

A Prometheus alert rule fires when CPU utilization exceeds a defined threshold for a specified duration.

---

## 24. What is Grafana?

Grafana is a visualization platform used for dashboards and monitoring.

---

## 25. Why is Grafana popular?

It supports multiple data sources and provides rich dashboards.

---

## 26. What data sources were configured?

* Prometheus
* Loki

---

## 27. What is Loki?

Loki is a log aggregation system developed by Grafana Labs.

---

## 28. How is Loki different from Elasticsearch?

Loki indexes labels instead of full log contents, making it lightweight and cost-effective.

---

## 29. What is Promtail?

Promtail collects logs and forwards them to Loki.

---

## 30. What logs were collected?

Linux system logs from /var/log.

---

## 31. How do users view logs?

Logs are viewed through Grafana Explore.

---

## 32. What is observability?

Observability combines metrics, logs, and alerts to understand system behavior.

---

## 33. What is the difference between monitoring and observability?

Monitoring tracks known metrics, while observability helps investigate unknown issues using multiple data sources.

---

## 34. What networking model was used?

Docker Bridge Networking.

---

## 35. Why are container names used in Prometheus configuration?

Docker DNS automatically resolves container names.

---

## 36. How does Prometheus communicate with Alertmanager?

Through the alerting configuration section in prometheus.yml.

---

## 37. What happens when CPU usage exceeds the threshold?

Prometheus evaluates the rule and sends an alert to Alertmanager.

---

## 38. How did you test alerting?

CPU load was artificially increased until the alert transitioned from pending to firing.

---

## 39. What screenshots were collected?

* Running containers
* Prometheus Targets
* Alert Rules
* Firing Alerts
* Alertmanager Alerts
* Grafana Dashboard
* Grafana Data Sources
* Loki Logs

---

## 40. Why was Loki added?

To provide centralized logging and complete observability.

---

## 41. What is a monitoring stack?

A collection of tools used for metrics, logging, alerting, and visualization.

---

## 42. What security improvements could be added?

* TLS
* Authentication
* Secrets Management
* Role-Based Access Control

---

## 43. How would you scale this project?

* Multiple exporters
* Remote storage
* Kubernetes deployment
* High Availability Alertmanager

---

## 44. What production improvements would you implement?

* Persistent storage
* Backup strategy
* Notification integrations
* Monitoring multiple hosts

---

## 45. What was the biggest learning outcome?

Building a complete observability platform using automation and Infrastructure as Code principles.

---

## 46. Why is observability important in DevOps?

It provides visibility into infrastructure and application health.

---

## 47. What DevOps concepts are demonstrated?

* Infrastructure as Code
* Monitoring
* Logging
* Alerting
* Automation
* Containerization

---

## 48. What would you improve next?

* Email alerts
* Slack integration
* Kubernetes deployment
* Multi-node monitoring

---

## 49. Why is Grafana paired with Prometheus?

Prometheus stores metrics while Grafana visualizes them.

---

## 50. Explain this project in one minute.

This project automates deployment of a complete observability platform using Vagrant, Ansible, Docker, Prometheus, Grafana, Alertmanager, Loki, and Promtail. The platform collects infrastructure metrics, visualizes system health, generates alerts, and centralizes logs, demonstrating monitoring, logging, alerting, automation, and Infrastructure as Code practices.
