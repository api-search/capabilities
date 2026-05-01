---
categories: []
consumed_apis:
- bloomberg
description: A capability that exposes Bloomberg Query Language (BQL) as a natural-language MCP tool for an analyst agent.
layout: capability
naftiko_layer: service-anchored
naftiko_partner: Amit Mahale
name: Bloomberg Bql Natural Language Finance Mcp
operations: []
personas: []
provider_name: Bloomberg
provider_slug: bloomberg
search_terms:
- capability
- that
- exposes
- bloomberg
- query
slug: bql-natural-language-finance-mcp
source_filename: bql-natural-language-finance-mcp.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Bloomberg Bql Natural Language Finance Mcp
    description: A capability that exposes Bloomberg Query Language (BQL) as a natural-language MCP tool for an analyst agent.
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
      namespace: bql-natural-language-finance-mcp-rest
      description: REST API for Bloomberg Bql Natural Language Finance Mcp.
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
      namespace: bql-natural-language-finance-mcp-mcp
      description: MCP server exposing Bloomberg Bql Natural Language Finance Mcp for AI agents.
      tools:
      - name: example
        description: A capability that exposes Bloomberg Query Language (BQL) as a natural-language MCP tool for an analyst agent.
        hints:
          readOnly: true
        call: bloomberg.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: bql-natural-language-finance-mcp-skills
      description: Agent Skill bundle for Bloomberg Bql Natural Language Finance Mcp.
      skills:
      - name: bql-natural-language-finance-mcp
        description: A capability that exposes Bloomberg Query Language (BQL) as a natural-language MCP tool for an analyst agent.
        location: file:///opt/naftiko/skills/bql-natural-language-finance-mcp
        allowed-tools: example
        tools:
        - name: example
          description: A capability that exposes Bloomberg Query Language (BQL) as a natural-language MCP tool for an analyst agent.
          from:
            sourceNamespace: bql-natural-language-finance-mcp-mcp
            action: example
---

A capability that exposes Bloomberg Query Language (BQL) as a natural-language MCP tool for an analyst agent. BQL is the most underutilized agent-shaped Bloomberg surface; agentifying it is fresh territory aligned with Bloomberg's automation thesis.
