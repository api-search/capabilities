---
categories: []
consumed_apis: []
description: Wraps an publication API as a capability with the Agent Skills adapter, packaged as a downloadable Skill folder via Control API and installed via CLI.
layout: capability
name: Agent Skills Publication Capability
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
- wraps an publication api as a capability with the agent skills adapter, packaged as a downloadable skill folder via control api and installed via cli.
- api integration
- spec-driven integration
- capabilities
- example op
- governance
slug: agent-skills-publication-capability
source_filename: agent-skills-publication-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Agent Skills Publication Capability\n  description: Wraps an publication API as a capability with the Agent Skills adapter, packaged as a downloadable Skill folder via Control API and installed via CLI.\n  tags:\n  - Naftiko\n  created: '2026-05-01'\n  modified: '2026-05-01'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko credentials.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: naftiko\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - name: example-op\n        method: GET\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: agent-skills-publication-capability-rest\n    description: REST API for Agent Skills Publication Capability.\n    resources:\n    - name: example\n      path: /example\n\
  \      operations:\n      - method: GET\n        name: example-op\n        call: naftiko.example-op\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: agent-skills-publication-capability-mcp\n    description: MCP server exposing Agent Skills Publication Capability for AI agents.\n    tools:\n    - name: example\n      description: Wraps an publication API as a capability with the Agent Skills adapter, packaged as a downloadable Skill folder via Control API and installed via CLI.\n      hints:\n        readOnly: true\n      call: naftiko.example-op\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: agent-skills-publication-capability-skills\n    description: Agent Skill bundle for Agent Skills Publication Capability.\n    skills:\n    - name: agent-skills-publication-capability\n      description: Wraps an publication API as a capability with the Agent Skills adapter, packaged as a downloadable Skill folder via Control API and installed via CLI.\n \
  \     location: file:///opt/naftiko/skills/agent-skills-publication-capability\n      allowed-tools: example\n      tools:\n      - name: example\n        description: Wraps an publication API as a capability with the Agent Skills adapter, packaged as a downloadable Skill folder via Control API and installed via CLI.\n        from:\n          sourceNamespace: agent-skills-publication-capability-mcp\n          action: example\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/agent-skills-publication-capability.yaml
tags:
- Naftiko
tools:
- description: Wraps an publication API as a capability with the Agent Skills adapter, packaged as a downloadable Skill folder via Control API and installed via CLI.
  hints:
    readOnly: true
  name: example
---
