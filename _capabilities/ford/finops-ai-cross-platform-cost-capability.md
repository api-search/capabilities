---
categories: []
consumed_apis:
- ford
description: A capability that fans out to every AI-spend source Ford touches (Microsoft, Google, Anthropic, Open Router, vendor-specific dashboards) and returns one cross-platform AI cost-of-ownership view by capability, team, and agent.
layout: capability
naftiko_layer: service-anchored
naftiko_partner: John Musser
name: Ford Finops Ai Cross Platform Cost Capability
operations: []
personas: []
provider_name: Ford
provider_slug: ford
search_terms:
- capability
- that
- fans
- every
- spend
slug: finops-ai-cross-platform-cost-capability
source_filename: finops-ai-cross-platform-cost-capability.yaml
source_heading: Capability Spec
source_yaml: |
  naftiko: 1.0.0-alpha2
  info:
    title: Ford Finops Ai Cross Platform Cost Capability
    description: A capability that fans out to every AI-spend source Ford touches (Microsoft, Google, Anthropic, Open Router, vendor-specific dashboards) and returns one cross-platform AI cost-of-ownership view by capability, team, and agent.
    tags:
    - Ford
    created: '2026-04-30'
    modified: '2026-04-30'
  binds:
  - namespace: ford-env
    description: Ford credentials.
    keys:
      FORD_API_KEY: FORD_API_KEY
  capability:
    consumes:
    - namespace: ford
      type: http
      baseUri: https://api.ford.com
      authentication:
        type: bearer
        token: '{{FORD_API_KEY}}'
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
      namespace: finops-ai-cross-platform-cost-capability-rest
      description: REST API for Ford Finops Ai Cross Platform Cost Capability.
      resources:
      - name: example
        path: /example
        operations:
        - method: GET
          name: example-op
          call: ford.example-op
    - type: mcp
      address: 0.0.0.0
      port: 3010
      namespace: finops-ai-cross-platform-cost-capability-mcp
      description: MCP server exposing Ford Finops Ai Cross Platform Cost Capability for AI agents.
      tools:
      - name: example
        description: A capability that fans out to every AI-spend source Ford touches (Microsoft, Google, Anthropic, Open Router, vendor-specific dashboards) and returns one cross-platform AI cost-of-ownership view by capability, team, and agent.
        hints:
          readOnly: true
        call: ford.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: finops-ai-cross-platform-cost-capability-skills
      description: Agent Skill bundle for Ford Finops Ai Cross Platform Cost Capability.
      skills:
      - name: finops-ai-cross-platform-cost-capability
        description: A capability that fans out to every AI-spend source Ford touches (Microsoft, Google, Anthropic, Open Router, vendor-specific dashboards) and returns one cross-platform AI cost-of-ownership view by capability, team, and agent.
        location: file:///opt/naftiko/skills/finops-ai-cross-platform-cost-capability
        allowed-tools: example
        tools:
        - name: example
          description: A capability that fans out to every AI-spend source Ford touches (Microsoft, Google, Anthropic, Open Router, vendor-specific dashboards) and returns one cross-platform AI cost-of-ownership view by capability, team, and agent.
          from:
            sourceNamespace: finops-ai-cross-platform-cost-capability-mcp
            action: example
---

A capability that fans out to every AI-spend source Ford touches (Microsoft, Google, Anthropic, Open Router, vendor-specific dashboards) and returns one cross-platform AI cost-of-ownership view by capability, team, and agent. This is "FinOps for AI" — the named 2026 objective on his list — answered as a deterministic capability instead of a cross-vendor spreadsheet; pairs with the existing multi-vendor observability bridge.
