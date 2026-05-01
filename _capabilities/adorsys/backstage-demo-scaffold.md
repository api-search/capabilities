---
categories: []
consumed_apis:
- adorsys
description: A capability scaffolded entirely from the Naftiko Templates for Backstage workflow, intended as Daniel's 2-minute live-demo sequence at apidays Munich (Choose template → generated repo → running engine).
layout: capability
naftiko_layer: proposed
naftiko_partner: Daniel Kocot
name: Adorsys Backstage Demo Scaffold
operations: []
personas: []
provider_name: Adorsys
provider_slug: adorsys
search_terms:
- capability
- scaffolded
- entirely
- from
- naftiko
slug: backstage-demo-scaffold
source_filename: backstage-demo-scaffold.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Adorsys Backstage Demo Scaffold
    description: A capability scaffolded entirely from the Naftiko Templates for Backstage workflow, intended as Daniel's 2-minute live-demo sequence at apidays Munich (Choose template → generated repo → running engine).
    tags:
    - Adorsys
    created: '2026-04-30'
    modified: '2026-04-30'
  binds:
  - namespace: adorsys-env
    description: Adorsys credentials.
    keys:
      ADORSYS_API_KEY: ADORSYS_API_KEY
  capability:
    consumes:
    - namespace: adorsys
      type: http
      baseUri: https://api.adorsys.com
      authentication:
        type: bearer
        token: '{{ADORSYS_API_KEY}}'
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
      namespace: backstage-demo-scaffold-rest
      description: REST API for Adorsys Backstage Demo Scaffold.
      resources:
      - name: example
        path: /example
        operations:
        - method: GET
          name: example-op
          call: adorsys.example-op
    - type: mcp
      address: 0.0.0.0
      port: 3010
      namespace: backstage-demo-scaffold-mcp
      description: MCP server exposing Adorsys Backstage Demo Scaffold for AI agents.
      tools:
      - name: example
        description: A capability scaffolded entirely from the Naftiko Templates for Backstage workflow, intended as Daniel's 2-minute live-demo sequence at apidays Munich (Choose template → generated repo → running engine).
        hints:
          readOnly: true
        call: adorsys.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: backstage-demo-scaffold-skills
      description: Agent Skill bundle for Adorsys Backstage Demo Scaffold.
      skills:
      - name: backstage-demo-scaffold
        description: A capability scaffolded entirely from the Naftiko Templates for Backstage workflow, intended as Daniel's 2-minute live-demo sequence at apidays Munich (Choose template → generated repo → running engine).
        location: file:///opt/naftiko/skills/backstage-demo-scaffold
        allowed-tools: example
        tools:
        - name: example
          description: A capability scaffolded entirely from the Naftiko Templates for Backstage workflow, intended as Daniel's 2-minute live-demo sequence at apidays Munich (Choose template → generated repo → running engine).
          from:
            sourceNamespace: backstage-demo-scaffold-mcp
            action: example
---

A capability scaffolded entirely from the Naftiko Templates for Backstage workflow, intended as Daniel's 2-minute live-demo sequence at apidays Munich (Choose template → generated repo → running engine). His apidays Munich session needs concrete scaffolding to show — this is the demo asset.
