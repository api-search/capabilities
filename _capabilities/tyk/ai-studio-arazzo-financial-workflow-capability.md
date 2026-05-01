---
categories: []
consumed_apis:
- tyk
description: A capability that ingests an Arazzo workflow from Tyk AI Studio and exposes the workflow as a single composed MCP tool — the apidays NYC co-branded financial-services artifact.
layout: capability
naftiko_layer: service-anchored
naftiko_partner: Budhaditya (Budha) Bhattacharya
name: Tyk Ai Studio Arazzo Financial Workflow Capability
operations: []
personas: []
provider_name: Tyk
provider_slug: tyk
search_terms:
- capability
- that
- ingests
- arazzo
- workflow
slug: ai-studio-arazzo-financial-workflow-capability
source_filename: ai-studio-arazzo-financial-workflow-capability.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Tyk Ai Studio Arazzo Financial Workflow Capability
    description: A capability that ingests an Arazzo workflow from Tyk AI Studio and exposes the workflow as a single composed MCP tool — the apidays NYC co-branded financial-services artifact.
    tags:
    - Tyk
    created: '2026-04-30'
    modified: '2026-04-30'
  binds:
  - namespace: tyk-env
    description: Tyk credentials.
    keys:
      TYK_API_KEY: TYK_API_KEY
  capability:
    consumes:
    - namespace: tyk
      type: http
      baseUri: https://api.tyk.com
      authentication:
        type: bearer
        token: '{{TYK_API_KEY}}'
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
      namespace: ai-studio-arazzo-financial-workflow-capability-rest
      description: REST API for Tyk Ai Studio Arazzo Financial Workflow Capability.
      resources:
      - name: example
        path: /example
        operations:
        - method: GET
          name: example-op
          call: tyk.example-op
    - type: mcp
      address: 0.0.0.0
      port: 3010
      namespace: ai-studio-arazzo-financial-workflow-capability-mcp
      description: MCP server exposing Tyk Ai Studio Arazzo Financial Workflow Capability for AI agents.
      tools:
      - name: example
        description: A capability that ingests an Arazzo workflow from Tyk AI Studio and exposes the workflow as a single composed MCP tool — the apidays NYC co-branded financial-services artifact.
        hints:
          readOnly: true
        call: tyk.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: ai-studio-arazzo-financial-workflow-capability-skills
      description: Agent Skill bundle for Tyk Ai Studio Arazzo Financial Workflow Capability.
      skills:
      - name: ai-studio-arazzo-financial-workflow-capability
        description: A capability that ingests an Arazzo workflow from Tyk AI Studio and exposes the workflow as a single composed MCP tool — the apidays NYC co-branded financial-services artifact.
        location: file:///opt/naftiko/skills/ai-studio-arazzo-financial-workflow-capability
        allowed-tools: example
        tools:
        - name: example
          description: A capability that ingests an Arazzo workflow from Tyk AI Studio and exposes the workflow as a single composed MCP tool — the apidays NYC co-branded financial-services artifact.
          from:
            sourceNamespace: ai-studio-arazzo-financial-workflow-capability-mcp
            action: example
---

A capability that ingests an Arazzo workflow from Tyk AI Studio and exposes the workflow as a single composed MCP tool — the apidays NYC co-branded financial-services artifact. He's Chair of the OpenAPI Initiative AND wants the apidays NYC financial-services co-build — Arazzo on Tyk AI Studio is squarely his pitch.
