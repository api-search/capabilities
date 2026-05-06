---
categories: []
consumed_apis: []
description: Wraps an publication API as a capability with the Agent Skills adapter, packaged as a downloadable Skill folder via Control API and installed via CLI.
layout: capability
name: Agent Skills Publication Capability
operations:
- description: Publish a skill folder
  method: POST
  name: publish-skill
  path: /publish
- description: Download the Skill folder zip.
  method: GET
  name: download-bundle
  path: /skills/{{skill_id}}/bundle
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- naftiko
- download bundle
- list skills
- get skill metadata.
- mcp
- get skill
- publication
- publish a skill folder
- publish skill
- api integration
- download the skill folder zip.
- agent skills
- publish an agent skill folder.
- ai
- governance
- list published skills
- spec-driven integration
- capabilities
slug: agent-skills-publication-capability
source_filename: agent-skills-publication-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Agent Skills Publication Capability\n  description: Wraps an publication API as a capability with the Agent Skills adapter, packaged as a downloadable Skill folder via Control API and installed via CLI.\n  tags: [Naftiko, Agent Skills, Publication]\n  created: '2026-05-01'\n  modified: '2026-05-04'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko Control API token.\n  keys: {NAFTIKO_API_KEY: NAFTIKO_API_KEY}\ncapability:\n  consumes:\n  - namespace: naftiko-control\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication: {type: bearer, token: '{{NAFTIKO_API_KEY}}'}\n    resources:\n    - name: skills\n      path: /v1/skills\n      operations:\n      - {name: list-skills, method: GET}\n      - {name: publish-skill, method: POST, description: Publish an Agent Skill folder.}\n    - name: skill\n      path: /v1/skills/{{skill_id}}\n      operations:\n      - name: get-skill\n        method: GET\n        inputParameters:\
  \ [{name: skill_id, in: path}]\n    - name: skill-bundle\n      path: /v1/skills/{{skill_id}}/bundle\n      operations:\n      - name: download-skill-bundle\n        method: GET\n        description: Download the Skill folder as a zip for CLI install.\n        inputParameters: [{name: skill_id, in: path}]\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: agent-skills-publication-capability-rest\n    description: REST surface for publishing and downloading Agent Skill bundles.\n    resources:\n    - name: publish\n      path: /publish\n      operations:\n      - {method: POST, name: publish-skill, description: Publish a skill folder, call: naftiko-control.publish-skill}\n    - name: bundle\n      path: /skills/{{skill_id}}/bundle\n      operations:\n      - method: GET\n        name: download-bundle\n        description: Download the Skill folder zip.\n        inputParameters: [{name: skill_id, in: path, type: string}]\n        call: naftiko-control.download-skill-bundle\n\
  \  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: agent-skills-publication-capability-mcp\n    description: MCP for agents to browse and pull Agent Skill bundles.\n    tools:\n    - {name: list-skills, description: List published skills, hints: {readOnly: true}, call: naftiko-control.list-skills}\n    - name: get-skill\n      description: Get skill metadata.\n      hints: {readOnly: true}\n      inputParameters: [{name: skill_id, type: string, required: true}]\n      call: naftiko-control.get-skill\n    - name: publish-skill\n      description: Publish an Agent Skill folder.\n      call: naftiko-control.publish-skill\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: agent-skills-publication-capability-skills\n    description: Skill bundle for skill-publication tooling.\n    skills:\n    - name: agent-skills-publication-capability\n      description: Publish and install Agent Skill folders.\n      location: file:///opt/naftiko/skills/agent-skills-publication-capability\n\
  \      allowed-tools: list-skills,get-skill,publish-skill\n      tools:\n      - {name: list-skills, from: {sourceNamespace: agent-skills-publication-capability-mcp, action: list-skills}}\n      - {name: get-skill, from: {sourceNamespace: agent-skills-publication-capability-mcp, action: get-skill}}\n      - {name: publish-skill, from: {sourceNamespace: agent-skills-publication-capability-mcp, action: publish-skill}}\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/agent-skills-publication-capability.yaml
tags:
- Naftiko
- Agent Skills
- Publication
tools:
- description: List published skills
  hints:
    readOnly: true
  name: list-skills
- description: Get skill metadata.
  hints:
    readOnly: true
  name: get-skill
- description: Publish an Agent Skill folder.
  hints: {}
  name: publish-skill
---
