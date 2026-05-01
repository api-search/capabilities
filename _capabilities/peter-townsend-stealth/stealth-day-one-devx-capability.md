---
categories: []
consumed_apis:
- peter-townsend-stealth
description: A capability seeded with the Naftiko VS Code extension + Backstage template defaults, intended as the day-1 dev workflow for the stealth team.
layout: capability
naftiko_layer: proposed
naftiko_partner: Peter Townsend
name: Peter Townsend Stealth Stealth Day One Devx Capability
operations: []
personas: []
provider_name: Peter Townsend Stealth
provider_slug: peter-townsend-stealth
search_terms:
- capability
- seeded
- with
- naftiko
- code
slug: stealth-day-one-devx-capability
source_filename: stealth-day-one-devx-capability.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Peter Townsend Stealth Stealth Day One Devx Capability
    description: A capability seeded with the Naftiko VS Code extension + Backstage template defaults, intended as the day-1 dev workflow for the stealth team.
    tags:
    - Peter Townsend Stealth
    created: '2026-04-30'
    modified: '2026-04-30'
  binds:
  - namespace: peter-townsend-stealth-env
    description: Peter Townsend Stealth credentials.
    keys:
      PETER_TOWNSEND_STEALTH_API_KEY: PETER_TOWNSEND_STEALTH_API_KEY
  capability:
    consumes:
    - namespace: peter-townsend-stealth
      type: http
      baseUri: https://api.peter-townsend-stealth.com
      authentication:
        type: bearer
        token: '{{PETER_TOWNSEND_STEALTH_API_KEY}}'
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
      namespace: stealth-day-one-devx-capability-rest
      description: REST API for Peter Townsend Stealth Stealth Day One Devx Capability.
      resources:
      - name: example
        path: /example
        operations:
        - method: GET
          name: example-op
          call: peter-townsend-stealth.example-op
    - type: mcp
      address: 0.0.0.0
      port: 3010
      namespace: stealth-day-one-devx-capability-mcp
      description: MCP server exposing Peter Townsend Stealth Stealth Day One Devx Capability for AI agents.
      tools:
      - name: example
        description: A capability seeded with the Naftiko VS Code extension + Backstage template defaults, intended as the day-1 dev workflow for the stealth team.
        hints:
          readOnly: true
        call: peter-townsend-stealth.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: stealth-day-one-devx-capability-skills
      description: Agent Skill bundle for Peter Townsend Stealth Stealth Day One Devx Capability.
      skills:
      - name: stealth-day-one-devx-capability
        description: A capability seeded with the Naftiko VS Code extension + Backstage template defaults, intended as the day-1 dev workflow for the stealth team.
        location: file:///opt/naftiko/skills/stealth-day-one-devx-capability
        allowed-tools: example
        tools:
        - name: example
          description: A capability seeded with the Naftiko VS Code extension + Backstage template defaults, intended as the day-1 dev workflow for the stealth team.
          from:
            sourceNamespace: stealth-day-one-devx-capability-mcp
            action: example
---

A capability seeded with the Naftiko VS Code extension + Backstage template defaults, intended as the day-1 dev workflow for the stealth team. Stealth teams pick tooling that scales; locking in the workflow early matters more than later.
