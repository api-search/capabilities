---
categories: []
consumed_apis:
- elsevier
description: A capability over a Snowflake-hosted publication / citation dataset, packaged as a downloadable Agent Skill folder + MCP tool with PII detection on author records.
layout: capability
naftiko_layer: service-anchored
naftiko_partner: Joyce Stack
name: Elsevier Snowflake Publication Data Agent Skill
operations: []
personas: []
provider_name: Elsevier
provider_slug: elsevier
search_terms:
- capability
- over
- snowflake
- hosted
- publication
slug: snowflake-publication-data-agent-skill
source_filename: snowflake-publication-data-agent-skill.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Elsevier Snowflake Publication Data Agent Skill
    description: A capability over a Snowflake-hosted publication / citation dataset, packaged as a downloadable Agent Skill folder + MCP tool with PII detection on author records.
    tags:
    - Elsevier
    created: '2026-04-30'
    modified: '2026-04-30'
  binds:
  - namespace: elsevier-env
    description: Elsevier credentials.
    keys:
      ELSEVIER_API_KEY: ELSEVIER_API_KEY
  capability:
    consumes:
    - namespace: elsevier
      type: http
      baseUri: https://api.elsevier.com
      authentication:
        type: bearer
        token: '{{ELSEVIER_API_KEY}}'
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
      namespace: snowflake-publication-data-agent-skill-rest
      description: REST API for Elsevier Snowflake Publication Data Agent Skill.
      resources:
      - name: example
        path: /example
        operations:
        - method: GET
          name: example-op
          call: elsevier.example-op
    - type: mcp
      address: 0.0.0.0
      port: 3010
      namespace: snowflake-publication-data-agent-skill-mcp
      description: MCP server exposing Elsevier Snowflake Publication Data Agent Skill for AI agents.
      tools:
      - name: example
        description: A capability over a Snowflake-hosted publication / citation dataset, packaged as a downloadable Agent Skill folder + MCP tool with PII detection on author records.
        hints:
          readOnly: true
        call: elsevier.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: snowflake-publication-data-agent-skill-skills
      description: Agent Skill bundle for Elsevier Snowflake Publication Data Agent Skill.
      skills:
      - name: snowflake-publication-data-agent-skill
        description: A capability over a Snowflake-hosted publication / citation dataset, packaged as a downloadable Agent Skill folder + MCP tool with PII detection on author records.
        location: file:///opt/naftiko/skills/snowflake-publication-data-agent-skill
        allowed-tools: example
        tools:
        - name: example
          description: A capability over a Snowflake-hosted publication / citation dataset, packaged as a downloadable Agent Skill folder + MCP tool with PII detection on author records.
          from:
            sourceNamespace: snowflake-publication-data-agent-skill-mcp
            action: example
---

A capability over a Snowflake-hosted publication / citation dataset, packaged as a downloadable Agent Skill folder + MCP tool with PII detection on author records. She named agent skills as one of two asks; the publication-data-on-Snowflake demo is the highest-recognition agent skill artifact.
