---
categories: []
consumed_apis: []
description: A Northwestern Mutual capability over Snowflake with object/column policy tags enforced — agents only see data their policy allows.
layout: capability
name: Nwm Snowflake Policy Tagged Data Mcp
operations:
- description: ''
  method: POST
  name: run-policy-tagged-sql
  path: /query
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- governance
- snowflake
- run policy tagged sql
- ai
- capabilities
- spec-driven integration
- api integration
- mcp
- nwm
- naftiko
- policy
slug: nwm-snowflake-policy-tagged-data-mcp
source_filename: nwm-snowflake-policy-tagged-data-mcp.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Nwm Snowflake Policy Tagged Data Mcp\n  description: A Northwestern Mutual capability over Snowflake with object/column policy tags enforced — agents only see data their policy allows.\n  tags: [Naftiko, NWM, Snowflake, Policy]\n  created: '2026-05-01'\n  modified: '2026-05-04'\nbinds:\n- namespace: snowflake-env\n  keys: {SNOWFLAKE_ACCOUNT: SNOWFLAKE_ACCOUNT, SNOWFLAKE_TOKEN: SNOWFLAKE_TOKEN}\ncapability:\n  consumes:\n  - namespace: snowflake\n    type: http\n    baseUri: https://{{SNOWFLAKE_ACCOUNT}}.snowflakecomputing.com\n    authentication: {type: bearer, token: '{{SNOWFLAKE_TOKEN}}'}\n    resources:\n    - {name: statements, path: /api/v2/statements, operations: [{name: run-policy-tagged-sql, method: POST}]}\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: nwm-snowflake-policy-tagged-data-mcp-rest\n    description: REST surface for policy-tagged Snowflake reads.\n    resources:\n    - {name: query,\
  \ path: /query, operations: [{method: POST, name: run-policy-tagged-sql, call: snowflake.run-policy-tagged-sql}]}\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: nwm-snowflake-policy-tagged-data-mcp-mcp\n    description: MCP for policy-tagged Snowflake.\n    tools:\n    - {name: run-policy-tagged-sql, call: snowflake.run-policy-tagged-sql}\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: nwm-snowflake-policy-tagged-data-mcp-skills\n    description: Skill for policy-tagged Snowflake.\n    skills:\n    - name: nwm-snowflake-policy-tagged-data-mcp\n      description: Policy-tagged Snowflake data.\n      location: file:///opt/naftiko/skills/nwm-snowflake-policy-tagged-data-mcp\n      allowed-tools: run-policy-tagged-sql\n      tools:\n      - {name: run-policy-tagged-sql, from: {sourceNamespace: nwm-snowflake-policy-tagged-data-mcp-mcp, action: run-policy-tagged-sql}}\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/nwm-snowflake-policy-tagged-data-mcp.yaml
tags:
- Naftiko
- NWM
- Snowflake
- Policy
tools:
- description: ''
  hints: {}
  name: run-policy-tagged-sql
---
