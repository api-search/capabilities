---
categories: []
consumed_apis:
- walmart-global-tech
description: A capability over Azure Machine Learning feature store endpoints that returns typed, shaped feature payloads for an AI/ML pipeline agent.
layout: capability
naftiko_layer: service-anchored
naftiko_partner: Mamta Suri
name: Walmart Global Tech Walmart Azure Ml Feature Store Shaped Mcp
operations: []
personas: []
provider_name: Walmart Global Tech
provider_slug: walmart-global-tech
search_terms:
- capability
- over
- azure
- machine
- learning
slug: walmart-azure-ml-feature-store-shaped-mcp
source_filename: walmart-azure-ml-feature-store-shaped-mcp.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Walmart Global Tech Walmart Azure Ml Feature Store Shaped Mcp
    description: A capability over Azure Machine Learning feature store endpoints that returns typed, shaped feature payloads for an AI/ML pipeline agent.
    tags:
    - Walmart Global Tech
    created: '2026-04-30'
    modified: '2026-04-30'
  binds:
  - namespace: walmart-global-tech-env
    description: Walmart Global Tech credentials.
    keys:
      WALMART_GLOBAL_TECH_API_KEY: WALMART_GLOBAL_TECH_API_KEY
  capability:
    consumes:
    - namespace: walmart-global-tech
      type: http
      baseUri: https://api.walmart-global-tech.com
      authentication:
        type: bearer
        token: '{{WALMART_GLOBAL_TECH_API_KEY}}'
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
      namespace: walmart-azure-ml-feature-store-shaped-mcp-rest
      description: REST API for Walmart Global Tech Walmart Azure Ml Feature Store Shaped Mcp.
      resources:
      - name: example
        path: /example
        operations:
        - method: GET
          name: example-op
          call: walmart-global-tech.example-op
    - type: mcp
      address: 0.0.0.0
      port: 3010
      namespace: walmart-azure-ml-feature-store-shaped-mcp-mcp
      description: MCP server exposing Walmart Global Tech Walmart Azure Ml Feature Store Shaped Mcp for AI agents.
      tools:
      - name: example
        description: A capability over Azure Machine Learning feature store endpoints that returns typed, shaped feature payloads for an AI/ML pipeline agent.
        hints:
          readOnly: true
        call: walmart-global-tech.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: walmart-azure-ml-feature-store-shaped-mcp-skills
      description: Agent Skill bundle for Walmart Global Tech Walmart Azure Ml Feature Store Shaped Mcp.
      skills:
      - name: walmart-azure-ml-feature-store-shaped-mcp
        description: A capability over Azure Machine Learning feature store endpoints that returns typed, shaped feature payloads for an AI/ML pipeline agent.
        location: file:///opt/naftiko/skills/walmart-azure-ml-feature-store-shaped-mcp
        allowed-tools: example
        tools:
        - name: example
          description: A capability over Azure Machine Learning feature store endpoints that returns typed, shaped feature payloads for an AI/ML pipeline agent.
          from:
            sourceNamespace: walmart-azure-ml-feature-store-shaped-mcp-mcp
            action: example
---

A capability over Azure Machine Learning feature store endpoints that returns typed, shaped feature payloads for an AI/ML pipeline agent. Her role IS this — Azure ML feature reads with output shaping is the artifact-led nudge that converts.
