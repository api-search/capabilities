---
categories: []
consumed_apis:
- ford
description: A composed capability (capability-consuming-capability) that fans out to dealer + customer APIs and returns one shaped context object for the assistant.
layout: capability
naftiko_layer: proposed
naftiko_partner: John Musser
name: Ford Dealer Customer Context Composition
operations: []
personas: []
provider_name: Ford
provider_slug: ford
search_terms:
- composed
- capability
- consuming
- that
- fans
slug: dealer-customer-context-composition
source_filename: dealer-customer-context-composition.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Ford Dealer Customer Context Composition
    description: A composed capability (capability-consuming-capability) that fans out to dealer + customer APIs and returns one shaped context object for the assistant.
    tags:
    - Ford
    created: '2026-04-30'
    modified: '2026-04-30'
  binds:
  - namespace: ford-env
    description: Ford credentials.
    keys:
      FORD_API_KEY: FORD_API_KEY
  capability:
    consumes:
    - namespace: ford
      type: http
      baseUri: https://api.ford.com
      authentication:
        type: bearer
        token: '{{FORD_API_KEY}}'
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
      namespace: dealer-customer-context-composition-rest
      description: REST API for Ford Dealer Customer Context Composition.
      resources:
      - name: example
        path: /example
        operations:
        - method: GET
          name: example-op
          call: ford.example-op
    - type: mcp
      address: 0.0.0.0
      port: 3010
      namespace: dealer-customer-context-composition-mcp
      description: MCP server exposing Ford Dealer Customer Context Composition for AI agents.
      tools:
      - name: example
        description: A composed capability (capability-consuming-capability) that fans out to dealer + customer APIs and returns one shaped context object for the assistant.
        hints:
          readOnly: true
        call: ford.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: dealer-customer-context-composition-skills
      description: Agent Skill bundle for Ford Dealer Customer Context Composition.
      skills:
      - name: dealer-customer-context-composition
        description: A composed capability (capability-consuming-capability) that fans out to dealer + customer APIs and returns one shaped context object for the assistant.
        location: file:///opt/naftiko/skills/dealer-customer-context-composition
        allowed-tools: example
        tools:
        - name: example
          description: A composed capability (capability-consuming-capability) that fans out to dealer + customer APIs and returns one shaped context object for the assistant.
          from:
            sourceNamespace: dealer-customer-context-composition-mcp
            action: example
---

A composed capability (capability-consuming-capability) that fans out to dealer + customer APIs and returns one shaped context object for the assistant. Orchestrated capabilities across automotive surfaces is exactly what the Ford proposal is.
