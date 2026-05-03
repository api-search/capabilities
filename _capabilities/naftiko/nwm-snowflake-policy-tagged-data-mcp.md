---
categories: []
consumed_apis: []
description: A capability over a Snowflake-hosted financial-services dataset that exposes governed read MCP tools with PII surface detection + data-classification tags as the Zero-Touch-Governance runtime.
layout: capability
name: Nwm Snowflake Policy Tagged Data Mcp
operations:
- description: ''
  method: GET
  name: example-op
  path: /example
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- example
- mcp
- ai
- naftiko
- api integration
- spec-driven integration
- capabilities
- example op
- governance
- a capability over a snowflake-hosted financial-services dataset that exposes governed read mcp tools with pii surface detection + data-classification tags as the zero-touch-governance runtime.
slug: nwm-snowflake-policy-tagged-data-mcp
source_filename: nwm-snowflake-policy-tagged-data-mcp.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Nwm Snowflake Policy Tagged Data Mcp\n  description: A capability over a Snowflake-hosted financial-services dataset that exposes governed read MCP tools with PII surface detection + data-classification tags as the Zero-Touch-Governance runtime.\n  tags:\n  - Naftiko\n  created: '2026-05-01'\n  modified: '2026-05-01'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko credentials.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: naftiko\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - name: example-op\n        method: GET\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: nwm-snowflake-policy-tagged-data-mcp-rest\n    description: REST API for Nwm Snowflake Policy Tagged Data Mcp.\n    resources:\n\
  \    - name: example\n      path: /example\n      operations:\n      - method: GET\n        name: example-op\n        call: naftiko.example-op\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: nwm-snowflake-policy-tagged-data-mcp-mcp\n    description: MCP server exposing Nwm Snowflake Policy Tagged Data Mcp for AI agents.\n    tools:\n    - name: example\n      description: A capability over a Snowflake-hosted financial-services dataset that exposes governed read MCP tools with PII surface detection + data-classification tags as the Zero-Touch-Governance runtime.\n      hints:\n        readOnly: true\n      call: naftiko.example-op\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: nwm-snowflake-policy-tagged-data-mcp-skills\n    description: Agent Skill bundle for Nwm Snowflake Policy Tagged Data Mcp.\n    skills:\n    - name: nwm-snowflake-policy-tagged-data-mcp\n      description: A capability over a Snowflake-hosted financial-services dataset\
  \ that exposes governed read MCP tools with PII surface detection + data-classification tags as the Zero-Touch-Governance runtime.\n      location: file:///opt/naftiko/skills/nwm-snowflake-policy-tagged-data-mcp\n      allowed-tools: example\n      tools:\n      - name: example\n        description: A capability over a Snowflake-hosted financial-services dataset that exposes governed read MCP tools with PII surface detection + data-classification tags as the Zero-Touch-Governance runtime.\n        from:\n          sourceNamespace: nwm-snowflake-policy-tagged-data-mcp-mcp\n          action: example\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/nwm-snowflake-policy-tagged-data-mcp.yaml
tags:
- Naftiko
tools:
- description: A capability over a Snowflake-hosted financial-services dataset that exposes governed read MCP tools with PII surface detection + data-classification tags as the Zero-Touch-Governance runtime.
  hints:
    readOnly: true
  name: example
---
