---
id: intro_data_azure
title: Stacks Azure Data Platform
sidebar_label: Introduction
hide_title: false
hide_table_of_contents: false
description: Introduction to Stacks Azure Data Platform
keywords:
  - data
  - python
  - etl
  - databricks
  - azure
  - adf
  - template
---

The [Stacks Azure Data Platform](https://github.com/ensono/stacks-azure-data) solution provides
a framework for accelerating the deployment of a production-ready data platform.

![Stacks Data Overview](images/stacks-data-overview.png)

1. Use the [Stacks CLI](https://stacks.amido.com/docs/stackscli/about) to generate a new data platform project.
2. Build and deploy the data platform infrastructure into your Azure environment.
3. Accelerate development of data workloads and ETL pipelines with [Datastacks](etl_pipelines/datastacks.md).

The Stacks Data Platform utilises tools including **Azure Data Factory** for data
ingestion and orchestration, **Databricks** for data processing and **Azure Data Lake Storage Gen2**
for data lake storage. The solution is based around a [Medallion Architecture](etl_pipelines/etl_intro_data_azure.md#data-pipelines), with Bronze, Silver and Gold layers for various stages of data preparation.

Key elements of the solution include:

* Infrastructure as code (IaC) for all infrastructure components (Terraform).
* [Datastacks](etl_pipelines/datastacks.md) - a library and CLI built to accelerate the development of data engineering
workloads in the data platform based upon templates.
* [Pysparkle](etl_pipelines/pysparkle/pysparkle_quickstart.md) - a library built to streamline data processing activities running in Apache Spark.
* Sample ingest pipeline that transfers data from a source into a landing (Bronze) data lake zone.
* Sample data processing pipelines performing data transformations from Bronze to Silver and Silver to Gold layers.
* Data Quality validations.
* Deployment pipelines to enable CI/CD and DataOps for all components.
* Automated tests to ensure quality assurance and operational efficiency.

### High-level architecture

![High-level architecture](images/Stacks_Azure_Data_Platform-HLD.png)

### Infrastructure deployed

* Resource Group
* Key Vault
* Azure Data Lake Storage Gen2
* Azure Blob Storage
* Azure Data Factory
* Log Analytics Workspace
* Databricks Workspace (optional)
* Azure SQL Database (optional)

The solution may be deployed within a secure private network. For details please see [Infrastructure](infrastructure_data_azure.md).

### Data Engineering workloads

Example data engineering workloads are provided, based upon the Datastacks templates:

* [Ingest](etl_pipelines/ingest_data_azure.md)
* [Bronze to Silver](etl_pipelines/silver_data_azure.md)

Each of the ingest and data processing workloads may optionally include [Data Quality checks](etl_pipelines/data_quality_azure.md).
