---
categories:
- data-engineering
consumed_apis: []
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
- pause an airflow dag to prevent scheduled runs.
- builds and triggers data pipelines using airflow dags.
- Platform Admin
- get dag run status
- list airflow dag run history with optional state filtering.
- trigger and monitor dag runs.
- scheduling
- managing pipeline configuration and integrations.
- airflow
- list task instances for a dag run.
- list dag runs
- list dags
- data pipeline
- airflow connections.
- list all connections.
- manage airflow dags, trigger runs, monitor task execution, and manage variables and connections.
- data engineering
- etl
- apache
- list dag runs.
- get details of an apache airflow dag by id.
- trigger an apache airflow dag run with optional configuration.
- list airflow variables for pipeline configuration.
- get a specific airflow variable by key.
- list variables
- workflow orchestration
- open source
- get the current status of an airflow dag run.
- monitor task instances.
- list all apache airflow dags.
- pause dag
- list task instances
- dag
- defining, scheduling, and executing data workflows.
- list all variables.
- airflow variables.
- Data Engineer
- monitoring and operating running pipelines.
- get variable
- list connections
- apache airflow dag management.
- get dag
- trigger a new dag run.
- list all dags.
- list task instances and their status for a dag run.
- list airflow connections for external service integrations.
- manages airflow connections, variables, pools, and infrastructure.
- trigger dag run
slug: workflow-orchestration
source_filename: workflow-orchestration.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Apache Airflow Workflow Orchestration\n  description: Unified workflow capability for managing Apache Airflow pipelines — DAGs, DAG runs, task monitoring, variables,\n    and connections. Used by data engineers and platform teams for orchestrating data pipelines.\n  tags:\n  - Airflow\n  - Workflow Orchestration\n  - Data Pipeline\n  - ETL\n  - Data Engineering\n  - Apache\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    AIRFLOW_BASE_URL: AIRFLOW_BASE_URL\n    AIRFLOW_USERNAME: AIRFLOW_USERNAME\n    AIRFLOW_PASSWORD: AIRFLOW_PASSWORD\ncapability:\n  consumes:\n  - type: http\n    namespace: airflow\n    baseUri: '{{AIRFLOW_BASE_URL}}/api/v2'\n    description: Apache Airflow REST API v2.\n    authentication:\n      type: basic\n      username: '{{AIRFLOW_USERNAME}}'\n      password: '{{AIRFLOW_PASSWORD}}'\n    resources:\n    - name: dags\n      path: /dags\n      description: Manage Directed Acyclic\
  \ Graphs (DAGs).\n      operations:\n      - name: list-dags\n        method: GET\n        description: List all DAGs.\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Number of DAGs to return.\n        - name: only_active\n          in: query\n          type: boolean\n          required: false\n          description: Filter to active DAGs only.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-dag\n        method: GET\n        description: Get a DAG by ID.\n        inputParameters:\n        - name: dag_id\n          in: path\n          type: string\n          required: true\n          description: DAG identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: patch-dag\n        method: PATCH\n        description:\
  \ Update a DAG (e.g., pause/unpause).\n        inputParameters:\n        - name: dag_id\n          in: path\n          type: string\n          required: true\n          description: DAG identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            is_paused: '{{tools.is_paused}}'\n    - name: dag-runs\n      path: /dags/{dag_id}/dagRuns\n      description: Manage DAG run executions.\n      operations:\n      - name: list-dag-runs\n        method: GET\n        description: List DAG runs for a specific DAG.\n        inputParameters:\n        - name: dag_id\n          in: path\n          type: string\n          required: true\n          description: DAG identifier.\n        - name: state\n          in: query\n          type: string\n          required: false\n          description: Filter by state (running, success, failed).\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: trigger-dag-run\n        method: POST\n        description: Trigger a new DAG run.\n        inputParameters:\n        - name: dag_id\n          in: path\n          type: string\n          required: true\n          description: DAG identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            logical_date: '{{tools.logical_date}}'\n            conf: '{{tools.conf}}'\n      - name: get-dag-run\n        method: GET\n        description: Get a specific DAG run.\n        inputParameters:\n        - name: dag_id\n          in: path\n          type: string\n          required: true\n          description: DAG identifier.\n        - name: dag_run_id\n          in: path\n          type: string\n          required: true\n          description:\
  \ DAG run identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: task-instances\n      path: /dags/{dag_id}/dagRuns/{dag_run_id}/taskInstances\n      description: Monitor and manage task instances within DAG runs.\n      operations:\n      - name: list-task-instances\n        method: GET\n        description: List task instances for a DAG run.\n        inputParameters:\n        - name: dag_id\n          in: path\n          type: string\n          required: true\n          description: DAG identifier.\n        - name: dag_run_id\n          in: path\n          type: string\n          required: true\n          description: DAG run identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: variables\n      path: /variables\n      description: Manage Airflow Variables.\n      operations:\n      - name: list-variables\n\
  \        method: GET\n        description: List all variables.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-variable\n        method: GET\n        description: Get a variable by key.\n        inputParameters:\n        - name: variable_key\n          in: path\n          type: string\n          required: true\n          description: Variable key.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: connections\n      path: /connections\n      description: Manage Airflow Connections.\n      operations:\n      - name: list-connections\n        method: GET\n        description: List all connections.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: airflow-orchestration-api\n\
  \    description: Unified REST API for Airflow workflow orchestration.\n    resources:\n    - path: /v1/dags\n      name: dags\n      description: Apache Airflow DAG management.\n      operations:\n      - method: GET\n        name: list-dags\n        description: List all DAGs.\n        call: airflow.list-dags\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/dag-runs\n      name: dag-runs\n      description: Trigger and monitor DAG runs.\n      operations:\n      - method: GET\n        name: list-dag-runs\n        description: List DAG runs.\n        call: airflow.list-dag-runs\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: trigger-dag-run\n        description: Trigger a new DAG run.\n        call: airflow.trigger-dag-run\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/task-instances\n      name: task-instances\n      description: Monitor\
  \ task instances.\n      operations:\n      - method: GET\n        name: list-task-instances\n        description: List task instances for a DAG run.\n        call: airflow.list-task-instances\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/variables\n      name: variables\n      description: Airflow Variables.\n      operations:\n      - method: GET\n        name: list-variables\n        description: List all variables.\n        call: airflow.list-variables\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/connections\n      name: connections\n      description: Airflow Connections.\n      operations:\n      - method: GET\n        name: list-connections\n        description: List all connections.\n        call: airflow.list-connections\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: airflow-orchestration-mcp\n    transport: http\n\
  \    description: MCP server for AI-assisted Airflow workflow management.\n    tools:\n    - name: list-dags\n      description: List all Apache Airflow DAGs.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: airflow.list-dags\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-dag\n      description: Get details of an Apache Airflow DAG by ID.\n      hints:\n        readOnly: true\n      call: airflow.get-dag\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: trigger-dag-run\n      description: Trigger an Apache Airflow DAG run with optional configuration.\n      hints:\n        readOnly: false\n      call: airflow.trigger-dag-run\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-dag-runs\n      description: List Airflow DAG run history with optional state filtering.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: airflow.list-dag-runs\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-dag-run-status\n      description: Get the current status of an Airflow DAG run.\n      hints:\n        readOnly: true\n      call: airflow.get-dag-run\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-task-instances\n      description: List task instances and their status for a DAG run.\n      hints:\n        readOnly: true\n      call: airflow.list-task-instances\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: pause-dag\n      description: Pause an Airflow DAG to prevent scheduled runs.\n      hints:\n        readOnly: false\n        idempotent: true\n      call: airflow.patch-dag\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-variables\n      description: List Airflow Variables for pipeline configuration.\n      hints:\n        readOnly: true\n      call: airflow.list-variables\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: get-variable\n      description: Get a specific Airflow Variable by key.\n      hints:\n        readOnly: true\n      call: airflow.get-variable\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-connections\n      description: List Airflow Connections for external service integrations.\n      hints:\n        readOnly: true\n      call: airflow.list-connections\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/airflow/refs/heads/main/capabilities/workflow-orchestration.yaml
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
