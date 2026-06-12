<div align="center">

# Data Context Hub: C64 Stack Integration

**Data Context Hub builds your engineering context layer.**

[**Website**](https://www.c64.ai/platform/data-context-hub/) · [**Documentation**](https://docs.datacontexthub.com/) · [**Release Notes**](https://docs.datacontexthub.com/release-notes) · [**Contact**](https://www.c64.ai/company/contact/)

[![Kubernetes](https://img.shields.io/badge/Kubernetes-326CE5?style=flat&logo=kubernetes&logoColor=white)](https://kubernetes.io/)
[![Helm](https://img.shields.io/badge/Helm-0F1689?style=flat&logo=helm&logoColor=white)](https://helm.sh/)
[![License: GPL](https://img.shields.io/badge/License-GPL-blue?style=flat)](LICENSE)

<br>
<a href="https://www.c64.ai/platform/data-context-hub/">
  <img src="/assets/dch-hero.svg" alt="Data Context Hub — engineering sources flow into a governed context graph and return precise query results in 128 ms" width="100%">
</a>
</div>


## 🧠 Overview

[**Data Context Hub (DCH)**](https://www.c64.ai/platform/data-context-hub/) turns fragmented engineering data — PLM, ALM, ERP, CAD, requirements, FMEA, documents — into one governed knowledge graph that every team and AI agent can query. Sources are connected through Intake Agents, mapped to your ontology without code, built into a versioned graph with full provenance and lineage, governed by fine-grained access policies, and retrieved on demand via the Linked Data API, GraphQL, and MCP.

This repository provides everything needed to deploy the [C64](https://www.c64.ai/) stack on Kubernetes.

## ✨ Key Features

- **Graph Builder Services (GBS)** — imports data via Intake Agents into a Neo4j knowledge graph and orchestrates workflows with Apache Airflow.
- **Ontology Builder** — model entities, relationships, and business rules visually; no code, versioned, auditable.
- **Graph Explorer** — navigate and analyze the living knowledge graph.
- **Linked Data API** — query the graph and build custom frontends, governed by the Graph Security Layer.
- **Memory 4 Your AI (M4AI)** — specialized engineering agents that retrieve precise, scoped context from the graph.

## 🧰 Prerequisites

A Kubernetes cluster on **Azure AKS**, **AWS EKS**, **Google GKE**, or generic **on-premises** infrastructure. Deployment is done via [Helm](https://helm.sh/) — see the [installation guide](https://docs.datacontexthub.com/deployment-and-maintenance/installation) for images, chart repository, and `values.yaml` configuration.

## ⚙️ Setup Requirements

|         | RAM    | CPU     |
|---------|--------|---------|
| Azure   | 64 GiB | 8 Cores |
| AWS     | 64 GiB | 8 Cores |
| GCP     | 64 GiB | 8 Cores |
| On-Prem | 64 GiB | 8 Cores |

## 🚀 Getting Started

1. Clone this repository:

   ```bash
   git clone https://github.com/context64ai/c64-stack-deployments.git
   ```

2. Navigate to the folder for your target platform and follow the setup instructions in its README (e.g. [azure](./azure/README.md)):

   ```bash
   cd c64-stack-deployments/azure
   ```

## 🛠️ Support

This repository is provided and maintained by [Context64](https://www.c64.ai/). For issues directly related to this repository, please use the Issues tab of this GitHub project — for all other questions, contact [github@c64.ai](mailto:github@c64.ai?subject=C64%20Stack%20Deployments)

## 📄 License

This project is licensed under the GNU GENERAL PUBLIC LICENSE — see the [LICENSE](LICENSE) file for details.

## 🎯 External Software

This project is based on the following powerful software:

[![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat&logo=postgresql&logoColor=white)](https://www.postgresql.org/)
[![Neo4j](https://img.shields.io/badge/Neo4j-008CC1?style=flat&logo=neo4j&logoColor=white)](https://www.neo4j.com/)
[![RabbitMQ](https://img.shields.io/badge/RabbitMQ-FF6600?style=flat&logo=rabbitmq&logoColor=white)](https://www.rabbitmq.com/)
[![Apache Airflow](https://img.shields.io/badge/Apache%20Airflow-017CEE?style=flat&logo=apacheairflow&logoColor=white)](https://airflow.apache.org/)
[![Keycloak](https://img.shields.io/badge/Keycloak-000000?style=flat&logo=keycloak&logoColor=white)](https://www.keycloak.org/)
[![OpenSearch](https://img.shields.io/badge/OpenSearch-005EB8?style=flat&logo=opensearch&logoColor=white)](https://opensearch.org/)
[![OpenTelemetry](https://img.shields.io/badge/OpenTelemetry-000000?style=flat&logo=opentelemetry&logoColor=white)](https://opentelemetry.io/)
[![Weaviate](https://img.shields.io/badge/Weaviate-20C997?style=flat&logo=weaviate&logoColor=white)](https://weaviate.io/)
[![Celery](https://img.shields.io/badge/Celery-37814A?style=flat&logo=celery&logoColor=white)](https://docs.celeryq.dev/en/latest/index.html#)