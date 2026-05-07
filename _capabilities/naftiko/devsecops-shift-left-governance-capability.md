---
categories: []
consumed_apis: []
description: A capability shifting governance left into the dev workflow — runs Spectral + 42Crunch + secret scans on PR open and emits a governance event.
layout: capability
name: Devsecops Shift Left Governance Capability
operations:
- description: ''
  method: POST
  name: scan-pr
  path: /scan-pr
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- devsecops
- governance
- scan pr
- list pulls
- ai
- capabilities
- spec-driven integration
- api integration
- mcp
- shift-left
- naftiko
slug: devsecops-shift-left-governance-capability
source_filename: devsecops-shift-left-governance-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Devsecops Shift Left Governance Capability\n  description: A capability shifting governance left into the dev workflow — runs Spectral + 42Crunch + secret scans on PR open and emits a governance event.\n  tags: [Naftiko, DevSecOps, Shift-Left]\n  created: '2026-05-01'\n  modified: '2026-05-04'\nbinds:\n- namespace: github-env\n  keys: {GITHUB_TOKEN: GITHUB_TOKEN}\n- namespace: fortytwocrunch-env\n  keys: {FORTYTWOCRUNCH_TOKEN: FORTYTWOCRUNCH_TOKEN}\ncapability:\n  consumes:\n  - namespace: github\n    type: http\n    baseUri: https://api.github.com\n    authentication: {type: bearer, token: '{{GITHUB_TOKEN}}'}\n    resources:\n    - name: pulls\n      path: /repos/{{owner}}/{{repo}}/pulls\n      operations:\n      - {name: list-pulls, method: GET, inputParameters: [{name: owner, in: path}, {name: repo, in: path}]}\n    - name: pull-checks\n      path: /repos/{{owner}}/{{repo}}/check-runs\n      operations:\n      - {name: create-check-run,\
  \ method: POST, inputParameters: [{name: owner, in: path}, {name: repo, in: path}]}\n  - namespace: fortytwocrunch\n    type: http\n    baseUri: https://platform.42crunch.com\n    authentication: {type: bearer, token: '{{FORTYTWOCRUNCH_TOKEN}}'}\n    resources:\n    - {name: apis, path: /api/v2/apis, operations: [{name: import-api, method: POST}]}\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: devsecops-shift-left-governance-capability-rest\n    description: REST surface for shift-left governance.\n    resources:\n    - {name: scan-pr, path: /scan-pr, operations: [{method: POST, name: scan-pr, call: fortytwocrunch.import-api}]}\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: devsecops-shift-left-governance-capability-mcp\n    description: MCP for shift-left governance.\n    tools:\n    - {name: scan-pr, call: fortytwocrunch.import-api}\n    - {name: list-pulls, hints: {readOnly: true}, call: github.list-pulls}\n  - type: skill\n \
  \   address: 0.0.0.0\n    port: 3011\n    namespace: devsecops-shift-left-governance-capability-skills\n    description: Skill for shift-left governance.\n    skills:\n    - name: devsecops-shift-left-governance-capability\n      description: Shift-left DevSecOps governance.\n      location: file:///opt/naftiko/skills/devsecops-shift-left-governance-capability\n      allowed-tools: scan-pr,list-pulls\n      tools:\n      - {name: scan-pr, from: {sourceNamespace: devsecops-shift-left-governance-capability-mcp, action: scan-pr}}\n      - {name: list-pulls, from: {sourceNamespace: devsecops-shift-left-governance-capability-mcp, action: list-pulls}}\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/devsecops-shift-left-governance-capability.yaml
tags:
- Naftiko
- DevSecOps
- Shift-Left
tools:
- description: ''
  hints: {}
  name: scan-pr
- description: ''
  hints:
    readOnly: true
  name: list-pulls
---
