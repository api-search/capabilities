---
categories: []
consumed_apis:
- bloomberg
description: A capability over the Bloomberg BLPAPI / Data License surface with billing-granularity + sensitivity tags on Consumes — the customer-facing shape for an external Bloomberg-customer agent build.
layout: capability
naftiko_layer: service-anchored
naftiko_partner: Amit Mahale
name: Bloomberg Blpapi Data License Billing Tagged Capability
operations: []
personas: []
provider_name: Bloomberg
provider_slug: bloomberg
search_terms:
- capability
- over
- bloomberg
- blpapi
- data
slug: blpapi-data-license-billing-tagged-capability
source_filename: blpapi-data-license-billing-tagged-capability.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Bloomberg Blpapi Data License Billing Tagged Capability
    description: A capability over the Bloomberg BLPAPI / Data License surface with billing-granularity + sensitivity tags on Consumes — the customer-facing shape for an external Bloomberg-customer agent build.
    tags:
    - Bloomberg
    created: '2026-04-30'
    modified: '2026-04-30'
  binds:
  - namespace: bloomberg-env
    description: Bloomberg credentials.
    keys:
      BLOOMBERG_API_KEY: BLOOMBERG_API_KEY
  capability:
    consumes:
    - namespace: bloomberg
      type: http
      baseUri: https://api.bloomberg.com
      authentication:
        type: bearer
        token: '{{BLOOMBERG_API_KEY}}'
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
      namespace: blpapi-data-license-billing-tagged-capability-rest
      description: REST API for Bloomberg Blpapi Data License Billing Tagged Capability.
      resources:
      - name: example
        path: /example
        operations:
        - method: GET
          name: example-op
          call: bloomberg.example-op
    - type: mcp
      address: 0.0.0.0
      port: 3010
      namespace: blpapi-data-license-billing-tagged-capability-mcp
      description: MCP server exposing Bloomberg Blpapi Data License Billing Tagged Capability for AI agents.
      tools:
      - name: example
        description: A capability over the Bloomberg BLPAPI / Data License surface with billing-granularity + sensitivity tags on Consumes — the customer-facing shape for an external Bloomberg-customer agent build.
        hints:
          readOnly: true
        call: bloomberg.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: blpapi-data-license-billing-tagged-capability-skills
      description: Agent Skill bundle for Bloomberg Blpapi Data License Billing Tagged Capability.
      skills:
      - name: blpapi-data-license-billing-tagged-capability
        description: A capability over the Bloomberg BLPAPI / Data License surface with billing-granularity + sensitivity tags on Consumes — the customer-facing shape for an external Bloomberg-customer agent build.
        location: file:///opt/naftiko/skills/blpapi-data-license-billing-tagged-capability
        allowed-tools: example
        tools:
        - name: example
          description: A capability over the Bloomberg BLPAPI / Data License surface with billing-granularity + sensitivity tags on Consumes — the customer-facing shape for an external Bloomberg-customer agent build.
          from:
            sourceNamespace: blpapi-data-license-billing-tagged-capability-mcp
            action: example
---

A capability over the Bloomberg BLPAPI / Data License surface with billing-granularity + sensitivity tags on Consumes — the customer-facing shape for an external Bloomberg-customer agent build. His next-step is "capabilities layered on Bloomberg, then reach customers" — billing-tagged is the most Bloomberg-customer-real shape possible.
