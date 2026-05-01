---
categories: []
consumed_apis:
- abn-amro
description: A capability that wraps SailPoint identity-governance lookups and exposes them as MCP for an internal agent that needs to verify role + entitlement before acting.
layout: capability
naftiko_layer: service-anchored
naftiko_partner: ABN AMRO Bank
name: ABN AMRO Bank Sailpoint Identity Governance Capability
operations: []
personas: []
provider_name: ABN AMRO Bank
provider_slug: abn-amro
search_terms:
- capability
- that
- wraps
- sailpoint
- identity
slug: sailpoint-identity-governance-capability
source_filename: sailpoint-identity-governance-capability.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: ABN AMRO Bank Sailpoint Identity Governance Capability
    description: A capability that wraps SailPoint identity-governance lookups and exposes them as MCP for an internal agent that needs to verify role + entitlement before acting.
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
      namespace: sailpoint-identity-governance-capability-rest
      description: REST API for ABN AMRO Bank Sailpoint Identity Governance Capability.
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
      namespace: sailpoint-identity-governance-capability-mcp
      description: MCP server exposing ABN AMRO Bank Sailpoint Identity Governance Capability for AI agents.
      tools:
      - name: example
        description: A capability that wraps SailPoint identity-governance lookups and exposes them as MCP for an internal agent that needs to verify role + entitlement before acting.
        hints:
          readOnly: true
        call: abn-amro.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: sailpoint-identity-governance-capability-skills
      description: Agent Skill bundle for ABN AMRO Bank Sailpoint Identity Governance Capability.
      skills:
      - name: sailpoint-identity-governance-capability
        description: A capability that wraps SailPoint identity-governance lookups and exposes them as MCP for an internal agent that needs to verify role + entitlement before acting.
        location: file:///opt/naftiko/skills/sailpoint-identity-governance-capability
        allowed-tools: example
        tools:
        - name: example
          description: A capability that wraps SailPoint identity-governance lookups and exposes them as MCP for an internal agent that needs to verify role + entitlement before acting.
          from:
            sourceNamespace: sailpoint-identity-governance-capability-mcp
            action: example
---

A capability that wraps SailPoint identity-governance lookups and exposes them as MCP for an internal agent that needs to verify role + entitlement before acting. SailPoint is the regulated-banking identity layer; agent-callable identity-governance is differentiator territory.
