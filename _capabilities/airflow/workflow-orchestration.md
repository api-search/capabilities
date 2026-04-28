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
- list airflow dag run history with optional state filtering.
- managing pipeline configuration and integrations.
- list dag runs.
- trigger and monitor dag runs.
- open source
- etl
- list connections
- apache airflow dag management.
- builds and triggers data pipelines using airflow dags.
- airflow connections.
- get details of an apache airflow dag by id.
- list dags
- list all variables.
- list all connections.
- pause an airflow dag to prevent scheduled runs.
- Platform Admin
- dag
- monitoring and operating running pipelines.
- manage airflow dags, trigger runs, monitor task execution, and manage variables and connections.
- defining, scheduling, and executing data workflows.
- apache
- Data Engineer
- trigger dag run
- monitor task instances.
- list dag runs
- data engineering
- airflow variables.
- data pipeline
- get a specific airflow variable by key.
- list airflow connections for external service integrations.
- list all apache airflow dags.
- get the current status of an airflow dag run.
- scheduling
- trigger an apache airflow dag run with optional configuration.
- pause dag
- list airflow variables for pipeline configuration.
- list variables
- get dag
- airflow
- get dag run status
- workflow orchestration
- get variable
- list task instances for a dag run.
- manages airflow connections, variables, pools, and infrastructure.
- list task instances and their status for a dag run.
- list all dags.
- trigger a new dag run.
- list task instances
slug: workflow-orchestration
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Apache Airflow Workflow Orchestration\"\n  description: \"Unified workflow capability for managing Apache Airflow pipelines — DAGs, DAG runs, task monitoring, variables, and connections. Used by data engineers and platform teams for orchestrating data pipelines.\"\n  tags:\n    - Airflow\n    - Workflow Orchestration\n    - Data Pipeline\n    - ETL\n    - Data Engineering\n    - Apache\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      AIRFLOW_BASE_URL: AIRFLOW_BASE_URL\n      AIRFLOW_USERNAME: AIRFLOW_USERNAME\n      AIRFLOW_PASSWORD: AIRFLOW_PASSWORD\n\ncapability:\n  consumes:\n    - import: airflow\n      location: ./shared/airflow-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: airflow-orchestration-api\n      description: \"Unified REST API for Airflow workflow orchestration.\"\n      resources:\n        - path: /v1/dags\n          name: dags\n\
  \          description: \"Apache Airflow DAG management.\"\n          operations:\n            - method: GET\n              name: list-dags\n              description: \"List all DAGs.\"\n              call: \"airflow.list-dags\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/dag-runs\n          name: dag-runs\n          description: \"Trigger and monitor DAG runs.\"\n          operations:\n            - method: GET\n              name: list-dag-runs\n              description: \"List DAG runs.\"\n              call: \"airflow.list-dag-runs\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: trigger-dag-run\n              description: \"Trigger a new DAG run.\"\n              call: \"airflow.trigger-dag-run\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n      \
  \  - path: /v1/task-instances\n          name: task-instances\n          description: \"Monitor task instances.\"\n          operations:\n            - method: GET\n              name: list-task-instances\n              description: \"List task instances for a DAG run.\"\n              call: \"airflow.list-task-instances\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/variables\n          name: variables\n          description: \"Airflow Variables.\"\n          operations:\n            - method: GET\n              name: list-variables\n              description: \"List all variables.\"\n              call: \"airflow.list-variables\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/connections\n          name: connections\n          description: \"Airflow Connections.\"\n          operations:\n            - method: GET\n              name: list-connections\n\
  \              description: \"List all connections.\"\n              call: \"airflow.list-connections\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: airflow-orchestration-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Airflow workflow management.\"\n      tools:\n        - name: list-dags\n          description: \"List all Apache Airflow DAGs.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"airflow.list-dags\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-dag\n          description: \"Get details of an Apache Airflow DAG by ID.\"\n          hints:\n            readOnly: true\n          call: \"airflow.get-dag\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: trigger-dag-run\n        \
  \  description: \"Trigger an Apache Airflow DAG run with optional configuration.\"\n          hints:\n            readOnly: false\n          call: \"airflow.trigger-dag-run\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-dag-runs\n          description: \"List Airflow DAG run history with optional state filtering.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"airflow.list-dag-runs\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-dag-run-status\n          description: \"Get the current status of an Airflow DAG run.\"\n          hints:\n            readOnly: true\n          call: \"airflow.get-dag-run\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-task-instances\n          description: \"List task instances and their status for a DAG run.\"\n        \
  \  hints:\n            readOnly: true\n          call: \"airflow.list-task-instances\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: pause-dag\n          description: \"Pause an Airflow DAG to prevent scheduled runs.\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"airflow.patch-dag\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-variables\n          description: \"List Airflow Variables for pipeline configuration.\"\n          hints:\n            readOnly: true\n          call: \"airflow.list-variables\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-variable\n          description: \"Get a specific Airflow Variable by key.\"\n          hints:\n            readOnly: true\n          call: \"airflow.get-variable\"\n          outputParameters:\n            -\
  \ type: object\n              mapping: \"$.\"\n        - name: list-connections\n          description: \"List Airflow Connections for external service integrations.\"\n          hints:\n            readOnly: true\n          call: \"airflow.list-connections\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
