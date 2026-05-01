---
categories: []
consumed_apis:
- elsevier
description: A Capability Composition wrapping multiple Elsevier APIs as one reusable capability — the second of her two named asks.
layout: capability
naftiko_layer: proposed
naftiko_partner: Joyce Stack
name: Elsevier Api Reusability Composition
operations: []
personas: []
provider_name: Elsevier
provider_slug: elsevier
search_terms:
- capability
- composition
- wrapping
- multiple
- elsevier
slug: api-reusability-composition
source_filename: api-reusability-composition.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Elsevier Api Reusability Composition
    description: A Capability Composition wrapping multiple Elsevier APIs as one reusable capability — the second of her two named asks.
    tags:
    - Elsevier
    created: '2026-04-30'
    modified: '2026-04-30'
  binds:
  - namespace: elsevier-env
    description: Elsevier credentials.
    keys:
      ELSEVIER_API_KEY: ELSEVIER_API_KEY
  capability:
    consumes:
    - namespace: elsevier
      type: http
      baseUri: https://api.elsevier.com
      authentication:
        type: bearer
        token: '{{ELSEVIER_API_KEY}}'
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
      namespace: api-reusability-composition-rest
      description: REST API for Elsevier Api Reusability Composition.
      resources:
      - name: example
        path: /example
        operations:
        - method: GET
          name: example-op
          call: elsevier.example-op
    - type: mcp
      address: 0.0.0.0
      port: 3010
      namespace: api-reusability-composition-mcp
      description: MCP server exposing Elsevier Api Reusability Composition for AI agents.
      tools:
      - name: example
        description: A Capability Composition wrapping multiple Elsevier APIs as one reusable capability — the second of her two named asks.
        hints:
          readOnly: true
        call: elsevier.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: api-reusability-composition-skills
      description: Agent Skill bundle for Elsevier Api Reusability Composition.
      skills:
      - name: api-reusability-composition
        description: A Capability Composition wrapping multiple Elsevier APIs as one reusable capability — the second of her two named asks.
        location: file:///opt/naftiko/skills/api-reusability-composition
        allowed-tools: example
        tools:
        - name: example
          description: A Capability Composition wrapping multiple Elsevier APIs as one reusable capability — the second of her two named asks.
          from:
            sourceNamespace: api-reusability-composition-mcp
            action: example
---

A Capability Composition wrapping multiple Elsevier APIs as one reusable capability — the second of her two named asks. She explicitly asked for API reusability — this is its canonical implementation.
