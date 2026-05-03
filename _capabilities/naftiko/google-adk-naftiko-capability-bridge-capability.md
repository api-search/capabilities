---
categories: []
consumed_apis: []
description: A capability that bridges Google's Agent Development Kit (ADK) into Naftiko capability layer so ADK-built agents call governed capabilities through the same MCP surface as Microsoft-built agents.
layout: capability
name: Google Adk Naftiko Capability Bridge Capability
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
- a capability that bridges google's agent development kit (adk) into naftiko capability layer so adk-built agents call governed capabilities through the same mcp surface as microsoft-built agents.
- api integration
- spec-driven integration
- capabilities
- example op
- governance
slug: google-adk-naftiko-capability-bridge-capability
source_filename: google-adk-naftiko-capability-bridge-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Google Adk Naftiko Capability Bridge Capability\n  description: A capability that bridges Google's Agent Development Kit (ADK) into Naftiko capability layer so ADK-built agents call governed capabilities through the same MCP surface as Microsoft-built agents.\n  tags:\n  - Naftiko\n  created: '2026-05-01'\n  modified: '2026-05-01'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko credentials.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: naftiko\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - name: example-op\n        method: GET\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: google-adk-naftiko-capability-bridge-capability-rest\n    description: REST API for Google Adk Naftiko Capability\
  \ Bridge Capability.\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - method: GET\n        name: example-op\n        call: naftiko.example-op\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: google-adk-naftiko-capability-bridge-capability-mcp\n    description: MCP server exposing Google Adk Naftiko Capability Bridge Capability for AI agents.\n    tools:\n    - name: example\n      description: A capability that bridges Google's Agent Development Kit (ADK) into Naftiko capability layer so ADK-built agents call governed capabilities through the same MCP surface as Microsoft-built agents.\n      hints:\n        readOnly: true\n      call: naftiko.example-op\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: google-adk-naftiko-capability-bridge-capability-skills\n    description: Agent Skill bundle for Google Adk Naftiko Capability Bridge Capability.\n    skills:\n    - name: google-adk-naftiko-capability-bridge-capability\n\
  \      description: A capability that bridges Google's Agent Development Kit (ADK) into Naftiko capability layer so ADK-built agents call governed capabilities through the same MCP surface as Microsoft-built agents.\n      location: file:///opt/naftiko/skills/google-adk-naftiko-capability-bridge-capability\n      allowed-tools: example\n      tools:\n      - name: example\n        description: A capability that bridges Google's Agent Development Kit (ADK) into Naftiko capability layer so ADK-built agents call governed capabilities through the same MCP surface as Microsoft-built agents.\n        from:\n          sourceNamespace: google-adk-naftiko-capability-bridge-capability-mcp\n          action: example\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/google-adk-naftiko-capability-bridge-capability.yaml
tags:
- Naftiko
tools:
- description: A capability that bridges Google's Agent Development Kit (ADK) into Naftiko capability layer so ADK-built agents call governed capabilities through the same MCP surface as Microsoft-built agents.
  hints:
    readOnly: true
  name: example
---
