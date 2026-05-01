---
categories: []
consumed_apis:
- vanguard
description: A capability over Bloomberg AIM portfolio positions exposing typed, deterministic MCP reads for the AI-Data-Enterprise-Tech opening artifact.
layout: capability
naftiko_layer: service-anchored
naftiko_partner: Vanguard
name: Vanguard Bloomberg Aim Deterministic Portfolio Mcp
operations: []
personas: []
provider_name: Vanguard
provider_slug: vanguard
search_terms:
- capability
- over
- bloomberg
- portfolio
- positions
slug: bloomberg-aim-deterministic-portfolio-mcp
source_filename: bloomberg-aim-deterministic-portfolio-mcp.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Vanguard Bloomberg Aim Deterministic Portfolio Mcp
    description: A capability over Bloomberg AIM portfolio positions exposing typed, deterministic MCP reads for the AI-Data-Enterprise-Tech opening artifact.
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
      namespace: bloomberg-aim-deterministic-portfolio-mcp-rest
      description: REST API for Vanguard Bloomberg Aim Deterministic Portfolio Mcp.
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
      namespace: bloomberg-aim-deterministic-portfolio-mcp-mcp
      description: MCP server exposing Vanguard Bloomberg Aim Deterministic Portfolio Mcp for AI agents.
      tools:
      - name: example
        description: A capability over Bloomberg AIM portfolio positions exposing typed, deterministic MCP reads for the AI-Data-Enterprise-Tech opening artifact.
        hints:
          readOnly: true
        call: vanguard.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: bloomberg-aim-deterministic-portfolio-mcp-skills
      description: Agent Skill bundle for Vanguard Bloomberg Aim Deterministic Portfolio Mcp.
      skills:
      - name: bloomberg-aim-deterministic-portfolio-mcp
        description: A capability over Bloomberg AIM portfolio positions exposing typed, deterministic MCP reads for the AI-Data-Enterprise-Tech opening artifact.
        location: file:///opt/naftiko/skills/bloomberg-aim-deterministic-portfolio-mcp
        allowed-tools: example
        tools:
        - name: example
          description: A capability over Bloomberg AIM portfolio positions exposing typed, deterministic MCP reads for the AI-Data-Enterprise-Tech opening artifact.
          from:
            sourceNamespace: bloomberg-aim-deterministic-portfolio-mcp-mcp
            action: example
---

A capability over Bloomberg AIM portfolio positions exposing typed, deterministic MCP reads for the AI-Data-Enterprise-Tech opening artifact. **Chris Bennett's** CIO role spans AI + Data + Enterprise Tech; deterministic agent reads on Bloomberg AIM portfolios is the convergence pitch his title demands.
