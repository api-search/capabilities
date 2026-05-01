---
categories: []
consumed_apis:
- humana
description: A capability over Azure Databricks-hosted claims data, exposing read-only deterministic MCP tools with HIPAA-shaped governance + PII detection.
layout: capability
naftiko_layer: service-anchored
naftiko_partner: Humana
name: Humana Databricks Payer Claims Deterministic Capability
operations: []
personas: []
provider_name: Humana
provider_slug: humana
search_terms:
- capability
- over
- azure
- databricks
- hosted
slug: databricks-payer-claims-deterministic-capability
source_filename: databricks-payer-claims-deterministic-capability.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Humana Databricks Payer Claims Deterministic Capability
    description: A capability over Azure Databricks-hosted claims data, exposing read-only deterministic MCP tools with HIPAA-shaped governance + PII detection.
    tags:
    - Humana
    created: '2026-04-30'
    modified: '2026-04-30'
  binds:
  - namespace: humana-env
    description: Humana credentials.
    keys:
      HUMANA_API_KEY: HUMANA_API_KEY
  capability:
    consumes:
    - namespace: humana
      type: http
      baseUri: https://api.humana.com
      authentication:
        type: bearer
        token: '{{HUMANA_API_KEY}}'
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
      namespace: databricks-payer-claims-deterministic-capability-rest
      description: REST API for Humana Databricks Payer Claims Deterministic Capability.
      resources:
      - name: example
        path: /example
        operations:
        - method: GET
          name: example-op
          call: humana.example-op
    - type: mcp
      address: 0.0.0.0
      port: 3010
      namespace: databricks-payer-claims-deterministic-capability-mcp
      description: MCP server exposing Humana Databricks Payer Claims Deterministic Capability for AI agents.
      tools:
      - name: example
        description: A capability over Azure Databricks-hosted claims data, exposing read-only deterministic MCP tools with HIPAA-shaped governance + PII detection.
        hints:
          readOnly: true
        call: humana.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: databricks-payer-claims-deterministic-capability-skills
      description: Agent Skill bundle for Humana Databricks Payer Claims Deterministic Capability.
      skills:
      - name: databricks-payer-claims-deterministic-capability
        description: A capability over Azure Databricks-hosted claims data, exposing read-only deterministic MCP tools with HIPAA-shaped governance + PII detection.
        location: file:///opt/naftiko/skills/databricks-payer-claims-deterministic-capability
        allowed-tools: example
        tools:
        - name: example
          description: A capability over Azure Databricks-hosted claims data, exposing read-only deterministic MCP tools with HIPAA-shaped governance + PII detection.
          from:
            sourceNamespace: databricks-payer-claims-deterministic-capability-mcp
            action: example
---

A capability over Azure Databricks-hosted claims data, exposing read-only deterministic MCP tools with HIPAA-shaped governance + PII detection. Payer claims on Databricks is the highest-stakes payer-grade artifact; deterministic agent reads is the LinkedIn-pipeline conversion hook.
