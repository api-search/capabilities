---
categories: []
consumed_apis: []
description: A capability that handles on-behalf-of token propagation across agent-to-agent calls, using Okta + Auth0 standards work to keep identity continuous through multi-step agent flows alongside the existing Microsoft Agent 365 bridge.
layout: capability
name: Okta Auth0 Obo Token Propagation Capability
operations:
- description: ''
  method: GET
  name: example-op
  path: /example
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- spec-driven integration
- example op
- example
- api integration
- naftiko
- a capability that handles on-behalf-of token propagation across agent-to-agent calls, using okta + auth0 standards work to keep identity continuous through multi-step agent flows alongside the existing microsoft agent 365 bridge.
- governance
- mcp
- capabilities
- ai
slug: okta-auth0-obo-token-propagation-capability
source_filename: okta-auth0-obo-token-propagation-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Okta Auth0 Obo Token Propagation Capability\n  description: A capability that handles on-behalf-of token propagation across agent-to-agent calls, using Okta + Auth0 standards work to keep identity continuous through multi-step agent flows alongside the existing Microsoft Agent 365 bridge.\n  tags:\n  - Naftiko\n  created: '2026-05-01'\n  modified: '2026-05-01'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko credentials.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: naftiko\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - name: example-op\n        method: GET\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: okta-auth0-obo-token-propagation-capability-rest\n    description: REST API for\
  \ Okta Auth0 Obo Token Propagation Capability.\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - method: GET\n        name: example-op\n        call: naftiko.example-op\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: okta-auth0-obo-token-propagation-capability-mcp\n    description: MCP server exposing Okta Auth0 Obo Token Propagation Capability for AI agents.\n    tools:\n    - name: example\n      description: A capability that handles on-behalf-of token propagation across agent-to-agent calls, using Okta + Auth0 standards work to keep identity continuous through multi-step agent flows alongside the existing Microsoft Agent 365 bridge.\n      hints:\n        readOnly: true\n      call: naftiko.example-op\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: okta-auth0-obo-token-propagation-capability-skills\n    description: Agent Skill bundle for Okta Auth0 Obo Token Propagation Capability.\n    skills:\n    -\
  \ name: okta-auth0-obo-token-propagation-capability\n      description: A capability that handles on-behalf-of token propagation across agent-to-agent calls, using Okta + Auth0 standards work to keep identity continuous through multi-step agent flows alongside the existing Microsoft Agent 365 bridge.\n      location: file:///opt/naftiko/skills/okta-auth0-obo-token-propagation-capability\n      allowed-tools: example\n      tools:\n      - name: example\n        description: A capability that handles on-behalf-of token propagation across agent-to-agent calls, using Okta + Auth0 standards work to keep identity continuous through multi-step agent flows alongside the existing Microsoft Agent 365 bridge.\n        from:\n          sourceNamespace: okta-auth0-obo-token-propagation-capability-mcp\n          action: example\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/okta-auth0-obo-token-propagation-capability.yaml
tags:
- Naftiko
tools:
- description: A capability that handles on-behalf-of token propagation across agent-to-agent calls, using Okta + Auth0 standards work to keep identity continuous through multi-step agent flows alongside the existing Microsoft Agent 365 bridge.
  hints:
    readOnly: true
  name: example
---
