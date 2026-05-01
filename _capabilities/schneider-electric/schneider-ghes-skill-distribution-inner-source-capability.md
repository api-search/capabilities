---
categories: []
consumed_apis:
- schneider-electric
description: A capability that mirrors enterprise agent skills as inner-source repos with allow-list + manifest semantics, filling the self-hosted GitHub Enterprise Server skill-distribution gap Manu flagged as broken.
layout: capability
naftiko_layer: service-anchored
naftiko_partner: Manu PK
name: Schneider Electric Schneider Ghes Skill Distribution Inner Source Capability
operations: []
personas: []
provider_name: Schneider Electric
provider_slug: schneider-electric
search_terms:
- capability
- that
- mirrors
- enterprise
- agent
slug: schneider-ghes-skill-distribution-inner-source-capability
source_filename: schneider-ghes-skill-distribution-inner-source-capability.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Schneider Electric Schneider Ghes Skill Distribution Inner Source Capability
    description: A capability that mirrors enterprise agent skills as inner-source repos with allow-list + manifest semantics, filling the self-hosted GitHub Enterprise Server skill-distribution gap Manu flagged as broken.
    tags:
    - Schneider Electric
    created: '2026-04-30'
    modified: '2026-04-30'
  binds:
  - namespace: schneider-electric-env
    description: Schneider Electric credentials.
    keys:
      SCHNEIDER_ELECTRIC_API_KEY: SCHNEIDER_ELECTRIC_API_KEY
  capability:
    consumes:
    - namespace: schneider-electric
      type: http
      baseUri: https://api.schneider-electric.com
      authentication:
        type: bearer
        token: '{{SCHNEIDER_ELECTRIC_API_KEY}}'
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
      namespace: schneider-ghes-skill-distribution-inner-source-capability-rest
      description: REST API for Schneider Electric Schneider Ghes Skill Distribution Inner Source Capability.
      resources:
      - name: example
        path: /example
        operations:
        - method: GET
          name: example-op
          call: schneider-electric.example-op
    - type: mcp
      address: 0.0.0.0
      port: 3010
      namespace: schneider-ghes-skill-distribution-inner-source-capability-mcp
      description: MCP server exposing Schneider Electric Schneider Ghes Skill Distribution Inner Source Capability for AI agents.
      tools:
      - name: example
        description: A capability that mirrors enterprise agent skills as inner-source repos with allow-list + manifest semantics, filling the self-hosted GitHub Enterprise Server skill-distribution gap Manu flagged as broken.
        hints:
          readOnly: true
        call: schneider-electric.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: schneider-ghes-skill-distribution-inner-source-capability-skills
      description: Agent Skill bundle for Schneider Electric Schneider Ghes Skill Distribution Inner Source Capability.
      skills:
      - name: schneider-ghes-skill-distribution-inner-source-capability
        description: A capability that mirrors enterprise agent skills as inner-source repos with allow-list + manifest semantics, filling the self-hosted GitHub Enterprise Server skill-distribution gap Manu flagged as broken.
        location: file:///opt/naftiko/skills/schneider-ghes-skill-distribution-inner-source-capability
        allowed-tools: example
        tools:
        - name: example
          description: A capability that mirrors enterprise agent skills as inner-source repos with allow-list + manifest semantics, filling the self-hosted GitHub Enterprise Server skill-distribution gap Manu flagged as broken.
          from:
            sourceNamespace: schneider-ghes-skill-distribution-inner-source-capability-mcp
            action: example
---

A capability that mirrors enterprise agent skills as inner-source repos with allow-list + manifest semantics, filling the self-hosted GitHub Enterprise Server skill-distribution gap Manu flagged as broken. He named this as the unsolved problem at his current scale. Naftiko building it as a capability gives Schneider (and every other GHES customer in the same position) the missing distribution layer.
