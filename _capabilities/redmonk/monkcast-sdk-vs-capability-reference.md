---
categories: []
consumed_apis:
- redmonk
description: A side-by-side reference capability that pairs a generated SDK with a Naftiko-exposed capability over the same upstream API, illustrating "Capabilities Are the New Abstraction Layer."
layout: capability
naftiko_layer: proposed
naftiko_partner: Kate Holterhoff
name: Redmonk Monkcast Sdk Vs Capability Reference
operations: []
personas: []
provider_name: Redmonk
provider_slug: redmonk
search_terms:
- side
- reference
- capability
- that
- pairs
slug: monkcast-sdk-vs-capability-reference
source_filename: monkcast-sdk-vs-capability-reference.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Redmonk Monkcast Sdk Vs Capability Reference
    description: A side-by-side reference capability that pairs a generated SDK with a Naftiko-exposed capability over the same upstream API, illustrating "Capabilities Are the New Abstraction Layer."
    tags:
    - Redmonk
    created: '2026-04-30'
    modified: '2026-04-30'
  binds:
  - namespace: redmonk-env
    description: Redmonk credentials.
    keys:
      REDMONK_API_KEY: REDMONK_API_KEY
  capability:
    consumes:
    - namespace: redmonk
      type: http
      baseUri: https://api.redmonk.com
      authentication:
        type: bearer
        token: '{{REDMONK_API_KEY}}'
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
      namespace: monkcast-sdk-vs-capability-reference-rest
      description: REST API for Redmonk Monkcast Sdk Vs Capability Reference.
      resources:
      - name: example
        path: /example
        operations:
        - method: GET
          name: example-op
          call: redmonk.example-op
    - type: mcp
      address: 0.0.0.0
      port: 3010
      namespace: monkcast-sdk-vs-capability-reference-mcp
      description: MCP server exposing Redmonk Monkcast Sdk Vs Capability Reference for AI agents.
      tools:
      - name: example
        description: A side-by-side reference capability that pairs a generated SDK with a Naftiko-exposed capability over the same upstream API, illustrating "Capabilities Are the New Abstraction Layer."
        hints:
          readOnly: true
        call: redmonk.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: monkcast-sdk-vs-capability-reference-skills
      description: Agent Skill bundle for Redmonk Monkcast Sdk Vs Capability Reference.
      skills:
      - name: monkcast-sdk-vs-capability-reference
        description: A side-by-side reference capability that pairs a generated SDK with a Naftiko-exposed capability over the same upstream API, illustrating "Capabilities Are the New Abstraction Layer."
        location: file:///opt/naftiko/skills/monkcast-sdk-vs-capability-reference
        allowed-tools: example
        tools:
        - name: example
          description: A side-by-side reference capability that pairs a generated SDK with a Naftiko-exposed capability over the same upstream API, illustrating "Capabilities Are the New Abstraction Layer."
          from:
            sourceNamespace: monkcast-sdk-vs-capability-reference-mcp
            action: example
---

A side-by-side reference capability that pairs a generated SDK with a Naftiko-exposed capability over the same upstream API, illustrating "Capabilities Are the New Abstraction Layer." Closes the loop on the campaign her MonkCast episode seeded — argument-by-artifact rather than slideware.
