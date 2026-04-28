---
categories:
- data-engineering
consumed_apis:
- airflow
description: Unified workflow capability for managing Apache Airflow pipelines — DAGs, DAG runs, task monitoring, variables, and connections. Used by data engineers and platform teams for orchestrating data pipelines.
layout: capability
name: Apache Airflow Workflow Orchestration
operations:
- description: List all DAGs.
  method: GET
  name: list-dags
  path: /v1/dags
- description: List DAG runs.
  method: GET
  name: list-dag-runs
  path: /v1/dag-runs
- description: Trigger a new DAG run.
  method: POST
  name: trigger-dag-run
  path: /v1/dag-runs
- description: List task instances for a DAG run.
  method: GET
  name: list-task-instances
  path: /v1/task-instances
- description: List all variables.
  method: GET
  name: list-variables
  path: /v1/variables
- description: List all connections.
  method: GET
  name: list-connections
  path: /v1/connections
personas: []
provider_name: Apache Airflow
provider_slug: airflow
search_terms:
- monitoring and operating running pipelines.
- list all apache airflow dags.
- get details of an apache airflow dag by id.
- list connections
- data engineering
- airflow variables.
- pause dag
- list all connections.
- Platform Admin
- data pipeline
- list dags
- list task instances and their status for a dag run.
- airflow
- scheduling
- get dag run status
- manage airflow dags, trigger runs, monitor task execution, and manage variables and connections.
- defining, scheduling, and executing data workflows.
- pause an airflow dag to prevent scheduled runs.
- managing pipeline configuration and integrations.
- apache airflow dag management.
- list airflow variables for pipeline configuration.
- apache
- trigger and monitor dag runs.
- builds and triggers data pipelines using airflow dags.
- get dag
- open source
- list variables
- list dag runs.
- trigger dag run
- manages airflow connections, variables, pools, and infrastructure.
- Data Engineer
- workflow orchestration
- list task instances for a dag run.
- get the current status of an airflow dag run.
- etl
- list airflow dag run history with optional state filtering.
- get variable
- dag
- get a specific airflow variable by key.
- airflow connections.
- trigger a new dag run.
- list all variables.
- list airflow connections for external service integrations.
- list all dags.
- monitor task instances.
- list task instances
- list dag runs
- trigger an apache airflow dag run with optional configuration.
slug: workflow-orchestration
tags:
- Airflow
- Workflow Orchestration
- Data Pipeline
- ETL
- Data Engineering
- Apache
tools:
- description: List all Apache Airflow DAGs.
  hints:
    openWorld: true
    readOnly: true
  name: list-dags
- description: Get details of an Apache Airflow DAG by ID.
  hints:
    readOnly: true
  name: get-dag
- description: Trigger an Apache Airflow DAG run with optional configuration.
  hints:
    readOnly: false
  name: trigger-dag-run
- description: List Airflow DAG run history with optional state filtering.
  hints:
    openWorld: true
    readOnly: true
  name: list-dag-runs
- description: Get the current status of an Airflow DAG run.
  hints:
    readOnly: true
  name: get-dag-run-status
- description: List task instances and their status for a DAG run.
  hints:
    readOnly: true
  name: list-task-instances
- description: Pause an Airflow DAG to prevent scheduled runs.
  hints:
    idempotent: true
    readOnly: false
  name: pause-dag
- description: List Airflow Variables for pipeline configuration.
  hints:
    readOnly: true
  name: list-variables
- description: Get a specific Airflow Variable by key.
  hints:
    readOnly: true
  name: get-variable
- description: List Airflow Connections for external service integrations.
  hints:
    readOnly: true
  name: list-connections
---
