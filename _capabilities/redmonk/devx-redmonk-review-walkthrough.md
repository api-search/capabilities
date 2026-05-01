---
categories: []
consumed_apis:
- redmonk
description: 'A capability built specifically for the analyst review brief, optimized to be probed in a 30-minute review window: VS Code extension + Backstage scaffold + downloadable Agent Skill.'
layout: capability
naftiko_layer: proposed
naftiko_partner: Kate Holterhoff
name: Redmonk Devx Redmonk Review Walkthrough
operations: []
personas: []
provider_name: Redmonk
provider_slug: redmonk
search_terms:
- capability
- built
- specifically
- analyst
- review
slug: devx-redmonk-review-walkthrough
source_filename: devx-redmonk-review-walkthrough.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Redmonk Devx Redmonk Review Walkthrough
    description: 'A capability built specifically for the analyst review brief, optimized to be probed in a 30-minute review window: VS Code extension + Backstage scaffold + downloadable Agent Skill.'
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
      namespace: devx-redmonk-review-walkthrough-rest
      description: REST API for Redmonk Devx Redmonk Review Walkthrough.
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
      namespace: devx-redmonk-review-walkthrough-mcp
      description: MCP server exposing Redmonk Devx Redmonk Review Walkthrough for AI agents.
      tools:
      - name: example
        description: 'A capability built specifically for the analyst review brief, optimized to be probed in a 30-minute review window: VS Code extension + Backstage scaffold + downloadable Agent Skill.'
        hints:
          readOnly: true
        call: redmonk.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: devx-redmonk-review-walkthrough-skills
      description: Agent Skill bundle for Redmonk Devx Redmonk Review Walkthrough.
      skills:
      - name: devx-redmonk-review-walkthrough
        description: 'A capability built specifically for the analyst review brief, optimized to be probed in a 30-minute review window: VS Code extension + Backstage scaffold + downloadable Agent Skill.'
        location: file:///opt/naftiko/skills/devx-redmonk-review-walkthrough
        allowed-tools: example
        tools:
        - name: example
          description: 'A capability built specifically for the analyst review brief, optimized to be probed in a 30-minute review window: VS Code extension + Backstage scaffold + downloadable Agent Skill.'
          from:
            sourceNamespace: devx-redmonk-review-walkthrough-mcp
            action: example
---

A capability built specifically for the analyst review brief, optimized to be probed in a 30-minute review window: VS Code extension + Backstage scaffold + downloadable Agent Skill. RedMonk's review lens is developer adoption; she said to come back when ready to brief — this is the briefing asset that demonstrates the developer-experience surface analysts probe first.
