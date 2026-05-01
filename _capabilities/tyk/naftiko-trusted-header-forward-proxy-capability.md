---
categories: []
consumed_apis:
- tyk
description: A capability deployed behind a Tyk gateway using Naftiko's Forward Proxy with Trusted-Header Security, illustrating the clean partnership boundary (Tyk = gateway, Naftiko = capability/MCP).
layout: capability
naftiko_layer: proposed
naftiko_partner: Budhaditya (Budha) Bhattacharya
name: Tyk Naftiko Trusted Header Forward Proxy Capability
operations: []
personas: []
provider_name: Tyk
provider_slug: tyk
search_terms:
- capability
- deployed
- behind
- gateway
- using
slug: naftiko-trusted-header-forward-proxy-capability
source_filename: naftiko-trusted-header-forward-proxy-capability.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Tyk Naftiko Trusted Header Forward Proxy Capability
    description: A capability deployed behind a Tyk gateway using Naftiko's Forward Proxy with Trusted-Header Security, illustrating the clean partnership boundary (Tyk = gateway, Naftiko = capability/MCP).
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
      namespace: naftiko-trusted-header-forward-proxy-capability-rest
      description: REST API for Tyk Naftiko Trusted Header Forward Proxy Capability.
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
      namespace: naftiko-trusted-header-forward-proxy-capability-mcp
      description: MCP server exposing Tyk Naftiko Trusted Header Forward Proxy Capability for AI agents.
      tools:
      - name: example
        description: A capability deployed behind a Tyk gateway using Naftiko's Forward Proxy with Trusted-Header Security, illustrating the clean partnership boundary (Tyk = gateway, Naftiko = capability/MCP).
        hints:
          readOnly: true
        call: tyk.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: naftiko-trusted-header-forward-proxy-capability-skills
      description: Agent Skill bundle for Tyk Naftiko Trusted Header Forward Proxy Capability.
      skills:
      - name: naftiko-trusted-header-forward-proxy-capability
        description: A capability deployed behind a Tyk gateway using Naftiko's Forward Proxy with Trusted-Header Security, illustrating the clean partnership boundary (Tyk = gateway, Naftiko = capability/MCP).
        location: file:///opt/naftiko/skills/naftiko-trusted-header-forward-proxy-capability
        allowed-tools: example
        tools:
        - name: example
          description: A capability deployed behind a Tyk gateway using Naftiko's Forward Proxy with Trusted-Header Security, illustrating the clean partnership boundary (Tyk = gateway, Naftiko = capability/MCP).
          from:
            sourceNamespace: naftiko-trusted-header-forward-proxy-capability-mcp
            action: example
---

A capability deployed behind a Tyk gateway using Naftiko's Forward Proxy with Trusted-Header Security, illustrating the clean partnership boundary (Tyk = gateway, Naftiko = capability/MCP). Tyk owns the gateway layer; Naftiko owns the capability/MCP layer. This makes the boundary explicit.
