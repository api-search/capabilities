---
categories: []
consumed_apis:
- emirates
description: 'A capability implementing Use Case #2 (Rightsize AI context) against airline IT API sprawl — a curated agent surface from many internal APIs.'
layout: capability
naftiko_layer: proposed
naftiko_partner: Sana Mazhoud
name: Emirates Rightsize Airline Context Capability
operations: []
personas: []
provider_name: Emirates
provider_slug: emirates
search_terms:
- capability
- implementing
- case
- rightsize
- context
slug: rightsize-airline-context-capability
source_filename: rightsize-airline-context-capability.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Emirates Rightsize Airline Context Capability
    description: 'A capability implementing Use Case #2 (Rightsize AI context) against airline IT API sprawl — a curated agent surface from many internal APIs.'
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
      namespace: rightsize-airline-context-capability-rest
      description: REST API for Emirates Rightsize Airline Context Capability.
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
      namespace: rightsize-airline-context-capability-mcp
      description: MCP server exposing Emirates Rightsize Airline Context Capability for AI agents.
      tools:
      - name: example
        description: 'A capability implementing Use Case #2 (Rightsize AI context) against airline IT API sprawl — a curated agent surface from many internal APIs.'
        hints:
          readOnly: true
        call: emirates.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: rightsize-airline-context-capability-skills
      description: Agent Skill bundle for Emirates Rightsize Airline Context Capability.
      skills:
      - name: rightsize-airline-context-capability
        description: 'A capability implementing Use Case #2 (Rightsize AI context) against airline IT API sprawl — a curated agent surface from many internal APIs.'
        location: file:///opt/naftiko/skills/rightsize-airline-context-capability
        allowed-tools: example
        tools:
        - name: example
          description: 'A capability implementing Use Case #2 (Rightsize AI context) against airline IT API sprawl — a curated agent surface from many internal APIs.'
          from:
            sourceNamespace: rightsize-airline-context-capability-mcp
            action: example
---

A capability implementing Use Case #2 (Rightsize AI context) against airline IT API sprawl — a curated agent surface from many internal APIs. Airline IT is canonically API-sprawl heavy; this is the use case that addresses the felt pain.
