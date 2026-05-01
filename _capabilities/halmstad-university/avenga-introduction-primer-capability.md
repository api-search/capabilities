---
categories: []
consumed_apis:
- halmstad-university
description: 'A small, runnable capability + use-case briefing pair (Use Cases #1 + #2) packaged as the Avenga introduction artifact.'
layout: capability
naftiko_layer: proposed
naftiko_partner: Farzaneh Etminani
name: Halmstad University Avenga Introduction Primer Capability
operations: []
personas: []
provider_name: Halmstad University
provider_slug: halmstad-university
search_terms:
- small
- runnable
- capability
- case
- briefing
slug: avenga-introduction-primer-capability
source_filename: avenga-introduction-primer-capability.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Halmstad University Avenga Introduction Primer Capability
    description: 'A small, runnable capability + use-case briefing pair (Use Cases #1 + #2) packaged as the Avenga introduction artifact.'
    tags:
    - Halmstad University
    created: '2026-04-30'
    modified: '2026-04-30'
  binds:
  - namespace: halmstad-university-env
    description: Halmstad University credentials.
    keys:
      HALMSTAD_UNIVERSITY_API_KEY: HALMSTAD_UNIVERSITY_API_KEY
  capability:
    consumes:
    - namespace: halmstad-university
      type: http
      baseUri: https://api.halmstad-university.com
      authentication:
        type: bearer
        token: '{{HALMSTAD_UNIVERSITY_API_KEY}}'
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
      namespace: avenga-introduction-primer-capability-rest
      description: REST API for Halmstad University Avenga Introduction Primer Capability.
      resources:
      - name: example
        path: /example
        operations:
        - method: GET
          name: example-op
          call: halmstad-university.example-op
    - type: mcp
      address: 0.0.0.0
      port: 3010
      namespace: avenga-introduction-primer-capability-mcp
      description: MCP server exposing Halmstad University Avenga Introduction Primer Capability for AI agents.
      tools:
      - name: example
        description: 'A small, runnable capability + use-case briefing pair (Use Cases #1 + #2) packaged as the Avenga introduction artifact.'
        hints:
          readOnly: true
        call: halmstad-university.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: avenga-introduction-primer-capability-skills
      description: Agent Skill bundle for Halmstad University Avenga Introduction Primer Capability.
      skills:
      - name: avenga-introduction-primer-capability
        description: 'A small, runnable capability + use-case briefing pair (Use Cases #1 + #2) packaged as the Avenga introduction artifact.'
        location: file:///opt/naftiko/skills/avenga-introduction-primer-capability
        allowed-tools: example
        tools:
        - name: example
          description: 'A small, runnable capability + use-case briefing pair (Use Cases #1 + #2) packaged as the Avenga introduction artifact.'
          from:
            sourceNamespace: avenga-introduction-primer-capability-mcp
            action: example
---

A small, runnable capability + use-case briefing pair (Use Cases #1 + #2) packaged as the Avenga introduction artifact. She offered to introduce Naftiko to Avenga; arming her with a runnable artifact + use-case pages makes the intro frictionless.
