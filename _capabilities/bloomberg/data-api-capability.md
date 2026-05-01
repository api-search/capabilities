---
categories: []
consumed_apis:
- bloomberg
description: A capability layered on top of the Bloomberg Data API showing typed outputParameters + tags-on-Consumes (data sensitivity, billing granularity) as the Bloomberg-customer-facing pattern.
layout: capability
naftiko_layer: proposed
naftiko_partner: Amit Mahale
name: Bloomberg Data Api Capability
operations: []
personas: []
provider_name: Bloomberg
provider_slug: bloomberg
search_terms:
- capability
- layered
- bloomberg
- data
- showing
slug: data-api-capability
source_filename: data-api-capability.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Bloomberg Data Api Capability
    description: A capability layered on top of the Bloomberg Data API showing typed outputParameters + tags-on-Consumes (data sensitivity, billing granularity) as the Bloomberg-customer-facing pattern.
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
      namespace: data-api-capability-rest
      description: REST API for Bloomberg Data Api Capability.
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
      namespace: data-api-capability-mcp
      description: MCP server exposing Bloomberg Data Api Capability for AI agents.
      tools:
      - name: example
        description: A capability layered on top of the Bloomberg Data API showing typed outputParameters + tags-on-Consumes (data sensitivity, billing granularity) as the Bloomberg-customer-facing pattern.
        hints:
          readOnly: true
        call: bloomberg.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: data-api-capability-skills
      description: Agent Skill bundle for Bloomberg Data Api Capability.
      skills:
      - name: data-api-capability
        description: A capability layered on top of the Bloomberg Data API showing typed outputParameters + tags-on-Consumes (data sensitivity, billing granularity) as the Bloomberg-customer-facing pattern.
        location: file:///opt/naftiko/skills/data-api-capability
        allowed-tools: example
        tools:
        - name: example
          description: A capability layered on top of the Bloomberg Data API showing typed outputParameters + tags-on-Consumes (data sensitivity, billing granularity) as the Bloomberg-customer-facing pattern.
          from:
            sourceNamespace: data-api-capability-mcp
            action: example
---

A capability layered on top of the Bloomberg Data API showing typed outputParameters + tags-on-Consumes (data sensitivity, billing granularity) as the Bloomberg-customer-facing pattern. His next-step is "capabilities layered on top of Bloomberg, and reach out to their customers" — this demos what the customer would build.
