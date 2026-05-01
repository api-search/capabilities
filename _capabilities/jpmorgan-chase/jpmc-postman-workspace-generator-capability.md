---
categories: []
consumed_apis:
- jpmorgan-chase
description: A capability that takes one or more capability specs and dynamically generates a Postman Workspace + a Bruno workspace.
layout: capability
naftiko_layer: service-anchored
naftiko_partner: Mark McAllister
name: JPMorgan Chase Jpmc Postman Workspace Generator Capability
operations: []
personas: []
provider_name: JPMorgan Chase
provider_slug: jpmorgan-chase
search_terms:
- capability
- that
- takes
- more
- specs
slug: jpmc-postman-workspace-generator-capability
source_filename: jpmc-postman-workspace-generator-capability.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: JPMorgan Chase Jpmc Postman Workspace Generator Capability
    description: A capability that takes one or more capability specs and dynamically generates a Postman Workspace + a Bruno workspace.
    tags:
    - JPMorgan Chase
    created: '2026-04-30'
    modified: '2026-04-30'
  binds:
  - namespace: jpmorgan-chase-env
    description: JPMorgan Chase credentials.
    keys:
      JPMORGAN_CHASE_API_KEY: JPMORGAN_CHASE_API_KEY
  capability:
    consumes:
    - namespace: jpmorgan-chase
      type: http
      baseUri: https://api.jpmorgan-chase.com
      authentication:
        type: bearer
        token: '{{JPMORGAN_CHASE_API_KEY}}'
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
      namespace: jpmc-postman-workspace-generator-capability-rest
      description: REST API for JPMorgan Chase Jpmc Postman Workspace Generator Capability.
      resources:
      - name: example
        path: /example
        operations:
        - method: GET
          name: example-op
          call: jpmorgan-chase.example-op
    - type: mcp
      address: 0.0.0.0
      port: 3010
      namespace: jpmc-postman-workspace-generator-capability-mcp
      description: MCP server exposing JPMorgan Chase Jpmc Postman Workspace Generator Capability for AI agents.
      tools:
      - name: example
        description: A capability that takes one or more capability specs and dynamically generates a Postman Workspace + a Bruno workspace.
        hints:
          readOnly: true
        call: jpmorgan-chase.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: jpmc-postman-workspace-generator-capability-skills
      description: Agent Skill bundle for JPMorgan Chase Jpmc Postman Workspace Generator Capability.
      skills:
      - name: jpmc-postman-workspace-generator-capability
        description: A capability that takes one or more capability specs and dynamically generates a Postman Workspace + a Bruno workspace.
        location: file:///opt/naftiko/skills/jpmc-postman-workspace-generator-capability
        allowed-tools: example
        tools:
        - name: example
          description: A capability that takes one or more capability specs and dynamically generates a Postman Workspace + a Bruno workspace.
          from:
            sourceNamespace: jpmc-postman-workspace-generator-capability-mcp
            action: example
---

A capability that takes one or more capability specs and dynamically generates a Postman Workspace + a Bruno workspace. Mark explicitly called out Postman + Bruno as the developer-facing surfaces his team materializes specs into; generating both from a capability closes that loop.
