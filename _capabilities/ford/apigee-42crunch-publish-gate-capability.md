---
categories: []
consumed_apis:
- ford
description: A capability that wires the Apigee + 42 Crunch publish pipeline into the Naftiko capability publish flow, so capability YAMLs cannot reach production without passing both gates and emit a per-publish audit record back to Ford's API governance layer.
layout: capability
naftiko_layer: service-anchored
naftiko_partner: John Musser
name: Ford Apigee 42crunch Publish Gate Capability
operations: []
personas: []
provider_name: Ford
provider_slug: ford
search_terms:
- capability
- that
- wires
- apigee
- crunch
slug: apigee-42crunch-publish-gate-capability
source_filename: apigee-42crunch-publish-gate-capability.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Ford Apigee 42crunch Publish Gate Capability
    description: A capability that wires the Apigee + 42 Crunch publish pipeline into the Naftiko capability publish flow, so capability YAMLs cannot reach production without passing both gates and emit a per-publish audit record back to Ford's API governance layer.
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
      namespace: apigee-42crunch-publish-gate-capability-rest
      description: REST API for Ford Apigee 42crunch Publish Gate Capability.
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
      namespace: apigee-42crunch-publish-gate-capability-mcp
      description: MCP server exposing Ford Apigee 42crunch Publish Gate Capability for AI agents.
      tools:
      - name: example
        description: A capability that wires the Apigee + 42 Crunch publish pipeline into the Naftiko capability publish flow, so capability YAMLs cannot reach production without passing both gates and emit a per-publish audit record back to Ford's API governance layer.
        hints:
          readOnly: true
        call: ford.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: apigee-42crunch-publish-gate-capability-skills
      description: Agent Skill bundle for Ford Apigee 42crunch Publish Gate Capability.
      skills:
      - name: apigee-42crunch-publish-gate-capability
        description: A capability that wires the Apigee + 42 Crunch publish pipeline into the Naftiko capability publish flow, so capability YAMLs cannot reach production without passing both gates and emit a per-publish audit record back to Ford's API governance layer.
        location: file:///opt/naftiko/skills/apigee-42crunch-publish-gate-capability
        allowed-tools: example
        tools:
        - name: example
          description: A capability that wires the Apigee + 42 Crunch publish pipeline into the Naftiko capability publish flow, so capability YAMLs cannot reach production without passing both gates and emit a per-publish audit record back to Ford's API governance layer.
          from:
            sourceNamespace: apigee-42crunch-publish-gate-capability-mcp
            action: example
---

A capability that wires the Apigee + 42 Crunch publish pipeline into the Naftiko capability publish flow, so capability YAMLs cannot reach production without passing both gates and emit a per-publish audit record back to Ford's API governance layer. He named the publish pipeline as the immovable boundary; modeling it inside a capability removes the "how does this fit our existing governance stack?" objection that's killed adoption elsewhere.
