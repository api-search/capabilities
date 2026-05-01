---
categories: []
consumed_apis:
- halmstad-university
description: A capability that consumes legacy EHR records (HL7v2 / X12) and exposes an openEHR-conformant + FHIR-conformant output, with PII detection + HTTPS gates wired in.
layout: capability
naftiko_layer: service-anchored
naftiko_partner: Farzaneh Etminani
name: Halmstad University Halmstad Openehr Fhir Translation Capability
operations: []
personas: []
provider_name: Halmstad University
provider_slug: halmstad-university
search_terms:
- capability
- that
- consumes
- legacy
- records
slug: halmstad-openehr-fhir-translation-capability
source_filename: halmstad-openehr-fhir-translation-capability.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Halmstad University Halmstad Openehr Fhir Translation Capability
    description: A capability that consumes legacy EHR records (HL7v2 / X12) and exposes an openEHR-conformant + FHIR-conformant output, with PII detection + HTTPS gates wired in.
    tags:
    - Halmstad University
    created: '2026-04-30'
    modified: '2026-04-30'
  binds:
  - namespace: halmstad-university-env
    description: Halmstad University credentials.
    keys:
      HALMSTAD_UNIVERSITY_API_KEY: HALMSTAD_UNIVERSITY_API_KEY
  capability:
    consumes:
    - namespace: halmstad-university
      type: http
      baseUri: https://api.halmstad-university.com
      authentication:
        type: bearer
        token: '{{HALMSTAD_UNIVERSITY_API_KEY}}'
      resources:
      - name: example
        path: /example
        operations:
        - name: example-op
          method: GET
    exposes:
    - type: rest
      address: 0.0.0.0
      port: 8080
      namespace: halmstad-openehr-fhir-translation-capability-rest
      description: REST API for Halmstad University Halmstad Openehr Fhir Translation Capability.
      resources:
      - name: example
        path: /example
        operations:
        - method: GET
          name: example-op
          call: halmstad-university.example-op
    - type: mcp
      address: 0.0.0.0
      port: 3010
      namespace: halmstad-openehr-fhir-translation-capability-mcp
      description: MCP server exposing Halmstad University Halmstad Openehr Fhir Translation Capability for AI agents.
      tools:
      - name: example
        description: A capability that consumes legacy EHR records (HL7v2 / X12) and exposes an openEHR-conformant + FHIR-conformant output, with PII detection + HTTPS gates wired in.
        hints:
          readOnly: true
        call: halmstad-university.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: halmstad-openehr-fhir-translation-capability-skills
      description: Agent Skill bundle for Halmstad University Halmstad Openehr Fhir Translation Capability.
      skills:
      - name: halmstad-openehr-fhir-translation-capability
        description: A capability that consumes legacy EHR records (HL7v2 / X12) and exposes an openEHR-conformant + FHIR-conformant output, with PII detection + HTTPS gates wired in.
        location: file:///opt/naftiko/skills/halmstad-openehr-fhir-translation-capability
        allowed-tools: example
        tools:
        - name: example
          description: A capability that consumes legacy EHR records (HL7v2 / X12) and exposes an openEHR-conformant + FHIR-conformant output, with PII detection + HTTPS gates wired in.
          from:
            sourceNamespace: halmstad-openehr-fhir-translation-capability-mcp
            action: example
---

A capability that consumes legacy EHR records (HL7v2 / X12) and exposes an openEHR-conformant + FHIR-conformant output, with PII detection + HTTPS gates wired in. Her 2026-04-27 conversation explicitly named this capability shape as the chronic-wound-care project's unmet need.
