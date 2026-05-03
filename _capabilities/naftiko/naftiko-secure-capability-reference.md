---
categories: []
consumed_apis: []
description: A "secure capability" reference where scanning + Naftiko's per-endpoint auth and tags-on-Exposes (data sensitivity, deprecation) co-demo on a shared capability.
layout: capability
name: Naftiko Secure Capability Reference
operations:
- description: ''
  method: GET
  name: example-op
  path: /example
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- example
- mcp
- ai
- naftiko
- api integration
- spec-driven integration
- capabilities
- example op
- governance
- a "secure capability" reference where scanning + naftiko's per-endpoint auth and tags-on-exposes (data sensitivity, deprecation) co-demo on a shared capability.
slug: naftiko-secure-capability-reference
source_filename: naftiko-secure-capability-reference.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Naftiko Secure Capability Reference\n  description: A \"secure capability\" reference where scanning + Naftiko's per-endpoint auth and tags-on-Exposes (data sensitivity, deprecation) co-demo on a shared capability.\n  tags:\n  - Naftiko\n  created: '2026-05-01'\n  modified: '2026-05-01'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko credentials.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: naftiko\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - name: example-op\n        method: GET\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: naftiko-secure-capability-reference-rest\n    description: REST API for Naftiko Secure Capability Reference.\n    resources:\n    - name: example\n      path:\
  \ /example\n      operations:\n      - method: GET\n        name: example-op\n        call: naftiko.example-op\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: naftiko-secure-capability-reference-mcp\n    description: MCP server exposing Naftiko Secure Capability Reference for AI agents.\n    tools:\n    - name: example\n      description: A \"secure capability\" reference where scanning + Naftiko's per-endpoint auth and tags-on-Exposes (data sensitivity, deprecation) co-demo on a shared capability.\n      hints:\n        readOnly: true\n      call: naftiko.example-op\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: naftiko-secure-capability-reference-skills\n    description: Agent Skill bundle for Naftiko Secure Capability Reference.\n    skills:\n    - name: naftiko-secure-capability-reference\n      description: A \"secure capability\" reference where scanning + Naftiko's per-endpoint auth and tags-on-Exposes (data sensitivity, deprecation)\
  \ co-demo on a shared capability.\n      location: file:///opt/naftiko/skills/naftiko-secure-capability-reference\n      allowed-tools: example\n      tools:\n      - name: example\n        description: A \"secure capability\" reference where scanning + Naftiko's per-endpoint auth and tags-on-Exposes (data sensitivity, deprecation) co-demo on a shared capability.\n        from:\n          sourceNamespace: naftiko-secure-capability-reference-mcp\n          action: example\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/naftiko-secure-capability-reference.yaml
tags:
- Naftiko
tools:
- description: A "secure capability" reference where scanning + Naftiko's per-endpoint auth and tags-on-Exposes (data sensitivity, deprecation) co-demo on a shared capability.
  hints:
    readOnly: true
  name: example
---
