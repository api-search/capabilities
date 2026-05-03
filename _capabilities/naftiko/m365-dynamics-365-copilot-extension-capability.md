---
categories: []
consumed_apis: []
description: A capability that wraps a Dynamics 365 (Sales/Service) endpoint as both an ISV-style M365 Copilot extension AND an MCP tool, demonstrating Sébastien's "two developer paths" pattern (line-of-business AND ISV).
layout: capability
name: M365 Dynamics 365 Copilot Extension Capability
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
- mcp
- a capability that wraps a dynamics 365 (sales/service) endpoint as both an isv-style m365 copilot extension and an mcp tool, demonstrating sébastien's "two developer paths" pattern (line-of-business and isv).
- capabilities
- ai
slug: m365-dynamics-365-copilot-extension-capability
source_filename: m365-dynamics-365-copilot-extension-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: M365 Dynamics 365 Copilot Extension Capability\n  description: A capability that wraps a Dynamics 365 (Sales/Service) endpoint as both an ISV-style M365 Copilot extension AND an MCP tool, demonstrating Sébastien's \"two developer paths\" pattern (line-of-business AND ISV).\n  tags:\n  - Naftiko\n  created: '2026-05-01'\n  modified: '2026-05-01'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko credentials.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: naftiko\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - name: example-op\n        method: GET\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: m365-dynamics-365-copilot-extension-capability-rest\n    description: REST API for M365 Dynamics\
  \ 365 Copilot Extension Capability.\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - method: GET\n        name: example-op\n        call: naftiko.example-op\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: m365-dynamics-365-copilot-extension-capability-mcp\n    description: MCP server exposing M365 Dynamics 365 Copilot Extension Capability for AI agents.\n    tools:\n    - name: example\n      description: A capability that wraps a Dynamics 365 (Sales/Service) endpoint as both an ISV-style M365 Copilot extension AND an MCP tool, demonstrating Sébastien's \"two developer paths\" pattern (line-of-business AND ISV).\n      hints:\n        readOnly: true\n      call: naftiko.example-op\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: m365-dynamics-365-copilot-extension-capability-skills\n    description: Agent Skill bundle for M365 Dynamics 365 Copilot Extension Capability.\n    skills:\n    - name: m365-dynamics-365-copilot-extension-capability\n\
  \      description: A capability that wraps a Dynamics 365 (Sales/Service) endpoint as both an ISV-style M365 Copilot extension AND an MCP tool, demonstrating Sébastien's \"two developer paths\" pattern (line-of-business AND ISV).\n      location: file:///opt/naftiko/skills/m365-dynamics-365-copilot-extension-capability\n      allowed-tools: example\n      tools:\n      - name: example\n        description: A capability that wraps a Dynamics 365 (Sales/Service) endpoint as both an ISV-style M365 Copilot extension AND an MCP tool, demonstrating Sébastien's \"two developer paths\" pattern (line-of-business AND ISV).\n        from:\n          sourceNamespace: m365-dynamics-365-copilot-extension-capability-mcp\n          action: example\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/m365-dynamics-365-copilot-extension-capability.yaml
tags:
- Naftiko
tools:
- description: A capability that wraps a Dynamics 365 (Sales/Service) endpoint as both an ISV-style M365 Copilot extension AND an MCP tool, demonstrating Sébastien's "two developer paths" pattern (line-of-business AND ISV).
  hints:
    readOnly: true
  name: example
---
