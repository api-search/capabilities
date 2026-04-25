---
consumed_apis:
- airflow-rest
description: Unified capability for managing and monitoring Apache Airflow DAGs, runs, tasks, connections, and variables. Used by data engineers and platform operators to orchestrate data pipelines.
layout: capability
name: Apache Airflow Workflow Orchestration
operations:
- description: List all DAGs.
  method: GET
  name: list-dags
  path: /v1/dags
- description: Trigger a DAG run.
  method: POST
  name: trigger-dag-run
  path: /v1/dag-runs
personas: []
provider_name: Apache Airflow
provider_slug: apache-airflow
search_terms:
- dag management
- engineers who build and manage data pipelines using airflow dags.
- workflow orchestration
- list airflow variables.
- list pools
- Platform Operator
- task scheduling
- list all dags.
- get dag run status
- list task instances for monitoring dag run progress.
- data pipeline
- open source
- python
- scheduling
- list dags
- trigger an airflow dag run.
- apache airflow
- apache
- dag
- operators who monitor and maintain airflow platform health.
- Data Engineer
- list all airflow dags.
- trigger dag run
- workflow
- list task instances
- orchestration
- list airflow resource pools.
- etl
- dag and task management capability.
- list variables
- trigger a dag run.
- list airflow connections for integrations.
- list connections
- get the status of an airflow dag run.
slug: airflow-orchestration
tags:
- Apache Airflow
- Workflow Orchestration
- DAG Management
- Data Pipeline
- ETL
tools:
- description: List all Airflow DAGs.
  hints:
    openWorld: true
    readOnly: true
  name: list-dags
- description: Trigger an Airflow DAG run.
  hints:
    openWorld: false
    readOnly: false
  name: trigger-dag-run
- description: Get the status of an Airflow DAG run.
  hints:
    openWorld: true
    readOnly: true
  name: get-dag-run-status
- description: List task instances for monitoring DAG run progress.
  hints:
    openWorld: true
    readOnly: true
  name: list-task-instances
- description: List Airflow connections for integrations.
  hints:
    openWorld: true
    readOnly: true
  name: list-connections
- description: List Airflow variables.
  hints:
    openWorld: true
    readOnly: true
  name: list-variables
- description: List Airflow resource pools.
  hints:
    openWorld: true
    readOnly: true
  name: list-pools
---
