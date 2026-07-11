# Kehina - Raspberry Pi + MicroPython + Prometheus + AWS + AI Threat Detection

## 📘 Project Overview
This project integrates **Raspberry Pi devices running MicroPython** with **Prometheus monitoring**, **AWS cloud hosting with Terraform + Ansible automation**, and an **AI pipeline for network scanning and threat detection**.

---

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
    Model --> Prometheus ```

## 🧩 Component Breakdown

### Edge Layer (Raspberry Pi + MicroPython)
- Collects traffic metrics
- Exposes Prometheus‑formatted endpoints

### Monitoring Layer (Prometheus + Grafana)
- Scrapes Pi metrics
- Visualizes dashboards
- Configures alerts

### Cloud Layer (AWS Infrastructure)
- Terraform provisions EC2, ELB, S3/Timestream
- Ansible configures Prometheus, Grafana, exporters

### AI Layer (Threat Detection)
- ML models detect anomalies
- Outputs anomaly scores to Prometheus
- Alerts via AWS SNS/Slack

---

## 🔧 Implementation Steps
- Flash MicroPython onto Raspberry Pi  
- Develop exporter script for Prometheus metrics  
- Deploy Prometheus + Grafana in AWS using Terraform  
- Configure with Ansible playbooks  
- Train AI anomaly detection model (TensorFlow Lite/scikit‑learn)  
- Integrate AI outputs into Prometheus metrics  
- Set up alerting pipeline (SNS/Slack)  

---

## ⚙️ Terraform + Ansible Workflow
**Terraform**
- Define modules for EC2, ELB, S3  
- Apply infrastructure plan  

**Ansible**
- Configure Prometheus/Grafana  
- Set up exporters and security rules  
- Automate deployment updates  

---

## 🤖 AI Threat Detection Pipeline
- Collect logs from Raspberry Pi  
- Stream to AWS (Kinesis/MQTT)  
- Train anomaly detection model  
- Deploy inference service in AWS  
- Feed anomaly scores into Prometheus  
- Trigger alerts on suspicious activity  

---

## 🚀 Next Steps
- Draft Terraform modules for AWS infrastructure  
- Write Ansible playbooks for Prometheus/Grafana setup  
- Develop MicroPython exporter script  
- Design AI model for anomaly detection  

---

## 📌 Tech Stack
- Raspberry Pi + MicroPython  
- Prometheus + Grafana  
- AWS EC2, ELB, S3, Timestream  
- Terraform + Ansible  
- AI Threat Detection (TensorFlow Lite / scikit‑learn)  

---

## 📄 License
GNU General Public License v3.0

