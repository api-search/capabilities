---
categories: []
consumed_apis:
- vonage
description: A capability collection wrapping Vonage SMS + Verify APIs as MCP tools with PII detection + HTTPS gates, packaged as an Agent-callable communications surface.
layout: capability
naftiko_layer: service-anchored
naftiko_partner: Vonage
name: Vonage Sms Verify Mcp Collection
operations: []
personas: []
provider_name: Vonage
provider_slug: vonage
search_terms:
- capability
- collection
- wrapping
- vonage
- verify
slug: sms-verify-mcp-collection
source_filename: sms-verify-mcp-collection.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Vonage Sms Verify Mcp Collection
    description: A capability collection wrapping Vonage SMS + Verify APIs as MCP tools with PII detection + HTTPS gates, packaged as an Agent-callable communications surface.
    tags:
    - Vonage
    created: '2026-04-30'
    modified: '2026-04-30'
  binds:
  - namespace: vonage-env
    description: Vonage credentials.
    keys:
      VONAGE_API_KEY: VONAGE_API_KEY
  capability:
    consumes:
    - namespace: vonage
      type: http
      baseUri: https://api.vonage.com
      authentication:
        type: bearer
        token: '{{VONAGE_API_KEY}}'
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
      namespace: sms-verify-mcp-collection-rest
      description: REST API for Vonage Sms Verify Mcp Collection.
      resources:
      - name: example
        path: /example
        operations:
        - method: GET
          name: example-op
          call: vonage.example-op
    - type: mcp
      address: 0.0.0.0
      port: 3010
      namespace: sms-verify-mcp-collection-mcp
      description: MCP server exposing Vonage Sms Verify Mcp Collection for AI agents.
      tools:
      - name: example
        description: A capability collection wrapping Vonage SMS + Verify APIs as MCP tools with PII detection + HTTPS gates, packaged as an Agent-callable communications surface.
        hints:
          readOnly: true
        call: vonage.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: sms-verify-mcp-collection-skills
      description: Agent Skill bundle for Vonage Sms Verify Mcp Collection.
      skills:
      - name: sms-verify-mcp-collection
        description: A capability collection wrapping Vonage SMS + Verify APIs as MCP tools with PII detection + HTTPS gates, packaged as an Agent-callable communications surface.
        location: file:///opt/naftiko/skills/sms-verify-mcp-collection
        allowed-tools: example
        tools:
        - name: example
          description: A capability collection wrapping Vonage SMS + Verify APIs as MCP tools with PII detection + HTTPS gates, packaged as an Agent-callable communications surface.
          from:
            sourceNamespace: sms-verify-mcp-collection-mcp
            action: example
---

A capability collection wrapping Vonage SMS + Verify APIs as MCP tools with PII detection + HTTPS gates, packaged as an Agent-callable communications surface. Communications APIs touch PII; agent-callable SMS + Verify with governance is the un-stickier next-step than another intro.
