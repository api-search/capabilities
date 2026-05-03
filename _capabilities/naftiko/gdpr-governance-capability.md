---
categories: []
consumed_apis: []
description: A capability with Compliance Frameworks (GDPR) + governance + tags-on-Exposes (network topology, data sensitivity) — the Dutch-banking pitch.
layout: capability
name: Gdpr Governance Capability
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
- a capability with compliance frameworks (gdpr) + governance + tags-on-exposes (network topology, data sensitivity) — the dutch-banking pitch.
- example op
- governance
slug: gdpr-governance-capability
source_filename: gdpr-governance-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Gdpr Governance Capability\n  description: A capability with Compliance Frameworks (GDPR) + governance + tags-on-Exposes (network topology, data sensitivity) — the Dutch-banking pitch.\n  tags:\n  - Naftiko\n  created: '2026-05-01'\n  modified: '2026-05-01'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko credentials.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: naftiko\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - name: example-op\n        method: GET\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: gdpr-governance-capability-rest\n    description: REST API for Gdpr Governance Capability.\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - method:\
  \ GET\n        name: example-op\n        call: naftiko.example-op\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: gdpr-governance-capability-mcp\n    description: MCP server exposing Gdpr Governance Capability for AI agents.\n    tools:\n    - name: example\n      description: A capability with Compliance Frameworks (GDPR) + governance + tags-on-Exposes (network topology, data sensitivity) — the Dutch-banking pitch.\n      hints:\n        readOnly: true\n      call: naftiko.example-op\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: gdpr-governance-capability-skills\n    description: Agent Skill bundle for Gdpr Governance Capability.\n    skills:\n    - name: gdpr-governance-capability\n      description: A capability with Compliance Frameworks (GDPR) + governance + tags-on-Exposes (network topology, data sensitivity) — the Dutch-banking pitch.\n      location: file:///opt/naftiko/skills/gdpr-governance-capability\n      allowed-tools: example\n\
  \      tools:\n      - name: example\n        description: A capability with Compliance Frameworks (GDPR) + governance + tags-on-Exposes (network topology, data sensitivity) — the Dutch-banking pitch.\n        from:\n          sourceNamespace: gdpr-governance-capability-mcp\n          action: example\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/gdpr-governance-capability.yaml
tags:
- Naftiko
tools:
- description: A capability with Compliance Frameworks (GDPR) + governance + tags-on-Exposes (network topology, data sensitivity) — the Dutch-banking pitch.
  hints:
    readOnly: true
  name: example
---
