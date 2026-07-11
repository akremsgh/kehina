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
    Model --> Prometheus
