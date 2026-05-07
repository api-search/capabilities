---
categories: []
consumed_apis: []
description: A capability bridging Microsoft Entra ID (Azure AD) into Microsoft Agent 365 so agents call Naftiko capabilities with the user's identity propagated.
layout: capability
name: Microsoft Agent 365 Identity Bridge
operations:
- description: ''
  method: GET
  name: get-identity
  path: /identity
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- list app roles
- governance
- agent 365
- entra
- get identity
- ai
- capabilities
- spec-driven integration
- identity
- api integration
- mcp
- naftiko
slug: microsoft-agent-365-identity-bridge
source_filename: microsoft-agent-365-identity-bridge.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Microsoft Agent 365 Identity Bridge\n  description: A capability bridging Microsoft Entra ID (Azure AD) into Microsoft Agent 365 so agents call Naftiko capabilities with the user's identity propagated.\n  tags: [Naftiko, Entra, Agent 365, Identity]\n  created: '2026-05-01'\n  modified: '2026-05-04'\nbinds:\n- namespace: entra-env\n  keys: {ENTRA_TENANT: ENTRA_TENANT, ENTRA_TOKEN: ENTRA_TOKEN}\ncapability:\n  consumes:\n  - namespace: entra\n    type: http\n    baseUri: https://graph.microsoft.com\n    authentication: {type: bearer, token: '{{ENTRA_TOKEN}}'}\n    resources:\n    - {name: me, path: /v1.0/me, operations: [{name: get-me, method: GET}]}\n    - {name: app-roles, path: /v1.0/me/appRoleAssignments, operations: [{name: list-app-roles, method: GET}]}\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: microsoft-agent-365-identity-bridge-rest\n    description: REST surface for identity propagation.\n\
  \    resources:\n    - {name: identity, path: /identity, operations: [{method: GET, name: get-identity, call: entra.get-me}]}\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: microsoft-agent-365-identity-bridge-mcp\n    description: MCP for Agent 365 identity.\n    tools:\n    - {name: get-identity, hints: {readOnly: true}, call: entra.get-me}\n    - {name: list-app-roles, hints: {readOnly: true}, call: entra.list-app-roles}\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: microsoft-agent-365-identity-bridge-skills\n    description: Skill for Agent 365 identity.\n    skills:\n    - name: microsoft-agent-365-identity-bridge\n      description: Agent 365 identity bridge.\n      location: file:///opt/naftiko/skills/microsoft-agent-365-identity-bridge\n      allowed-tools: get-identity,list-app-roles\n      tools:\n      - {name: get-identity, from: {sourceNamespace: microsoft-agent-365-identity-bridge-mcp, action: get-identity}}\n      - {name: list-app-roles,\
  \ from: {sourceNamespace: microsoft-agent-365-identity-bridge-mcp, action: list-app-roles}}\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/microsoft-agent-365-identity-bridge.yaml
tags:
- Naftiko
- Entra
- Agent 365
- Identity
tools:
- description: ''
  hints:
    readOnly: true
  name: get-identity
- description: ''
  hints:
    readOnly: true
  name: list-app-roles
---
