# 🧠 Design and Optimization of a Cloud-Based Transactional Data Lake for Evolving Data Models

This repository contains the implementation and documentation of my **Master’s Thesis** project — an end-to-end cloud-based **transactional data lakehouse** built with **Apache Iceberg** and **AWS** services.  

The project bridges the gap between traditional data lakes and warehouses by introducing **ACID compliance**, **schema evolution**, and **real-time adaptability**, optimized for large-scale and evolving analytical workloads.

---

## 📖 Abstract

The rapid expansion of data-driven applications demands scalable and transactional cloud architectures.  
This project designs and evaluates a **data lakehouse** that integrates the flexibility of **data lakes** with the transactional integrity of **data warehouses**, leveraging **Apache Iceberg** as the open table format.  

It benchmarks **Copy-on-Write (CoW)** and **Merge-on-Read (MoR)** strategies to assess ingestion throughput, query performance, and compaction efficiency, while demonstrating schema evolution, rollback, and time travel capabilities.

---

## 🧩 Architecture Overview

The proposed lakehouse is composed of **five modular layers**:

1. **Ingestion Layer** — IoT data ingestion using **AWS IoT Core** and **MQTT** protocols.  
2. **Storage Layer** — Persistent, scalable storage in **Amazon S3** (raw + curated zones).  
3. **Processing Layer** — ETL pipelines using **AWS Glue** and **Apache Spark** with metadata tracked in **AWS Glue Data Catalog**.  
4. **API Layer** — Query access via **Amazon Athena** for SQL-based analytics.  
5. **Consumption Layer** — Interactive visualization and real-time monitoring through **Grafana** and **Amazon CloudWatch**.

---

## 🧪 Research Focus

The main research objective is to design and optimize a **transactional, cloud-native data lakehouse** capable of handling high-ingestion IoT data streams while maintaining performance, consistency, and reliability.

### 🔍 Comparative Evaluation
- **Apache Iceberg vs Apache Hudi**
- **Copy-on-Write (CoW)** vs **Merge-on-Read (MoR)**
- Analysis of **query latency**, **ingestion throughput**, **compaction cost**, and **metadata scalability**

### 🧠 Core Features
- ACID-compliant table management  
- Schema evolution and snapshot rollback  
- Metadata pruning and partition optimization  
- ETL automation through AWS Glue  
- IaC deployment using **AWS CDK**  

---

## ⚙️ Technologies Used

| Category | Technologies |
|-----------|--------------|
| Cloud Services | AWS S3, Glue, Athena, IoT Core, CloudWatch, Managed Grafana |
| Data Frameworks | Apache Iceberg, Apache Hudi, Apache Spark |
| Programming | Python, PySpark, Boto3 |
| Infrastructure | AWS CDK (IaC), Virtual Machines (Edge Simulation) |
| Visualization | Grafana, CloudWatch Dashboards |

---

## 🧰 Industrial Simulator

A local **industrial monitoring simulator** was developed to generate realistic IoT metrics (CPU, memory, disk I/O, network I/O).  
Each virtual device (VM) publishes telemetry payloads to AWS IoT Core via **MQTT**, storing raw CSV data in S3 before transformation into **Parquet** format for Iceberg tables.

---

## 📊 Performance Experiments

Benchmarks included:
- Read and write latency under CoW vs MoR strategies  
- Query time before and after compaction  
- Schema evolution tests (column addition/removal)  
- Snapshot rollback and time-travel verification  

Results demonstrated that **Iceberg’s metadata layer** significantly improves query performance and storage efficiency, making it a robust foundation for **scalable, cost-effective cloud lakehouses**.

---

## 🗂️ License

This project is licensed under the **MIT License**.
