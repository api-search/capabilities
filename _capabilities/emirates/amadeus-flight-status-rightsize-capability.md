---
categories: []
consumed_apis:
- emirates
description: 'A capability over Amadeus / FlightAware-style flight-status APIs implementing Use Case #2 (Rightsize AI context) for an airline-IT API-sprawl scenario.'
layout: capability
naftiko_layer: service-anchored
naftiko_partner: Sana Mazhoud
name: Emirates Amadeus Flight Status Rightsize Capability
operations: []
personas: []
provider_name: Emirates
provider_slug: emirates
search_terms:
- capability
- over
- amadeus
- flightaware
- style
slug: amadeus-flight-status-rightsize-capability
source_filename: amadeus-flight-status-rightsize-capability.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Emirates Amadeus Flight Status Rightsize Capability
    description: 'A capability over Amadeus / FlightAware-style flight-status APIs implementing Use Case #2 (Rightsize AI context) for an airline-IT API-sprawl scenario.'
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
      namespace: amadeus-flight-status-rightsize-capability-rest
      description: REST API for Emirates Amadeus Flight Status Rightsize Capability.
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
      namespace: amadeus-flight-status-rightsize-capability-mcp
      description: MCP server exposing Emirates Amadeus Flight Status Rightsize Capability for AI agents.
      tools:
      - name: example
        description: 'A capability over Amadeus / FlightAware-style flight-status APIs implementing Use Case #2 (Rightsize AI context) for an airline-IT API-sprawl scenario.'
        hints:
          readOnly: true
        call: emirates.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: amadeus-flight-status-rightsize-capability-skills
      description: Agent Skill bundle for Emirates Amadeus Flight Status Rightsize Capability.
      skills:
      - name: amadeus-flight-status-rightsize-capability
        description: 'A capability over Amadeus / FlightAware-style flight-status APIs implementing Use Case #2 (Rightsize AI context) for an airline-IT API-sprawl scenario.'
        location: file:///opt/naftiko/skills/amadeus-flight-status-rightsize-capability
        allowed-tools: example
        tools:
        - name: example
          description: 'A capability over Amadeus / FlightAware-style flight-status APIs implementing Use Case #2 (Rightsize AI context) for an airline-IT API-sprawl scenario.'
          from:
            sourceNamespace: amadeus-flight-status-rightsize-capability-mcp
            action: example
---

A capability over Amadeus / FlightAware-style flight-status APIs implementing Use Case #2 (Rightsize AI context) for an airline-IT API-sprawl scenario. Airline IT is canonically API-sprawl heavy; rightsizing public flight-status APIs is the use case that addresses the felt pain.
