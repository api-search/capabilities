---
categories: []
consumed_apis:
- bloomberg
description: 'Implements Guide-Use-Cases #6 (Rightsize a set of microservices) as the apidays talking point.'
layout: capability
naftiko_layer: proposed
naftiko_partner: Brendan Burgess
name: Bloomberg Microservice Rightsize Capability
operations: []
personas: []
provider_name: Bloomberg
provider_slug: bloomberg
search_terms:
- implements
- guide
- cases
- rightsize
- microservices
slug: microservice-rightsize-capability
source_filename: microservice-rightsize-capability.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Bloomberg Microservice Rightsize Capability
    description: 'Implements Guide-Use-Cases #6 (Rightsize a set of microservices) as the apidays talking point.'
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
      namespace: microservice-rightsize-capability-rest
      description: REST API for Bloomberg Microservice Rightsize Capability.
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
      namespace: microservice-rightsize-capability-mcp
      description: MCP server exposing Bloomberg Microservice Rightsize Capability for AI agents.
      tools:
      - name: example
        description: 'Implements Guide-Use-Cases #6 (Rightsize a set of microservices) as the apidays talking point.'
        hints:
          readOnly: true
        call: bloomberg.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: microservice-rightsize-capability-skills
      description: Agent Skill bundle for Bloomberg Microservice Rightsize Capability.
      skills:
      - name: microservice-rightsize-capability
        description: 'Implements Guide-Use-Cases #6 (Rightsize a set of microservices) as the apidays talking point.'
        location: file:///opt/naftiko/skills/microservice-rightsize-capability
        allowed-tools: example
        tools:
        - name: example
          description: 'Implements Guide-Use-Cases #6 (Rightsize a set of microservices) as the apidays talking point.'
          from:
            sourceNamespace: microservice-rightsize-capability-mcp
            action: example
---

Implements Guide-Use-Cases #6 (Rightsize a set of microservices) as the apidays talking point. A concrete use case framed for his role makes the booth conversation easy to start.
