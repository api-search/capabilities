---
categories: []
consumed_apis:
- schneider-electric
description: A capability over GitHub MCP for pull-request review and comment triage — the GitHub leg of Manu's UX → ticket → code workflow chain.
layout: capability
naftiko_layer: service-anchored
naftiko_partner: Manu PK
name: Schneider Electric Schneider Github Mcp Pr Review Capability
operations: []
personas: []
provider_name: Schneider Electric
provider_slug: schneider-electric
search_terms:
- capability
- over
- github
- pull
- request
slug: schneider-github-mcp-pr-review-capability
source_filename: schneider-github-mcp-pr-review-capability.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Schneider Electric Schneider Github Mcp Pr Review Capability
    description: A capability over GitHub MCP for pull-request review and comment triage — the GitHub leg of Manu's UX → ticket → code workflow chain.
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
      namespace: schneider-github-mcp-pr-review-capability-rest
      description: REST API for Schneider Electric Schneider Github Mcp Pr Review Capability.
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
      namespace: schneider-github-mcp-pr-review-capability-mcp
      description: MCP server exposing Schneider Electric Schneider Github Mcp Pr Review Capability for AI agents.
      tools:
      - name: example
        description: A capability over GitHub MCP for pull-request review and comment triage — the GitHub leg of Manu's UX → ticket → code workflow chain.
        hints:
          readOnly: true
        call: schneider-electric.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: schneider-github-mcp-pr-review-capability-skills
      description: Agent Skill bundle for Schneider Electric Schneider Github Mcp Pr Review Capability.
      skills:
      - name: schneider-github-mcp-pr-review-capability
        description: A capability over GitHub MCP for pull-request review and comment triage — the GitHub leg of Manu's UX → ticket → code workflow chain.
        location: file:///opt/naftiko/skills/schneider-github-mcp-pr-review-capability
        allowed-tools: example
        tools:
        - name: example
          description: A capability over GitHub MCP for pull-request review and comment triage — the GitHub leg of Manu's UX → ticket → code workflow chain.
          from:
            sourceNamespace: schneider-github-mcp-pr-review-capability-mcp
            action: example
---

A capability over GitHub MCP for pull-request review and comment triage — the GitHub leg of Manu's UX → ticket → code workflow chain. He named GitHub MCP as one of "the main ones" closing the developer workflow loop — the third stage after Figma + Atlassian. Shipping it as a capability makes the full workflow registry-ready.
