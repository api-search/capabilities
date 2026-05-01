---
categories: []
consumed_apis:
- cvent
description: 'A Cvent-flavored capability bundle implementing the "Rightsize AI context" use case (Guide-Use-Cases #2): typed outputParameters and JSONPath that shape a verbose Cvent endpoint into a token-budgeted agent context object.'
layout: capability
naftiko_layer: proposed
naftiko_partner: Jeff Seifert
name: Cvent Rightsize Context Bundle
operations: []
personas: []
provider_name: Cvent
provider_slug: cvent
search_terms:
- cvent
- flavored
- capability
- bundle
- implementing
slug: rightsize-context-bundle
source_filename: rightsize-context-bundle.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Cvent Rightsize Context Bundle
    description: 'A Cvent-flavored capability bundle implementing the "Rightsize AI context" use case (Guide-Use-Cases #2): typed outputParameters and JSONPath that shape a verbose Cvent endpoint into a token-budgeted agent context object.'
    tags:
    - Cvent
    created: '2026-04-30'
    modified: '2026-04-30'
  binds:
  - namespace: cvent-env
    description: Cvent credentials.
    keys:
      CVENT_API_KEY: CVENT_API_KEY
  capability:
    consumes:
    - namespace: cvent
      type: http
      baseUri: https://api.cvent.com
      authentication:
        type: bearer
        token: '{{CVENT_API_KEY}}'
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
      namespace: rightsize-context-bundle-rest
      description: REST API for Cvent Rightsize Context Bundle.
      resources:
      - name: example
        path: /example
        operations:
        - method: GET
          name: example-op
          call: cvent.example-op
    - type: mcp
      address: 0.0.0.0
      port: 3010
      namespace: rightsize-context-bundle-mcp
      description: MCP server exposing Cvent Rightsize Context Bundle for AI agents.
      tools:
      - name: example
        description: 'A Cvent-flavored capability bundle implementing the "Rightsize AI context" use case (Guide-Use-Cases #2): typed outputParameters and JSONPath that shape a verbose Cvent endpoint into a token-budgeted agent context object.'
        hints:
          readOnly: true
        call: cvent.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: rightsize-context-bundle-skills
      description: Agent Skill bundle for Cvent Rightsize Context Bundle.
      skills:
      - name: rightsize-context-bundle
        description: 'A Cvent-flavored capability bundle implementing the "Rightsize AI context" use case (Guide-Use-Cases #2): typed outputParameters and JSONPath that shape a verbose Cvent endpoint into a token-budgeted agent context object.'
        location: file:///opt/naftiko/skills/rightsize-context-bundle
        allowed-tools: example
        tools:
        - name: example
          description: 'A Cvent-flavored capability bundle implementing the "Rightsize AI context" use case (Guide-Use-Cases #2): typed outputParameters and JSONPath that shape a verbose Cvent endpoint into a token-budgeted agent context object.'
          from:
            sourceNamespace: rightsize-context-bundle-mcp
            action: example
---

A Cvent-flavored capability bundle implementing the "Rightsize AI context" use case (Guide-Use-Cases #2): typed outputParameters and JSONPath that shape a verbose Cvent endpoint into a token-budgeted agent context object. He explicitly named context engineering; this use case is its canonical demo.
