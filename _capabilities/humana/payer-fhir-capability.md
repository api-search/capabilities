---
categories: []
consumed_apis:
- humana
description: A healthcare-payer capability (HIPAA-shaped, FHIR-adjacent) wrapping a representative Humana-public API, with PII surface detection + HTTPS enforcement governance.
layout: capability
naftiko_layer: proposed
naftiko_partner: Humana
name: Humana Payer Fhir Capability
operations: []
personas: []
provider_name: Humana
provider_slug: humana
search_terms:
- healthcare
- payer
- capability
- hipaa
- shaped
slug: payer-fhir-capability
source_filename: payer-fhir-capability.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Humana Payer Fhir Capability
    description: A healthcare-payer capability (HIPAA-shaped, FHIR-adjacent) wrapping a representative Humana-public API, with PII surface detection + HTTPS enforcement governance.
    tags:
    - Humana
    created: '2026-04-30'
    modified: '2026-04-30'
  binds:
  - namespace: humana-env
    description: Humana credentials.
    keys:
      HUMANA_API_KEY: HUMANA_API_KEY
  capability:
    consumes:
    - namespace: humana
      type: http
      baseUri: https://api.humana.com
      authentication:
        type: bearer
        token: '{{HUMANA_API_KEY}}'
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
      namespace: payer-fhir-capability-rest
      description: REST API for Humana Payer Fhir Capability.
      resources:
      - name: example
        path: /example
        operations:
        - method: GET
          name: example-op
          call: humana.example-op
    - type: mcp
      address: 0.0.0.0
      port: 3010
      namespace: payer-fhir-capability-mcp
      description: MCP server exposing Humana Payer Fhir Capability for AI agents.
      tools:
      - name: example
        description: A healthcare-payer capability (HIPAA-shaped, FHIR-adjacent) wrapping a representative Humana-public API, with PII surface detection + HTTPS enforcement governance.
        hints:
          readOnly: true
        call: humana.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: payer-fhir-capability-skills
      description: Agent Skill bundle for Humana Payer Fhir Capability.
      skills:
      - name: payer-fhir-capability
        description: A healthcare-payer capability (HIPAA-shaped, FHIR-adjacent) wrapping a representative Humana-public API, with PII surface detection + HTTPS enforcement governance.
        location: file:///opt/naftiko/skills/payer-fhir-capability
        allowed-tools: example
        tools:
        - name: example
          description: A healthcare-payer capability (HIPAA-shaped, FHIR-adjacent) wrapping a representative Humana-public API, with PII surface detection + HTTPS enforcement governance.
          from:
            sourceNamespace: payer-fhir-capability-mcp
            action: example
---

A healthcare-payer capability (HIPAA-shaped, FHIR-adjacent) wrapping a representative Humana-public API, with PII surface detection + HTTPS enforcement governance. Pipeline conversion needs a concrete artifact; healthcare payers don't engage on tooling without compliance posture.
