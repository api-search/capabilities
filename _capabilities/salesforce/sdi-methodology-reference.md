---
categories: []
consumed_apis:
- salesforce
description: A reference capability paired with framework-wiki/Spec-Driven-Integration.md as the methodology backbone of the pitch.
layout: capability
naftiko_layer: proposed
naftiko_partner: Kris Harrison
name: Salesforce Sdi Methodology Reference
operations: []
personas: []
provider_name: Salesforce
provider_slug: salesforce
search_terms:
- reference
- capability
- paired
- with
- framework
slug: sdi-methodology-reference
source_filename: sdi-methodology-reference.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Salesforce Sdi Methodology Reference
    description: A reference capability paired with framework-wiki/Spec-Driven-Integration.md as the methodology backbone of the pitch.
    tags:
    - Salesforce
    created: '2026-04-30'
    modified: '2026-04-30'
  binds:
  - namespace: salesforce-env
    description: Salesforce credentials.
    keys:
      SALESFORCE_API_KEY: SALESFORCE_API_KEY
  capability:
    consumes:
    - namespace: salesforce
      type: http
      baseUri: https://api.salesforce.com
      authentication:
        type: bearer
        token: '{{SALESFORCE_API_KEY}}'
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
      namespace: sdi-methodology-reference-rest
      description: REST API for Salesforce Sdi Methodology Reference.
      resources:
      - name: example
        path: /example
        operations:
        - method: GET
          name: example-op
          call: salesforce.example-op
    - type: mcp
      address: 0.0.0.0
      port: 3010
      namespace: sdi-methodology-reference-mcp
      description: MCP server exposing Salesforce Sdi Methodology Reference for AI agents.
      tools:
      - name: example
        description: A reference capability paired with framework-wiki/Spec-Driven-Integration.md as the methodology backbone of the pitch.
        hints:
          readOnly: true
        call: salesforce.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: sdi-methodology-reference-skills
      description: Agent Skill bundle for Salesforce Sdi Methodology Reference.
      skills:
      - name: sdi-methodology-reference
        description: A reference capability paired with framework-wiki/Spec-Driven-Integration.md as the methodology backbone of the pitch.
        location: file:///opt/naftiko/skills/sdi-methodology-reference
        allowed-tools: example
        tools:
        - name: example
          description: A reference capability paired with framework-wiki/Spec-Driven-Integration.md as the methodology backbone of the pitch.
          from:
            sourceNamespace: sdi-methodology-reference-mcp
            action: example
---

A reference capability paired with framework-wiki/Spec-Driven-Integration.md as the methodology backbone of the pitch. "Worth understanding better" suggests he wants depth; this is the depth.
