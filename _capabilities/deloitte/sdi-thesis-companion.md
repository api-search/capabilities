---
categories: []
consumed_apis:
- deloitte
description: A capability paired with framework-wiki/Spec-Driven-Integration.md "operational governance of AI" framing as a partner-channel narrative.
layout: capability
naftiko_layer: proposed
naftiko_partner: Fabrice Marque
name: Deloitte Sdi Thesis Companion
operations: []
personas: []
provider_name: Deloitte
provider_slug: deloitte
search_terms:
- capability
- paired
- with
- framework
- wiki
slug: sdi-thesis-companion
source_filename: sdi-thesis-companion.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Deloitte Sdi Thesis Companion
    description: A capability paired with framework-wiki/Spec-Driven-Integration.md "operational governance of AI" framing as a partner-channel narrative.
    tags:
    - Deloitte
    created: '2026-04-30'
    modified: '2026-04-30'
  binds:
  - namespace: deloitte-env
    description: Deloitte credentials.
    keys:
      DELOITTE_API_KEY: DELOITTE_API_KEY
  capability:
    consumes:
    - namespace: deloitte
      type: http
      baseUri: https://api.deloitte.com
      authentication:
        type: bearer
        token: '{{DELOITTE_API_KEY}}'
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
      namespace: sdi-thesis-companion-rest
      description: REST API for Deloitte Sdi Thesis Companion.
      resources:
      - name: example
        path: /example
        operations:
        - method: GET
          name: example-op
          call: deloitte.example-op
    - type: mcp
      address: 0.0.0.0
      port: 3010
      namespace: sdi-thesis-companion-mcp
      description: MCP server exposing Deloitte Sdi Thesis Companion for AI agents.
      tools:
      - name: example
        description: A capability paired with framework-wiki/Spec-Driven-Integration.md "operational governance of AI" framing as a partner-channel narrative.
        hints:
          readOnly: true
        call: deloitte.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: sdi-thesis-companion-skills
      description: Agent Skill bundle for Deloitte Sdi Thesis Companion.
      skills:
      - name: sdi-thesis-companion
        description: A capability paired with framework-wiki/Spec-Driven-Integration.md "operational governance of AI" framing as a partner-channel narrative.
        location: file:///opt/naftiko/skills/sdi-thesis-companion
        allowed-tools: example
        tools:
        - name: example
          description: A capability paired with framework-wiki/Spec-Driven-Integration.md "operational governance of AI" framing as a partner-channel narrative.
          from:
            sourceNamespace: sdi-thesis-companion-mcp
            action: example
---

A capability paired with framework-wiki/Spec-Driven-Integration.md "operational governance of AI" framing as a partner-channel narrative. Big-Four partners need a thesis to take to their clients; SDI is that thesis.
