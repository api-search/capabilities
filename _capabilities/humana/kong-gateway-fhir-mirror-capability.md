---
categories: []
consumed_apis:
- humana
description: A capability over a public Humana FHIR/CMS Interoperability Final Rule endpoint, mirrored behind their Kong gateway with PII detection + HTTPS gates.
layout: capability
naftiko_layer: service-anchored
naftiko_partner: Humana
name: Humana Kong Gateway Fhir Mirror Capability
operations: []
personas: []
provider_name: Humana
provider_slug: humana
search_terms:
- capability
- over
- public
- humana
- fhir
slug: kong-gateway-fhir-mirror-capability
source_filename: kong-gateway-fhir-mirror-capability.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Humana Kong Gateway Fhir Mirror Capability
    description: A capability over a public Humana FHIR/CMS Interoperability Final Rule endpoint, mirrored behind their Kong gateway with PII detection + HTTPS gates.
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
      namespace: kong-gateway-fhir-mirror-capability-rest
      description: REST API for Humana Kong Gateway Fhir Mirror Capability.
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
      namespace: kong-gateway-fhir-mirror-capability-mcp
      description: MCP server exposing Humana Kong Gateway Fhir Mirror Capability for AI agents.
      tools:
      - name: example
        description: A capability over a public Humana FHIR/CMS Interoperability Final Rule endpoint, mirrored behind their Kong gateway with PII detection + HTTPS gates.
        hints:
          readOnly: true
        call: humana.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: kong-gateway-fhir-mirror-capability-skills
      description: Agent Skill bundle for Humana Kong Gateway Fhir Mirror Capability.
      skills:
      - name: kong-gateway-fhir-mirror-capability
        description: A capability over a public Humana FHIR/CMS Interoperability Final Rule endpoint, mirrored behind their Kong gateway with PII detection + HTTPS gates.
        location: file:///opt/naftiko/skills/kong-gateway-fhir-mirror-capability
        allowed-tools: example
        tools:
        - name: example
          description: A capability over a public Humana FHIR/CMS Interoperability Final Rule endpoint, mirrored behind their Kong gateway with PII detection + HTTPS gates.
          from:
            sourceNamespace: kong-gateway-fhir-mirror-capability-mcp
            action: example
---

A capability over a public Humana FHIR/CMS Interoperability Final Rule endpoint, mirrored behind their Kong gateway with PII detection + HTTPS gates. Healthcare payers are mandated to expose FHIR; routing through Kong matches their actual gateway and gives them a credible compliance posture.
