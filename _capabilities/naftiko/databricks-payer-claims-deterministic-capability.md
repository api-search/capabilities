---
categories: []
consumed_apis: []
description: A deterministic capability over a Databricks payer-claims dataset — same query input yields same shaped result, suitable for audit-graded payer flows.
layout: capability
name: Databricks Payer Claims Deterministic Capability
operations:
- description: ''
  method: POST
  name: query-claims
  path: /claims/query
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- naftiko
- healthcare
- query claims
- api integration
- get claim result
- capabilities
- governance
- ai
- spec-driven integration
- mcp
- databricks
- payer
slug: databricks-payer-claims-deterministic-capability
source_filename: databricks-payer-claims-deterministic-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Databricks Payer Claims Deterministic Capability\n  description: A deterministic capability over a Databricks payer-claims dataset — same query input yields same shaped result, suitable for audit-graded payer flows.\n  tags: [Naftiko, Databricks, Payer, Healthcare]\n  created: '2026-05-01'\n  modified: '2026-05-04'\nbinds:\n- namespace: databricks-env\n  keys: {DATABRICKS_HOST: DATABRICKS_HOST, DATABRICKS_TOKEN: DATABRICKS_TOKEN, DATABRICKS_WAREHOUSE_ID: DATABRICKS_WAREHOUSE_ID}\ncapability:\n  consumes:\n  - namespace: databricks\n    type: http\n    baseUri: https://{{DATABRICKS_HOST}}\n    authentication: {type: bearer, token: '{{DATABRICKS_TOKEN}}'}\n    resources:\n    - {name: sql-statements, path: /api/2.0/sql/statements, operations: [{name: execute-sql, method: POST}]}\n    - name: sql-statement\n      path: /api/2.0/sql/statements/{{statement_id}}\n      operations:\n      - {name: get-statement-result, method: GET, inputParameters:\
  \ [{name: statement_id, in: path}]}\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: databricks-payer-claims-deterministic-capability-rest\n    description: REST surface for deterministic payer-claims queries.\n    resources:\n    - {name: claims, path: /claims/query, operations: [{method: POST, name: query-claims, call: databricks.execute-sql}]}\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: databricks-payer-claims-deterministic-capability-mcp\n    description: MCP for payer-claims queries.\n    tools:\n    - {name: query-claims, call: databricks.execute-sql}\n    - name: get-claim-result\n      hints: {readOnly: true}\n      inputParameters: [{name: statement_id, type: string, required: true}]\n      call: databricks.get-statement-result\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: databricks-payer-claims-deterministic-capability-skills\n    description: Skill for payer claims.\n    skills:\n    - name:\
  \ databricks-payer-claims-deterministic-capability\n      description: Deterministic payer-claims queries.\n      location: file:///opt/naftiko/skills/databricks-payer-claims-deterministic-capability\n      allowed-tools: query-claims,get-claim-result\n      tools:\n      - {name: query-claims, from: {sourceNamespace: databricks-payer-claims-deterministic-capability-mcp, action: query-claims}}\n      - {name: get-claim-result, from: {sourceNamespace: databricks-payer-claims-deterministic-capability-mcp, action: get-claim-result}}\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/databricks-payer-claims-deterministic-capability.yaml
tags:
- Naftiko
- Databricks
- Payer
- Healthcare
tools:
- description: ''
  hints: {}
  name: query-claims
- description: ''
  hints:
    readOnly: true
  name: get-claim-result
---
