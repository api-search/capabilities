---
categories: []
consumed_apis:
- ford
description: A collection that mirrors the Ford-Apigee-managed APIs as Naftiko capabilities so each becomes MCP-callable without bypassing the existing gateway.
layout: capability
naftiko_layer: service-anchored
naftiko_partner: John Musser
name: Ford Apigee Mcp Mirror Collection
operations: []
personas: []
provider_name: Ford
provider_slug: ford
search_terms:
- collection
- that
- mirrors
- ford
- apigee
slug: apigee-mcp-mirror-collection
source_filename: apigee-mcp-mirror-collection.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Ford Apigee Mcp Mirror Collection
    description: A collection that mirrors the Ford-Apigee-managed APIs as Naftiko capabilities so each becomes MCP-callable without bypassing the existing gateway.
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
      namespace: apigee-mcp-mirror-collection-rest
      description: REST API for Ford Apigee Mcp Mirror Collection.
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
      namespace: apigee-mcp-mirror-collection-mcp
      description: MCP server exposing Ford Apigee Mcp Mirror Collection for AI agents.
      tools:
      - name: example
        description: A collection that mirrors the Ford-Apigee-managed APIs as Naftiko capabilities so each becomes MCP-callable without bypassing the existing gateway.
        hints:
          readOnly: true
        call: ford.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: apigee-mcp-mirror-collection-skills
      description: Agent Skill bundle for Ford Apigee Mcp Mirror Collection.
      skills:
      - name: apigee-mcp-mirror-collection
        description: A collection that mirrors the Ford-Apigee-managed APIs as Naftiko capabilities so each becomes MCP-callable without bypassing the existing gateway.
        location: file:///opt/naftiko/skills/apigee-mcp-mirror-collection
        allowed-tools: example
        tools:
        - name: example
          description: A collection that mirrors the Ford-Apigee-managed APIs as Naftiko capabilities so each becomes MCP-callable without bypassing the existing gateway.
          from:
            sourceNamespace: apigee-mcp-mirror-collection-mcp
            action: example
---

A collection that mirrors the Ford-Apigee-managed APIs as Naftiko capabilities so each becomes MCP-callable without bypassing the existing gateway. He explicitly asked how MCP integrates with Ford's existing governance stack; this answers Apigee directly.
