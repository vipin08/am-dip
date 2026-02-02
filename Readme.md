# AM-DIP – Autonomous Monitoring & Deployment Intelligence Platform

AM-DIP is a DevOps and cloud-native project that demonstrates how a containerized application can be automatically built, deployed, monitored, and reacted upon using modern infrastructure automation tools.

The focus of this project is not application complexity, but **system design, automation, monitoring, and intelligent decision-making**, which are core responsibilities in real-world DevOps and SRE roles.

-------------------------------------------------------------------

## 🚀 What Problem Does AM-DIP Solve?

In real production environments:
- Applications may crash
- Pods may restart frequently
- Performance may degrade unexpectedly

AM-DIP simulates such failures and shows how an automated system can:
- Detect issues using metrics and alerts
- Decide when the system is unhealthy
- Trigger corrective or failover actions without manual intervention

-------------------------------------------------------------------

## 🧠 High-Level Architecture

GitHub (Source Code)
|
Jenkins (CI/CD Pipeline)
|
Docker (Container Image)
|
Kubernetes (Minikube Cluster)
|
Prometheus (Metrics Collection)
|
Alertmanager (Alert Trigger)
|
Python Logic Engine
|
Failover Decision (Simulated)

-------------------------------------------------------------------

## 🧩 Core Components

### 🔹 Application Layer
- Simple Flask-based web application
- Exposes application and health endpoints
- Containerized using Docker

### 🔹 CI/CD Layer
- Jenkins automates the build and deployment process
- Jenkinsfile defines the entire pipeline as code
- On every run, Docker images are built and deployed automatically

### 🔹 Orchestration Layer
- Kubernetes manages application lifecycle
- Deployment and Service manifests define desired state
- Application runs inside a Kubernetes cluster (Minikube)

### 🔹 Monitoring & Observability
- Prometheus collects Kubernetes and pod-level metrics
- Grafana visualizes CPU, memory, and pod behavior
- System health can be observed in real time

### 🔹 Alerting & Intelligence
- Prometheus alert rules detect abnormal behavior (e.g., frequent pod restarts)
- Alertmanager sends alerts to a webhook
- Python-based logic engine processes alerts and decides system state

### 🔹 Failover Simulation
- Failover state is maintained using a state file
- When alerts cross thresholds, the system automatically switches traffic state
- The design can be extended to real DNS-based or multi-cloud failover

-------------------------------------------------------------------

## 📂 Repository Structure

am-dip/
│
├── app/ # Application source code
│ ├── app.py
│ ├── Dockerfile
│ └── requirements.txt
│
├── k8s/ # Kubernetes manifests
│ ├── deployment.yaml
│ └── service.yaml
│
├── monitoring/ # Monitoring & alerting configs
│ ├── alerts.yaml
│ └── alertmanager.yaml
│
├── logic-engine/ # Intelligence & decision logic
│ ├── decide.py
│ ├── webhook.py
│ └── failover_state.txt
│
├── Jenkinsfile # CI/CD pipeline definition
└── README.md

-------------------------------------------------------------------

## 🧪 Failure Scenarios Tested

- Pod deletion
- Pod restarts
- Unstable application behavior

These failures are detected by Prometheus, alerts are triggered, and automated logic reacts accordingly.

-------------------------------------------------------------------

## 🎯 Key Skills Demonstrated

- CI/CD pipeline design using Jenkins
- Docker containerization
- Kubernetes deployments and services
- Monitoring and observability with Prometheus & Grafana
- Alert-driven automation
- Infrastructure and system-level thinking
- Automation-first DevOps mindset

-------------------------------------------------------------------

## 🗣️ Interview One-Liner

> “I built an automated deployment and monitoring system where Jenkins deploys containerized applications to Kubernetes, Prometheus detects failures, and a logic engine triggers failover decisions.”

-------------------------------------------------------------------

## ⚠️ Notes

- This project emphasizes **automation and reliability**, not business logic
- Failover is currently simulated and can be extended to real cloud DNS or load balancers
- The architecture is cloud-ready and can be deployed to AWS or GCP

-------------------------------------------------------------------

## 🔮 Possible Extensions

- Multi-cloud deployment (AWS EKS + GCP GKE)
- DNS-based traffic switching
- Slack or email alert integration
- Predictive failure detection using ML
