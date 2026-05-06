---
categories:
- data-engineering
consumed_apis: []
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
- get dag run status
- get the status of an airflow dag run.
- scheduling
- workflow
- list airflow variables.
- list dags
- data pipeline
- Data Engineer
- list pools
- etl
- list all airflow dags.
- list airflow resource pools.
- apache
- list variables
- trigger an airflow dag run.
- workflow orchestration
- open source
- orchestration
- list task instances
- Platform Operator
- operators who monitor and maintain airflow platform health.
- dag
- list airflow connections for integrations.
- task scheduling
- python
- dag and task management capability.
- dag management
- list task instances for monitoring dag run progress.
- list connections
- apache airflow
- trigger a dag run.
- list all dags.
- engineers who build and manage data pipelines using airflow dags.
- trigger dag run
slug: airflow-orchestration
source_filename: airflow-orchestration.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Apache Airflow Workflow Orchestration\n  description: Unified capability for managing and monitoring Apache Airflow DAGs, runs, tasks, connections, and variables.\n    Used by data engineers and platform operators to orchestrate data pipelines.\n  tags:\n  - Apache Airflow\n  - Workflow Orchestration\n  - DAG Management\n  - Data Pipeline\n  - ETL\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    AIRFLOW_USERNAME: AIRFLOW_USERNAME\n    AIRFLOW_PASSWORD: AIRFLOW_PASSWORD\ncapability:\n  consumes:\n  - type: http\n    namespace: airflow-rest\n    baseUri: http://localhost:8080/api/v1\n    description: Apache Airflow stable REST API.\n    authentication:\n      type: basic\n      username: '{{AIRFLOW_USERNAME}}'\n      password: '{{AIRFLOW_PASSWORD}}'\n    resources:\n    - name: dags\n      path: /dags\n      description: Manage DAG definitions.\n      operations:\n      - name: list-dags\n      \
  \  method: GET\n        description: List all DAGs.\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n        - name: offset\n          in: query\n          type: integer\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-dag\n        method: GET\n        description: Get a specific DAG.\n        inputParameters:\n        - name: dag_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: patch-dag\n        method: PATCH\n        description: Update a DAG (pause/unpause).\n        inputParameters:\n        - name: dag_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: dag-runs\n      path: /dags/{dag_id}/dagRuns\n      description: Manage DAG runs.\n      operations:\n      - name: list-dag-runs\n        method: GET\n        description: List DAG runs for a DAG.\n        inputParameters:\n        - name: dag_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: trigger-dag-run\n        method: POST\n        description: Trigger a new DAG run.\n        inputParameters:\n        - name: dag_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-dag-run\n        method: GET\n        description: Get a specific DAG run.\n        inputParameters:\n      \
  \  - name: dag_id\n          in: path\n          type: string\n          required: true\n        - name: dag_run_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: task-instances\n      path: /dags/{dag_id}/dagRuns/{dag_run_id}/taskInstances\n      description: Monitor task instances.\n      operations:\n      - name: list-task-instances\n        method: GET\n        description: List task instances for a DAG run.\n        inputParameters:\n        - name: dag_id\n          in: path\n          type: string\n          required: true\n        - name: dag_run_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: connections\n      path: /connections\n      description: Manage\
  \ Airflow connections.\n      operations:\n      - name: list-connections\n        method: GET\n        description: List all connections.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-connection\n        method: POST\n        description: Create a new connection.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: variables\n      path: /variables\n      description: Manage Airflow variables.\n      operations:\n      - name: list-variables\n        method: GET\n        description: List all variables.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-variable\n        method: POST\n        description: Create a new\
  \ variable.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: pools\n      path: /pools\n      description: Manage Airflow resource pools.\n      operations:\n      - name: list-pools\n        method: GET\n        description: List all pools.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: airflow-orchestration-api\n    description: Unified REST API for Airflow workflow orchestration.\n    resources:\n    - path: /v1/dags\n      name: dags\n      operations:\n      - method: GET\n        name: list-dags\n        description: List all DAGs.\n        call: airflow-rest.list-dags\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/dag-runs\n      name: dag-runs\n     \
  \ operations:\n      - method: POST\n        name: trigger-dag-run\n        description: Trigger a DAG run.\n        call: airflow-rest.trigger-dag-run\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: airflow-orchestration-mcp\n    transport: http\n    description: MCP server for AI-assisted Airflow workflow management.\n    tools:\n    - name: list-dags\n      description: List all Airflow DAGs.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: airflow-rest.list-dags\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: trigger-dag-run\n      description: Trigger an Airflow DAG run.\n      hints:\n        readOnly: false\n        openWorld: false\n      call: airflow-rest.trigger-dag-run\n      with:\n        dag_id: tools.dag_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-dag-run-status\n      description: Get the status\
  \ of an Airflow DAG run.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: airflow-rest.get-dag-run\n      with:\n        dag_id: tools.dag_id\n        dag_run_id: tools.dag_run_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-task-instances\n      description: List task instances for monitoring DAG run progress.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: airflow-rest.list-task-instances\n      with:\n        dag_id: tools.dag_id\n        dag_run_id: tools.dag_run_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-connections\n      description: List Airflow connections for integrations.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: airflow-rest.list-connections\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-variables\n      description: List Airflow variables.\n      hints:\n      \
  \  readOnly: true\n        openWorld: true\n      call: airflow-rest.list-variables\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-pools\n      description: List Airflow resource pools.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: airflow-rest.list-pools\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
