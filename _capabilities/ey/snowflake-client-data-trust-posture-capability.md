---
categories: []
consumed_apis:
- ey
description: A capability over a Snowflake-hosted client engagement dataset that leads with governance + sensitivity tags + PII detection — the "trust posture" artifact for re-engagement.
layout: capability
naftiko_layer: service-anchored
naftiko_partner: Ulrich Trinkaus
name: EY Snowflake Client Data Trust Posture Capability
operations: []
personas: []
provider_name: EY
provider_slug: ey
search_terms:
- capability
- over
- snowflake
- hosted
- client
slug: snowflake-client-data-trust-posture-capability
source_filename: snowflake-client-data-trust-posture-capability.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: EY Snowflake Client Data Trust Posture Capability
    description: A capability over a Snowflake-hosted client engagement dataset that leads with governance + sensitivity tags + PII detection — the "trust posture" artifact for re-engagement.
    tags:
    - EY
    created: '2026-04-30'
    modified: '2026-04-30'
  binds:
  - namespace: ey-env
    description: EY credentials.
    keys:
      EY_API_KEY: EY_API_KEY
  capability:
    consumes:
    - namespace: ey
      type: http
      baseUri: https://api.ey.com
      authentication:
        type: bearer
        token: '{{EY_API_KEY}}'
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
      namespace: snowflake-client-data-trust-posture-capability-rest
      description: REST API for EY Snowflake Client Data Trust Posture Capability.
      resources:
      - name: example
        path: /example
        operations:
        - method: GET
          name: example-op
          call: ey.example-op
    - type: mcp
      address: 0.0.0.0
      port: 3010
      namespace: snowflake-client-data-trust-posture-capability-mcp
      description: MCP server exposing EY Snowflake Client Data Trust Posture Capability for AI agents.
      tools:
      - name: example
        description: A capability over a Snowflake-hosted client engagement dataset that leads with governance + sensitivity tags + PII detection — the "trust posture" artifact for re-engagement.
        hints:
          readOnly: true
        call: ey.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: snowflake-client-data-trust-posture-capability-skills
      description: Agent Skill bundle for EY Snowflake Client Data Trust Posture Capability.
      skills:
      - name: snowflake-client-data-trust-posture-capability
        description: A capability over a Snowflake-hosted client engagement dataset that leads with governance + sensitivity tags + PII detection — the "trust posture" artifact for re-engagement.
        location: file:///opt/naftiko/skills/snowflake-client-data-trust-posture-capability
        allowed-tools: example
        tools:
        - name: example
          description: A capability over a Snowflake-hosted client engagement dataset that leads with governance + sensitivity tags + PII detection — the "trust posture" artifact for re-engagement.
          from:
            sourceNamespace: snowflake-client-data-trust-posture-capability-mcp
            action: example
---

A capability over a Snowflake-hosted client engagement dataset that leads with governance + sensitivity tags + PII detection — the "trust posture" artifact for re-engagement. His feedback explicitly asked for governance-and-trust as the lead; client data on Snowflake is exactly where that posture lands.
