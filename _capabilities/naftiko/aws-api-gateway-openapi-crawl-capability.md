---
categories: []
consumed_apis: []
description: A capability that pulls OpenAPI specs out of an AWS API Gateway account (and Kong + Apigee), normalizes them, and republishes the enriched specs back to a portal AND to MCP for IDE-injected developer tooling.
layout: capability
naftiko_layer: service-anchored
naftiko_partner: Mark McAllister
name: Aws Api Gateway Openapi Crawl Capability
operations: []
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- capability
- that
- pulls
- openapi
- specs
slug: aws-api-gateway-openapi-crawl-capability
source_filename: aws-api-gateway-openapi-crawl-capability.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
  title: Aws Api Gateway Openapi Crawl Capability
  description: A capability that pulls OpenAPI specs out of an AWS API Gateway account (and Kong + Apigee), normalizes them, and republishes the enriched specs back to a portal AND to MCP for IDE-injected developer tooling.
  tags:
  Naftiko
  created:'2026-05-01'
  modified:'2026-05-01'
  binds:
  namespace: naftiko-env
  description: Naftiko credentials.
  keys:
  NAFTIKO_API_KEY: NAFTIKO_API_KEY
  capability:
  consumes:
  namespace: naftiko
  type: http
  baseUri: https://api.naftiko.com
  authentication:
  type: bearer
  token:'{{NAFTIKO_API_KEY}}'
  resources:
  name: example
  path: /example
  operations:
  name: example-op
  method: GET
  exposes:
  type: rest
  address: 0.0.0.0
  port: 8080
  namespace: aws-api-gateway-openapi-crawl-capability-rest
  description: REST API for Aws Api Gateway Openapi Crawl Capability.
  resources:
  name: example
  path: /example
  operations:
  method: GET
  name: example-op
  call: naftiko.example-op
  type: mcp
  address: 0.0.0.0
  port: 3010
  namespace: aws-api-gateway-openapi-crawl-capability-mcp
  description: MCP server exposing Aws Api Gateway Openapi Crawl Capability for AI agents.
  tools:
  name: example
  description: A capability that pulls OpenAPI specs out of an AWS API Gateway account (and Kong + Apigee), normalizes them, and republishes the enriched specs back to a portal AND to MCP for IDE-injected developer tooling.
  hints:
  readOnly: true
  call: naftiko.example-op
  type: skill
  address: 0.0.0.0
  port: 3011
  namespace: aws-api-gateway-openapi-crawl-capability-skills
  description: Agent Skill bundle for Aws Api Gateway Openapi Crawl Capability.
  skills:
  name: aws-api-gateway-openapi-crawl-capability
  description: A capability that pulls OpenAPI specs out of an AWS API Gateway account (and Kong + Apigee), normalizes them, and republishes the enriched specs back to a portal AND to MCP for IDE-injected developer tooling.
  location: file:///opt/naftiko/skills/aws-api-gateway-openapi-crawl-capability
  allowed-tools: example
  tools:
  name: example
  description: A capability that pulls OpenAPI specs out of an AWS API Gateway account (and Kong + Apigee), normalizes them, and republishes the enriched specs back to a portal AND to MCP for IDE-injected developer tooling.
  from:
  sourceNamespace: aws-api-gateway-openapi-crawl-capability-mcp
  action: example
---

A capability that pulls OpenAPI specs out of an AWS API Gateway account (and Kong + Apigee), normalizes them, and republishes the enriched specs back to a portal AND to MCP for IDE-injected developer tooling.
