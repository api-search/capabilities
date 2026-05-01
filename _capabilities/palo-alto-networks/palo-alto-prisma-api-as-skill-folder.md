---
categories: []
consumed_apis:
- palo-alto-networks
description: A capability over a Prisma Cloud API that ships AGENT.md + SKILL.md as the canonical published documentation, repositioning his TW role as the spec author.
layout: capability
naftiko_layer: service-anchored
naftiko_partner: James DeVore
name: Palo Alto Networks Palo Alto Prisma Api As Skill Folder
operations: []
personas: []
provider_name: Palo Alto Networks
provider_slug: palo-alto-networks
search_terms:
- capability
- over
- prisma
- cloud
- that
slug: palo-alto-prisma-api-as-skill-folder
source_filename: palo-alto-prisma-api-as-skill-folder.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Palo Alto Networks Palo Alto Prisma Api As Skill Folder
    description: A capability over a Prisma Cloud API that ships AGENT.md + SKILL.md as the canonical published documentation, repositioning his TW role as the spec author.
    tags:
    - Palo Alto Networks
    created: '2026-04-30'
    modified: '2026-04-30'
  binds:
  - namespace: palo-alto-networks-env
    description: Palo Alto Networks credentials.
    keys:
      PALO_ALTO_NETWORKS_API_KEY: PALO_ALTO_NETWORKS_API_KEY
  capability:
    consumes:
    - namespace: palo-alto-networks
      type: http
      baseUri: https://api.palo-alto-networks.com
      authentication:
        type: bearer
        token: '{{PALO_ALTO_NETWORKS_API_KEY}}'
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
      namespace: palo-alto-prisma-api-as-skill-folder-rest
      description: REST API for Palo Alto Networks Palo Alto Prisma Api As Skill Folder.
      resources:
      - name: example
        path: /example
        operations:
        - method: GET
          name: example-op
          call: palo-alto-networks.example-op
    - type: mcp
      address: 0.0.0.0
      port: 3010
      namespace: palo-alto-prisma-api-as-skill-folder-mcp
      description: MCP server exposing Palo Alto Networks Palo Alto Prisma Api As Skill Folder for AI agents.
      tools:
      - name: example
        description: A capability over a Prisma Cloud API that ships AGENT.md + SKILL.md as the canonical published documentation, repositioning his TW role as the spec author.
        hints:
          readOnly: true
        call: palo-alto-networks.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: palo-alto-prisma-api-as-skill-folder-skills
      description: Agent Skill bundle for Palo Alto Networks Palo Alto Prisma Api As Skill Folder.
      skills:
      - name: palo-alto-prisma-api-as-skill-folder
        description: A capability over a Prisma Cloud API that ships AGENT.md + SKILL.md as the canonical published documentation, repositioning his TW role as the spec author.
        location: file:///opt/naftiko/skills/palo-alto-prisma-api-as-skill-folder
        allowed-tools: example
        tools:
        - name: example
          description: A capability over a Prisma Cloud API that ships AGENT.md + SKILL.md as the canonical published documentation, repositioning his TW role as the spec author.
          from:
            sourceNamespace: palo-alto-prisma-api-as-skill-folder-mcp
            action: example
---

A capability over a Prisma Cloud API that ships AGENT.md + SKILL.md as the canonical published documentation, repositioning his TW role as the spec author. His role IS this persona — show that the spec + SKILL.md is the docs.
