---
categories: []
consumed_apis: []
description: A capability shaped to the EHDS cross-border patient-care + research data-sharing flow with consent + provenance tags.
layout: capability
name: Halmstad Ehds Cross Border Care Context Capability
operations:
- description: ''
  method: GET
  name: example-op
  path: /example
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- ai
- a capability shaped to the ehds cross-border patient-care + research data-sharing flow with consent + provenance tags.
- api integration
- spec-driven integration
- capabilities
- naftiko
- mcp
- example op
- example
- governance
slug: halmstad-ehds-cross-border-care-context-capability
source_filename: halmstad-ehds-cross-border-care-context-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Halmstad Ehds Cross Border Care Context Capability\n  description: A capability shaped to the EHDS cross-border patient-care + research data-sharing flow with consent + provenance tags.\n  tags:\n  - Naftiko\n  created: '2026-05-01'\n  modified: '2026-05-01'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko credentials.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: naftiko\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - name: example-op\n        method: GET\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: halmstad-ehds-cross-border-care-context-capability-rest\n    description: REST API for Halmstad Ehds Cross Border Care Context Capability.\n    resources:\n    - name: example\n      path:\
  \ /example\n      operations:\n      - method: GET\n        name: example-op\n        call: naftiko.example-op\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: halmstad-ehds-cross-border-care-context-capability-mcp\n    description: MCP server exposing Halmstad Ehds Cross Border Care Context Capability for AI agents.\n    tools:\n    - name: example\n      description: A capability shaped to the EHDS cross-border patient-care + research data-sharing flow with consent + provenance tags.\n      hints:\n        readOnly: true\n      call: naftiko.example-op\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: halmstad-ehds-cross-border-care-context-capability-skills\n    description: Agent Skill bundle for Halmstad Ehds Cross Border Care Context Capability.\n    skills:\n    - name: halmstad-ehds-cross-border-care-context-capability\n      description: A capability shaped to the EHDS cross-border patient-care + research data-sharing flow with consent\
  \ + provenance tags.\n      location: file:///opt/naftiko/skills/halmstad-ehds-cross-border-care-context-capability\n      allowed-tools: example\n      tools:\n      - name: example\n        description: A capability shaped to the EHDS cross-border patient-care + research data-sharing flow with consent + provenance tags.\n        from:\n          sourceNamespace: halmstad-ehds-cross-border-care-context-capability-mcp\n          action: example\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/halmstad-ehds-cross-border-care-context-capability.yaml
tags:
- Naftiko
tools:
- description: A capability shaped to the EHDS cross-border patient-care + research data-sharing flow with consent + provenance tags.
  hints:
    readOnly: true
  name: example
---
