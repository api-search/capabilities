---
categories: []
consumed_apis:
- xero
description: A Xero accounting-API capability (REST + MCP dual exposure) wrapping a representative Xero endpoint, brought as the apidays NYC follow-on artifact.
layout: capability
naftiko_layer: proposed
naftiko_partner: Rose Missier
name: Xero Accounting Rest Mcp Capability
operations: []
personas: []
provider_name: Xero
provider_slug: xero
search_terms:
- xero
- accounting
- capability
- rest
- dual
slug: accounting-rest-mcp-capability
source_filename: accounting-rest-mcp-capability.yaml
source_heading: Capability Spec
source_yaml: |
  naftiko: 1.0.0-alpha2
  info:
    title: Xero Accounting Rest Mcp Capability
    description: A Xero accounting-API capability (REST + MCP dual exposure) wrapping a representative Xero endpoint, brought as the apidays NYC follow-on artifact.
    tags:
    - Xero
    created: '2026-04-30'
    modified: '2026-04-30'
  binds:
  - namespace: xero-env
    description: Xero credentials.
    keys:
      XERO_API_KEY: XERO_API_KEY
  capability:
    consumes:
    - namespace: xero
      type: http
      baseUri: https://api.xero.com
      authentication:
        type: bearer
        token: '{{XERO_API_KEY}}'
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
      namespace: accounting-rest-mcp-capability-rest
      description: REST API for Xero Accounting Rest Mcp Capability.
      resources:
      - name: example
        path: /example
        operations:
        - method: GET
          name: example-op
          call: xero.example-op
    - type: mcp
      address: 0.0.0.0
      port: 3010
      namespace: accounting-rest-mcp-capability-mcp
      description: MCP server exposing Xero Accounting Rest Mcp Capability for AI agents.
      tools:
      - name: example
        description: A Xero accounting-API capability (REST + MCP dual exposure) wrapping a representative Xero endpoint, brought as the apidays NYC follow-on artifact.
        hints:
          readOnly: true
        call: xero.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: accounting-rest-mcp-capability-skills
      description: Agent Skill bundle for Xero Accounting Rest Mcp Capability.
      skills:
      - name: accounting-rest-mcp-capability
        description: A Xero accounting-API capability (REST + MCP dual exposure) wrapping a representative Xero endpoint, brought as the apidays NYC follow-on artifact.
        location: file:///opt/naftiko/skills/accounting-rest-mcp-capability
        allowed-tools: example
        tools:
        - name: example
          description: A Xero accounting-API capability (REST + MCP dual exposure) wrapping a representative Xero endpoint, brought as the apidays NYC follow-on artifact.
          from:
            sourceNamespace: accounting-rest-mcp-capability-mcp
            action: example
---

A Xero accounting-API capability (REST + MCP dual exposure) wrapping a representative Xero endpoint, brought as the apidays NYC follow-on artifact. She's a PM — a built artifact she can show internally is more compelling than a feature list.
