---
categories: []
consumed_apis: []
description: A CLI-driven capability over Palo Alto Cortex XDR that fetches alerts, shapes them for analyst triage, and exposes the shaped feed.
layout: capability
name: Cortex Xdr Alert Shaping Cli Capability
operations:
- description: ''
  method: GET
  name: get-shaped-alerts
  path: /alerts
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- governance
- spec-driven integration
- get incidents
- ai
- security
- capabilities
- get shaped alerts
- api integration
- mcp
- cortex xdr
- naftiko
slug: cortex-xdr-alert-shaping-cli-capability
source_filename: cortex-xdr-alert-shaping-cli-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Cortex Xdr Alert Shaping Cli Capability\n  description: A CLI-driven capability over Palo Alto Cortex XDR that fetches alerts, shapes them for analyst triage, and exposes the shaped feed.\n  tags: [Naftiko, Cortex XDR, Security]\n  created: '2026-05-01'\n  modified: '2026-05-04'\nbinds:\n- namespace: cortex-env\n  keys: {CORTEX_HOST: CORTEX_HOST, CORTEX_API_KEY: CORTEX_API_KEY, CORTEX_API_KEY_ID: CORTEX_API_KEY_ID}\ncapability:\n  consumes:\n  - namespace: cortex\n    type: http\n    baseUri: https://{{CORTEX_HOST}}\n    authentication: {type: bearer, token: '{{CORTEX_API_KEY}}'}\n    resources:\n    - {name: alerts, path: /public_api/v1/alerts/get_alerts_multi_events, operations: [{name: get-alerts, method: POST}]}\n    - {name: incidents, path: /public_api/v1/incidents/get_incidents, operations: [{name: get-incidents, method: POST}]}\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: cortex-xdr-alert-shaping-cli-capability-rest\n\
  \    description: REST surface for shaped Cortex XDR alerts.\n    resources:\n    - {name: alerts, path: /alerts, operations: [{method: GET, name: get-shaped-alerts, call: cortex.get-alerts}]}\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: cortex-xdr-alert-shaping-cli-capability-mcp\n    description: MCP for shaped Cortex XDR alerts.\n    tools:\n    - {name: get-shaped-alerts, hints: {readOnly: true}, call: cortex.get-alerts}\n    - {name: get-incidents, hints: {readOnly: true}, call: cortex.get-incidents}\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: cortex-xdr-alert-shaping-cli-capability-skills\n    description: Skill for shaped Cortex XDR alerts.\n    skills:\n    - name: cortex-xdr-alert-shaping-cli-capability\n      description: Shaped Cortex XDR alerts for analyst triage.\n      location: file:///opt/naftiko/skills/cortex-xdr-alert-shaping-cli-capability\n      allowed-tools: get-shaped-alerts,get-incidents\n      tools:\n      - {name:\
  \ get-shaped-alerts, from: {sourceNamespace: cortex-xdr-alert-shaping-cli-capability-mcp, action: get-shaped-alerts}}\n      - {name: get-incidents, from: {sourceNamespace: cortex-xdr-alert-shaping-cli-capability-mcp, action: get-incidents}}\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/cortex-xdr-alert-shaping-cli-capability.yaml
tags:
- Naftiko
- Cortex XDR
- Security
tools:
- description: ''
  hints:
    readOnly: true
  name: get-shaped-alerts
- description: ''
  hints:
    readOnly: true
  name: get-incidents
---
