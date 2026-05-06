---
categories: []
consumed_apis: []
description: A governance capability over banking APIs that enforces consent, audit, and risk-policy gates on every consumer call.
layout: capability
name: Banking Governance Capability
operations:
- description: ''
  method: GET
  name: list-governed-accounts
  path: /accounts
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- naftiko
- list governed accounts
- create consent
- list accounts
- list consents
- mcp
- governance
- api integration
- spec-driven integration
- ai
- banking
- capabilities
slug: banking-governance-capability
source_filename: banking-governance-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Banking Governance Capability\n  description: A governance capability over banking APIs that enforces consent, audit, and risk-policy gates on every consumer call.\n  tags: [Naftiko, Banking, Governance]\n  created: '2026-05-01'\n  modified: '2026-05-04'\nbinds:\n- namespace: openbanking-env\n  keys: {OB_HOST: OB_HOST, OB_TOKEN: OB_TOKEN}\n- namespace: naftiko-env\n  keys: {NAFTIKO_API_KEY: NAFTIKO_API_KEY}\ncapability:\n  consumes:\n  - namespace: openbanking\n    type: http\n    baseUri: https://{{OB_HOST}}\n    authentication: {type: bearer, token: '{{OB_TOKEN}}'}\n    resources:\n    - {name: consents, path: /open-banking/v3.1/aisp/account-access-consents, operations: [{name: list-consents, method: GET}, {name: create-consent, method: POST}]}\n    - {name: accounts, path: /open-banking/v3.1/aisp/accounts, operations: [{name: list-accounts, method: GET}]}\n  - namespace: naftiko-control\n    type: http\n    baseUri: https://api.naftiko.com\n\
  \    authentication: {type: bearer, token: '{{NAFTIKO_API_KEY}}'}\n    resources:\n    - {name: governance-events, path: /v1/governance/events, operations: [{name: emit-governance-event, method: POST}]}\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: banking-governance-capability-rest\n    description: Governance-gated banking surface.\n    resources:\n    - {name: governed-accounts, path: /accounts, operations: [{method: GET, name: list-governed-accounts, call: openbanking.list-accounts}]}\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: banking-governance-capability-mcp\n    description: MCP for governed banking ops.\n    tools:\n    - {name: list-accounts, hints: {readOnly: true}, call: openbanking.list-accounts}\n    - {name: list-consents, hints: {readOnly: true}, call: openbanking.list-consents}\n    - {name: create-consent, call: openbanking.create-consent}\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace:\
  \ banking-governance-capability-skills\n    description: Skill for banking governance.\n    skills:\n    - name: banking-governance-capability\n      description: Governance-gated banking access.\n      location: file:///opt/naftiko/skills/banking-governance-capability\n      allowed-tools: list-accounts,list-consents,create-consent\n      tools:\n      - {name: list-accounts, from: {sourceNamespace: banking-governance-capability-mcp, action: list-accounts}}\n      - {name: list-consents, from: {sourceNamespace: banking-governance-capability-mcp, action: list-consents}}\n      - {name: create-consent, from: {sourceNamespace: banking-governance-capability-mcp, action: create-consent}}\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/banking-governance-capability.yaml
tags:
- Naftiko
- Banking
- Governance
tools:
- description: ''
  hints:
    readOnly: true
  name: list-accounts
- description: ''
  hints:
    readOnly: true
  name: list-consents
- description: ''
  hints: {}
  name: create-consent
---
