---
categories: []
consumed_apis: []
description: A capability deployed via the NaftikoCapability CRD that simultaneously exposes MCP Tools/Resources/Prompts, demonstrating MCP-as-platform-resource end-to-end.
layout: capability
name: Mcp As K8S Resource Demo
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
- a capability deployed via the naftikocapability crd that simultaneously exposes mcp tools/resources/prompts, demonstrating mcp-as-platform-resource end-to-end.
slug: mcp-as-k8s-resource-demo
source_filename: mcp-as-k8s-resource-demo.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Mcp As K8s Resource Demo\n  description: A capability deployed via the NaftikoCapability CRD that simultaneously exposes MCP Tools/Resources/Prompts, demonstrating MCP-as-platform-resource end-to-end.\n  tags:\n  - Naftiko\n  created: '2026-05-01'\n  modified: '2026-05-01'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko credentials.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: naftiko\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - name: example-op\n        method: GET\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: mcp-as-k8s-resource-demo-rest\n    description: REST API for Mcp As K8s Resource Demo.\n    resources:\n    - name: example\n      path: /example\n      operations:\n  \
  \    - method: GET\n        name: example-op\n        call: naftiko.example-op\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: mcp-as-k8s-resource-demo-mcp\n    description: MCP server exposing Mcp As K8s Resource Demo for AI agents.\n    tools:\n    - name: example\n      description: A capability deployed via the NaftikoCapability CRD that simultaneously exposes MCP Tools/Resources/Prompts, demonstrating MCP-as-platform-resource end-to-end.\n      hints:\n        readOnly: true\n      call: naftiko.example-op\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: mcp-as-k8s-resource-demo-skills\n    description: Agent Skill bundle for Mcp As K8s Resource Demo.\n    skills:\n    - name: mcp-as-k8s-resource-demo\n      description: A capability deployed via the NaftikoCapability CRD that simultaneously exposes MCP Tools/Resources/Prompts, demonstrating MCP-as-platform-resource end-to-end.\n      location: file:///opt/naftiko/skills/mcp-as-k8s-resource-demo\n\
  \      allowed-tools: example\n      tools:\n      - name: example\n        description: A capability deployed via the NaftikoCapability CRD that simultaneously exposes MCP Tools/Resources/Prompts, demonstrating MCP-as-platform-resource end-to-end.\n        from:\n          sourceNamespace: mcp-as-k8s-resource-demo-mcp\n          action: example\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/mcp-as-k8s-resource-demo.yaml
tags:
- Naftiko
tools:
- description: A capability deployed via the NaftikoCapability CRD that simultaneously exposes MCP Tools/Resources/Prompts, demonstrating MCP-as-platform-resource end-to-end.
  hints:
    readOnly: true
  name: example
---
