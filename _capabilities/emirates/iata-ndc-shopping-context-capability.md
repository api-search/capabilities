---
categories: []
consumed_apis:
- emirates
description: A capability over the IATA NDC airline-distribution surface that returns one shaped agent-context object for an Emirates customer-service AI assistant.
layout: capability
naftiko_layer: service-anchored
naftiko_partner: Sana Mazhoud
name: Emirates Iata Ndc Shopping Context Capability
operations: []
personas: []
provider_name: Emirates
provider_slug: emirates
search_terms:
- capability
- over
- iata
- airline
- distribution
slug: iata-ndc-shopping-context-capability
source_filename: iata-ndc-shopping-context-capability.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Emirates Iata Ndc Shopping Context Capability
    description: A capability over the IATA NDC airline-distribution surface that returns one shaped agent-context object for an Emirates customer-service AI assistant.
    tags:
    - Emirates
    created: '2026-04-30'
    modified: '2026-04-30'
  binds:
  - namespace: emirates-env
    description: Emirates credentials.
    keys:
      EMIRATES_API_KEY: EMIRATES_API_KEY
  capability:
    consumes:
    - namespace: emirates
      type: http
      baseUri: https://api.emirates.com
      authentication:
        type: bearer
        token: '{{EMIRATES_API_KEY}}'
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
      namespace: iata-ndc-shopping-context-capability-rest
      description: REST API for Emirates Iata Ndc Shopping Context Capability.
      resources:
      - name: example
        path: /example
        operations:
        - method: GET
          name: example-op
          call: emirates.example-op
    - type: mcp
      address: 0.0.0.0
      port: 3010
      namespace: iata-ndc-shopping-context-capability-mcp
      description: MCP server exposing Emirates Iata Ndc Shopping Context Capability for AI agents.
      tools:
      - name: example
        description: A capability over the IATA NDC airline-distribution surface that returns one shaped agent-context object for an Emirates customer-service AI assistant.
        hints:
          readOnly: true
        call: emirates.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: iata-ndc-shopping-context-capability-skills
      description: Agent Skill bundle for Emirates Iata Ndc Shopping Context Capability.
      skills:
      - name: iata-ndc-shopping-context-capability
        description: A capability over the IATA NDC airline-distribution surface that returns one shaped agent-context object for an Emirates customer-service AI assistant.
        location: file:///opt/naftiko/skills/iata-ndc-shopping-context-capability
        allowed-tools: example
        tools:
        - name: example
          description: A capability over the IATA NDC airline-distribution surface that returns one shaped agent-context object for an Emirates customer-service AI assistant.
          from:
            sourceNamespace: iata-ndc-shopping-context-capability-mcp
            action: example
---

A capability over the IATA NDC airline-distribution surface that returns one shaped agent-context object for an Emirates customer-service AI assistant. IATA NDC is the modern aviation API standard; a built artifact on the canonical airline-IT surface makes the next outreach concrete.
