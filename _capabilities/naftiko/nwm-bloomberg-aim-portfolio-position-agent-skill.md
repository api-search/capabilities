---
categories: []
consumed_apis: []
description: A capability over Bloomberg AIM portfolio positions, packaged as an Agent Skill folder with explicit safety + effect tags for the financial-advisor agent context.
layout: capability
name: Nwm Bloomberg Aim Portfolio Position Agent Skill
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
- a capability over bloomberg aim portfolio positions, packaged as an agent skill folder with explicit safety + effect tags for the financial-advisor agent context.
slug: nwm-bloomberg-aim-portfolio-position-agent-skill
source_filename: nwm-bloomberg-aim-portfolio-position-agent-skill.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Nwm Bloomberg Aim Portfolio Position Agent Skill\n  description: A capability over Bloomberg AIM portfolio positions, packaged as an Agent Skill folder with explicit safety + effect tags for the financial-advisor agent context.\n  tags:\n  - Naftiko\n  created: '2026-05-01'\n  modified: '2026-05-01'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko credentials.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: naftiko\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - name: example-op\n        method: GET\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: nwm-bloomberg-aim-portfolio-position-agent-skill-rest\n    description: REST API for Nwm Bloomberg Aim Portfolio Position Agent Skill.\n    resources:\n\
  \    - name: example\n      path: /example\n      operations:\n      - method: GET\n        name: example-op\n        call: naftiko.example-op\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: nwm-bloomberg-aim-portfolio-position-agent-skill-mcp\n    description: MCP server exposing Nwm Bloomberg Aim Portfolio Position Agent Skill for AI agents.\n    tools:\n    - name: example\n      description: A capability over Bloomberg AIM portfolio positions, packaged as an Agent Skill folder with explicit safety + effect tags for the financial-advisor agent context.\n      hints:\n        readOnly: true\n      call: naftiko.example-op\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: nwm-bloomberg-aim-portfolio-position-agent-skill-skills\n    description: Agent Skill bundle for Nwm Bloomberg Aim Portfolio Position Agent Skill.\n    skills:\n    - name: nwm-bloomberg-aim-portfolio-position-agent-skill\n      description: A capability over Bloomberg AIM portfolio\
  \ positions, packaged as an Agent Skill folder with explicit safety + effect tags for the financial-advisor agent context.\n      location: file:///opt/naftiko/skills/nwm-bloomberg-aim-portfolio-position-agent-skill\n      allowed-tools: example\n      tools:\n      - name: example\n        description: A capability over Bloomberg AIM portfolio positions, packaged as an Agent Skill folder with explicit safety + effect tags for the financial-advisor agent context.\n        from:\n          sourceNamespace: nwm-bloomberg-aim-portfolio-position-agent-skill-mcp\n          action: example\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/nwm-bloomberg-aim-portfolio-position-agent-skill.yaml
tags:
- Naftiko
tools:
- description: A capability over Bloomberg AIM portfolio positions, packaged as an Agent Skill folder with explicit safety + effect tags for the financial-advisor agent context.
  hints:
    readOnly: true
  name: example
---
