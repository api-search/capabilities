---
categories: []
consumed_apis: []
description: A capability that walks GitHub + Datadog + ServiceNow as systems-of-record and auto-publishes Backstage catalog entities so developers never enter catalog data manually (Mark's stated zero-manual-work principle).
layout: capability
name: Backstage Source Of Record Auto Catalog
operations:
- description: ''
  method: GET
  name: example-op
  path: /example
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- ai
- api integration
- spec-driven integration
- a capability that walks github + datadog + servicenow as systems-of-record and auto-publishes backstage catalog entities so developers never enter catalog data manually (mark's stated zero-manual-work principle).
- capabilities
- naftiko
- mcp
- example op
- example
- governance
slug: backstage-source-of-record-auto-catalog
source_filename: backstage-source-of-record-auto-catalog.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Backstage Source Of Record Auto Catalog\n  description: A capability that walks GitHub + Datadog + ServiceNow as systems-of-record and auto-publishes Backstage catalog entities so developers never enter catalog data manually (Mark's stated zero-manual-work principle).\n  tags:\n  - Naftiko\n  created: '2026-05-01'\n  modified: '2026-05-01'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko credentials.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: naftiko\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - name: example-op\n        method: GET\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: backstage-source-of-record-auto-catalog-rest\n    description: REST API for Backstage Source Of Record\
  \ Auto Catalog.\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - method: GET\n        name: example-op\n        call: naftiko.example-op\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: backstage-source-of-record-auto-catalog-mcp\n    description: MCP server exposing Backstage Source Of Record Auto Catalog for AI agents.\n    tools:\n    - name: example\n      description: A capability that walks GitHub + Datadog + ServiceNow as systems-of-record and auto-publishes Backstage catalog entities so developers never enter catalog data manually (Mark's stated zero-manual-work principle).\n      hints:\n        readOnly: true\n      call: naftiko.example-op\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: backstage-source-of-record-auto-catalog-skills\n    description: Agent Skill bundle for Backstage Source Of Record Auto Catalog.\n    skills:\n    - name: backstage-source-of-record-auto-catalog\n      description:\
  \ A capability that walks GitHub + Datadog + ServiceNow as systems-of-record and auto-publishes Backstage catalog entities so developers never enter catalog data manually (Mark's stated zero-manual-work principle).\n      location: file:///opt/naftiko/skills/backstage-source-of-record-auto-catalog\n      allowed-tools: example\n      tools:\n      - name: example\n        description: A capability that walks GitHub + Datadog + ServiceNow as systems-of-record and auto-publishes Backstage catalog entities so developers never enter catalog data manually (Mark's stated zero-manual-work principle).\n        from:\n          sourceNamespace: backstage-source-of-record-auto-catalog-mcp\n          action: example\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/backstage-source-of-record-auto-catalog.yaml
tags:
- Naftiko
tools:
- description: A capability that walks GitHub + Datadog + ServiceNow as systems-of-record and auto-publishes Backstage catalog entities so developers never enter catalog data manually (Mark's stated zero-manual-work principle).
  hints:
    readOnly: true
  name: example
---
