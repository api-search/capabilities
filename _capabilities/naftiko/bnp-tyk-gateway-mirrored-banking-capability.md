---
categories: []
consumed_apis: []
description: A capability that fronts a Tyk-managed BNP banking API as a Naftiko capability with Forward Proxy + Trusted-Header Security — letting BNP's API-First program add agent-shaped MCP without bypassing the gateway.
layout: capability
name: Bnp Tyk Gateway Mirrored Banking Capability
operations:
- description: ''
  method: GET
  name: example-op
  path: /example
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- spec-driven integration
- example op
- example
- api integration
- naftiko
- a capability that fronts a tyk-managed bnp banking api as a naftiko capability with forward proxy + trusted-header security — letting bnp's api-first program add agent-shaped mcp without bypassing the gateway.
- governance
- mcp
- capabilities
- ai
slug: bnp-tyk-gateway-mirrored-banking-capability
source_filename: bnp-tyk-gateway-mirrored-banking-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Bnp Tyk Gateway Mirrored Banking Capability\n  description: A capability that fronts a Tyk-managed BNP banking API as a Naftiko capability with Forward Proxy + Trusted-Header Security — letting BNP's API-First program add agent-shaped MCP without bypassing the gateway.\n  tags:\n  - Naftiko\n  created: '2026-05-01'\n  modified: '2026-05-01'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko credentials.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: naftiko\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - name: example-op\n        method: GET\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: bnp-tyk-gateway-mirrored-banking-capability-rest\n    description: REST API for Bnp Tyk Gateway Mirrored\
  \ Banking Capability.\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - method: GET\n        name: example-op\n        call: naftiko.example-op\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: bnp-tyk-gateway-mirrored-banking-capability-mcp\n    description: MCP server exposing Bnp Tyk Gateway Mirrored Banking Capability for AI agents.\n    tools:\n    - name: example\n      description: A capability that fronts a Tyk-managed BNP banking API as a Naftiko capability with Forward Proxy + Trusted-Header Security — letting BNP's API-First program add agent-shaped MCP without bypassing the gateway.\n      hints:\n        readOnly: true\n      call: naftiko.example-op\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: bnp-tyk-gateway-mirrored-banking-capability-skills\n    description: Agent Skill bundle for Bnp Tyk Gateway Mirrored Banking Capability.\n    skills:\n    - name: bnp-tyk-gateway-mirrored-banking-capability\n\
  \      description: A capability that fronts a Tyk-managed BNP banking API as a Naftiko capability with Forward Proxy + Trusted-Header Security — letting BNP's API-First program add agent-shaped MCP without bypassing the gateway.\n      location: file:///opt/naftiko/skills/bnp-tyk-gateway-mirrored-banking-capability\n      allowed-tools: example\n      tools:\n      - name: example\n        description: A capability that fronts a Tyk-managed BNP banking API as a Naftiko capability with Forward Proxy + Trusted-Header Security — letting BNP's API-First program add agent-shaped MCP without bypassing the gateway.\n        from:\n          sourceNamespace: bnp-tyk-gateway-mirrored-banking-capability-mcp\n          action: example\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/bnp-tyk-gateway-mirrored-banking-capability.yaml
tags:
- Naftiko
tools:
- description: A capability that fronts a Tyk-managed BNP banking API as a Naftiko capability with Forward Proxy + Trusted-Header Security — letting BNP's API-First program add agent-shaped MCP without bypassing the gateway.
  hints:
    readOnly: true
  name: example
---
