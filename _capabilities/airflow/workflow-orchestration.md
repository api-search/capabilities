---
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
- scheduling
- airflow connections.
- dag
- managing pipeline configuration and integrations.
- workflow orchestration
- list dag runs.
- get a specific airflow variable by key.
- get the current status of an airflow dag run.
- list airflow connections for external service integrations.
- apache airflow dag management.
- trigger dag run
- list all connections.
- get dag run status
- get variable
- manage airflow dags, trigger runs, monitor task execution, and manage variables and connections.
- pause an airflow dag to prevent scheduled runs.
- Platform Admin
- manages airflow connections, variables, pools, and infrastructure.
- airflow variables.
- get dag
- etl
- apache
- list task instances for a dag run.
- list all variables.
- airflow
- get details of an apache airflow dag by id.
- list airflow variables for pipeline configuration.
- trigger an apache airflow dag run with optional configuration.
- open source
- builds and triggers data pipelines using airflow dags.
- list dags
- data engineering
- trigger and monitor dag runs.
- Data Engineer
- defining, scheduling, and executing data workflows.
- pause dag
- list task instances and their status for a dag run.
- list dag runs
- list airflow dag run history with optional state filtering.
- trigger a new dag run.
- list all dags.
- list task instances
- monitor task instances.
- list variables
- list connections
- data pipeline
- list all apache airflow dags.
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
