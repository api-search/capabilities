---
categories: []
consumed_apis:
- bnp-paribas
description: A BNP-Paribas-flavored API-First capability collection wrapping representative banking APIs, exposed REST + MCP, governance-tagged for banking compliance.
layout: capability
naftiko_layer: proposed
naftiko_partner: Cedric MONIER
name: BNP Paribas Bnp Api First Banking Capability Collection
operations: []
personas: []
provider_name: BNP Paribas
provider_slug: bnp-paribas
search_terms:
- paribas
- flavored
- first
- capability
- collection
slug: bnp-api-first-banking-capability-collection
source_filename: bnp-api-first-banking-capability-collection.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: BNP Paribas Bnp Api First Banking Capability Collection
    description: A BNP-Paribas-flavored API-First capability collection wrapping representative banking APIs, exposed REST + MCP, governance-tagged for banking compliance.
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
      namespace: bnp-api-first-banking-capability-collection-rest
      description: REST API for BNP Paribas Bnp Api First Banking Capability Collection.
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
      namespace: bnp-api-first-banking-capability-collection-mcp
      description: MCP server exposing BNP Paribas Bnp Api First Banking Capability Collection for AI agents.
      tools:
      - name: example
        description: A BNP-Paribas-flavored API-First capability collection wrapping representative banking APIs, exposed REST + MCP, governance-tagged for banking compliance.
        hints:
          readOnly: true
        call: bnp-paribas.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: bnp-api-first-banking-capability-collection-skills
      description: Agent Skill bundle for BNP Paribas Bnp Api First Banking Capability Collection.
      skills:
      - name: bnp-api-first-banking-capability-collection
        description: A BNP-Paribas-flavored API-First capability collection wrapping representative banking APIs, exposed REST + MCP, governance-tagged for banking compliance.
        location: file:///opt/naftiko/skills/bnp-api-first-banking-capability-collection
        allowed-tools: example
        tools:
        - name: example
          description: A BNP-Paribas-flavored API-First capability collection wrapping representative banking APIs, exposed REST + MCP, governance-tagged for banking compliance.
          from:
            sourceNamespace: bnp-api-first-banking-capability-collection-mcp
            action: example
---

A BNP-Paribas-flavored API-First capability collection wrapping representative banking APIs, exposed REST + MCP, governance-tagged for banking compliance. Stalled — needs a built artifact to reopen; he runs an API-First Program, so show what API-First means in the agent era.
