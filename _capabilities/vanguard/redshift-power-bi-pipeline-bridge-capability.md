---
categories: []
consumed_apis:
- vanguard
description: A capability that bridges Amazon Redshift queries to a Power BI dataset refresh, exposing the data-pipeline path as MCP + REST — directly addressing Vanguard's signaled api/eventDriven/dataPipelines gap.
layout: capability
naftiko_layer: service-anchored
naftiko_partner: Vanguard
name: Vanguard Redshift Power Bi Pipeline Bridge Capability
operations: []
personas: []
provider_name: Vanguard
provider_slug: vanguard
search_terms:
- capability
- that
- bridges
- amazon
- redshift
slug: redshift-power-bi-pipeline-bridge-capability
source_filename: redshift-power-bi-pipeline-bridge-capability.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Vanguard Redshift Power Bi Pipeline Bridge Capability
    description: A capability that bridges Amazon Redshift queries to a Power BI dataset refresh, exposing the data-pipeline path as MCP + REST — directly addressing Vanguard's signaled api/eventDriven/dataPipelines gap.
    tags:
    - Vanguard
    created: '2026-04-30'
    modified: '2026-04-30'
  binds:
  - namespace: vanguard-env
    description: Vanguard credentials.
    keys:
      VANGUARD_API_KEY: VANGUARD_API_KEY
  capability:
    consumes:
    - namespace: vanguard
      type: http
      baseUri: https://api.vanguard.com
      authentication:
        type: bearer
        token: '{{VANGUARD_API_KEY}}'
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
      namespace: redshift-power-bi-pipeline-bridge-capability-rest
      description: REST API for Vanguard Redshift Power Bi Pipeline Bridge Capability.
      resources:
      - name: example
        path: /example
        operations:
        - method: GET
          name: example-op
          call: vanguard.example-op
    - type: mcp
      address: 0.0.0.0
      port: 3010
      namespace: redshift-power-bi-pipeline-bridge-capability-mcp
      description: MCP server exposing Vanguard Redshift Power Bi Pipeline Bridge Capability for AI agents.
      tools:
      - name: example
        description: A capability that bridges Amazon Redshift queries to a Power BI dataset refresh, exposing the data-pipeline path as MCP + REST — directly addressing Vanguard's signaled api/eventDriven/dataPipelines gap.
        hints:
          readOnly: true
        call: vanguard.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: redshift-power-bi-pipeline-bridge-capability-skills
      description: Agent Skill bundle for Vanguard Redshift Power Bi Pipeline Bridge Capability.
      skills:
      - name: redshift-power-bi-pipeline-bridge-capability
        description: A capability that bridges Amazon Redshift queries to a Power BI dataset refresh, exposing the data-pipeline path as MCP + REST — directly addressing Vanguard's signaled api/eventDriven/dataPipelines gap.
        location: file:///opt/naftiko/skills/redshift-power-bi-pipeline-bridge-capability
        allowed-tools: example
        tools:
        - name: example
          description: A capability that bridges Amazon Redshift queries to a Power BI dataset refresh, exposing the data-pipeline path as MCP + REST — directly addressing Vanguard's signaled api/eventDriven/dataPipelines gap.
          from:
            sourceNamespace: redshift-power-bi-pipeline-bridge-capability-mcp
            action: example
---

A capability that bridges Amazon Redshift queries to a Power BI dataset refresh, exposing the data-pipeline path as MCP + REST — directly addressing Vanguard's signaled api/eventDriven/dataPipelines gap. The published Signals story IS the Redshift→Power BI pipeline gap; this is the diagnosis-plus-prescription artifact for any of the four contacts.
