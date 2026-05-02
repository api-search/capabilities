---
categories: []
consumed_apis: []
description: A capability that exposes -internal Naftiko capabilities as MCP servers inside GitHub Copilot's VS Code extension window — the developer-onboarding fleet entry-point.
layout: capability
name: Github Copilot Mcp Developer Onboarding Capability
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
- a capability that exposes -internal naftiko capabilities as mcp servers inside github copilot's vs code extension window — the developer-onboarding fleet entry-point.
- api integration
- spec-driven integration
- capabilities
- naftiko
- mcp
- example op
- example
- governance
slug: github-copilot-mcp-developer-onboarding-capability
source_filename: github-copilot-mcp-developer-onboarding-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Github Copilot Mcp Developer Onboarding Capability\n  description: A capability that exposes -internal Naftiko capabilities as MCP servers inside GitHub Copilot's VS Code extension window — the developer-onboarding fleet entry-point.\n  tags:\n  - Naftiko\n  created: '2026-05-01'\n  modified: '2026-05-01'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko credentials.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: naftiko\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - name: example-op\n        method: GET\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: github-copilot-mcp-developer-onboarding-capability-rest\n    description: REST API for Github Copilot Mcp Developer Onboarding Capability.\n\
  \    resources:\n    - name: example\n      path: /example\n      operations:\n      - method: GET\n        name: example-op\n        call: naftiko.example-op\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: github-copilot-mcp-developer-onboarding-capability-mcp\n    description: MCP server exposing Github Copilot Mcp Developer Onboarding Capability for AI agents.\n    tools:\n    - name: example\n      description: A capability that exposes -internal Naftiko capabilities as MCP servers inside GitHub Copilot's VS Code extension window — the developer-onboarding fleet entry-point.\n      hints:\n        readOnly: true\n      call: naftiko.example-op\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: github-copilot-mcp-developer-onboarding-capability-skills\n    description: Agent Skill bundle for Github Copilot Mcp Developer Onboarding Capability.\n    skills:\n    - name: github-copilot-mcp-developer-onboarding-capability\n      description: A capability\
  \ that exposes -internal Naftiko capabilities as MCP servers inside GitHub Copilot's VS Code extension window — the developer-onboarding fleet entry-point.\n      location: file:///opt/naftiko/skills/github-copilot-mcp-developer-onboarding-capability\n      allowed-tools: example\n      tools:\n      - name: example\n        description: A capability that exposes -internal Naftiko capabilities as MCP servers inside GitHub Copilot's VS Code extension window — the developer-onboarding fleet entry-point.\n        from:\n          sourceNamespace: github-copilot-mcp-developer-onboarding-capability-mcp\n          action: example\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/github-copilot-mcp-developer-onboarding-capability.yaml
tags:
- Naftiko
tools:
- description: A capability that exposes -internal Naftiko capabilities as MCP servers inside GitHub Copilot's VS Code extension window — the developer-onboarding fleet entry-point.
  hints:
    readOnly: true
  name: example
---
