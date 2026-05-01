---
categories: []
consumed_apis:
- jpmorgan-chase
description: A capability that pulls OpenAPI specs out of an AWS API Gateway account (and Kong + Apigee), normalizes them, and republishes the enriched specs back to a portal AND to MCP for IDE-injected developer tooling.
layout: capability
naftiko_layer: service-anchored
naftiko_partner: Mark McAllister
name: JPMorgan Chase Jpmc Aws Api Gateway Openapi Crawl Capability
operations: []
personas: []
provider_name: JPMorgan Chase
provider_slug: jpmorgan-chase
search_terms:
- capability
- that
- pulls
- openapi
- specs
slug: jpmc-aws-api-gateway-openapi-crawl-capability
source_filename: jpmc-aws-api-gateway-openapi-crawl-capability.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: JPMorgan Chase Jpmc Aws Api Gateway Openapi Crawl Capability
    description: A capability that pulls OpenAPI specs out of an AWS API Gateway account (and Kong + Apigee), normalizes them, and republishes the enriched specs back to a portal AND to MCP for IDE-injected developer tooling.
    tags:
    - JPMorgan Chase
    created: '2026-04-30'
    modified: '2026-04-30'
  binds:
  - namespace: jpmorgan-chase-env
    description: JPMorgan Chase credentials.
    keys:
      JPMORGAN_CHASE_API_KEY: JPMORGAN_CHASE_API_KEY
  capability:
    consumes:
    - namespace: jpmorgan-chase
      type: http
      baseUri: https://api.jpmorgan-chase.com
      authentication:
        type: bearer
        token: '{{JPMORGAN_CHASE_API_KEY}}'
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
      namespace: jpmc-aws-api-gateway-openapi-crawl-capability-rest
      description: REST API for JPMorgan Chase Jpmc Aws Api Gateway Openapi Crawl Capability.
      resources:
      - name: example
        path: /example
        operations:
        - method: GET
          name: example-op
          call: jpmorgan-chase.example-op
    - type: mcp
      address: 0.0.0.0
      port: 3010
      namespace: jpmc-aws-api-gateway-openapi-crawl-capability-mcp
      description: MCP server exposing JPMorgan Chase Jpmc Aws Api Gateway Openapi Crawl Capability for AI agents.
      tools:
      - name: example
        description: A capability that pulls OpenAPI specs out of an AWS API Gateway account (and Kong + Apigee), normalizes them, and republishes the enriched specs back to a portal AND to MCP for IDE-injected developer tooling.
        hints:
          readOnly: true
        call: jpmorgan-chase.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: jpmc-aws-api-gateway-openapi-crawl-capability-skills
      description: Agent Skill bundle for JPMorgan Chase Jpmc Aws Api Gateway Openapi Crawl Capability.
      skills:
      - name: jpmc-aws-api-gateway-openapi-crawl-capability
        description: A capability that pulls OpenAPI specs out of an AWS API Gateway account (and Kong + Apigee), normalizes them, and republishes the enriched specs back to a portal AND to MCP for IDE-injected developer tooling.
        location: file:///opt/naftiko/skills/jpmc-aws-api-gateway-openapi-crawl-capability
        allowed-tools: example
        tools:
        - name: example
          description: A capability that pulls OpenAPI specs out of an AWS API Gateway account (and Kong + Apigee), normalizes them, and republishes the enriched specs back to a portal AND to MCP for IDE-injected developer tooling.
          from:
            sourceNamespace: jpmc-aws-api-gateway-openapi-crawl-capability-mcp
            action: example
---

A capability that pulls OpenAPI specs out of an AWS API Gateway account (and Kong + Apigee), normalizes them, and republishes the enriched specs back to a portal AND to MCP for IDE-injected developer tooling. His exact ask — "Pulling OpenAPIs from GitHub repos, AWS API Gateway, and Kong" — and his crawl→enrich→feed-back-to-MCP loop.
