---
categories: []
consumed_apis:
- procter-gamble
description: A capability over the SAP integration surface that exposes shaped MCP tools the next-gen replacement can call alongside legacy Boomi flows during the migration.
layout: capability
naftiko_layer: service-anchored
naftiko_partner: Norbert Anthony
name: Procter & Gamble Pg Sap Integration Platform Replacement Bridge
operations: []
personas: []
provider_name: Procter & Gamble
provider_slug: procter-gamble
search_terms:
- capability
- over
- integration
- surface
- that
slug: pg-sap-integration-platform-replacement-bridge
source_filename: pg-sap-integration-platform-replacement-bridge.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Procter & Gamble Pg Sap Integration Platform Replacement Bridge
    description: A capability over the SAP integration surface that exposes shaped MCP tools the next-gen replacement can call alongside legacy Boomi flows during the migration.
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
      namespace: pg-sap-integration-platform-replacement-bridge-rest
      description: REST API for Procter & Gamble Pg Sap Integration Platform Replacement Bridge.
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
      namespace: pg-sap-integration-platform-replacement-bridge-mcp
      description: MCP server exposing Procter & Gamble Pg Sap Integration Platform Replacement Bridge for AI agents.
      tools:
      - name: example
        description: A capability over the SAP integration surface that exposes shaped MCP tools the next-gen replacement can call alongside legacy Boomi flows during the migration.
        hints:
          readOnly: true
        call: procter-gamble.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: pg-sap-integration-platform-replacement-bridge-skills
      description: Agent Skill bundle for Procter & Gamble Pg Sap Integration Platform Replacement Bridge.
      skills:
      - name: pg-sap-integration-platform-replacement-bridge
        description: A capability over the SAP integration surface that exposes shaped MCP tools the next-gen replacement can call alongside legacy Boomi flows during the migration.
        location: file:///opt/naftiko/skills/pg-sap-integration-platform-replacement-bridge
        allowed-tools: example
        tools:
        - name: example
          description: A capability over the SAP integration surface that exposes shaped MCP tools the next-gen replacement can call alongside legacy Boomi flows during the migration.
          from:
            sourceNamespace: pg-sap-integration-platform-replacement-bridge-mcp
            action: example
---

A capability over the SAP integration surface that exposes shaped MCP tools the next-gen replacement can call alongside legacy Boomi flows during the migration. He's mid-migration off the SAP integration platform across 4,000+ interfaces — a capability that bridges old + new is the most useful artifact possible.
