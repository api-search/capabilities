---
categories: []
consumed_apis: []
description: A capability that consumes legacy EHR records (HL7v2 / X12) and exposes an openEHR-conformant + FHIR-conformant output, with PII detection + HTTPS gates wired in.
layout: capability
name: Halmstad Openehr Fhir Translation Capability
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
- a capability that consumes legacy ehr records (hl7v2 / x12) and exposes an openehr-conformant + fhir-conformant output, with pii detection + https gates wired in.
- naftiko
- governance
- mcp
- capabilities
- ai
slug: halmstad-openehr-fhir-translation-capability
source_filename: halmstad-openehr-fhir-translation-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Halmstad Openehr Fhir Translation Capability\n  description: A capability that consumes legacy EHR records (HL7v2 / X12) and exposes an openEHR-conformant + FHIR-conformant output, with PII detection + HTTPS gates wired in.\n  tags:\n  - Naftiko\n  created: '2026-05-01'\n  modified: '2026-05-01'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko credentials.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: naftiko\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - name: example-op\n        method: GET\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: halmstad-openehr-fhir-translation-capability-rest\n    description: REST API for Halmstad Openehr Fhir Translation Capability.\n    resources:\n \
  \   - name: example\n      path: /example\n      operations:\n      - method: GET\n        name: example-op\n        call: naftiko.example-op\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: halmstad-openehr-fhir-translation-capability-mcp\n    description: MCP server exposing Halmstad Openehr Fhir Translation Capability for AI agents.\n    tools:\n    - name: example\n      description: A capability that consumes legacy EHR records (HL7v2 / X12) and exposes an openEHR-conformant + FHIR-conformant output, with PII detection + HTTPS gates wired in.\n      hints:\n        readOnly: true\n      call: naftiko.example-op\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: halmstad-openehr-fhir-translation-capability-skills\n    description: Agent Skill bundle for Halmstad Openehr Fhir Translation Capability.\n    skills:\n    - name: halmstad-openehr-fhir-translation-capability\n      description: A capability that consumes legacy EHR records (HL7v2 /\
  \ X12) and exposes an openEHR-conformant + FHIR-conformant output, with PII detection + HTTPS gates wired in.\n      location: file:///opt/naftiko/skills/halmstad-openehr-fhir-translation-capability\n      allowed-tools: example\n      tools:\n      - name: example\n        description: A capability that consumes legacy EHR records (HL7v2 / X12) and exposes an openEHR-conformant + FHIR-conformant output, with PII detection + HTTPS gates wired in.\n        from:\n          sourceNamespace: halmstad-openehr-fhir-translation-capability-mcp\n          action: example\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/halmstad-openehr-fhir-translation-capability.yaml
tags:
- Naftiko
tools:
- description: A capability that consumes legacy EHR records (HL7v2 / X12) and exposes an openEHR-conformant + FHIR-conformant output, with PII detection + HTTPS gates wired in.
  hints:
    readOnly: true
  name: example
---
