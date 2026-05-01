---
categories: []
consumed_apis:
- northwestern-mutual
description: A capability over a Snowflake-hosted financial-services dataset that exposes governed read MCP tools with PII surface detection + data-classification tags as the Zero-Touch-Governance runtime.
layout: capability
naftiko_layer: service-anchored
naftiko_partner: Supreet Nagi
name: Northwestern Mutual Nwm Snowflake Policy Tagged Data Mcp
operations: []
personas: []
provider_name: Northwestern Mutual
provider_slug: northwestern-mutual
search_terms:
- capability
- over
- snowflake
- hosted
- financial
slug: nwm-snowflake-policy-tagged-data-mcp
source_filename: nwm-snowflake-policy-tagged-data-mcp.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Northwestern Mutual Nwm Snowflake Policy Tagged Data Mcp
    description: A capability over a Snowflake-hosted financial-services dataset that exposes governed read MCP tools with PII surface detection + data-classification tags as the Zero-Touch-Governance runtime.
    tags:
    - Northwestern Mutual
    created: '2026-04-30'
    modified: '2026-04-30'
  binds:
  - namespace: northwestern-mutual-env
    description: Northwestern Mutual credentials.
    keys:
      NORTHWESTERN_MUTUAL_API_KEY: NORTHWESTERN_MUTUAL_API_KEY
  capability:
    consumes:
    - namespace: northwestern-mutual
      type: http
      baseUri: https://api.northwestern-mutual.com
      authentication:
        type: bearer
        token: '{{NORTHWESTERN_MUTUAL_API_KEY}}'
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
      namespace: nwm-snowflake-policy-tagged-data-mcp-rest
      description: REST API for Northwestern Mutual Nwm Snowflake Policy Tagged Data Mcp.
      resources:
      - name: example
        path: /example
        operations:
        - method: GET
          name: example-op
          call: northwestern-mutual.example-op
    - type: mcp
      address: 0.0.0.0
      port: 3010
      namespace: nwm-snowflake-policy-tagged-data-mcp-mcp
      description: MCP server exposing Northwestern Mutual Nwm Snowflake Policy Tagged Data Mcp for AI agents.
      tools:
      - name: example
        description: A capability over a Snowflake-hosted financial-services dataset that exposes governed read MCP tools with PII surface detection + data-classification tags as the Zero-Touch-Governance runtime.
        hints:
          readOnly: true
        call: northwestern-mutual.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: nwm-snowflake-policy-tagged-data-mcp-skills
      description: Agent Skill bundle for Northwestern Mutual Nwm Snowflake Policy Tagged Data Mcp.
      skills:
      - name: nwm-snowflake-policy-tagged-data-mcp
        description: A capability over a Snowflake-hosted financial-services dataset that exposes governed read MCP tools with PII surface detection + data-classification tags as the Zero-Touch-Governance runtime.
        location: file:///opt/naftiko/skills/nwm-snowflake-policy-tagged-data-mcp
        allowed-tools: example
        tools:
        - name: example
          description: A capability over a Snowflake-hosted financial-services dataset that exposes governed read MCP tools with PII surface detection + data-classification tags as the Zero-Touch-Governance runtime.
          from:
            sourceNamespace: nwm-snowflake-policy-tagged-data-mcp-mcp
            action: example
---

A capability over a Snowflake-hosted financial-services dataset that exposes governed read MCP tools with PII surface detection + data-classification tags as the Zero-Touch-Governance runtime. Her Zero-Touch Governance thesis runs on the data platform — Snowflake is NWM's, so the runtime story lands.
