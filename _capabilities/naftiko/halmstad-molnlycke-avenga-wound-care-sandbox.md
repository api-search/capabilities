---
categories: []
consumed_apis: []
description: A self-contained runnable sandbox that mocks a Mölnlycke wound-care device data source and exposes openEHR + FHIR via the Avenga-introduction-ready capability.
layout: capability
name: Halmstad Molnlycke Avenga Wound Care Sandbox
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
- a self-contained runnable sandbox that mocks a mölnlycke wound-care device data source and exposes openehr + fhir via the avenga-introduction-ready capability.
- api integration
- spec-driven integration
- capabilities
- naftiko
- mcp
- example op
- example
- governance
slug: halmstad-molnlycke-avenga-wound-care-sandbox
source_filename: halmstad-molnlycke-avenga-wound-care-sandbox.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Halmstad Molnlycke Avenga Wound Care Sandbox\n  description: A self-contained runnable sandbox that mocks a Mölnlycke wound-care device data source and exposes openEHR + FHIR via the Avenga-introduction-ready capability.\n  tags:\n  - Naftiko\n  created: '2026-05-01'\n  modified: '2026-05-01'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko credentials.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: naftiko\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - name: example-op\n        method: GET\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: halmstad-molnlycke-avenga-wound-care-sandbox-rest\n    description: REST API for Halmstad Molnlycke Avenga Wound Care Sandbox.\n    resources:\n    -\
  \ name: example\n      path: /example\n      operations:\n      - method: GET\n        name: example-op\n        call: naftiko.example-op\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: halmstad-molnlycke-avenga-wound-care-sandbox-mcp\n    description: MCP server exposing Halmstad Molnlycke Avenga Wound Care Sandbox for AI agents.\n    tools:\n    - name: example\n      description: A self-contained runnable sandbox that mocks a Mölnlycke wound-care device data source and exposes openEHR + FHIR via the Avenga-introduction-ready capability.\n      hints:\n        readOnly: true\n      call: naftiko.example-op\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: halmstad-molnlycke-avenga-wound-care-sandbox-skills\n    description: Agent Skill bundle for Halmstad Molnlycke Avenga Wound Care Sandbox.\n    skills:\n    - name: halmstad-molnlycke-avenga-wound-care-sandbox\n      description: A self-contained runnable sandbox that mocks a Mölnlycke wound-care\
  \ device data source and exposes openEHR + FHIR via the Avenga-introduction-ready capability.\n      location: file:///opt/naftiko/skills/halmstad-molnlycke-avenga-wound-care-sandbox\n      allowed-tools: example\n      tools:\n      - name: example\n        description: A self-contained runnable sandbox that mocks a Mölnlycke wound-care device data source and exposes openEHR + FHIR via the Avenga-introduction-ready capability.\n        from:\n          sourceNamespace: halmstad-molnlycke-avenga-wound-care-sandbox-mcp\n          action: example\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/halmstad-molnlycke-avenga-wound-care-sandbox.yaml
tags:
- Naftiko
tools:
- description: A self-contained runnable sandbox that mocks a Mölnlycke wound-care device data source and exposes openEHR + FHIR via the Avenga-introduction-ready capability.
  hints:
    readOnly: true
  name: example
---
