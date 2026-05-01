---
categories: []
consumed_apis:
- ford
description: A composite Compose AI Context capability that fans out to Ford's Salesforce Service Cloud + Sales Cloud + Apigee dealer APIs and returns one shaped context object.
layout: capability
naftiko_layer: service-anchored
naftiko_partner: John Musser
name: Ford Salesforce Service Cloud Dealer Context
operations: []
personas: []
provider_name: Ford
provider_slug: ford
search_terms:
- composite
- compose
- context
- capability
- that
slug: salesforce-service-cloud-dealer-context
source_filename: salesforce-service-cloud-dealer-context.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Ford Salesforce Service Cloud Dealer Context
    description: A composite Compose AI Context capability that fans out to Ford's Salesforce Service Cloud + Sales Cloud + Apigee dealer APIs and returns one shaped context object.
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
      namespace: salesforce-service-cloud-dealer-context-rest
      description: REST API for Ford Salesforce Service Cloud Dealer Context.
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
      namespace: salesforce-service-cloud-dealer-context-mcp
      description: MCP server exposing Ford Salesforce Service Cloud Dealer Context for AI agents.
      tools:
      - name: example
        description: A composite Compose AI Context capability that fans out to Ford's Salesforce Service Cloud + Sales Cloud + Apigee dealer APIs and returns one shaped context object.
        hints:
          readOnly: true
        call: ford.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: salesforce-service-cloud-dealer-context-skills
      description: Agent Skill bundle for Ford Salesforce Service Cloud Dealer Context.
      skills:
      - name: salesforce-service-cloud-dealer-context
        description: A composite Compose AI Context capability that fans out to Ford's Salesforce Service Cloud + Sales Cloud + Apigee dealer APIs and returns one shaped context object.
        location: file:///opt/naftiko/skills/salesforce-service-cloud-dealer-context
        allowed-tools: example
        tools:
        - name: example
          description: A composite Compose AI Context capability that fans out to Ford's Salesforce Service Cloud + Sales Cloud + Apigee dealer APIs and returns one shaped context object.
          from:
            sourceNamespace: salesforce-service-cloud-dealer-context-mcp
            action: example
---

A composite Compose AI Context capability that fans out to Ford's Salesforce Service Cloud + Sales Cloud + Apigee dealer APIs and returns one shaped context object. His Ford proposal calls for Compose AI Context across vehicle/dealer/customer surfaces; Service Cloud is Ford's actual customer system.
