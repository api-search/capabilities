---
categories: []
consumed_apis: []
description: A capability that exposes a data warehouse over a uniform Data API surface — query, schema, and lineage as REST + MCP.
layout: capability
name: Data Api Capability
operations:
- description: ''
  method: POST
  name: run-sql
  path: /query
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- snowflake
- spec-driven integration
- run sql
- mcp
- capabilities
- get statement
- naftiko
- api integration
- data api
- governance
- ai
slug: data-api-capability
source_filename: data-api-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Data Api Capability\n  description: A capability that exposes a data warehouse over a uniform Data API surface — query, schema, and lineage as REST + MCP.\n  tags: [Naftiko, Data API, Snowflake]\n  created: '2026-05-01'\n  modified: '2026-05-04'\nbinds:\n- namespace: snowflake-env\n  keys: {SNOWFLAKE_ACCOUNT: SNOWFLAKE_ACCOUNT, SNOWFLAKE_TOKEN: SNOWFLAKE_TOKEN}\ncapability:\n  consumes:\n  - namespace: snowflake\n    type: http\n    baseUri: https://{{SNOWFLAKE_ACCOUNT}}.snowflakecomputing.com\n    authentication: {type: bearer, token: '{{SNOWFLAKE_TOKEN}}'}\n    resources:\n    - {name: statements, path: /api/v2/statements, operations: [{name: run-sql, method: POST}]}\n    - name: statement\n      path: /api/v2/statements/{{statement_handle}}\n      operations:\n      - {name: get-statement, method: GET, inputParameters: [{name: statement_handle, in: path}]}\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace:\
  \ data-api-capability-rest\n    description: REST surface for the data API.\n    resources:\n    - {name: query, path: /query, operations: [{method: POST, name: run-sql, call: snowflake.run-sql}]}\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: data-api-capability-mcp\n    description: MCP for data API.\n    tools:\n    - {name: run-sql, call: snowflake.run-sql}\n    - name: get-statement\n      hints: {readOnly: true}\n      inputParameters: [{name: statement_handle, type: string, required: true}]\n      call: snowflake.get-statement\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: data-api-capability-skills\n    description: Skill for data API.\n    skills:\n    - name: data-api-capability\n      description: Data API over warehouse.\n      location: file:///opt/naftiko/skills/data-api-capability\n      allowed-tools: run-sql,get-statement\n      tools:\n      - {name: run-sql, from: {sourceNamespace: data-api-capability-mcp, action: run-sql}}\n\
  \      - {name: get-statement, from: {sourceNamespace: data-api-capability-mcp, action: get-statement}}\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/data-api-capability.yaml
tags:
- Naftiko
- Data API
- Snowflake
tools:
- description: ''
  hints: {}
  name: run-sql
- description: ''
  hints:
    readOnly: true
  name: get-statement
---
