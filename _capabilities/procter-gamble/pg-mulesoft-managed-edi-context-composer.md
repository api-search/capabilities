---
categories: []
consumed_apis:
- procter-gamble
description: A capability that joins MuleSoft-managed EDI flows + a Salesforce Einstein lookup and returns one composed context object — the integration-sprawl rightsizer for an AI assistant.
layout: capability
naftiko_layer: service-anchored
naftiko_partner: Norbert Anthony
name: Procter & Gamble Pg Mulesoft Managed Edi Context Composer
operations: []
personas: []
provider_name: Procter & Gamble
provider_slug: procter-gamble
search_terms:
- capability
- that
- joins
- mulesoft
- managed
slug: pg-mulesoft-managed-edi-context-composer
source_filename: pg-mulesoft-managed-edi-context-composer.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Procter & Gamble Pg Mulesoft Managed Edi Context Composer
    description: A capability that joins MuleSoft-managed EDI flows + a Salesforce Einstein lookup and returns one composed context object — the integration-sprawl rightsizer for an AI assistant.
    tags:
    - Procter & Gamble
    created: '2026-04-30'
    modified: '2026-04-30'
  binds:
  - namespace: procter-gamble-env
    description: Procter & Gamble credentials.
    keys:
      PROCTER_GAMBLE_API_KEY: PROCTER_GAMBLE_API_KEY
  capability:
    consumes:
    - namespace: procter-gamble
      type: http
      baseUri: https://api.procter-gamble.com
      authentication:
        type: bearer
        token: '{{PROCTER_GAMBLE_API_KEY}}'
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
      namespace: pg-mulesoft-managed-edi-context-composer-rest
      description: REST API for Procter & Gamble Pg Mulesoft Managed Edi Context Composer.
      resources:
      - name: example
        path: /example
        operations:
        - method: GET
          name: example-op
          call: procter-gamble.example-op
    - type: mcp
      address: 0.0.0.0
      port: 3010
      namespace: pg-mulesoft-managed-edi-context-composer-mcp
      description: MCP server exposing Procter & Gamble Pg Mulesoft Managed Edi Context Composer for AI agents.
      tools:
      - name: example
        description: A capability that joins MuleSoft-managed EDI flows + a Salesforce Einstein lookup and returns one composed context object — the integration-sprawl rightsizer for an AI assistant.
        hints:
          readOnly: true
        call: procter-gamble.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: pg-mulesoft-managed-edi-context-composer-skills
      description: Agent Skill bundle for Procter & Gamble Pg Mulesoft Managed Edi Context Composer.
      skills:
      - name: pg-mulesoft-managed-edi-context-composer
        description: A capability that joins MuleSoft-managed EDI flows + a Salesforce Einstein lookup and returns one composed context object — the integration-sprawl rightsizer for an AI assistant.
        location: file:///opt/naftiko/skills/pg-mulesoft-managed-edi-context-composer
        allowed-tools: example
        tools:
        - name: example
          description: A capability that joins MuleSoft-managed EDI flows + a Salesforce Einstein lookup and returns one composed context object — the integration-sprawl rightsizer for an AI assistant.
          from:
            sourceNamespace: pg-mulesoft-managed-edi-context-composer-mcp
            action: example
---

A capability that joins MuleSoft-managed EDI flows + a Salesforce Einstein lookup and returns one composed context object — the integration-sprawl rightsizer for an AI assistant. Senior Director of Enterprise Integration is the persona; MuleSoft + EDI + Salesforce is the actual P&G shape.
