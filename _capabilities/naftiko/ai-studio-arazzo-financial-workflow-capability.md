---
categories: []
consumed_apis: []
description: A capability that ingests an Arazzo workflow from AI Studio and exposes the workflow as a single composed MCP tool — the apidays NYC co-branded financial-services artifact.
layout: capability
name: Ai Studio Arazzo Financial Workflow Capability
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
- a capability that ingests an arazzo workflow from ai studio and exposes the workflow as a single composed mcp tool — the apidays nyc co-branded financial-services artifact.
- naftiko
- capabilities
- mcp
- example op
- example
- governance
slug: ai-studio-arazzo-financial-workflow-capability
source_filename: ai-studio-arazzo-financial-workflow-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Ai Studio Arazzo Financial Workflow Capability\n  description: A capability that ingests an Arazzo workflow from AI Studio and exposes the workflow as a single composed MCP tool — the apidays NYC co-branded financial-services artifact.\n  tags:\n  - Naftiko\n  created: '2026-05-01'\n  modified: '2026-05-01'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko credentials.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: naftiko\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - name: example-op\n        method: GET\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: ai-studio-arazzo-financial-workflow-capability-rest\n    description: REST API for Ai Studio Arazzo Financial Workflow Capability.\n \
  \   resources:\n    - name: example\n      path: /example\n      operations:\n      - method: GET\n        name: example-op\n        call: naftiko.example-op\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: ai-studio-arazzo-financial-workflow-capability-mcp\n    description: MCP server exposing Ai Studio Arazzo Financial Workflow Capability for AI agents.\n    tools:\n    - name: example\n      description: A capability that ingests an Arazzo workflow from AI Studio and exposes the workflow as a single composed MCP tool — the apidays NYC co-branded financial-services artifact.\n      hints:\n        readOnly: true\n      call: naftiko.example-op\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: ai-studio-arazzo-financial-workflow-capability-skills\n    description: Agent Skill bundle for Ai Studio Arazzo Financial Workflow Capability.\n    skills:\n    - name: ai-studio-arazzo-financial-workflow-capability\n      description: A capability that ingests\
  \ an Arazzo workflow from AI Studio and exposes the workflow as a single composed MCP tool — the apidays NYC co-branded financial-services artifact.\n      location: file:///opt/naftiko/skills/ai-studio-arazzo-financial-workflow-capability\n      allowed-tools: example\n      tools:\n      - name: example\n        description: A capability that ingests an Arazzo workflow from AI Studio and exposes the workflow as a single composed MCP tool — the apidays NYC co-branded financial-services artifact.\n        from:\n          sourceNamespace: ai-studio-arazzo-financial-workflow-capability-mcp\n          action: example\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/ai-studio-arazzo-financial-workflow-capability.yaml
tags:
- Naftiko
tools:
- description: A capability that ingests an Arazzo workflow from AI Studio and exposes the workflow as a single composed MCP tool — the apidays NYC co-branded financial-services artifact.
  hints:
    readOnly: true
  name: example
---
