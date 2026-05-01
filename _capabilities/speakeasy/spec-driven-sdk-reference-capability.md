---
categories: []
consumed_apis:
- speakeasy
description: A reference capability where the exposed REST adapter is wired through Speakeasy SDK generation — published as the joint reference architecture.
layout: capability
naftiko_layer: proposed
naftiko_partner: Daniel Kovac
name: Speakeasy Spec Driven Sdk Reference Capability
operations: []
personas: []
provider_name: Speakeasy
provider_slug: speakeasy
search_terms:
- reference
- capability
- where
- exposed
- rest
slug: spec-driven-sdk-reference-capability
source_filename: spec-driven-sdk-reference-capability.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Speakeasy Spec Driven Sdk Reference Capability
    description: A reference capability where the exposed REST adapter is wired through Speakeasy SDK generation — published as the joint reference architecture.
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
      namespace: spec-driven-sdk-reference-capability-rest
      description: REST API for Speakeasy Spec Driven Sdk Reference Capability.
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
      namespace: spec-driven-sdk-reference-capability-mcp
      description: MCP server exposing Speakeasy Spec Driven Sdk Reference Capability for AI agents.
      tools:
      - name: example
        description: A reference capability where the exposed REST adapter is wired through Speakeasy SDK generation — published as the joint reference architecture.
        hints:
          readOnly: true
        call: speakeasy.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: spec-driven-sdk-reference-capability-skills
      description: Agent Skill bundle for Speakeasy Spec Driven Sdk Reference Capability.
      skills:
      - name: spec-driven-sdk-reference-capability
        description: A reference capability where the exposed REST adapter is wired through Speakeasy SDK generation — published as the joint reference architecture.
        location: file:///opt/naftiko/skills/spec-driven-sdk-reference-capability
        allowed-tools: example
        tools:
        - name: example
          description: A reference capability where the exposed REST adapter is wired through Speakeasy SDK generation — published as the joint reference architecture.
          from:
            sourceNamespace: spec-driven-sdk-reference-capability-mcp
            action: example
---

A reference capability where the exposed REST adapter is wired through Speakeasy SDK generation — published as the joint reference architecture. His next-step is "using them as a reference model"; a built reference makes the model concrete.
