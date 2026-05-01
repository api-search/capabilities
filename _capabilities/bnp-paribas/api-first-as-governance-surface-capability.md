---
categories: []
consumed_apis:
- bnp-paribas
description: A capability annotated against the SDI "specification as governance surface" framing as the API-First Program reading.
layout: capability
naftiko_layer: proposed
naftiko_partner: Cedric MONIER
name: BNP Paribas Api First As Governance Surface Capability
operations: []
personas: []
provider_name: BNP Paribas
provider_slug: bnp-paribas
search_terms:
- capability
- annotated
- against
- specification
- governance
slug: api-first-as-governance-surface-capability
source_filename: api-first-as-governance-surface-capability.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: BNP Paribas Api First As Governance Surface Capability
    description: A capability annotated against the SDI "specification as governance surface" framing as the API-First Program reading.
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
      namespace: api-first-as-governance-surface-capability-rest
      description: REST API for BNP Paribas Api First As Governance Surface Capability.
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
      namespace: api-first-as-governance-surface-capability-mcp
      description: MCP server exposing BNP Paribas Api First As Governance Surface Capability for AI agents.
      tools:
      - name: example
        description: A capability annotated against the SDI "specification as governance surface" framing as the API-First Program reading.
        hints:
          readOnly: true
        call: bnp-paribas.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: api-first-as-governance-surface-capability-skills
      description: Agent Skill bundle for BNP Paribas Api First As Governance Surface Capability.
      skills:
      - name: api-first-as-governance-surface-capability
        description: A capability annotated against the SDI "specification as governance surface" framing as the API-First Program reading.
        location: file:///opt/naftiko/skills/api-first-as-governance-surface-capability
        allowed-tools: example
        tools:
        - name: example
          description: A capability annotated against the SDI "specification as governance surface" framing as the API-First Program reading.
          from:
            sourceNamespace: api-first-as-governance-surface-capability-mcp
            action: example
---

A capability annotated against the SDI "specification as governance surface" framing as the API-First Program reading. His program needs a methodology; SDI is the natural extension of API-First into the agent era.
