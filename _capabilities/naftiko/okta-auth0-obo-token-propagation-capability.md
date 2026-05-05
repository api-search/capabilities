---
categories: []
consumed_apis: []
description: A capability that propagates Okta/Auth0 on-behalf-of (OBO) tokens through the Naftiko proxy so upstream APIs see the original user identity.
layout: capability
name: Okta Auth0 Obo Token Propagation Capability
operations:
- description: ''
  method: POST
  name: exchange-obo-token
  path: /token/exchange
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- exchange obo token
- spec-driven integration
- mcp
- introspect token
- capabilities
- auth0
- naftiko
- api integration
- okta
- governance
- ai
- obo
slug: okta-auth0-obo-token-propagation-capability
source_filename: okta-auth0-obo-token-propagation-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Okta Auth0 Obo Token Propagation Capability\n  description: A capability that propagates Okta/Auth0 on-behalf-of (OBO) tokens through the Naftiko proxy so upstream APIs see the original user identity.\n  tags: [Naftiko, Okta, Auth0, OBO]\n  created: '2026-05-01'\n  modified: '2026-05-04'\nbinds:\n- namespace: okta-env\n  keys: {OKTA_DOMAIN: OKTA_DOMAIN, OKTA_TOKEN: OKTA_TOKEN}\ncapability:\n  consumes:\n  - namespace: okta\n    type: http\n    baseUri: https://{{OKTA_DOMAIN}}\n    authentication: {type: bearer, token: '{{OKTA_TOKEN}}'}\n    resources:\n    - {name: token, path: /oauth2/v1/token, operations: [{name: exchange-obo-token, method: POST, description: RFC 8693 token exchange for OBO.}]}\n    - {name: introspect, path: /oauth2/v1/introspect, operations: [{name: introspect-token, method: POST}]}\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: okta-auth0-obo-token-propagation-capability-rest\n \
  \   description: REST surface for OBO token exchange.\n    resources:\n    - {name: exchange, path: /token/exchange, operations: [{method: POST, name: exchange-obo-token, call: okta.exchange-obo-token}]}\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: okta-auth0-obo-token-propagation-capability-mcp\n    description: MCP for OBO token exchange.\n    tools:\n    - {name: exchange-obo-token, call: okta.exchange-obo-token}\n    - {name: introspect-token, call: okta.introspect-token}\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: okta-auth0-obo-token-propagation-capability-skills\n    description: Skill for OBO propagation.\n    skills:\n    - name: okta-auth0-obo-token-propagation-capability\n      description: Okta/Auth0 OBO token propagation.\n      location: file:///opt/naftiko/skills/okta-auth0-obo-token-propagation-capability\n      allowed-tools: exchange-obo-token,introspect-token\n      tools:\n      - {name: exchange-obo-token, from: {sourceNamespace:\
  \ okta-auth0-obo-token-propagation-capability-mcp, action: exchange-obo-token}}\n      - {name: introspect-token, from: {sourceNamespace: okta-auth0-obo-token-propagation-capability-mcp, action: introspect-token}}\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/okta-auth0-obo-token-propagation-capability.yaml
tags:
- Naftiko
- Okta
- Auth0
- OBO
tools:
- description: ''
  hints: {}
  name: exchange-obo-token
- description: ''
  hints: {}
  name: introspect-token
---
