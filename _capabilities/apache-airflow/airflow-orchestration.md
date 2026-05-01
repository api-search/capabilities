---
categories:
- data-engineering
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
- dag and task management capability.
- list variables
- apache airflow
- Data Engineer
- list task instances for monitoring dag run progress.
- list airflow variables.
- list dags
- workflow
- list airflow connections for integrations.
- list airflow resource pools.
- list connections
- trigger an airflow dag run.
- trigger dag run
- list task instances
- get the status of an airflow dag run.
- operators who monitor and maintain airflow platform health.
- scheduling
- dag management
- trigger a dag run.
- engineers who build and manage data pipelines using airflow dags.
- list all airflow dags.
- orchestration
- workflow orchestration
- open source
- apache
- Platform Operator
- data pipeline
- dag
- etl
- task scheduling
- get dag run status
- list pools
- list all dags.
- python
slug: airflow-orchestration
source_filename: airflow-orchestration.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha1\ninfo:\n  label: Apache Airflow Workflow Orchestration\n  description: Unified capability for managing and monitoring Apache Airflow \n    DAGs, runs, tasks, connections, and variables. Used by data engineers and \n    platform operators to orchestrate data pipelines.\n  tags:\n  - Apache Airflow\n  - Workflow Orchestration\n  - DAG Management\n  - Data Pipeline\n  - ETL\n  created: '2026-04-19'\n  modified: '2026-04-19'\nbinds:\n- namespace: env\n  keys:\n    AIRFLOW_USERNAME: AIRFLOW_USERNAME\n    AIRFLOW_PASSWORD: AIRFLOW_PASSWORD\ncapability:\n  consumes:\n  - import: airflow-rest\n    location: ./shared/airflow-rest.yaml\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: airflow-orchestration-api\n    description: Unified REST API for Airflow workflow orchestration.\n    resources:\n    - path: /v1/dags\n      name: dags\n      operations:\n      - method: GET\n        name: list-dags\n        description: List all DAGs.\n        call: airflow-rest.list-dags\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/dag-runs\n      name: dag-runs\n      operations:\n      - method: POST\n        name: trigger-dag-run\n        description: Trigger a DAG run.\n        call: airflow-rest.trigger-dag-run\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: airflow-orchestration-mcp\n    transport: http\n    description: MCP server for AI-assisted Airflow workflow management.\n    tools:\n    - name: list-dags\n      description: List all Airflow DAGs.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: airflow-rest.list-dags\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: trigger-dag-run\n      description: Trigger an Airflow DAG run.\n      hints:\n        readOnly: false\n        openWorld: false\n      call: airflow-rest.trigger-dag-run\n      with:\n        dag_id: tools.dag_id\n     \
  \ outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-dag-run-status\n      description: Get the status of an Airflow DAG run.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: airflow-rest.get-dag-run\n      with:\n        dag_id: tools.dag_id\n        dag_run_id: tools.dag_run_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-task-instances\n      description: List task instances for monitoring DAG run progress.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: airflow-rest.list-task-instances\n      with:\n        dag_id: tools.dag_id\n        dag_run_id: tools.dag_run_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-connections\n      description: List Airflow connections for integrations.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: airflow-rest.list-connections\n      outputParameters:\n      -\
  \ type: object\n        mapping: $.\n    - name: list-variables\n      description: List Airflow variables.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: airflow-rest.list-variables\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-pools\n      description: List Airflow resource pools.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: airflow-rest.list-pools\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/apache-airflow/refs/heads/main/capabilities/airflow-orchestration.yaml
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
