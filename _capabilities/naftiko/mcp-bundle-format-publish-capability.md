---
categories: []
consumed_apis: []
description: A capability that publishes Naftiko-governed capability set in the November 2025 MCP Bundle Format spec so they can be installed into any compliant agent runtime as a unit.
layout: capability
name: Mcp Bundle Format Publish Capability
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
- a capability that publishes naftiko-governed capability set in the november 2025 mcp bundle format spec so they can be installed into any compliant agent runtime as a unit.
- naftiko
- api integration
- spec-driven integration
- capabilities
- example op
- governance
slug: mcp-bundle-format-publish-capability
source_filename: mcp-bundle-format-publish-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Mcp Bundle Format Publish Capability\n  description: A capability that publishes Naftiko-governed capability set in the November 2025 MCP Bundle Format spec so they can be installed into any compliant agent runtime as a unit.\n  tags:\n  - Naftiko\n  created: '2026-05-01'\n  modified: '2026-05-01'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko credentials.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: naftiko\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - name: example-op\n        method: GET\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: mcp-bundle-format-publish-capability-rest\n    description: REST API for Mcp Bundle Format Publish Capability.\n    resources:\n    - name: example\n\
  \      path: /example\n      operations:\n      - method: GET\n        name: example-op\n        call: naftiko.example-op\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: mcp-bundle-format-publish-capability-mcp\n    description: MCP server exposing Mcp Bundle Format Publish Capability for AI agents.\n    tools:\n    - name: example\n      description: A capability that publishes Naftiko-governed capability set in the November 2025 MCP Bundle Format spec so they can be installed into any compliant agent runtime as a unit.\n      hints:\n        readOnly: true\n      call: naftiko.example-op\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: mcp-bundle-format-publish-capability-skills\n    description: Agent Skill bundle for Mcp Bundle Format Publish Capability.\n    skills:\n    - name: mcp-bundle-format-publish-capability\n      description: A capability that publishes Naftiko-governed capability set in the November 2025 MCP Bundle Format spec so\
  \ they can be installed into any compliant agent runtime as a unit.\n      location: file:///opt/naftiko/skills/mcp-bundle-format-publish-capability\n      allowed-tools: example\n      tools:\n      - name: example\n        description: A capability that publishes Naftiko-governed capability set in the November 2025 MCP Bundle Format spec so they can be installed into any compliant agent runtime as a unit.\n        from:\n          sourceNamespace: mcp-bundle-format-publish-capability-mcp\n          action: example\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/mcp-bundle-format-publish-capability.yaml
tags:
- Naftiko
tools:
- description: A capability that publishes Naftiko-governed capability set in the November 2025 MCP Bundle Format spec so they can be installed into any compliant agent runtime as a unit.
  hints:
    readOnly: true
  name: example
---
