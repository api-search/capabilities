---
categories: []
consumed_apis:
- speakeasy
description: A capability paired with a follow-on episode/article on "spec-driven SDKs from spec-driven integrations."
layout: capability
naftiko_layer: proposed
naftiko_partner: Daniel Kovac
name: Speakeasy Spec Driven Sdks From Spec Driven Integrations Capability
operations: []
personas: []
provider_name: Speakeasy
provider_slug: speakeasy
search_terms:
- capability
- paired
- with
- follow
- episode
slug: spec-driven-sdks-from-spec-driven-integrations-capability
source_filename: spec-driven-sdks-from-spec-driven-integrations-capability.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Speakeasy Spec Driven Sdks From Spec Driven Integrations Capability
    description: A capability paired with a follow-on episode/article on "spec-driven SDKs from spec-driven integrations."
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
      namespace: spec-driven-sdks-from-spec-driven-integrations-capability-rest
      description: REST API for Speakeasy Spec Driven Sdks From Spec Driven Integrations Capability.
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
      namespace: spec-driven-sdks-from-spec-driven-integrations-capability-mcp
      description: MCP server exposing Speakeasy Spec Driven Sdks From Spec Driven Integrations Capability for AI agents.
      tools:
      - name: example
        description: A capability paired with a follow-on episode/article on "spec-driven SDKs from spec-driven integrations."
        hints:
          readOnly: true
        call: speakeasy.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: spec-driven-sdks-from-spec-driven-integrations-capability-skills
      description: Agent Skill bundle for Speakeasy Spec Driven Sdks From Spec Driven Integrations Capability.
      skills:
      - name: spec-driven-sdks-from-spec-driven-integrations-capability
        description: A capability paired with a follow-on episode/article on "spec-driven SDKs from spec-driven integrations."
        location: file:///opt/naftiko/skills/spec-driven-sdks-from-spec-driven-integrations-capability
        allowed-tools: example
        tools:
        - name: example
          description: A capability paired with a follow-on episode/article on "spec-driven SDKs from spec-driven integrations."
          from:
            sourceNamespace: spec-driven-sdks-from-spec-driven-integrations-capability-mcp
            action: example
---

A capability paired with a follow-on episode/article on "spec-driven SDKs from spec-driven integrations." The narrative is sitting there from the podcast; one more artifact moves it from conversation to category.
