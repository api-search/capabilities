---
categories: []
consumed_apis:
- bloomberg
description: A built Bloomberg-shaped capability used as the apidays NYC re-engagement hook — designed for booth conversation, not screen-share.
layout: capability
naftiko_layer: proposed
naftiko_partner: Brendan Burgess
name: Bloomberg Apidays Nyc Booth Capability
operations: []
personas: []
provider_name: Bloomberg
provider_slug: bloomberg
search_terms:
- built
- bloomberg
- shaped
- capability
- used
slug: apidays-nyc-booth-capability
source_filename: apidays-nyc-booth-capability.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Bloomberg Apidays Nyc Booth Capability
    description: A built Bloomberg-shaped capability used as the apidays NYC re-engagement hook — designed for booth conversation, not screen-share.
    tags:
    - Bloomberg
    created: '2026-04-30'
    modified: '2026-04-30'
  binds:
  - namespace: bloomberg-env
    description: Bloomberg credentials.
    keys:
      BLOOMBERG_API_KEY: BLOOMBERG_API_KEY
  capability:
    consumes:
    - namespace: bloomberg
      type: http
      baseUri: https://api.bloomberg.com
      authentication:
        type: bearer
        token: '{{BLOOMBERG_API_KEY}}'
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
      namespace: apidays-nyc-booth-capability-rest
      description: REST API for Bloomberg Apidays Nyc Booth Capability.
      resources:
      - name: example
        path: /example
        operations:
        - method: GET
          name: example-op
          call: bloomberg.example-op
    - type: mcp
      address: 0.0.0.0
      port: 3010
      namespace: apidays-nyc-booth-capability-mcp
      description: MCP server exposing Bloomberg Apidays Nyc Booth Capability for AI agents.
      tools:
      - name: example
        description: A built Bloomberg-shaped capability used as the apidays NYC re-engagement hook — designed for booth conversation, not screen-share.
        hints:
          readOnly: true
        call: bloomberg.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: apidays-nyc-booth-capability-skills
      description: Agent Skill bundle for Bloomberg Apidays Nyc Booth Capability.
      skills:
      - name: apidays-nyc-booth-capability
        description: A built Bloomberg-shaped capability used as the apidays NYC re-engagement hook — designed for booth conversation, not screen-share.
        location: file:///opt/naftiko/skills/apidays-nyc-booth-capability
        allowed-tools: example
        tools:
        - name: example
          description: A built Bloomberg-shaped capability used as the apidays NYC re-engagement hook — designed for booth conversation, not screen-share.
          from:
            sourceNamespace: apidays-nyc-booth-capability-mcp
            action: example
---

A built Bloomberg-shaped capability used as the apidays NYC re-engagement hook — designed for booth conversation, not screen-share. He hasn't responded to messages; an apidays NYC pitch needs a tangible artifact face-to-face.
