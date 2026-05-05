---
categories: []
consumed_apis: []
description: A capability used to onboard new developers to GitHub Copilot's MCP support — points Copilot at Naftiko-hosted MCP servers and surfaces a curated list.
layout: capability
name: Github Copilot Mcp Developer Onboarding Capability
operations:
- description: ''
  method: GET
  name: list-mcp-servers
  path: /mcp-servers
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- spec-driven integration
- mcp
- capabilities
- github copilot
- list mcp servers
- naftiko
- onboarding
- get copilot config
- api integration
- governance
- ai
slug: github-copilot-mcp-developer-onboarding-capability
source_filename: github-copilot-mcp-developer-onboarding-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Github Copilot Mcp Developer Onboarding Capability\n  description: A capability used to onboard new developers to GitHub Copilot's MCP support — points Copilot at Naftiko-hosted MCP servers and surfaces a curated list.\n  tags: [Naftiko, GitHub Copilot, MCP, Onboarding]\n  created: '2026-05-01'\n  modified: '2026-05-04'\nbinds:\n- namespace: github-env\n  keys: {GITHUB_TOKEN: GITHUB_TOKEN}\n- namespace: naftiko-env\n  keys: {NAFTIKO_API_KEY: NAFTIKO_API_KEY}\ncapability:\n  consumes:\n  - namespace: github\n    type: http\n    baseUri: https://api.github.com\n    authentication: {type: bearer, token: '{{GITHUB_TOKEN}}'}\n    resources:\n    - name: copilot-config\n      path: /repos/{{owner}}/{{repo}}/contents/.github/copilot.yml\n      operations:\n      - {name: get-copilot-config, method: GET, inputParameters: [{name: owner, in: path}, {name: repo, in: path}]}\n  - namespace: naftiko-control\n    type: http\n    baseUri: https://api.naftiko.com\n\
  \    authentication: {type: bearer, token: '{{NAFTIKO_API_KEY}}'}\n    resources:\n    - {name: mcp-servers, path: /v1/mcp-servers, operations: [{name: list-mcp-servers, method: GET}]}\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: github-copilot-mcp-developer-onboarding-capability-rest\n    description: REST surface for Copilot MCP onboarding.\n    resources:\n    - {name: mcp-servers, path: /mcp-servers, operations: [{method: GET, name: list-mcp-servers, call: naftiko-control.list-mcp-servers}]}\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: github-copilot-mcp-developer-onboarding-capability-mcp\n    description: MCP for Copilot onboarding.\n    tools:\n    - {name: list-mcp-servers, hints: {readOnly: true}, call: naftiko-control.list-mcp-servers}\n    - name: get-copilot-config\n      hints: {readOnly: true}\n      inputParameters: [{name: owner, type: string, required: true}, {name: repo, type: string, required: true}]\n    \
  \  call: github.get-copilot-config\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: github-copilot-mcp-developer-onboarding-capability-skills\n    description: Skill for Copilot onboarding.\n    skills:\n    - name: github-copilot-mcp-developer-onboarding-capability\n      description: Onboard developers to Copilot MCP.\n      location: file:///opt/naftiko/skills/github-copilot-mcp-developer-onboarding-capability\n      allowed-tools: list-mcp-servers,get-copilot-config\n      tools:\n      - {name: list-mcp-servers, from: {sourceNamespace: github-copilot-mcp-developer-onboarding-capability-mcp, action: list-mcp-servers}}\n      - {name: get-copilot-config, from: {sourceNamespace: github-copilot-mcp-developer-onboarding-capability-mcp, action: get-copilot-config}}\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/github-copilot-mcp-developer-onboarding-capability.yaml
tags:
- Naftiko
- GitHub Copilot
- MCP
- Onboarding
tools:
- description: ''
  hints:
    readOnly: true
  name: list-mcp-servers
- description: ''
  hints:
    readOnly: true
  name: get-copilot-config
---
