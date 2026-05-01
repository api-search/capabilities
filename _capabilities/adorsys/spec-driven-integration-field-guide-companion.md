---
categories: []
consumed_apis:
- adorsys
description: Reference capability that compiles every Spec-Driven Integration concept (consumes adapter, exposes block, governance ruleset, lint pass, JSONPath shaping) into one annotated YAML used as the working example in Daniel's wiki co-author project.
layout: capability
naftiko_layer: proposed
naftiko_partner: Daniel Kocot
name: Adorsys Spec Driven Integration Field Guide Companion
operations: []
personas: []
provider_name: Adorsys
provider_slug: adorsys
search_terms:
- reference
- capability
- that
- compiles
- every
slug: spec-driven-integration-field-guide-companion
source_filename: spec-driven-integration-field-guide-companion.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Adorsys Spec Driven Integration Field Guide Companion
    description: Reference capability that compiles every Spec-Driven Integration concept (consumes adapter, exposes block, governance ruleset, lint pass, JSONPath shaping) into one annotated YAML used as the working example in Daniel's wiki co-author project.
    tags:
    - Adorsys
    created: '2026-04-30'
    modified: '2026-04-30'
  binds:
  - namespace: adorsys-env
    description: Adorsys credentials.
    keys:
      ADORSYS_API_KEY: ADORSYS_API_KEY
  capability:
    consumes:
    - namespace: adorsys
      type: http
      baseUri: https://api.adorsys.com
      authentication:
        type: bearer
        token: '{{ADORSYS_API_KEY}}'
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
      namespace: spec-driven-integration-field-guide-companion-rest
      description: REST API for Adorsys Spec Driven Integration Field Guide Companion.
      resources:
      - name: example
        path: /example
        operations:
        - method: GET
          name: example-op
          call: adorsys.example-op
    - type: mcp
      address: 0.0.0.0
      port: 3010
      namespace: spec-driven-integration-field-guide-companion-mcp
      description: MCP server exposing Adorsys Spec Driven Integration Field Guide Companion for AI agents.
      tools:
      - name: example
        description: Reference capability that compiles every Spec-Driven Integration concept (consumes adapter, exposes block, governance ruleset, lint pass, JSONPath shaping) into one annotated YAML used as the working example in Daniel's wiki co-author project.
        hints:
          readOnly: true
        call: adorsys.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: spec-driven-integration-field-guide-companion-skills
      description: Agent Skill bundle for Adorsys Spec Driven Integration Field Guide Companion.
      skills:
      - name: spec-driven-integration-field-guide-companion
        description: Reference capability that compiles every Spec-Driven Integration concept (consumes adapter, exposes block, governance ruleset, lint pass, JSONPath shaping) into one annotated YAML used as the working example in Daniel's wiki co-author project.
        location: file:///opt/naftiko/skills/spec-driven-integration-field-guide-companion
        allowed-tools: example
        tools:
        - name: example
          description: Reference capability that compiles every Spec-Driven Integration concept (consumes adapter, exposes block, governance ruleset, lint pass, JSONPath shaping) into one annotated YAML used as the working example in Daniel's wiki co-author project.
          from:
            sourceNamespace: spec-driven-integration-field-guide-companion-mcp
            action: example
---

Reference capability that compiles every Spec-Driven Integration concept (consumes adapter, exposes block, governance ruleset, lint pass, JSONPath shaping) into one annotated YAML used as the working example in Daniel's wiki co-author project. His recommendations call out co-authoring a Spec-Driven Integration field guide; this is the citation-ready artifact the guide will reference.
