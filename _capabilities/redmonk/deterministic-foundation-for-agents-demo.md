---
categories: []
consumed_apis:
- redmonk
description: A capability whose `exposes` block is annotated to show the deterministic adapter layer (typed outputParameters, JSONPath shaping, governance rules) versus what an agent would otherwise hallucinate against the same API.
layout: capability
naftiko_layer: proposed
naftiko_partner: Kate Holterhoff
name: Redmonk Deterministic Foundation For Agents Demo
operations: []
personas: []
provider_name: Redmonk
provider_slug: redmonk
search_terms:
- capability
- whose
- exposes
- block
- annotated
slug: deterministic-foundation-for-agents-demo
source_filename: deterministic-foundation-for-agents-demo.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Redmonk Deterministic Foundation For Agents Demo
    description: A capability whose `exposes` block is annotated to show the deterministic adapter layer (typed outputParameters, JSONPath shaping, governance rules) versus what an agent would otherwise hallucinate against the same API.
    tags:
    - Redmonk
    created: '2026-04-30'
    modified: '2026-04-30'
  binds:
  - namespace: redmonk-env
    description: Redmonk credentials.
    keys:
      REDMONK_API_KEY: REDMONK_API_KEY
  capability:
    consumes:
    - namespace: redmonk
      type: http
      baseUri: https://api.redmonk.com
      authentication:
        type: bearer
        token: '{{REDMONK_API_KEY}}'
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
      namespace: deterministic-foundation-for-agents-demo-rest
      description: REST API for Redmonk Deterministic Foundation For Agents Demo.
      resources:
      - name: example
        path: /example
        operations:
        - method: GET
          name: example-op
          call: redmonk.example-op
    - type: mcp
      address: 0.0.0.0
      port: 3010
      namespace: deterministic-foundation-for-agents-demo-mcp
      description: MCP server exposing Redmonk Deterministic Foundation For Agents Demo for AI agents.
      tools:
      - name: example
        description: A capability whose `exposes` block is annotated to show the deterministic adapter layer (typed outputParameters, JSONPath shaping, governance rules) versus what an agent would otherwise hallucinate against the same API.
        hints:
          readOnly: true
        call: redmonk.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: deterministic-foundation-for-agents-demo-skills
      description: Agent Skill bundle for Redmonk Deterministic Foundation For Agents Demo.
      skills:
      - name: deterministic-foundation-for-agents-demo
        description: A capability whose `exposes` block is annotated to show the deterministic adapter layer (typed outputParameters, JSONPath shaping, governance rules) versus what an agent would otherwise hallucinate against the same API.
        location: file:///opt/naftiko/skills/deterministic-foundation-for-agents-demo
        allowed-tools: example
        tools:
        - name: example
          description: A capability whose `exposes` block is annotated to show the deterministic adapter layer (typed outputParameters, JSONPath shaping, governance rules) versus what an agent would otherwise hallucinate against the same API.
          from:
            sourceNamespace: deterministic-foundation-for-agents-demo-mcp
            action: example
---

A capability whose `exposes` block is annotated to show the deterministic adapter layer (typed outputParameters, JSONPath shaping, governance rules) versus what an agent would otherwise hallucinate against the same API. Her recommendations call out the SDI "Deterministic Foundation for Agents" framing as the analyst-grade thesis statement for the review.
