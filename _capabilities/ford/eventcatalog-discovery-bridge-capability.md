---
categories: []
consumed_apis:
- ford
description: A capability that consumes Ford's EventCatalog inventory and exposes the event + schema-registry payload as MCP tools the AI assistant can query alongside REST endpoints, so event-driven and request-response surfaces are equally discoverable.
layout: capability
naftiko_layer: service-anchored
naftiko_partner: John Musser
name: Ford Eventcatalog Discovery Bridge Capability
operations: []
personas: []
provider_name: Ford
provider_slug: ford
search_terms:
- capability
- that
- consumes
- ford
- eventcatalog
slug: eventcatalog-discovery-bridge-capability
source_filename: eventcatalog-discovery-bridge-capability.yaml
source_heading: Capability Spec
source_yaml: |
  naftiko: 1.0.0-alpha2
  info:
    title: Ford Eventcatalog Discovery Bridge Capability
    description: A capability that consumes Ford's EventCatalog inventory and exposes the event + schema-registry payload as MCP tools the AI assistant can query alongside REST endpoints, so event-driven and request-response surfaces are equally discoverable.
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
      namespace: eventcatalog-discovery-bridge-capability-rest
      description: REST API for Ford Eventcatalog Discovery Bridge Capability.
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
      namespace: eventcatalog-discovery-bridge-capability-mcp
      description: MCP server exposing Ford Eventcatalog Discovery Bridge Capability for AI agents.
      tools:
      - name: example
        description: A capability that consumes Ford's EventCatalog inventory and exposes the event + schema-registry payload as MCP tools the AI assistant can query alongside REST endpoints, so event-driven and request-response surfaces are equally discoverable.
        hints:
          readOnly: true
        call: ford.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: eventcatalog-discovery-bridge-capability-skills
      description: Agent Skill bundle for Ford Eventcatalog Discovery Bridge Capability.
      skills:
      - name: eventcatalog-discovery-bridge-capability
        description: A capability that consumes Ford's EventCatalog inventory and exposes the event + schema-registry payload as MCP tools the AI assistant can query alongside REST endpoints, so event-driven and request-response surfaces are equally discoverable.
        location: file:///opt/naftiko/skills/eventcatalog-discovery-bridge-capability
        allowed-tools: example
        tools:
        - name: example
          description: A capability that consumes Ford's EventCatalog inventory and exposes the event + schema-registry payload as MCP tools the AI assistant can query alongside REST endpoints, so event-driven and request-response surfaces are equally discoverable.
          from:
            sourceNamespace: eventcatalog-discovery-bridge-capability-mcp
            action: example
---

A capability that consumes Ford's EventCatalog inventory and exposes the event + schema-registry payload as MCP tools the AI assistant can query alongside REST endpoints, so event-driven and request-response surfaces are equally discoverable. His event-driven discovery exploration sits next to the API discovery work the existing Apigee mirror already covers; this completes the inventory surface so the AI assistant sees events on equal footing with REST.
