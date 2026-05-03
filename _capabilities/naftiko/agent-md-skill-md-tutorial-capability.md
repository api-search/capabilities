---
categories: []
consumed_apis: []
description: A single capability used as the running example in framework-wiki Tutorial-Part-1, with the AI Assistance angle (AGENT.md, SKILL.md prompts) highlighted.
layout: capability
name: Agent Md Skill Md Tutorial Capability
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
- a single capability used as the running example in framework-wiki tutorial-part-1, with the ai assistance angle (agent.md, skill.md prompts) highlighted.
- example op
- governance
slug: agent-md-skill-md-tutorial-capability
source_filename: agent-md-skill-md-tutorial-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Agent Md Skill Md Tutorial Capability\n  description: A single capability used as the running example in framework-wiki Tutorial-Part-1, with the AI Assistance angle (AGENT.md, SKILL.md prompts) highlighted.\n  tags:\n  - Naftiko\n  created: '2026-05-01'\n  modified: '2026-05-01'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko credentials.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: naftiko\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - name: example-op\n        method: GET\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: agent-md-skill-md-tutorial-capability-rest\n    description: REST API for Agent Md Skill Md Tutorial Capability.\n    resources:\n    - name: example\n      path:\
  \ /example\n      operations:\n      - method: GET\n        name: example-op\n        call: naftiko.example-op\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: agent-md-skill-md-tutorial-capability-mcp\n    description: MCP server exposing Agent Md Skill Md Tutorial Capability for AI agents.\n    tools:\n    - name: example\n      description: A single capability used as the running example in framework-wiki Tutorial-Part-1, with the AI Assistance angle (AGENT.md, SKILL.md prompts) highlighted.\n      hints:\n        readOnly: true\n      call: naftiko.example-op\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: agent-md-skill-md-tutorial-capability-skills\n    description: Agent Skill bundle for Agent Md Skill Md Tutorial Capability.\n    skills:\n    - name: agent-md-skill-md-tutorial-capability\n      description: A single capability used as the running example in framework-wiki Tutorial-Part-1, with the AI Assistance angle (AGENT.md, SKILL.md\
  \ prompts) highlighted.\n      location: file:///opt/naftiko/skills/agent-md-skill-md-tutorial-capability\n      allowed-tools: example\n      tools:\n      - name: example\n        description: A single capability used as the running example in framework-wiki Tutorial-Part-1, with the AI Assistance angle (AGENT.md, SKILL.md prompts) highlighted.\n        from:\n          sourceNamespace: agent-md-skill-md-tutorial-capability-mcp\n          action: example\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/agent-md-skill-md-tutorial-capability.yaml
tags:
- Naftiko
tools:
- description: A single capability used as the running example in framework-wiki Tutorial-Part-1, with the AI Assistance angle (AGENT.md, SKILL.md prompts) highlighted.
  hints:
    readOnly: true
  name: example
---
