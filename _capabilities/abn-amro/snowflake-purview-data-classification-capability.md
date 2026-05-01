---
categories: []
consumed_apis:
- abn-amro
description: A capability over Snowflake-hosted banking data with Microsoft Purview data-classification labels surfaced as Naftiko sensitivity tags.
layout: capability
naftiko_layer: service-anchored
naftiko_partner: ABN AMRO Bank
name: ABN AMRO Bank Snowflake Purview Data Classification Capability
operations: []
personas: []
provider_name: ABN AMRO Bank
provider_slug: abn-amro
search_terms:
- capability
- over
- snowflake
- hosted
- banking
slug: snowflake-purview-data-classification-capability
source_filename: snowflake-purview-data-classification-capability.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: ABN AMRO Bank Snowflake Purview Data Classification Capability
    description: A capability over Snowflake-hosted banking data with Microsoft Purview data-classification labels surfaced as Naftiko sensitivity tags.
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
      namespace: snowflake-purview-data-classification-capability-rest
      description: REST API for ABN AMRO Bank Snowflake Purview Data Classification Capability.
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
      namespace: snowflake-purview-data-classification-capability-mcp
      description: MCP server exposing ABN AMRO Bank Snowflake Purview Data Classification Capability for AI agents.
      tools:
      - name: example
        description: A capability over Snowflake-hosted banking data with Microsoft Purview data-classification labels surfaced as Naftiko sensitivity tags.
        hints:
          readOnly: true
        call: abn-amro.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: snowflake-purview-data-classification-capability-skills
      description: Agent Skill bundle for ABN AMRO Bank Snowflake Purview Data Classification Capability.
      skills:
      - name: snowflake-purview-data-classification-capability
        description: A capability over Snowflake-hosted banking data with Microsoft Purview data-classification labels surfaced as Naftiko sensitivity tags.
        location: file:///opt/naftiko/skills/snowflake-purview-data-classification-capability
        allowed-tools: example
        tools:
        - name: example
          description: A capability over Snowflake-hosted banking data with Microsoft Purview data-classification labels surfaced as Naftiko sensitivity tags.
          from:
            sourceNamespace: snowflake-purview-data-classification-capability-mcp
            action: example
---

A capability over Snowflake-hosted banking data with Microsoft Purview data-classification labels surfaced as Naftiko sensitivity tags. Dutch banking + GDPR + classified data = governance-tagged-on-Snowflake is the EU-banking-credible posture.
