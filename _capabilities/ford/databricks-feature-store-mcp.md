---
categories: []
consumed_apis:
- ford
description: A capability over Ford's Azure Databricks feature store, exposing typed model-feature retrieval as MCP for the AI assistant flows John is architecting.
layout: capability
naftiko_layer: service-anchored
naftiko_partner: John Musser
name: Ford Databricks Feature Store Mcp
operations: []
personas: []
provider_name: Ford
provider_slug: ford
search_terms:
- capability
- over
- ford
- azure
- databricks
slug: databricks-feature-store-mcp
source_filename: databricks-feature-store-mcp.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Ford Databricks Feature Store Mcp
    description: A capability over Ford's Azure Databricks feature store, exposing typed model-feature retrieval as MCP for the AI assistant flows John is architecting.
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
      namespace: databricks-feature-store-mcp-rest
      description: REST API for Ford Databricks Feature Store Mcp.
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
      namespace: databricks-feature-store-mcp-mcp
      description: MCP server exposing Ford Databricks Feature Store Mcp for AI agents.
      tools:
      - name: example
        description: A capability over Ford's Azure Databricks feature store, exposing typed model-feature retrieval as MCP for the AI assistant flows John is architecting.
        hints:
          readOnly: true
        call: ford.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: databricks-feature-store-mcp-skills
      description: Agent Skill bundle for Ford Databricks Feature Store Mcp.
      skills:
      - name: databricks-feature-store-mcp
        description: A capability over Ford's Azure Databricks feature store, exposing typed model-feature retrieval as MCP for the AI assistant flows John is architecting.
        location: file:///opt/naftiko/skills/databricks-feature-store-mcp
        allowed-tools: example
        tools:
        - name: example
          description: A capability over Ford's Azure Databricks feature store, exposing typed model-feature retrieval as MCP for the AI assistant flows John is architecting.
          from:
            sourceNamespace: databricks-feature-store-mcp-mcp
            action: example
---

A capability over Ford's Azure Databricks feature store, exposing typed model-feature retrieval as MCP for the AI assistant flows John is architecting. Ford's AI architecture sits on Databricks; agent-grade access to features is a credible Fortune 50 use case.
