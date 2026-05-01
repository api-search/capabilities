---
categories: []
consumed_apis:
- ey
description: A Privatbanken / Professional Services capability that opens with the business-challenges layer, wraps a representative client-perspective workflow, exposes via MCP, and tags with governance.
layout: capability
naftiko_layer: proposed
naftiko_partner: Ulrich Trinkaus
name: EY Privatbanken Client Perspective Capability
operations: []
personas: []
provider_name: EY
provider_slug: ey
search_terms:
- privatbanken
- professional
- services
- capability
- that
slug: privatbanken-client-perspective-capability
source_filename: privatbanken-client-perspective-capability.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: EY Privatbanken Client Perspective Capability
    description: A Privatbanken / Professional Services capability that opens with the business-challenges layer, wraps a representative client-perspective workflow, exposes via MCP, and tags with governance.
    tags:
    - EY
    created: '2026-04-30'
    modified: '2026-04-30'
  binds:
  - namespace: ey-env
    description: EY credentials.
    keys:
      EY_API_KEY: EY_API_KEY
  capability:
    consumes:
    - namespace: ey
      type: http
      baseUri: https://api.ey.com
      authentication:
        type: bearer
        token: '{{EY_API_KEY}}'
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
      namespace: privatbanken-client-perspective-capability-rest
      description: REST API for EY Privatbanken Client Perspective Capability.
      resources:
      - name: example
        path: /example
        operations:
        - method: GET
          name: example-op
          call: ey.example-op
    - type: mcp
      address: 0.0.0.0
      port: 3010
      namespace: privatbanken-client-perspective-capability-mcp
      description: MCP server exposing EY Privatbanken Client Perspective Capability for AI agents.
      tools:
      - name: example
        description: A Privatbanken / Professional Services capability that opens with the business-challenges layer, wraps a representative client-perspective workflow, exposes via MCP, and tags with governance.
        hints:
          readOnly: true
        call: ey.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: privatbanken-client-perspective-capability-skills
      description: Agent Skill bundle for EY Privatbanken Client Perspective Capability.
      skills:
      - name: privatbanken-client-perspective-capability
        description: A Privatbanken / Professional Services capability that opens with the business-challenges layer, wraps a representative client-perspective workflow, exposes via MCP, and tags with governance.
        location: file:///opt/naftiko/skills/privatbanken-client-perspective-capability
        allowed-tools: example
        tools:
        - name: example
          description: A Privatbanken / Professional Services capability that opens with the business-challenges layer, wraps a representative client-perspective workflow, exposes via MCP, and tags with governance.
          from:
            sourceNamespace: privatbanken-client-perspective-capability-mcp
            action: example
---

A Privatbanken / Professional Services capability that opens with the business-challenges layer, wraps a representative client-perspective workflow, exposes via MCP, and tags with governance. His feedback was explicitly to strengthen the business-challenges layer, frame from the client perspective, lead with governance and trust — build to the feedback.
