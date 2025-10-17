# Data Context Hub: C64 Stack Integration

Welcome to the official repository of the [**Data Context Hub (DCH)**](https://www.datacontexthub.com/) C64 stack integration. This repository demonstrates our commitment to bridging legacy systems with modern data architectures, enabling seamless data integration, contextualization, and AI-driven insights.
[![Watch the video](https://files.datacontexthub.com/c64_engineer_graphic_transparent.png)](https://cdn.prod.website-files.com/67176348f740b09778716f1b%2F680763fe846020190e26629d_C64_Memory4YourAi_1920-transcode.mp4
)

## 🧠 Overview
[**Data Context Hub**](https://www.datacontexthub.com/) is a platform designed to integrate data from multiple sources into an explorable knowledge graph, enabling users to visualize and traverse complex relationships within their data.

## ✨ Key Features

- **ETL for Graphs**  
  Extract data from various sources (e.g., relational databases, flat files, JSON, SOAP, XML), transform it into a graph structure, and load it into a Neo4j graph database.

- **Graph Builder Services (GBS)**  
  The core component that processes data into a knowledge graph using Data Pumps and manages workflows via Apache Airflow.

- **Explorer**  
  A user-friendly interface for navigating and analyzing the knowledge graph.

- **Memory For Your AI (M4AI)**  
  Generates a knowledge graph to provide contextual information to AI models, enhancing their ability to deliver domain-specific insights.

- **Deployment**  
  Deployable on Kubernetes using Helm charts.

## 🔄 Integration with Data Context Hub

At [DCH](https://www.datacontexthub.com/), we leverage the [C64](https://www.c64.ai/) stack's principles to facilitate:

- **Seamless Data Integration**: Transforming disparate data sources into cohesive knowledge graphs.
- **Contextualization**: Enriching data with contextual information to enhance decision-making.
- **AI Integration**: Utilizing structured data to fine-tune AI models for specific applications.

Our platform provides tools like the [Graph Builder](https://www.datacontexthub.com/), [Data Explorer](https://www.datacontexthub.com/), and [Linked Data API](https://www.datacontexthub.com/) to empower organizations in transforming their data into actionable insights.

## 🧰 Prerequisites

Kubernetes Cluster running on either of the following platforms:

- Azure AKS (Azure Kubernetes Service)
- AWS EKS (Amazon Elastic Kubernetes Service)
- "Generic" on-premises or Google Kubernetes Engine (GKE)

## ⚙️ Setup Requirements

|         | Memory    | (v)CPUs |
|---------|-----------|---------|
| Azure   | 32 GiB    | 4       |
| AWS     | 32 GiB    | 4       |
| GCP     | 32 GiB    | 4       |
| On-Prem | 32 GiB    | 4       |

## 🚀 Getting Started

To explore the C64 stack integration:

1. Clone this repository:

   ```bash
   git clone https://github.com/context64ai/c64-stack-deployments.git

2. Navigate to the project directory and choose the apropriate folder (e.g. azure):

   ```bash
   cd context64ai/c64-stack-deployments/azure

AND

3. Follow the setup instructions in the README File in the apropriate folder (e.g. [azure](./azure/README.md))

## 🛠️ Support
Context64 provided scripts in this GitHub project. For direct issues, please refer to the Issues tab of this GitHub project.

For other questions related to this project, contact github@c64.ai

## 📄 License

This project is licensed under the GNU GENERAL PUBLIC LICENSE – see the [LICENSE](LICENSE) file for details.


## External Software 🎯

This project is based on the following powerful software:


![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat&logo=postgresql&logoColor=white)
![Neo4j](https://img.shields.io/badge/Neo4j-008CC1?style=flat&logo=neo4j&logoColor=white)
![RabbitMQ](https://img.shields.io/badge/RabbitMQ-FF6600?style=flat&logo=rabbitmq&logoColor=white)
![Apache Airflow](https://img.shields.io/badge/Apache%20Airflow-017CEE?style=flat&logo=apacheairflow&logoColor=white)
![Keycloak](https://img.shields.io/badge/Keycloak-000000?style=flat&logo=keycloak&logoColor=white)
![OpenSearch](https://img.shields.io/badge/OpenSearch-005EB8?style=flat&logo=opensearch&logoColor=white)
![OpenTelemetry](https://img.shields.io/badge/OpenTelemetry-000000?style=flat&logo=opentelemetry&logoColor=white)
![Weaviate](https://img.shields.io/badge/Weaviate-20C997?style=flat&logo=weaviate&logoColor=white)
![Celery](https://img.shields.io/badge/Celery-37814A?style=flat&logo=celery&logoColor=white)










## Status
Active development ✅
