---
categories: []
consumed_apis: []
description: A capability over Azure Databricks feature store, exposing typed model-feature retrieval as MCP for the AI assistant flows John is architecting.
layout: capability
name: Databricks Feature Store Mcp
operations:
- description: Search feature tables by free-text query.
  method: GET
  name: search-feature-tables
  path: /feature-tables
- description: Fetch a feature table's schema, primary keys, online stores, and metadata.
  method: GET
  name: get-feature-table
  path: /feature-tables/{{name}}
- description: Retrieve typed feature values for a set of lookup keys.
  method: POST
  name: get-features-for-model
  path: /model-features
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- naftiko
- mlops
- search feature tables by free-text query.
- get a feature table's schema, primary keys, source, online stores, and metadata.
- capabilities
- retrieve typed feature values for a set of lookup keys.
- get feature table
- fetch a feature table's schema, primary keys, online stores, and metadata.
- search feature tables
- get features for model
- spec-driven integration
- ai
- mcp
- retrieve typed feature values for one or more lookup keys for online inference.
- list features
- api integration
- list features (columns and types) defined on a feature table.
- search feature tables in the databricks feature store by free-text query.
- feature store
- governance
- databricks
slug: databricks-feature-store-mcp
source_filename: databricks-feature-store-mcp.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Databricks Feature Store Mcp\n  description: A capability over Azure Databricks feature store, exposing typed model-feature retrieval as MCP for the AI assistant flows John is architecting.\n  tags:\n  - Naftiko\n  - Databricks\n  - Feature Store\n  - MLOps\n  created: '2026-05-01'\n  modified: '2026-05-04'\nbinds:\n- namespace: databricks-env\n  description: Azure Databricks workspace host and personal access token.\n  keys:\n    DATABRICKS_HOST: DATABRICKS_HOST\n    DATABRICKS_TOKEN: DATABRICKS_TOKEN\ncapability:\n  consumes:\n  - namespace: databricks\n    type: http\n    baseUri: https://{{DATABRICKS_HOST}}\n    authentication:\n      type: bearer\n      token: '{{DATABRICKS_TOKEN}}'\n    resources:\n    - name: feature-tables\n      path: /api/2.0/feature-store/feature-tables/get\n      operations:\n      - name: get-feature-table\n        method: GET\n        inputParameters:\n        - name: name\n          in: query\n         \
  \ description: Three-level feature-table name (catalog.schema.table).\n    - name: feature-table-search\n      path: /api/2.0/feature-store/feature-tables/search\n      operations:\n      - name: search-feature-tables\n        method: GET\n        inputParameters:\n        - name: text\n          in: query\n          description: Free-text search across feature table names and descriptions.\n        - name: max_results\n          in: query\n    - name: features\n      path: /api/2.0/feature-store/features/list\n      operations:\n      - name: list-features\n        method: GET\n        inputParameters:\n        - name: feature_table\n          in: query\n          description: Three-level feature-table name to list features for.\n    - name: online-stores\n      path: /api/2.0/feature-store/online-stores/list\n      operations:\n      - name: list-online-stores\n        method: GET\n    - name: model-serving-features\n      path: /api/2.0/feature-store/feature-tables/get-features\n  \
  \    operations:\n      - name: get-features-for-model\n        method: POST\n        description: Retrieve typed feature values for a set of lookup keys, suitable for online inference.\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: databricks-feature-store-mcp-rest\n    description: REST API exposing typed feature-store reads from Azure Databricks.\n    resources:\n    - name: feature-tables\n      path: /feature-tables\n      operations:\n      - method: GET\n        name: search-feature-tables\n        description: Search feature tables by free-text query.\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n        call: databricks.search-feature-tables\n    - name: feature-table\n      path: /feature-tables/{{name}}\n      operations:\n      - method: GET\n        name: get-feature-table\n        description: Fetch a feature table's schema, primary keys, online stores, and metadata.\n        inputParameters:\n\
  \        - name: name\n          in: path\n          type: string\n          description: Three-level feature-table name (catalog.schema.table).\n        call: databricks.get-feature-table\n    - name: model-features\n      path: /model-features\n      operations:\n      - method: POST\n        name: get-features-for-model\n        description: Retrieve typed feature values for a set of lookup keys.\n        call: databricks.get-features-for-model\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: databricks-feature-store-mcp-mcp\n    description: MCP server giving AI assistants typed access to the Databricks feature store.\n    tools:\n    - name: search-feature-tables\n      description: Search feature tables in the Databricks feature store by free-text query.\n      hints:\n        readOnly: true\n      inputParameters:\n      - name: q\n        type: string\n        required: true\n        description: Search text.\n      call: databricks.search-feature-tables\n \
  \   - name: get-feature-table\n      description: Get a feature table's schema, primary keys, source, online stores, and metadata.\n      hints:\n        readOnly: true\n      inputParameters:\n      - name: name\n        type: string\n        required: true\n        description: Three-level feature-table name (catalog.schema.table).\n      call: databricks.get-feature-table\n    - name: list-features\n      description: List features (columns and types) defined on a feature table.\n      hints:\n        readOnly: true\n      inputParameters:\n      - name: feature_table\n        type: string\n        required: true\n      call: databricks.list-features\n    - name: get-features-for-model\n      description: Retrieve typed feature values for one or more lookup keys for online inference.\n      hints:\n        readOnly: true\n      call: databricks.get-features-for-model\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: databricks-feature-store-mcp-skills\n    description:\
  \ Agent Skill bundle giving AI assistants typed feature-store access.\n    skills:\n    - name: databricks-feature-store-mcp\n      description: Typed model-feature retrieval from the Databricks feature store for AI assistant flows.\n      location: file:///opt/naftiko/skills/databricks-feature-store-mcp\n      allowed-tools: search-feature-tables,get-feature-table,list-features,get-features-for-model\n      argument-hint: 'Use when an agent needs to look up feature definitions or fetch typed feature values for inference.'\n      tools:\n      - name: search-feature-tables\n        description: Search feature tables.\n        from:\n          sourceNamespace: databricks-feature-store-mcp-mcp\n          action: search-feature-tables\n      - name: get-feature-table\n        description: Get a feature table's schema and metadata.\n        from:\n          sourceNamespace: databricks-feature-store-mcp-mcp\n          action: get-feature-table\n      - name: list-features\n        description:\
  \ List features on a feature table.\n        from:\n          sourceNamespace: databricks-feature-store-mcp-mcp\n          action: list-features\n      - name: get-features-for-model\n        description: Retrieve typed feature values for inference.\n        from:\n          sourceNamespace: databricks-feature-store-mcp-mcp\n          action: get-features-for-model\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/databricks-feature-store-mcp.yaml
tags:
- Naftiko
- Databricks
- Feature Store
- MLOps
tools:
- description: Search feature tables in the Databricks feature store by free-text query.
  hints:
    readOnly: true
  name: search-feature-tables
- description: Get a feature table's schema, primary keys, source, online stores, and metadata.
  hints:
    readOnly: true
  name: get-feature-table
- description: List features (columns and types) defined on a feature table.
  hints:
    readOnly: true
  name: list-features
- description: Retrieve typed feature values for one or more lookup keys for online inference.
  hints:
    readOnly: true
  name: get-features-for-model
---
