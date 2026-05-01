---
categories: []
consumed_apis:
- vanguard
description: A capability annotated against the SDI "Deterministic Foundation for Agents" framing, used as the AI-Data-Enterprise-Tech opening artifact.
layout: capability
naftiko_layer: proposed
naftiko_partner: Vanguard
name: Vanguard Deterministic Agent Foundation
operations: []
personas: []
provider_name: Vanguard
provider_slug: vanguard
search_terms:
- capability
- annotated
- against
- deterministic
- foundation
slug: deterministic-agent-foundation
source_filename: deterministic-agent-foundation.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Vanguard Deterministic Agent Foundation
    description: A capability annotated against the SDI "Deterministic Foundation for Agents" framing, used as the AI-Data-Enterprise-Tech opening artifact.
    tags:
    - Vanguard
    created: '2026-04-30'
    modified: '2026-04-30'
  binds:
  - namespace: vanguard-env
    description: Vanguard credentials.
    keys:
      VANGUARD_API_KEY: VANGUARD_API_KEY
  capability:
    consumes:
    - namespace: vanguard
      type: http
      baseUri: https://api.vanguard.com
      authentication:
        type: bearer
        token: '{{VANGUARD_API_KEY}}'
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
      namespace: deterministic-agent-foundation-rest
      description: REST API for Vanguard Deterministic Agent Foundation.
      resources:
      - name: example
        path: /example
        operations:
        - method: GET
          name: example-op
          call: vanguard.example-op
    - type: mcp
      address: 0.0.0.0
      port: 3010
      namespace: deterministic-agent-foundation-mcp
      description: MCP server exposing Vanguard Deterministic Agent Foundation for AI agents.
      tools:
      - name: example
        description: A capability annotated against the SDI "Deterministic Foundation for Agents" framing, used as the AI-Data-Enterprise-Tech opening artifact.
        hints:
          readOnly: true
        call: vanguard.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: deterministic-agent-foundation-skills
      description: Agent Skill bundle for Vanguard Deterministic Agent Foundation.
      skills:
      - name: deterministic-agent-foundation
        description: A capability annotated against the SDI "Deterministic Foundation for Agents" framing, used as the AI-Data-Enterprise-Tech opening artifact.
        location: file:///opt/naftiko/skills/deterministic-agent-foundation
        allowed-tools: example
        tools:
        - name: example
          description: A capability annotated against the SDI "Deterministic Foundation for Agents" framing, used as the AI-Data-Enterprise-Tech opening artifact.
          from:
            sourceNamespace: deterministic-agent-foundation-mcp
            action: example
---

A capability annotated against the SDI "Deterministic Foundation for Agents" framing, used as the AI-Data-Enterprise-Tech opening artifact. **Chris Bennett's** CIO role is exactly AI + Data + Enterprise Tech; deterministic-agent integration is the convergence pitch his role title demands.
