---
categories: []
consumed_apis:
- salesforce
description: Compose AI Context (#5) using Salesforce + a complementary system (e.g., Marketing Cloud or an external billing API) as the orchestration example.
layout: capability
naftiko_layer: proposed
naftiko_partner: Kris Harrison
name: Salesforce Customer360 Context Composition
operations: []
personas: []
provider_name: Salesforce
provider_slug: salesforce
search_terms:
- compose
- context
- using
- salesforce
- complementary
slug: customer360-context-composition
source_filename: customer360-context-composition.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Salesforce Customer360 Context Composition
    description: Compose AI Context (#5) using Salesforce + a complementary system (e.g., Marketing Cloud or an external billing API) as the orchestration example.
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
      namespace: customer360-context-composition-rest
      description: REST API for Salesforce Customer360 Context Composition.
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
      namespace: customer360-context-composition-mcp
      description: MCP server exposing Salesforce Customer360 Context Composition for AI agents.
      tools:
      - name: example
        description: Compose AI Context (#5) using Salesforce + a complementary system (e.g., Marketing Cloud or an external billing API) as the orchestration example.
        hints:
          readOnly: true
        call: salesforce.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: customer360-context-composition-skills
      description: Agent Skill bundle for Salesforce Customer360 Context Composition.
      skills:
      - name: customer360-context-composition
        description: Compose AI Context (#5) using Salesforce + a complementary system (e.g., Marketing Cloud or an external billing API) as the orchestration example.
        location: file:///opt/naftiko/skills/customer360-context-composition
        allowed-tools: example
        tools:
        - name: example
          description: Compose AI Context (#5) using Salesforce + a complementary system (e.g., Marketing Cloud or an external billing API) as the orchestration example.
          from:
            sourceNamespace: customer360-context-composition-mcp
            action: example
---

Compose AI Context (#5) using Salesforce + a complementary system (e.g., Marketing Cloud or an external billing API) as the orchestration example. Salesforce's customer-360 narrative aligns directly with multi-source context composition.
