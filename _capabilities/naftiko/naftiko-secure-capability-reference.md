---
categories: []
consumed_apis: []
description: A reference capability demonstrating the Naftiko secure-capability pattern — secrets via Vault, mTLS to upstreams, audit on every call.
layout: capability
name: Naftiko Secure Capability Reference
operations:
- description: ''
  method: GET
  name: get-secret
  path: /secrets/{{path}}
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- naftiko
- reference
- secure
- get secret
- api integration
- governance
- spec-driven integration
- ai
- mcp
- capabilities
slug: naftiko-secure-capability-reference
source_filename: naftiko-secure-capability-reference.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Naftiko Secure Capability Reference\n  description: A reference capability demonstrating the Naftiko secure-capability pattern — secrets via Vault, mTLS to upstreams, audit on every call.\n  tags: [Naftiko, Secure, Reference]\n  created: '2026-05-01'\n  modified: '2026-05-04'\nbinds:\n- namespace: vault-env\n  keys: {VAULT_HOST: VAULT_HOST, VAULT_TOKEN: VAULT_TOKEN}\ncapability:\n  consumes:\n  - namespace: vault\n    type: http\n    baseUri: https://{{VAULT_HOST}}\n    authentication: {type: bearer, token: '{{VAULT_TOKEN}}'}\n    resources:\n    - name: secret\n      path: '/v1/secret/data/{{path}}'\n      operations:\n      - {name: get-secret, method: GET, inputParameters: [{name: path, in: path}]}\n    - {name: lease, path: /v1/sys/leases/lookup, operations: [{name: lookup-lease, method: POST}]}\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: naftiko-secure-capability-reference-rest\n    description:\
  \ REST surface for the secure-capability reference.\n    resources:\n    - {name: secret, path: '/secrets/{{path}}', operations: [{method: GET, name: get-secret, inputParameters: [{name: path, in: path, type: string}], call: vault.get-secret}]}\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: naftiko-secure-capability-reference-mcp\n    description: MCP for secure-capability reference.\n    tools:\n    - name: get-secret\n      hints: {readOnly: true}\n      inputParameters: [{name: path, type: string, required: true}]\n      call: vault.get-secret\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: naftiko-secure-capability-reference-skills\n    description: Skill for secure-capability reference.\n    skills:\n    - name: naftiko-secure-capability-reference\n      description: Secure-capability reference.\n      location: file:///opt/naftiko/skills/naftiko-secure-capability-reference\n      allowed-tools: get-secret\n      tools:\n      - {name:\
  \ get-secret, from: {sourceNamespace: naftiko-secure-capability-reference-mcp, action: get-secret}}\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/naftiko-secure-capability-reference.yaml
tags:
- Naftiko
- Secure
- Reference
tools:
- description: ''
  hints:
    readOnly: true
  name: get-secret
---
