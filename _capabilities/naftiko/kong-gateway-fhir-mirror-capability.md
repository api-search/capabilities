---
categories: []
consumed_apis: []
description: A capability over a public FHIR/CMS Interoperability Final Rule endpoint, mirrored behind their Kong gateway with PII detection + HTTPS gates.
layout: capability
name: Kong Gateway Fhir Mirror Capability
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
- a capability over a public fhir/cms interoperability final rule endpoint, mirrored behind their kong gateway with pii detection + https gates.
- api integration
- spec-driven integration
- capabilities
- naftiko
- mcp
- example op
- example
- governance
slug: kong-gateway-fhir-mirror-capability
source_filename: kong-gateway-fhir-mirror-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Kong Gateway Fhir Mirror Capability\n  description: A capability over a public FHIR/CMS Interoperability Final Rule endpoint, mirrored behind their Kong gateway with PII detection + HTTPS gates.\n  tags:\n  - Naftiko\n  created: '2026-05-01'\n  modified: '2026-05-01'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko credentials.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: naftiko\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - name: example-op\n        method: GET\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: kong-gateway-fhir-mirror-capability-rest\n    description: REST API for Kong Gateway Fhir Mirror Capability.\n    resources:\n    - name: example\n      path: /example\n     \
  \ operations:\n      - method: GET\n        name: example-op\n        call: naftiko.example-op\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: kong-gateway-fhir-mirror-capability-mcp\n    description: MCP server exposing Kong Gateway Fhir Mirror Capability for AI agents.\n    tools:\n    - name: example\n      description: A capability over a public FHIR/CMS Interoperability Final Rule endpoint, mirrored behind their Kong gateway with PII detection + HTTPS gates.\n      hints:\n        readOnly: true\n      call: naftiko.example-op\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: kong-gateway-fhir-mirror-capability-skills\n    description: Agent Skill bundle for Kong Gateway Fhir Mirror Capability.\n    skills:\n    - name: kong-gateway-fhir-mirror-capability\n      description: A capability over a public FHIR/CMS Interoperability Final Rule endpoint, mirrored behind their Kong gateway with PII detection + HTTPS gates.\n      location: file:///opt/naftiko/skills/kong-gateway-fhir-mirror-capability\n\
  \      allowed-tools: example\n      tools:\n      - name: example\n        description: A capability over a public FHIR/CMS Interoperability Final Rule endpoint, mirrored behind their Kong gateway with PII detection + HTTPS gates.\n        from:\n          sourceNamespace: kong-gateway-fhir-mirror-capability-mcp\n          action: example\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/kong-gateway-fhir-mirror-capability.yaml
tags:
- Naftiko
tools:
- description: A capability over a public FHIR/CMS Interoperability Final Rule endpoint, mirrored behind their Kong gateway with PII detection + HTTPS gates.
  hints:
    readOnly: true
  name: example
---
