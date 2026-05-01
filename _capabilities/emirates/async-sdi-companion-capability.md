---
categories: []
consumed_apis:
- emirates
description: A capability paired with framework-wiki/Spec-Driven-Integration.md as the standalone read, freeing her from needing to schedule.
layout: capability
naftiko_layer: proposed
naftiko_partner: Sana Mazhoud
name: Emirates Async Sdi Companion Capability
operations: []
personas: []
provider_name: Emirates
provider_slug: emirates
search_terms:
- capability
- paired
- with
- framework
- wiki
slug: async-sdi-companion-capability
source_filename: async-sdi-companion-capability.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Emirates Async Sdi Companion Capability
    description: A capability paired with framework-wiki/Spec-Driven-Integration.md as the standalone read, freeing her from needing to schedule.
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
      namespace: async-sdi-companion-capability-rest
      description: REST API for Emirates Async Sdi Companion Capability.
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
      namespace: async-sdi-companion-capability-mcp
      description: MCP server exposing Emirates Async Sdi Companion Capability for AI agents.
      tools:
      - name: example
        description: A capability paired with framework-wiki/Spec-Driven-Integration.md as the standalone read, freeing her from needing to schedule.
        hints:
          readOnly: true
        call: emirates.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: async-sdi-companion-capability-skills
      description: Agent Skill bundle for Emirates Async Sdi Companion Capability.
      skills:
      - name: async-sdi-companion-capability
        description: A capability paired with framework-wiki/Spec-Driven-Integration.md as the standalone read, freeing her from needing to schedule.
        location: file:///opt/naftiko/skills/async-sdi-companion-capability
        allowed-tools: example
        tools:
        - name: example
          description: A capability paired with framework-wiki/Spec-Driven-Integration.md as the standalone read, freeing her from needing to schedule.
          from:
            sourceNamespace: async-sdi-companion-capability-mcp
            action: example
---

A capability paired with framework-wiki/Spec-Driven-Integration.md as the standalone read, freeing her from needing to schedule. She's asked to talk three times — give her a way to engage asynchronously while we wait.
