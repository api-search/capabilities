---
categories: []
consumed_apis:
- speakeasy
description: A capability where the spec is the source of truth for both the engine runtime and the downstream Speakeasy SDK pipeline, demonstrating the deterministic flow end-to-end.
layout: capability
naftiko_layer: proposed
naftiko_partner: Daniel Kovac
name: Speakeasy Deterministic Sdk Pipeline Capability
operations: []
personas: []
provider_name: Speakeasy
provider_slug: speakeasy
search_terms:
- capability
- where
- spec
- source
- truth
slug: deterministic-sdk-pipeline-capability
source_filename: deterministic-sdk-pipeline-capability.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Speakeasy Deterministic Sdk Pipeline Capability
    description: A capability where the spec is the source of truth for both the engine runtime and the downstream Speakeasy SDK pipeline, demonstrating the deterministic flow end-to-end.
    tags:
    - Speakeasy
    created: '2026-04-30'
    modified: '2026-04-30'
  binds:
  - namespace: speakeasy-env
    description: Speakeasy credentials.
    keys:
      SPEAKEASY_API_KEY: SPEAKEASY_API_KEY
  capability:
    consumes:
    - namespace: speakeasy
      type: http
      baseUri: https://api.speakeasy.com
      authentication:
        type: bearer
        token: '{{SPEAKEASY_API_KEY}}'
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
      namespace: deterministic-sdk-pipeline-capability-rest
      description: REST API for Speakeasy Deterministic Sdk Pipeline Capability.
      resources:
      - name: example
        path: /example
        operations:
        - method: GET
          name: example-op
          call: speakeasy.example-op
    - type: mcp
      address: 0.0.0.0
      port: 3010
      namespace: deterministic-sdk-pipeline-capability-mcp
      description: MCP server exposing Speakeasy Deterministic Sdk Pipeline Capability for AI agents.
      tools:
      - name: example
        description: A capability where the spec is the source of truth for both the engine runtime and the downstream Speakeasy SDK pipeline, demonstrating the deterministic flow end-to-end.
        hints:
          readOnly: true
        call: speakeasy.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: deterministic-sdk-pipeline-capability-skills
      description: Agent Skill bundle for Speakeasy Deterministic Sdk Pipeline Capability.
      skills:
      - name: deterministic-sdk-pipeline-capability
        description: A capability where the spec is the source of truth for both the engine runtime and the downstream Speakeasy SDK pipeline, demonstrating the deterministic flow end-to-end.
        location: file:///opt/naftiko/skills/deterministic-sdk-pipeline-capability
        allowed-tools: example
        tools:
        - name: example
          description: A capability where the spec is the source of truth for both the engine runtime and the downstream Speakeasy SDK pipeline, demonstrating the deterministic flow end-to-end.
          from:
            sourceNamespace: deterministic-sdk-pipeline-capability-mcp
            action: example
---

A capability where the spec is the source of truth for both the engine runtime and the downstream Speakeasy SDK pipeline, demonstrating the deterministic flow end-to-end. His Deterministic SDK Generation podcast framed exactly this story; the capability spec is the upstream of that pipeline.
