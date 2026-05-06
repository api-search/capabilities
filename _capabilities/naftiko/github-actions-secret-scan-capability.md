---
categories: []
consumed_apis: []
description: A capability that runs secret-scan checks against repos using GitHub's secret-scanning alerts API and exposes results as governance events.
layout: capability
name: Github Actions Secret Scan Capability
operations:
- description: ''
  method: GET
  name: list-secret-alerts
  path: /alerts/{{owner}}/{{repo}}
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- naftiko
- mcp
- secret scanning
- api integration
- governance
- spec-driven integration
- ai
- list secret alerts
- github
- capabilities
- get secret alert
slug: github-actions-secret-scan-capability
source_filename: github-actions-secret-scan-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Github Actions Secret Scan Capability\n  description: A capability that runs secret-scan checks against repos using GitHub's secret-scanning alerts API and exposes results as governance events.\n  tags: [Naftiko, GitHub, Secret Scanning]\n  created: '2026-05-01'\n  modified: '2026-05-04'\nbinds:\n- namespace: github-env\n  keys: {GITHUB_TOKEN: GITHUB_TOKEN}\ncapability:\n  consumes:\n  - namespace: github\n    type: http\n    baseUri: https://api.github.com\n    authentication: {type: bearer, token: '{{GITHUB_TOKEN}}'}\n    resources:\n    - name: secret-scanning-alerts\n      path: '/repos/{{owner}}/{{repo}}/secret-scanning/alerts'\n      operations:\n      - {name: list-secret-alerts, method: GET, inputParameters: [{name: owner, in: path}, {name: repo, in: path}]}\n    - name: secret-alert\n      path: '/repos/{{owner}}/{{repo}}/secret-scanning/alerts/{{alert_number}}'\n      operations:\n      - {name: get-secret-alert, method: GET,\
  \ inputParameters: [{name: owner, in: path}, {name: repo, in: path}, {name: alert_number, in: path}]}\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: github-actions-secret-scan-capability-rest\n    description: REST surface for GitHub secret-scan results.\n    resources:\n    - {name: alerts, path: '/alerts/{{owner}}/{{repo}}', operations: [{method: GET, name: list-secret-alerts, inputParameters: [{name: owner, in: path, type: string}, {name: repo, in: path, type: string}], call: github.list-secret-alerts}]}\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: github-actions-secret-scan-capability-mcp\n    description: MCP for secret-scan results.\n    tools:\n    - name: list-secret-alerts\n      hints: {readOnly: true}\n      inputParameters: [{name: owner, type: string, required: true}, {name: repo, type: string, required: true}]\n      call: github.list-secret-alerts\n    - name: get-secret-alert\n      hints: {readOnly: true}\n   \
  \   inputParameters: [{name: owner, type: string, required: true}, {name: repo, type: string, required: true}, {name: alert_number, type: string, required: true}]\n      call: github.get-secret-alert\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: github-actions-secret-scan-capability-skills\n    description: Skill for secret-scan governance.\n    skills:\n    - name: github-actions-secret-scan-capability\n      description: GitHub secret-scanning governance.\n      location: file:///opt/naftiko/skills/github-actions-secret-scan-capability\n      allowed-tools: list-secret-alerts,get-secret-alert\n      tools:\n      - {name: list-secret-alerts, from: {sourceNamespace: github-actions-secret-scan-capability-mcp, action: list-secret-alerts}}\n      - {name: get-secret-alert, from: {sourceNamespace: github-actions-secret-scan-capability-mcp, action: get-secret-alert}}\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/github-actions-secret-scan-capability.yaml
tags:
- Naftiko
- GitHub
- Secret Scanning
tools:
- description: ''
  hints:
    readOnly: true
  name: list-secret-alerts
- description: ''
  hints:
    readOnly: true
  name: get-secret-alert
---
