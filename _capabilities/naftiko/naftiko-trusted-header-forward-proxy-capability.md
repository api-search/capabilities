---
categories: []
consumed_apis: []
description: A capability that injects a Naftiko-trusted header (signed JWT with capability id + caller) when forwarding to upstream APIs.
layout: capability
name: Naftiko Trusted Header Forward Proxy Capability
operations:
- description: ''
  method: POST
  name: mint-trusted-token
  path: /tokens
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- governance
- spec-driven integration
- proxy
- introspect trusted token
- mint trusted token
- trust
- ai
- capabilities
- api integration
- mcp
- naftiko
slug: naftiko-trusted-header-forward-proxy-capability
source_filename: naftiko-trusted-header-forward-proxy-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Naftiko Trusted Header Forward Proxy Capability\n  description: A capability that injects a Naftiko-trusted header (signed JWT with capability id + caller) when forwarding to upstream APIs.\n  tags: [Naftiko, Trust, Proxy]\n  created: '2026-05-01'\n  modified: '2026-05-04'\nbinds:\n- namespace: naftiko-env\n  keys: {NAFTIKO_API_KEY: NAFTIKO_API_KEY}\ncapability:\n  consumes:\n  - namespace: naftiko-trust\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication: {type: bearer, token: '{{NAFTIKO_API_KEY}}'}\n    resources:\n    - {name: trusted-tokens, path: /v1/trust/tokens, operations: [{name: mint-trusted-token, method: POST}]}\n    - {name: token-introspect, path: /v1/trust/tokens/introspect, operations: [{name: introspect-trusted-token, method: POST}]}\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: naftiko-trusted-header-forward-proxy-capability-rest\n    description: REST surface\
  \ for trusted-token minting.\n    resources:\n    - {name: token, path: /tokens, operations: [{method: POST, name: mint-trusted-token, call: naftiko-trust.mint-trusted-token}]}\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: naftiko-trusted-header-forward-proxy-capability-mcp\n    description: MCP for trusted-token minting.\n    tools:\n    - {name: mint-trusted-token, call: naftiko-trust.mint-trusted-token}\n    - {name: introspect-trusted-token, call: naftiko-trust.introspect-trusted-token}\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: naftiko-trusted-header-forward-proxy-capability-skills\n    description: Skill for trusted-header forward proxy.\n    skills:\n    - name: naftiko-trusted-header-forward-proxy-capability\n      description: Trusted-header forward proxy.\n      location: file:///opt/naftiko/skills/naftiko-trusted-header-forward-proxy-capability\n      allowed-tools: mint-trusted-token,introspect-trusted-token\n      tools:\n\
  \      - {name: mint-trusted-token, from: {sourceNamespace: naftiko-trusted-header-forward-proxy-capability-mcp, action: mint-trusted-token}}\n      - {name: introspect-trusted-token, from: {sourceNamespace: naftiko-trusted-header-forward-proxy-capability-mcp, action: introspect-trusted-token}}\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/naftiko-trusted-header-forward-proxy-capability.yaml
tags:
- Naftiko
- Trust
- Proxy
tools:
- description: ''
  hints: {}
  name: mint-trusted-token
- description: ''
  hints: {}
  name: introspect-trusted-token
---
