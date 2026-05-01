---
categories: []
consumed_apis:
- abn-amro
description: A capability that fronts ABN AMRO's PSD2 / open banking surface behind their Kong gateway, exposing MCP without bypassing the gateway and tagged GDPR.
layout: capability
naftiko_layer: service-anchored
naftiko_partner: ABN AMRO Bank
name: ABN AMRO Bank Kong Gateway Psd2 Mirror Capability
operations: []
personas: []
provider_name: ABN AMRO Bank
provider_slug: abn-amro
search_terms:
- capability
- that
- fronts
- amro
- psd2
slug: kong-gateway-psd2-mirror-capability
source_filename: kong-gateway-psd2-mirror-capability.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: ABN AMRO Bank Kong Gateway Psd2 Mirror Capability
    description: A capability that fronts ABN AMRO's PSD2 / open banking surface behind their Kong gateway, exposing MCP without bypassing the gateway and tagged GDPR.
    tags:
    - ABN AMRO Bank
    created: '2026-04-30'
    modified: '2026-04-30'
  binds:
  - namespace: abn-amro-env
    description: ABN AMRO Bank credentials.
    keys:
      ABN_AMRO_API_KEY: ABN_AMRO_API_KEY
  capability:
    consumes:
    - namespace: abn-amro
      type: http
      baseUri: https://api.abn-amro.com
      authentication:
        type: bearer
        token: '{{ABN_AMRO_API_KEY}}'
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
      namespace: kong-gateway-psd2-mirror-capability-rest
      description: REST API for ABN AMRO Bank Kong Gateway Psd2 Mirror Capability.
      resources:
      - name: example
        path: /example
        operations:
        - method: GET
          name: example-op
          call: abn-amro.example-op
    - type: mcp
      address: 0.0.0.0
      port: 3010
      namespace: kong-gateway-psd2-mirror-capability-mcp
      description: MCP server exposing ABN AMRO Bank Kong Gateway Psd2 Mirror Capability for AI agents.
      tools:
      - name: example
        description: A capability that fronts ABN AMRO's PSD2 / open banking surface behind their Kong gateway, exposing MCP without bypassing the gateway and tagged GDPR.
        hints:
          readOnly: true
        call: abn-amro.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: kong-gateway-psd2-mirror-capability-skills
      description: Agent Skill bundle for ABN AMRO Bank Kong Gateway Psd2 Mirror Capability.
      skills:
      - name: kong-gateway-psd2-mirror-capability
        description: A capability that fronts ABN AMRO's PSD2 / open banking surface behind their Kong gateway, exposing MCP without bypassing the gateway and tagged GDPR.
        location: file:///opt/naftiko/skills/kong-gateway-psd2-mirror-capability
        allowed-tools: example
        tools:
        - name: example
          description: A capability that fronts ABN AMRO's PSD2 / open banking surface behind their Kong gateway, exposing MCP without bypassing the gateway and tagged GDPR.
          from:
            sourceNamespace: kong-gateway-psd2-mirror-capability-mcp
            action: example
---

A capability that fronts ABN AMRO's PSD2 / open banking surface behind their Kong gateway, exposing MCP without bypassing the gateway and tagged GDPR. They run Kong — open banking through their actual gateway is the artifact a cold institutional contact respects.
