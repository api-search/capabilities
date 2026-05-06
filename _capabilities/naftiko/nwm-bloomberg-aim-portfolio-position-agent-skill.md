---
categories: []
consumed_apis: []
description: A Northwestern Mutual Agent Skill over Bloomberg AIM portfolio positions for advisor-facing AI flows.
layout: capability
name: Nwm Bloomberg Aim Portfolio Position Agent Skill
operations:
- description: ''
  method: GET
  name: list-positions
  path: /portfolios/{{portfolio_id}}/positions
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- naftiko
- bloomberg aim
- nwm
- list positions
- api integration
- governance
- spec-driven integration
- ai
- mcp
- capabilities
- agent skill
slug: nwm-bloomberg-aim-portfolio-position-agent-skill
source_filename: nwm-bloomberg-aim-portfolio-position-agent-skill.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Nwm Bloomberg Aim Portfolio Position Agent Skill\n  description: A Northwestern Mutual Agent Skill over Bloomberg AIM portfolio positions for advisor-facing AI flows.\n  tags: [Naftiko, NWM, Bloomberg AIM, Agent Skill]\n  created: '2026-05-01'\n  modified: '2026-05-04'\nbinds:\n- namespace: bloomberg-env\n  keys: {BLOOMBERG_TOKEN: BLOOMBERG_TOKEN}\ncapability:\n  consumes:\n  - namespace: aim\n    type: http\n    baseUri: https://api.bloomberg.com\n    authentication: {type: bearer, token: '{{BLOOMBERG_TOKEN}}'}\n    resources:\n    - name: positions\n      path: '/eap/aim/v1/portfolios/{{portfolio_id}}/positions'\n      operations:\n      - {name: list-positions, method: GET, inputParameters: [{name: portfolio_id, in: path}]}\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: nwm-bloomberg-aim-portfolio-position-agent-skill-rest\n    description: REST surface for advisor portfolio positions.\n    resources:\n\
  \    - {name: positions, path: '/portfolios/{{portfolio_id}}/positions', operations: [{method: GET, name: list-positions, inputParameters: [{name: portfolio_id, in: path, type: string}], call: aim.list-positions}]}\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: nwm-bloomberg-aim-portfolio-position-agent-skill-mcp\n    description: MCP for advisor portfolio positions.\n    tools:\n    - name: list-positions\n      hints: {readOnly: true}\n      inputParameters: [{name: portfolio_id, type: string, required: true}]\n      call: aim.list-positions\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: nwm-bloomberg-aim-portfolio-position-agent-skill-skills\n    description: Agent Skill for advisor portfolio positions.\n    skills:\n    - name: nwm-bloomberg-aim-portfolio-position-agent-skill\n      description: Advisor-facing AIM portfolio positions.\n      location: file:///opt/naftiko/skills/nwm-bloomberg-aim-portfolio-position-agent-skill\n      allowed-tools:\
  \ list-positions\n      tools:\n      - {name: list-positions, from: {sourceNamespace: nwm-bloomberg-aim-portfolio-position-agent-skill-mcp, action: list-positions}}\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/nwm-bloomberg-aim-portfolio-position-agent-skill.yaml
tags:
- Naftiko
- NWM
- Bloomberg AIM
- Agent Skill
tools:
- description: ''
  hints:
    readOnly: true
  name: list-positions
---
