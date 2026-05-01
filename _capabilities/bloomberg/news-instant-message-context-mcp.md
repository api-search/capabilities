---
categories: []
consumed_apis:
- bloomberg
description: A capability that joins Bloomberg News headlines + Bloomberg Instant Messaging (IB) thread context into one MCP-callable agent tool for an internal trading-floor assistant.
layout: capability
naftiko_layer: service-anchored
naftiko_partner: Brendan Burgess
name: Bloomberg News Instant Message Context Mcp
operations: []
personas: []
provider_name: Bloomberg
provider_slug: bloomberg
search_terms:
- capability
- that
- joins
- bloomberg
- news
slug: news-instant-message-context-mcp
source_filename: news-instant-message-context-mcp.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Bloomberg News Instant Message Context Mcp
    description: A capability that joins Bloomberg News headlines + Bloomberg Instant Messaging (IB) thread context into one MCP-callable agent tool for an internal trading-floor assistant.
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
      namespace: news-instant-message-context-mcp-rest
      description: REST API for Bloomberg News Instant Message Context Mcp.
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
      namespace: news-instant-message-context-mcp-mcp
      description: MCP server exposing Bloomberg News Instant Message Context Mcp for AI agents.
      tools:
      - name: example
        description: A capability that joins Bloomberg News headlines + Bloomberg Instant Messaging (IB) thread context into one MCP-callable agent tool for an internal trading-floor assistant.
        hints:
          readOnly: true
        call: bloomberg.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: news-instant-message-context-mcp-skills
      description: Agent Skill bundle for Bloomberg News Instant Message Context Mcp.
      skills:
      - name: news-instant-message-context-mcp
        description: A capability that joins Bloomberg News headlines + Bloomberg Instant Messaging (IB) thread context into one MCP-callable agent tool for an internal trading-floor assistant.
        location: file:///opt/naftiko/skills/news-instant-message-context-mcp
        allowed-tools: example
        tools:
        - name: example
          description: A capability that joins Bloomberg News headlines + Bloomberg Instant Messaging (IB) thread context into one MCP-callable agent tool for an internal trading-floor assistant.
          from:
            sourceNamespace: news-instant-message-context-mcp-mcp
            action: example
---

A capability that joins Bloomberg News headlines + Bloomberg Instant Messaging (IB) thread context into one MCP-callable agent tool for an internal trading-floor assistant. An apidays NYC re-engagement needs a tangible artifact that crosses internal Bloomberg surfaces — News + IB is canonically Bloomberg.
