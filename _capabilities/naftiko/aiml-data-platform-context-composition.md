---
categories: []
consumed_apis: []
description: A -Global-Tech-shaped capability across AI/ML + data platform APIs implementing Compose AI Context.
layout: capability
name: Aiml Data Platform Context Composition
operations:
- description: Pull data-platform features (Snowflake) plus model metadata (MLflow) into one shaped AI context object.
  method: POST
  name: compose-ai-context
  path: /ai-context
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- naftiko
- compose ai context
- api integration
- governance
- ai/ml
- pull data-platform features (snowflake) plus model metadata (mlflow) into one shaped ai context object.
- data platform
- get a registered mlflow model.
- ai
- mcp
- compose ai context from data-platform + ml registry.
- capabilities
- get registered model
- composition
- spec-driven integration
slug: aiml-data-platform-context-composition
source_filename: aiml-data-platform-context-composition.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Aiml Data Platform Context Composition\n  description: A -Global-Tech-shaped capability across AI/ML + data platform APIs implementing Compose AI Context.\n  tags: [Naftiko, AI/ML, Data Platform, Composition]\n  created: '2026-05-01'\n  modified: '2026-05-04'\nbinds:\n- namespace: snowflake-env\n  description: Snowflake account, user, and PAT.\n  keys: {SNOWFLAKE_ACCOUNT: SNOWFLAKE_ACCOUNT, SNOWFLAKE_TOKEN: SNOWFLAKE_TOKEN}\n- namespace: mlflow-env\n  description: MLflow tracking-server bearer token.\n  keys: {MLFLOW_TOKEN: MLFLOW_TOKEN, MLFLOW_HOST: MLFLOW_HOST}\ncapability:\n  consumes:\n  - namespace: snowflake\n    type: http\n    baseUri: https://{{SNOWFLAKE_ACCOUNT}}.snowflakecomputing.com\n    authentication: {type: bearer, token: '{{SNOWFLAKE_TOKEN}}'}\n    resources:\n    - name: query\n      path: /api/v2/statements\n      operations:\n      - {name: run-sql, method: POST, description: Run a SQL statement.}\n  - namespace: mlflow\n\
  \    type: http\n    baseUri: https://{{MLFLOW_HOST}}\n    authentication: {type: bearer, token: '{{MLFLOW_TOKEN}}'}\n    resources:\n    - name: registered-models\n      path: /api/2.0/mlflow/registered-models/get\n      operations:\n      - name: get-registered-model\n        method: GET\n        inputParameters: [{name: name, in: query}]\n    - name: experiments\n      path: /api/2.0/mlflow/experiments/search\n      operations:\n      - {name: search-experiments, method: POST}\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: aiml-data-platform-context-composition-rest\n    description: REST surface composing data-platform query + ML model context into one call.\n    resources:\n    - name: ai-context\n      path: /ai-context\n      operations:\n      - method: POST\n        name: compose-ai-context\n        description: Pull data-platform features (Snowflake) plus model metadata (MLflow) into one shaped AI context object.\n        call: snowflake.run-sql\n\
  \  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: aiml-data-platform-context-composition-mcp\n    description: MCP server exposing composed AI context retrieval.\n    tools:\n    - {name: compose-ai-context, description: Compose AI context from data-platform + ML registry., call: snowflake.run-sql}\n    - name: get-registered-model\n      description: Get a registered MLflow model.\n      hints: {readOnly: true}\n      inputParameters: [{name: name, type: string, required: true}]\n      call: mlflow.get-registered-model\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: aiml-data-platform-context-composition-skills\n    description: Skill bundle for AI context composition.\n    skills:\n    - name: aiml-data-platform-context-composition\n      description: Compose AI context from data + model platforms.\n      location: file:///opt/naftiko/skills/aiml-data-platform-context-composition\n      allowed-tools: compose-ai-context,get-registered-model\n\
  \      tools:\n      - {name: compose-ai-context, from: {sourceNamespace: aiml-data-platform-context-composition-mcp, action: compose-ai-context}}\n      - {name: get-registered-model, from: {sourceNamespace: aiml-data-platform-context-composition-mcp, action: get-registered-model}}\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/aiml-data-platform-context-composition.yaml
tags:
- Naftiko
- AI/ML
- Data Platform
- Composition
tools:
- description: Compose AI context from data-platform + ML registry.
  hints: {}
  name: compose-ai-context
- description: Get a registered MLflow model.
  hints:
    readOnly: true
  name: get-registered-model
---
