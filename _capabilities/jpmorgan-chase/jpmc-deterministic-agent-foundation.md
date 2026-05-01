---
categories: []
consumed_apis:
- jpmorgan-chase
description: A capability annotated with the SDI "Deterministic Foundation for Agents" framing, designed to be the lead artifact when AI risk officers join the conversation.
layout: capability
naftiko_layer: proposed
naftiko_partner: Mark McAllister
name: JPMorgan Chase Jpmc Deterministic Agent Foundation
operations: []
personas: []
provider_name: JPMorgan Chase
provider_slug: jpmorgan-chase
search_terms:
- capability
- annotated
- with
- deterministic
- foundation
slug: jpmc-deterministic-agent-foundation
source_filename: jpmc-deterministic-agent-foundation.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: JPMorgan Chase Jpmc Deterministic Agent Foundation
    description: A capability annotated with the SDI "Deterministic Foundation for Agents" framing, designed to be the lead artifact when AI risk officers join the conversation.
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
      namespace: jpmc-deterministic-agent-foundation-rest
      description: REST API for JPMorgan Chase Jpmc Deterministic Agent Foundation.
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
      namespace: jpmc-deterministic-agent-foundation-mcp
      description: MCP server exposing JPMorgan Chase Jpmc Deterministic Agent Foundation for AI agents.
      tools:
      - name: example
        description: A capability annotated with the SDI "Deterministic Foundation for Agents" framing, designed to be the lead artifact when AI risk officers join the conversation.
        hints:
          readOnly: true
        call: jpmorgan-chase.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: jpmc-deterministic-agent-foundation-skills
      description: Agent Skill bundle for JPMorgan Chase Jpmc Deterministic Agent Foundation.
      skills:
      - name: jpmc-deterministic-agent-foundation
        description: A capability annotated with the SDI "Deterministic Foundation for Agents" framing, designed to be the lead artifact when AI risk officers join the conversation.
        location: file:///opt/naftiko/skills/jpmc-deterministic-agent-foundation
        allowed-tools: example
        tools:
        - name: example
          description: A capability annotated with the SDI "Deterministic Foundation for Agents" framing, designed to be the lead artifact when AI risk officers join the conversation.
          from:
            sourceNamespace: jpmc-deterministic-agent-foundation-mcp
            action: example
---

A capability annotated with the SDI "Deterministic Foundation for Agents" framing, designed to be the lead artifact when AI risk officers join the conversation. JPMC AI risk officers will care about deterministic-vs-hallucinated agent behavior more than any feature.
