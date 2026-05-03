---
categories: []
consumed_apis: []
description: A capability bundle wired into NaftikoFabricExplorerPage + Federation Across Fabrics, framed as -Terminal-grade for API platform leadership.
layout: capability
name: Fabric Explorer Platform Demo
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
- a capability bundle wired into naftikofabricexplorerpage + federation across fabrics, framed as -terminal-grade for api platform leadership.
- ai
- mcp
- naftiko
- api integration
- spec-driven integration
- capabilities
- example op
- governance
slug: fabric-explorer-platform-demo
source_filename: fabric-explorer-platform-demo.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Fabric Explorer Platform Demo\n  description: A capability bundle wired into NaftikoFabricExplorerPage + Federation Across Fabrics, framed as -Terminal-grade for API platform leadership.\n  tags:\n  - Naftiko\n  created: '2026-05-01'\n  modified: '2026-05-01'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko credentials.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: naftiko\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - name: example-op\n        method: GET\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: fabric-explorer-platform-demo-rest\n    description: REST API for Fabric Explorer Platform Demo.\n    resources:\n    - name: example\n      path: /example\n      operations:\n      -\
  \ method: GET\n        name: example-op\n        call: naftiko.example-op\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: fabric-explorer-platform-demo-mcp\n    description: MCP server exposing Fabric Explorer Platform Demo for AI agents.\n    tools:\n    - name: example\n      description: A capability bundle wired into NaftikoFabricExplorerPage + Federation Across Fabrics, framed as -Terminal-grade for API platform leadership.\n      hints:\n        readOnly: true\n      call: naftiko.example-op\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: fabric-explorer-platform-demo-skills\n    description: Agent Skill bundle for Fabric Explorer Platform Demo.\n    skills:\n    - name: fabric-explorer-platform-demo\n      description: A capability bundle wired into NaftikoFabricExplorerPage + Federation Across Fabrics, framed as -Terminal-grade for API platform leadership.\n      location: file:///opt/naftiko/skills/fabric-explorer-platform-demo\n   \
  \   allowed-tools: example\n      tools:\n      - name: example\n        description: A capability bundle wired into NaftikoFabricExplorerPage + Federation Across Fabrics, framed as -Terminal-grade for API platform leadership.\n        from:\n          sourceNamespace: fabric-explorer-platform-demo-mcp\n          action: example\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/fabric-explorer-platform-demo.yaml
tags:
- Naftiko
tools:
- description: A capability bundle wired into NaftikoFabricExplorerPage + Federation Across Fabrics, framed as -Terminal-grade for API platform leadership.
  hints:
    readOnly: true
  name: example
---
