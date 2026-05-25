# Air Quality Index Data Pipeline using Databricks Asset Bundles

## Overview

This project demonstrates an end-to-end Air Quality Index (AQI) data engineering pipeline built using Databricks Lakeflow Declarative Pipelines (Delta Live Tables) and deployed using Databricks Asset Bundles.

The project automates ingestion, transformation, orchestration, and deployment of AQI datasets in a scalable and production-ready manner.

The solution follows Infrastructure-as-Code principles for managing Databricks jobs, pipelines, environments, and deployment configurations across development and production workspaces.

---

## Key Features

* Databricks Asset Bundle based deployment
* Lakeflow Declarative Pipeline (Delta Live Tables)
* Scheduled Databricks Job orchestration
* Environment-based deployment configuration
* Dev and Prod target separation
* Notebook-driven ETL pipeline
* Serverless pipeline execution
* Photon optimized execution
* Infrastructure-as-Code approach
* Git-integrated project structure

---

## Project Structure

```text
air_quality_index_bundle/
│
├── databricks.yml
│
├── resources/
│   ├── jobs/
│   │   └── job configuration YAML files
│   │
│   ├── pipelines/
│   │   └── DLT pipeline configuration YAML files
│   │
│   └── variables/
│       └── environment variable definitions
│
├── src/
│   └── notebooks/
│       ├── Data.ipynb
│       └── streaming_transformations.ipynb
│
├── tests/
│
├── fixtures/
│
└── dist/
```

---

## Technologies Used

* Databricks
* Databricks Asset Bundles
* Delta Live Tables (Lakeflow Declarative Pipelines)
* PySpark
* Unity Catalog
* Databricks Workflows
* YAML
* Git & GitHub

---

## Pipeline Architecture

### 1. Data Ingestion

The `Data.ipynb` notebook is responsible for ingesting AQI data into the Databricks environment.

### 2. Data Transformation

The `streaming_transformations.ipynb` notebook performs streaming transformations and builds the analytical pipeline using Lakeflow Declarative Pipelines.

### 3. Orchestration

Databricks Workflows are used for scheduling and orchestrating the AQI job execution.

### 4. Deployment

Databricks Asset Bundles manage deployment across multiple environments using reusable YAML configurations.

---

## Databricks Asset Bundle Configuration

The project contains:

* Development target
* Production target
* Workspace-specific root paths
* Environment variables
* Permissions management
* Deployment presets

Example deployment targets:

```yaml
targets:
  dev:
    mode: development

  prod:
    mode: production
```

---

## Deployment Commands

### Validate Bundle

```bash
databricks bundle validate
```

### Deploy to Development

```bash
databricks bundle deploy --target dev
```

### Deploy to Production

```bash
databricks bundle deploy --target prod
```

### Run Job

```bash
databricks bundle run AQI_DATA --target dev
```

---

## Environment Variables

The following variables are configured:

| Variable | Description            |
| -------- | ---------------------- |
| catalog  | Unity Catalog name     |
| schema   | Schema name            |
| env      | Deployment environment |

---

## Workflow Configuration

The AQI workflow is configured with:

* Scheduled execution using Quartz Cron
* Workspace notebook execution
* Parameterized environment support
* Queue-enabled execution
* Performance optimized execution mode

---

## Pipeline Configuration

The Delta Live Tables pipeline includes:

* Notebook-based library configuration
* Serverless execution
* Photon acceleration
* Preview channel support
* Environment-specific schema and catalog

---

## Learning Outcomes

This project demonstrates practical implementation of:

* Databricks Asset Bundles
* CI/CD style deployment in Databricks
* Delta Live Tables pipelines
* Environment-based infrastructure management
* Production-ready Databricks project structuring
* Job and pipeline orchestration

---

## Future Enhancements

* CI/CD integration using GitHub Actions or Azure DevOps
* Monitoring and alerting integration
* Data quality validation
* Real-time dashboard integration
* Advanced streaming optimizations
* Unit and integration testing automation

---

## Author

Sougata Pandit

GitHub Repository:
https://github.com/sougata99/AQI-Dashboard-With-AssetBundle
