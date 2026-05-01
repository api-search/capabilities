---
categories: []
consumed_apis:
- tyk
description: A Tyk-fronted financial-services capability collection — wraps Tyk-managed APIs as Naftiko capabilities, exposes as MCP, layers billing-granularity + retry-safety tags on consumed operations.
layout: capability
naftiko_layer: proposed
naftiko_partner: Budhaditya (Budha) Bhattacharya
name: Tyk Financial Services Gateway Mirror
operations: []
personas: []
provider_name: Tyk
provider_slug: tyk
search_terms:
- fronted
- financial
- services
- capability
- collection
slug: financial-services-gateway-mirror
source_filename: financial-services-gateway-mirror.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Tyk Financial Services Gateway Mirror
    description: A Tyk-fronted financial-services capability collection — wraps Tyk-managed APIs as Naftiko capabilities, exposes as MCP, layers billing-granularity + retry-safety tags on consumed operations.
    tags:
    - Tyk
    created: '2026-04-30'
    modified: '2026-04-30'
  binds:
  - namespace: tyk-env
    description: Tyk credentials.
    keys:
      TYK_API_KEY: TYK_API_KEY
  capability:
    consumes:
    - namespace: tyk
      type: http
      baseUri: https://api.tyk.com
      authentication:
        type: bearer
        token: '{{TYK_API_KEY}}'
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
      namespace: financial-services-gateway-mirror-rest
      description: REST API for Tyk Financial Services Gateway Mirror.
      resources:
      - name: example
        path: /example
        operations:
        - method: GET
          name: example-op
          call: tyk.example-op
    - type: mcp
      address: 0.0.0.0
      port: 3010
      namespace: financial-services-gateway-mirror-mcp
      description: MCP server exposing Tyk Financial Services Gateway Mirror for AI agents.
      tools:
      - name: example
        description: A Tyk-fronted financial-services capability collection — wraps Tyk-managed APIs as Naftiko capabilities, exposes as MCP, layers billing-granularity + retry-safety tags on consumed operations.
        hints:
          readOnly: true
        call: tyk.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: financial-services-gateway-mirror-skills
      description: Agent Skill bundle for Tyk Financial Services Gateway Mirror.
      skills:
      - name: financial-services-gateway-mirror
        description: A Tyk-fronted financial-services capability collection — wraps Tyk-managed APIs as Naftiko capabilities, exposes as MCP, layers billing-granularity + retry-safety tags on consumed operations.
        location: file:///opt/naftiko/skills/financial-services-gateway-mirror
        allowed-tools: example
        tools:
        - name: example
          description: A Tyk-fronted financial-services capability collection — wraps Tyk-managed APIs as Naftiko capabilities, exposes as MCP, layers billing-granularity + retry-safety tags on consumed operations.
          from:
            sourceNamespace: financial-services-gateway-mirror-mcp
            action: example
---

A Tyk-fronted financial-services capability collection — wraps Tyk-managed APIs as Naftiko capabilities, exposes as MCP, layers billing-granularity + retry-safety tags on consumed operations. He wants to partner around Tyk's financial API work surrounding apidays NYC; this is the co-branded booth artifact.
