---
categories: []
consumed_apis:
- jpmorgan-chase
description: A capability that takes a Naftiko-published OpenAPI spec, generates Microcks sandboxes via Git, and returns runnable mock URLs as MCP-callable tools.
layout: capability
naftiko_layer: service-anchored
naftiko_partner: Mark McAllister
name: JPMorgan Chase Jpmc Microcks Sandbox Bridge Capability
operations: []
personas: []
provider_name: JPMorgan Chase
provider_slug: jpmorgan-chase
search_terms:
- capability
- that
- takes
- naftiko
- published
slug: jpmc-microcks-sandbox-bridge-capability
source_filename: jpmc-microcks-sandbox-bridge-capability.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: JPMorgan Chase Jpmc Microcks Sandbox Bridge Capability
    description: A capability that takes a Naftiko-published OpenAPI spec, generates Microcks sandboxes via Git, and returns runnable mock URLs as MCP-callable tools.
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
      namespace: jpmc-microcks-sandbox-bridge-capability-rest
      description: REST API for JPMorgan Chase Jpmc Microcks Sandbox Bridge Capability.
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
      namespace: jpmc-microcks-sandbox-bridge-capability-mcp
      description: MCP server exposing JPMorgan Chase Jpmc Microcks Sandbox Bridge Capability for AI agents.
      tools:
      - name: example
        description: A capability that takes a Naftiko-published OpenAPI spec, generates Microcks sandboxes via Git, and returns runnable mock URLs as MCP-callable tools.
        hints:
          readOnly: true
        call: jpmorgan-chase.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: jpmc-microcks-sandbox-bridge-capability-skills
      description: Agent Skill bundle for JPMorgan Chase Jpmc Microcks Sandbox Bridge Capability.
      skills:
      - name: jpmc-microcks-sandbox-bridge-capability
        description: A capability that takes a Naftiko-published OpenAPI spec, generates Microcks sandboxes via Git, and returns runnable mock URLs as MCP-callable tools.
        location: file:///opt/naftiko/skills/jpmc-microcks-sandbox-bridge-capability
        allowed-tools: example
        tools:
        - name: example
          description: A capability that takes a Naftiko-published OpenAPI spec, generates Microcks sandboxes via Git, and returns runnable mock URLs as MCP-callable tools.
          from:
            sourceNamespace: jpmc-microcks-sandbox-bridge-capability-mcp
            action: example
---

A capability that takes a Naftiko-published OpenAPI spec, generates Microcks sandboxes via Git, and returns runnable mock URLs as MCP-callable tools. Microcks is the sandbox layer he asked us to bridge into — this turns each capability spec into a reachable mock without leaving his pipeline.
