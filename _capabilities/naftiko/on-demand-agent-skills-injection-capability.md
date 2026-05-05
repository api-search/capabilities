---
categories: []
consumed_apis: []
description: A capability that injects Agent Skills on-demand into a running agent runtime — pulled from the Naftiko skills registry.
layout: capability
name: On Demand Agent Skills Injection Capability
operations:
- description: ''
  method: POST
  name: inject-skill
  path: /inject
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- inject skill
- download skill
- spec-driven integration
- agent skills
- mcp
- capabilities
- injection
- naftiko
- api integration
- governance
- ai
- list skills
slug: on-demand-agent-skills-injection-capability
source_filename: on-demand-agent-skills-injection-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: On Demand Agent Skills Injection Capability\n  description: A capability that injects Agent Skills on-demand into a running agent runtime — pulled from the Naftiko skills registry.\n  tags: [Naftiko, Agent Skills, Injection]\n  created: '2026-05-01'\n  modified: '2026-05-04'\nbinds:\n- namespace: naftiko-env\n  keys: {NAFTIKO_API_KEY: NAFTIKO_API_KEY}\ncapability:\n  consumes:\n  - namespace: naftiko-skills\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication: {type: bearer, token: '{{NAFTIKO_API_KEY}}'}\n    resources:\n    - {name: skills, path: /v1/skills, operations: [{name: list-skills, method: GET}]}\n    - name: skill-bundle\n      path: /v1/skills/{{skill_id}}/bundle\n      operations:\n      - {name: download-skill, method: GET, inputParameters: [{name: skill_id, in: path}]}\n    - {name: agent-skill-injection, path: /v1/agent-skill-injection, operations: [{name: inject-skill, method: POST}]}\n  exposes:\n\
  \  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: on-demand-agent-skills-injection-capability-rest\n    description: REST surface for on-demand skill injection.\n    resources:\n    - {name: inject, path: /inject, operations: [{method: POST, name: inject-skill, call: naftiko-skills.inject-skill}]}\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: on-demand-agent-skills-injection-capability-mcp\n    description: MCP for skill injection.\n    tools:\n    - {name: list-skills, hints: {readOnly: true}, call: naftiko-skills.list-skills}\n    - {name: inject-skill, call: naftiko-skills.inject-skill}\n    - name: download-skill\n      hints: {readOnly: true}\n      inputParameters: [{name: skill_id, type: string, required: true}]\n      call: naftiko-skills.download-skill\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: on-demand-agent-skills-injection-capability-skills\n    description: Skill for skill injection.\n    skills:\n   \
  \ - name: on-demand-agent-skills-injection-capability\n      description: On-demand Agent Skill injection.\n      location: file:///opt/naftiko/skills/on-demand-agent-skills-injection-capability\n      allowed-tools: list-skills,inject-skill,download-skill\n      tools:\n      - {name: list-skills, from: {sourceNamespace: on-demand-agent-skills-injection-capability-mcp, action: list-skills}}\n      - {name: inject-skill, from: {sourceNamespace: on-demand-agent-skills-injection-capability-mcp, action: inject-skill}}\n      - {name: download-skill, from: {sourceNamespace: on-demand-agent-skills-injection-capability-mcp, action: download-skill}}\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/on-demand-agent-skills-injection-capability.yaml
tags:
- Naftiko
- Agent Skills
- Injection
tools:
- description: ''
  hints:
    readOnly: true
  name: list-skills
- description: ''
  hints: {}
  name: inject-skill
- description: ''
  hints:
    readOnly: true
  name: download-skill
---
