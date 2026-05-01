---
categories: []
consumed_apis:
- abn-amro
description: 'A reference capability tying open banking to Guide-Use-Cases #9 (Capability-first API reusability) as the thought-leadership angle.'
layout: capability
naftiko_layer: proposed
naftiko_partner: ABN AMRO Bank
name: ABN AMRO Bank Api Reusability Open Banking Reference
operations: []
personas: []
provider_name: ABN AMRO Bank
provider_slug: abn-amro
search_terms:
- reference
- capability
- tying
- open
- banking
slug: api-reusability-open-banking-reference
source_filename: api-reusability-open-banking-reference.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: ABN AMRO Bank Api Reusability Open Banking Reference
    description: 'A reference capability tying open banking to Guide-Use-Cases #9 (Capability-first API reusability) as the thought-leadership angle.'
    tags:
    - ABN AMRO Bank
    created: '2026-04-30'
    modified: '2026-04-30'
  binds:
  - namespace: abn-amro-env
    description: ABN AMRO Bank credentials.
    keys:
      ABN_AMRO_API_KEY: ABN_AMRO_API_KEY
  capability:
    consumes:
    - namespace: abn-amro
      type: http
      baseUri: https://api.abn-amro.com
      authentication:
        type: bearer
        token: '{{ABN_AMRO_API_KEY}}'
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
      namespace: api-reusability-open-banking-reference-rest
      description: REST API for ABN AMRO Bank Api Reusability Open Banking Reference.
      resources:
      - name: example
        path: /example
        operations:
        - method: GET
          name: example-op
          call: abn-amro.example-op
    - type: mcp
      address: 0.0.0.0
      port: 3010
      namespace: api-reusability-open-banking-reference-mcp
      description: MCP server exposing ABN AMRO Bank Api Reusability Open Banking Reference for AI agents.
      tools:
      - name: example
        description: 'A reference capability tying open banking to Guide-Use-Cases #9 (Capability-first API reusability) as the thought-leadership angle.'
        hints:
          readOnly: true
        call: abn-amro.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: api-reusability-open-banking-reference-skills
      description: Agent Skill bundle for ABN AMRO Bank Api Reusability Open Banking Reference.
      skills:
      - name: api-reusability-open-banking-reference
        description: 'A reference capability tying open banking to Guide-Use-Cases #9 (Capability-first API reusability) as the thought-leadership angle.'
        location: file:///opt/naftiko/skills/api-reusability-open-banking-reference
        allowed-tools: example
        tools:
        - name: example
          description: 'A reference capability tying open banking to Guide-Use-Cases #9 (Capability-first API reusability) as the thought-leadership angle.'
          from:
            sourceNamespace: api-reusability-open-banking-reference-mcp
            action: example
---

A reference capability tying open banking to Guide-Use-Cases #9 (Capability-first API reusability) as the thought-leadership angle. PSD2 / open banking IS API reusability under regulation.
