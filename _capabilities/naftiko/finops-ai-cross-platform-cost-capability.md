---
categories: []
consumed_apis: []
description: A capability that fans out to every AI-spend source touches (Microsoft, Google, Anthropic, Open Router, vendor-specific dashboards) and returns one cross-platform AI cost-of-ownership view by capability, team, and agent.
layout: capability
name: Finops Ai Cross Platform Cost Capability
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
- governance
- a capability that fans out to every ai-spend source touches (microsoft, google, anthropic, open router, vendor-specific dashboards) and returns one cross-platform ai cost-of-ownership view by capability, team, and agent.
- mcp
- capabilities
- ai
slug: finops-ai-cross-platform-cost-capability
source_filename: finops-ai-cross-platform-cost-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Finops Ai Cross Platform Cost Capability\n  description: A capability that fans out to every AI-spend source touches (Microsoft, Google, Anthropic, Open Router, vendor-specific dashboards) and returns one cross-platform AI cost-of-ownership view by capability, team, and agent.\n  tags:\n  - Naftiko\n  created: '2026-05-01'\n  modified: '2026-05-01'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko credentials.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: naftiko\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - name: example-op\n        method: GET\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: finops-ai-cross-platform-cost-capability-rest\n    description: REST API for Finops Ai Cross\
  \ Platform Cost Capability.\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - method: GET\n        name: example-op\n        call: naftiko.example-op\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: finops-ai-cross-platform-cost-capability-mcp\n    description: MCP server exposing Finops Ai Cross Platform Cost Capability for AI agents.\n    tools:\n    - name: example\n      description: A capability that fans out to every AI-spend source touches (Microsoft, Google, Anthropic, Open Router, vendor-specific dashboards) and returns one cross-platform AI cost-of-ownership view by capability, team, and agent.\n      hints:\n        readOnly: true\n      call: naftiko.example-op\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: finops-ai-cross-platform-cost-capability-skills\n    description: Agent Skill bundle for Finops Ai Cross Platform Cost Capability.\n    skills:\n    - name: finops-ai-cross-platform-cost-capability\n\
  \      description: A capability that fans out to every AI-spend source touches (Microsoft, Google, Anthropic, Open Router, vendor-specific dashboards) and returns one cross-platform AI cost-of-ownership view by capability, team, and agent.\n      location: file:///opt/naftiko/skills/finops-ai-cross-platform-cost-capability\n      allowed-tools: example\n      tools:\n      - name: example\n        description: A capability that fans out to every AI-spend source touches (Microsoft, Google, Anthropic, Open Router, vendor-specific dashboards) and returns one cross-platform AI cost-of-ownership view by capability, team, and agent.\n        from:\n          sourceNamespace: finops-ai-cross-platform-cost-capability-mcp\n          action: example\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/finops-ai-cross-platform-cost-capability.yaml
tags:
- Naftiko
tools:
- description: A capability that fans out to every AI-spend source touches (Microsoft, Google, Anthropic, Open Router, vendor-specific dashboards) and returns one cross-platform AI cost-of-ownership view by capability, team, and agent.
  hints:
    readOnly: true
  name: example
---
