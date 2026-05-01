---
categories: []
consumed_apis:
- emirates
description: A small capability demo wrapping a public Emirates or aviation-adjacent API — bring something concrete to the next outreach.
layout: capability
naftiko_layer: proposed
naftiko_partner: Sana Mazhoud
name: Emirates Public Aviation Capability
operations: []
personas: []
provider_name: Emirates
provider_slug: emirates
search_terms:
- small
- capability
- demo
- wrapping
- public
slug: public-aviation-capability
source_filename: public-aviation-capability.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Emirates Public Aviation Capability
    description: A small capability demo wrapping a public Emirates or aviation-adjacent API — bring something concrete to the next outreach.
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
      namespace: public-aviation-capability-rest
      description: REST API for Emirates Public Aviation Capability.
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
      namespace: public-aviation-capability-mcp
      description: MCP server exposing Emirates Public Aviation Capability for AI agents.
      tools:
      - name: example
        description: A small capability demo wrapping a public Emirates or aviation-adjacent API — bring something concrete to the next outreach.
        hints:
          readOnly: true
        call: emirates.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: public-aviation-capability-skills
      description: Agent Skill bundle for Emirates Public Aviation Capability.
      skills:
      - name: public-aviation-capability
        description: A small capability demo wrapping a public Emirates or aviation-adjacent API — bring something concrete to the next outreach.
        location: file:///opt/naftiko/skills/public-aviation-capability
        allowed-tools: example
        tools:
        - name: example
          description: A small capability demo wrapping a public Emirates or aviation-adjacent API — bring something concrete to the next outreach.
          from:
            sourceNamespace: public-aviation-capability-mcp
            action: example
---

A small capability demo wrapping a public Emirates or aviation-adjacent API — bring something concrete to the next outreach. Three cycles of date-asking with no confirmation; the relationship needs an artifact, not another invite.
