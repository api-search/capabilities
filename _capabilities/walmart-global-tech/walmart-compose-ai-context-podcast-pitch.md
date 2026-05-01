---
categories: []
consumed_apis:
- walmart-global-tech
description: A capability sized to be the topic of a podcast episode pitch — a specific topic she can say yes to.
layout: capability
naftiko_layer: proposed
naftiko_partner: Mamta Suri
name: Walmart Global Tech Walmart Compose Ai Context Podcast Pitch
operations: []
personas: []
provider_name: Walmart Global Tech
provider_slug: walmart-global-tech
search_terms:
- capability
- sized
- topic
- podcast
- episode
slug: walmart-compose-ai-context-podcast-pitch
source_filename: walmart-compose-ai-context-podcast-pitch.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Walmart Global Tech Walmart Compose Ai Context Podcast Pitch
    description: A capability sized to be the topic of a podcast episode pitch — a specific topic she can say yes to.
    tags:
    - Walmart Global Tech
    created: '2026-04-30'
    modified: '2026-04-30'
  binds:
  - namespace: walmart-global-tech-env
    description: Walmart Global Tech credentials.
    keys:
      WALMART_GLOBAL_TECH_API_KEY: WALMART_GLOBAL_TECH_API_KEY
  capability:
    consumes:
    - namespace: walmart-global-tech
      type: http
      baseUri: https://api.walmart-global-tech.com
      authentication:
        type: bearer
        token: '{{WALMART_GLOBAL_TECH_API_KEY}}'
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
      namespace: walmart-compose-ai-context-podcast-pitch-rest
      description: REST API for Walmart Global Tech Walmart Compose Ai Context Podcast Pitch.
      resources:
      - name: example
        path: /example
        operations:
        - method: GET
          name: example-op
          call: walmart-global-tech.example-op
    - type: mcp
      address: 0.0.0.0
      port: 3010
      namespace: walmart-compose-ai-context-podcast-pitch-mcp
      description: MCP server exposing Walmart Global Tech Walmart Compose Ai Context Podcast Pitch for AI agents.
      tools:
      - name: example
        description: A capability sized to be the topic of a podcast episode pitch — a specific topic she can say yes to.
        hints:
          readOnly: true
        call: walmart-global-tech.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: walmart-compose-ai-context-podcast-pitch-skills
      description: Agent Skill bundle for Walmart Global Tech Walmart Compose Ai Context Podcast Pitch.
      skills:
      - name: walmart-compose-ai-context-podcast-pitch
        description: A capability sized to be the topic of a podcast episode pitch — a specific topic she can say yes to.
        location: file:///opt/naftiko/skills/walmart-compose-ai-context-podcast-pitch
        allowed-tools: example
        tools:
        - name: example
          description: A capability sized to be the topic of a podcast episode pitch — a specific topic she can say yes to.
          from:
            sourceNamespace: walmart-compose-ai-context-podcast-pitch-mcp
            action: example
---

A capability sized to be the topic of a podcast episode pitch — a specific topic she can say yes to. A specific topic gives her something to say yes to instead of a generic podcast slot.
