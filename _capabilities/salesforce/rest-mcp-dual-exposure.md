---
categories: []
consumed_apis:
- salesforce
description: Wraps a Salesforce REST API as a capability and exposes both REST + MCP, demonstrating dual exposure on a familiar SaaS surface.
layout: capability
naftiko_layer: proposed
naftiko_partner: Kris Harrison
name: Salesforce Rest Mcp Dual Exposure
operations: []
personas: []
provider_name: Salesforce
provider_slug: salesforce
search_terms:
- wraps
- salesforce
- rest
- capability
- exposes
slug: rest-mcp-dual-exposure
source_filename: rest-mcp-dual-exposure.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Salesforce Rest Mcp Dual Exposure
    description: Wraps a Salesforce REST API as a capability and exposes both REST + MCP, demonstrating dual exposure on a familiar SaaS surface.
    tags:
    - Salesforce
    created: '2026-04-30'
    modified: '2026-04-30'
  binds:
  - namespace: salesforce-env
    description: Salesforce credentials.
    keys:
      SALESFORCE_API_KEY: SALESFORCE_API_KEY
  capability:
    consumes:
    - namespace: salesforce
      type: http
      baseUri: https://api.salesforce.com
      authentication:
        type: bearer
        token: '{{SALESFORCE_API_KEY}}'
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
      namespace: rest-mcp-dual-exposure-rest
      description: REST API for Salesforce Rest Mcp Dual Exposure.
      resources:
      - name: example
        path: /example
        operations:
        - method: GET
          name: example-op
          call: salesforce.example-op
    - type: mcp
      address: 0.0.0.0
      port: 3010
      namespace: rest-mcp-dual-exposure-mcp
      description: MCP server exposing Salesforce Rest Mcp Dual Exposure for AI agents.
      tools:
      - name: example
        description: Wraps a Salesforce REST API as a capability and exposes both REST + MCP, demonstrating dual exposure on a familiar SaaS surface.
        hints:
          readOnly: true
        call: salesforce.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: rest-mcp-dual-exposure-skills
      description: Agent Skill bundle for Salesforce Rest Mcp Dual Exposure.
      skills:
      - name: rest-mcp-dual-exposure
        description: Wraps a Salesforce REST API as a capability and exposes both REST + MCP, demonstrating dual exposure on a familiar SaaS surface.
        location: file:///opt/naftiko/skills/rest-mcp-dual-exposure
        allowed-tools: example
        tools:
        - name: example
          description: Wraps a Salesforce REST API as a capability and exposes both REST + MCP, demonstrating dual exposure on a familiar SaaS surface.
          from:
            sourceNamespace: rest-mcp-dual-exposure-mcp
            action: example
---

Wraps a Salesforce REST API as a capability and exposes both REST + MCP, demonstrating dual exposure on a familiar SaaS surface. A working Salesforce capability is more compelling than a deck for a Salesforce employee.
