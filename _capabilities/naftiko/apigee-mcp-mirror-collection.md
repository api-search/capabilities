---
categories: []
consumed_apis: []
description: A collection that mirrors the -Apigee-managed APIs as Naftiko capabilities so each becomes MCP-callable without bypassing the existing gateway.
layout: capability
name: Apigee Mcp Mirror Collection
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
- capabilities
- naftiko
- a collection that mirrors the -apigee-managed apis as naftiko capabilities so each becomes mcp-callable without bypassing the existing gateway.
- example op
- mcp
- example
- governance
slug: apigee-mcp-mirror-collection
source_filename: apigee-mcp-mirror-collection.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Apigee Mcp Mirror Collection\n  description: A collection that mirrors the -Apigee-managed APIs as Naftiko capabilities so each becomes MCP-callable without bypassing the existing gateway.\n  tags:\n  - Naftiko\n  created: '2026-05-01'\n  modified: '2026-05-01'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko credentials.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: naftiko\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - name: example-op\n        method: GET\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: apigee-mcp-mirror-collection-rest\n    description: REST API for Apigee Mcp Mirror Collection.\n    resources:\n    - name: example\n      path: /example\n      operations:\n      -\
  \ method: GET\n        name: example-op\n        call: naftiko.example-op\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: apigee-mcp-mirror-collection-mcp\n    description: MCP server exposing Apigee Mcp Mirror Collection for AI agents.\n    tools:\n    - name: example\n      description: A collection that mirrors the -Apigee-managed APIs as Naftiko capabilities so each becomes MCP-callable without bypassing the existing gateway.\n      hints:\n        readOnly: true\n      call: naftiko.example-op\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: apigee-mcp-mirror-collection-skills\n    description: Agent Skill bundle for Apigee Mcp Mirror Collection.\n    skills:\n    - name: apigee-mcp-mirror-collection\n      description: A collection that mirrors the -Apigee-managed APIs as Naftiko capabilities so each becomes MCP-callable without bypassing the existing gateway.\n      location: file:///opt/naftiko/skills/apigee-mcp-mirror-collection\n   \
  \   allowed-tools: example\n      tools:\n      - name: example\n        description: A collection that mirrors the -Apigee-managed APIs as Naftiko capabilities so each becomes MCP-callable without bypassing the existing gateway.\n        from:\n          sourceNamespace: apigee-mcp-mirror-collection-mcp\n          action: example\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/apigee-mcp-mirror-collection.yaml
tags:
- Naftiko
tools:
- description: A collection that mirrors the -Apigee-managed APIs as Naftiko capabilities so each becomes MCP-callable without bypassing the existing gateway.
  hints:
    readOnly: true
  name: example
---
