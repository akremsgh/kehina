# Kehina - Raspberry Pi + MicroPython + Prometheus + AWS + AI Threat Detection

## 📘 Project Overview
This project integrates **Raspberry Pi devices running MicroPython** with **Prometheus monitoring**, **AWS cloud hosting with Terraform + Ansible automation**, and an **AI pipeline for network scanning and threat detection**.

---

## 🏗️ High-Level Architecture

## 🏗️ High-Level Architecture

```mermaid
flowchart LR
    subgraph Edge["Edge Layer (Raspberry Pi + MicroPython)"]
        Pi[Raspberry Pi\nMicroPython Exporter]
    end

    subgraph Monitoring["Monitoring Layer (Prometheus + Grafana)"]
        Prometheus[Prometheus Server]
        Grafana[Grafana Dashboards]
        Prometheus --> Grafana
    end

    subgraph Cloud["AWS Cloud Layer"]
        EC2[EC2 Instances]
        ELB[Elastic Load Balancer]
        S3[S3 / Timestream Storage]
    end

    subgraph Automation["Automation Layer"]
        Terraform[Terraform Infrastructure]
        Ansible[Ansible Configuration]
    end

    subgraph AI["AI Threat Detection Layer"]
        Model[AI Model\nAnomaly Detection]
    end

    Pi --> Prometheus
    Prometheus --> EC2
    EC2 --> ELB
    EC2 --> S3
    Terraform --> EC2
    Ansible --> Prometheus
    Prometheus --> Model
    Model --> Prometheus

---

## 🧩 Component Breakdown

- **Edge Layer (Raspberry Pi + MicroPython)**  
  - Collects traffic metrics.  
  - Exposes Prometheus‑formatted endpoints.  

- **Monitoring Layer (Prometheus + Grafana)**  
  - Scrapes Pi metrics.  
  - Visualizes dashboards.  
  - Configures alerts.  

- **Cloud Layer (AWS Infrastructure)**  
  - Terraform provisions EC2, ELB, S3/Timestream.  
  - Ansible configures Prometheus, Grafana, exporters.  

- **AI Layer (Threat Detection)**  
  - ML models detect anomalies.  
  - Outputs anomaly scores to Prometheus.  
  - Alerts via AWS SNS/Slack.  

---

## 🔧 Implementation Steps

1. Flash MicroPython onto Raspberry Pi.  
2. Develop exporter script for Prometheus metrics.  
3. Deploy Prometheus + Grafana in AWS using Terraform.  
4. Configure with Ansible playbooks.  
5. Train AI anomaly detection model (TensorFlow Lite/scikit‑learn).  
6. Integrate AI outputs into Prometheus metrics.  
7. Set up alerting pipeline (SNS/Slack).  

---

## ⚙️ Terraform + Ansible Workflow

- **Terraform**  
  - Define modules for EC2, ELB, S3.  
  - Apply infrastructure plan.  

- **Ansible**  
  - Configure Prometheus/Grafana.  
  - Set up exporters and security rules.  
  - Automate deployment updates.  

---

## 🤖 AI Threat Detection Pipeline

- Collect logs from Raspberry Pi.  
- Stream to AWS (Kinesis/MQTT).  
- Train anomaly detection model.  
- Deploy inference service in AWS.  
- Feed anomaly scores into Prometheus.  
- Trigger alerts on suspicious activity.  

---

## 🚀 Next Steps

- Draft Terraform modules for AWS infrastructure.  
- Write Ansible playbooks for Prometheus/Grafana setup.  
- Develop MicroPython exporter script.  
- Design AI model for anomaly detection.  

---

## 📌 Tech Stack

- **[Raspberry Pi + MicroPython](ca://s?q=Raspberry_Pi_MicroPython_setup)**  
- **[Prometheus + Grafana](ca://s?q=Prometheus_monitoring_Raspberry_Pi)**  
- **[AWS EC2, ELB, S3, Timestream](ca://s?q=AWS_infrastructure_for_Prometheus)**  
- **[Terraform + Ansible](ca://s?q=Terraform_Ansible_AWS_workflow)**  
- **[AI Threat Detection (TensorFlow Lite / scikit-learn)](ca://s?q=AI_threat_detection_pipeline_AWS)**  

---

## 📄 License
MIT License


