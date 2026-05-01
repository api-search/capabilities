---
categories: []
consumed_apis:
- vonage
description: A capability over Vonage's Network APIs (Ericsson-aggregated carrier-network surfaces — number verification, location, device status) exposing carrier-grade governed reads as MCP.
layout: capability
naftiko_layer: service-anchored
naftiko_partner: Vonage
name: Vonage Network Api Aggregation Capability
operations: []
personas: []
provider_name: Vonage
provider_slug: vonage
search_terms:
- capability
- over
- vonage
- network
- apis
slug: network-api-aggregation-capability
source_filename: network-api-aggregation-capability.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Vonage Network Api Aggregation Capability
    description: A capability over Vonage's Network APIs (Ericsson-aggregated carrier-network surfaces — number verification, location, device status) exposing carrier-grade governed reads as MCP.
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
      namespace: network-api-aggregation-capability-rest
      description: REST API for Vonage Network Api Aggregation Capability.
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
      namespace: network-api-aggregation-capability-mcp
      description: MCP server exposing Vonage Network Api Aggregation Capability for AI agents.
      tools:
      - name: example
        description: A capability over Vonage's Network APIs (Ericsson-aggregated carrier-network surfaces — number verification, location, device status) exposing carrier-grade governed reads as MCP.
        hints:
          readOnly: true
        call: vonage.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: network-api-aggregation-capability-skills
      description: Agent Skill bundle for Vonage Network Api Aggregation Capability.
      skills:
      - name: network-api-aggregation-capability
        description: A capability over Vonage's Network APIs (Ericsson-aggregated carrier-network surfaces — number verification, location, device status) exposing carrier-grade governed reads as MCP.
        location: file:///opt/naftiko/skills/network-api-aggregation-capability
        allowed-tools: example
        tools:
        - name: example
          description: A capability over Vonage's Network APIs (Ericsson-aggregated carrier-network surfaces — number verification, location, device status) exposing carrier-grade governed reads as MCP.
          from:
            sourceNamespace: network-api-aggregation-capability-mcp
            action: example
---

A capability over Vonage's Network APIs (Ericsson-aggregated carrier-network surfaces — number verification, location, device status) exposing carrier-grade governed reads as MCP. Network APIs are Ericsson's strategic differentiator post-acquisition; an agent-friendly capability over them is a credible podcast hook.
