---
categories: []
consumed_apis:
- bnp-paribas
description: A capability that fronts a Tyk-managed BNP banking API as a Naftiko capability with Forward Proxy + Trusted-Header Security — letting BNP's API-First program add agent-shaped MCP without bypassing the gateway.
layout: capability
naftiko_layer: service-anchored
naftiko_partner: Cedric MONIER
name: BNP Paribas Bnp Tyk Gateway Mirrored Banking Capability
operations: []
personas: []
provider_name: BNP Paribas
provider_slug: bnp-paribas
search_terms:
- capability
- that
- fronts
- managed
- banking
slug: bnp-tyk-gateway-mirrored-banking-capability
source_filename: bnp-tyk-gateway-mirrored-banking-capability.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: BNP Paribas Bnp Tyk Gateway Mirrored Banking Capability
    description: A capability that fronts a Tyk-managed BNP banking API as a Naftiko capability with Forward Proxy + Trusted-Header Security — letting BNP's API-First program add agent-shaped MCP without bypassing the gateway.
    tags:
    - BNP Paribas
    created: '2026-04-30'
    modified: '2026-04-30'
  binds:
  - namespace: bnp-paribas-env
    description: BNP Paribas credentials.
    keys:
      BNP_PARIBAS_API_KEY: BNP_PARIBAS_API_KEY
  capability:
    consumes:
    - namespace: bnp-paribas
      type: http
      baseUri: https://api.bnp-paribas.com
      authentication:
        type: bearer
        token: '{{BNP_PARIBAS_API_KEY}}'
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
      namespace: bnp-tyk-gateway-mirrored-banking-capability-rest
      description: REST API for BNP Paribas Bnp Tyk Gateway Mirrored Banking Capability.
      resources:
      - name: example
        path: /example
        operations:
        - method: GET
          name: example-op
          call: bnp-paribas.example-op
    - type: mcp
      address: 0.0.0.0
      port: 3010
      namespace: bnp-tyk-gateway-mirrored-banking-capability-mcp
      description: MCP server exposing BNP Paribas Bnp Tyk Gateway Mirrored Banking Capability for AI agents.
      tools:
      - name: example
        description: A capability that fronts a Tyk-managed BNP banking API as a Naftiko capability with Forward Proxy + Trusted-Header Security — letting BNP's API-First program add agent-shaped MCP without bypassing the gateway.
        hints:
          readOnly: true
        call: bnp-paribas.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: bnp-tyk-gateway-mirrored-banking-capability-skills
      description: Agent Skill bundle for BNP Paribas Bnp Tyk Gateway Mirrored Banking Capability.
      skills:
      - name: bnp-tyk-gateway-mirrored-banking-capability
        description: A capability that fronts a Tyk-managed BNP banking API as a Naftiko capability with Forward Proxy + Trusted-Header Security — letting BNP's API-First program add agent-shaped MCP without bypassing the gateway.
        location: file:///opt/naftiko/skills/bnp-tyk-gateway-mirrored-banking-capability
        allowed-tools: example
        tools:
        - name: example
          description: A capability that fronts a Tyk-managed BNP banking API as a Naftiko capability with Forward Proxy + Trusted-Header Security — letting BNP's API-First program add agent-shaped MCP without bypassing the gateway.
          from:
            sourceNamespace: bnp-tyk-gateway-mirrored-banking-capability-mcp
            action: example
---

A capability that fronts a Tyk-managed BNP banking API as a Naftiko capability with Forward Proxy + Trusted-Header Security — letting BNP's API-First program add agent-shaped MCP without bypassing the gateway. He runs an API-First Program AND BNP runs Tyk; mirroring through the gateway is the only re-engagement framing that respects his existing platform.
