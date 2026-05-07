---
categories: []
consumed_apis: []
description: A Capability Composition over the Airflow + Prefect + Dagster pipeline trio that exposes shared steps as reusable capabilities — the API-reusability ask, made concrete on actual data stack.
layout: capability
name: Airflow Prefect Dagster Pipeline Reusability Capability
operations:
- description: Trigger a shared pipeline step on whichever orchestrator owns it.
  method: POST
  name: trigger-shared-pipeline
  path: /pipelines/{{pipeline_id}}/trigger
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- governance
- trigger shared pipeline
- spec-driven integration
- list airflow dags.
- list prefect deployments
- trigger a shared pipeline step.
- api integration
- airflow
- dagster
- prefect
- list prefect deployments.
- ai
- reusability
- capabilities
- list airflow dags
- mcp
- trigger a shared pipeline step on whichever orchestrator owns it.
- naftiko
slug: airflow-prefect-dagster-pipeline-reusability-capability
source_filename: airflow-prefect-dagster-pipeline-reusability-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Airflow Prefect Dagster Pipeline Reusability Capability\n  description: A Capability Composition over the Airflow + Prefect + Dagster pipeline trio that exposes shared steps as reusable capabilities — the API-reusability ask, made concrete on actual data stack.\n  tags: [Naftiko, Airflow, Prefect, Dagster, Reusability]\n  created: '2026-05-01'\n  modified: '2026-05-04'\nbinds:\n- namespace: airflow-env\n  keys: {AIRFLOW_HOST: AIRFLOW_HOST, AIRFLOW_TOKEN: AIRFLOW_TOKEN}\n- namespace: prefect-env\n  keys: {PREFECT_HOST: PREFECT_HOST, PREFECT_TOKEN: PREFECT_TOKEN}\n- namespace: dagster-env\n  keys: {DAGSTER_HOST: DAGSTER_HOST, DAGSTER_TOKEN: DAGSTER_TOKEN}\ncapability:\n  consumes:\n  - namespace: airflow\n    type: http\n    baseUri: https://{{AIRFLOW_HOST}}\n    authentication: {type: bearer, token: '{{AIRFLOW_TOKEN}}'}\n    resources:\n    - name: dags\n      path: /api/v1/dags\n      operations: [{name: list-dags, method: GET}]\n    -\
  \ name: dag-run\n      path: /api/v1/dags/{{dag_id}}/dagRuns\n      operations:\n      - {name: trigger-dag, method: POST, inputParameters: [{name: dag_id, in: path}]}\n  - namespace: prefect\n    type: http\n    baseUri: https://{{PREFECT_HOST}}\n    authentication: {type: bearer, token: '{{PREFECT_TOKEN}}'}\n    resources:\n    - name: deployments\n      path: /api/deployments/filter\n      operations: [{name: list-deployments, method: POST}]\n    - name: deployment-run\n      path: /api/deployments/{{deployment_id}}/create_flow_run\n      operations:\n      - {name: trigger-deployment, method: POST, inputParameters: [{name: deployment_id, in: path}]}\n  - namespace: dagster\n    type: http\n    baseUri: https://{{DAGSTER_HOST}}\n    authentication: {type: bearer, token: '{{DAGSTER_TOKEN}}'}\n    resources:\n    - name: graphql\n      path: /graphql\n      operations: [{name: graphql-query, method: POST, description: Dagster GraphQL endpoint for jobs and runs.}]\n  exposes:\n  - type:\
  \ rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: airflow-prefect-dagster-pipeline-reusability-capability-rest\n    description: REST surface exposing shared pipeline steps reusable across Airflow/Prefect/Dagster.\n    resources:\n    - name: trigger\n      path: /pipelines/{{pipeline_id}}/trigger\n      operations:\n      - method: POST\n        name: trigger-shared-pipeline\n        description: Trigger a shared pipeline step on whichever orchestrator owns it.\n        inputParameters: [{name: pipeline_id, in: path, type: string}]\n        call: airflow.trigger-dag\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: airflow-prefect-dagster-pipeline-reusability-capability-mcp\n    description: MCP server for cross-orchestrator pipeline triggering.\n    tools:\n    - {name: list-airflow-dags, description: List Airflow DAGs., hints: {readOnly: true}, call: airflow.list-dags}\n    - {name: list-prefect-deployments, description: List Prefect deployments., call:\
  \ prefect.list-deployments}\n    - name: trigger-shared-pipeline\n      description: Trigger a shared pipeline step.\n      inputParameters: [{name: pipeline_id, type: string, required: true}]\n      call: airflow.trigger-dag\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: airflow-prefect-dagster-pipeline-reusability-capability-skills\n    description: Skill bundle for reusable pipeline triggering.\n    skills:\n    - name: airflow-prefect-dagster-pipeline-reusability-capability\n      description: Trigger shared pipeline steps across Airflow, Prefect, Dagster.\n      location: file:///opt/naftiko/skills/airflow-prefect-dagster-pipeline-reusability-capability\n      allowed-tools: list-airflow-dags,list-prefect-deployments,trigger-shared-pipeline\n      tools:\n      - {name: list-airflow-dags, from: {sourceNamespace: airflow-prefect-dagster-pipeline-reusability-capability-mcp, action: list-airflow-dags}}\n      - {name: list-prefect-deployments, from: {sourceNamespace:\
  \ airflow-prefect-dagster-pipeline-reusability-capability-mcp, action: list-prefect-deployments}}\n      - {name: trigger-shared-pipeline, from: {sourceNamespace: airflow-prefect-dagster-pipeline-reusability-capability-mcp, action: trigger-shared-pipeline}}\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/airflow-prefect-dagster-pipeline-reusability-capability.yaml
tags:
- Naftiko
- Airflow
- Prefect
- Dagster
- Reusability
tools:
- description: List Airflow DAGs.
  hints:
    readOnly: true
  name: list-airflow-dags
- description: List Prefect deployments.
  hints: {}
  name: list-prefect-deployments
- description: Trigger a shared pipeline step.
  hints: {}
  name: trigger-shared-pipeline
---
