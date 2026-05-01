---
categories: []
consumed_apis:
- tyk
description: A capability paired with a follow-on to the Zero-Touch API Governance podcast, joining capability governance to gateway governance.
layout: capability
naftiko_layer: proposed
naftiko_partner: Budhaditya (Budha) Bhattacharya
name: Tyk Zero Touch Governance Tyk Companion
operations: []
personas: []
provider_name: Tyk
provider_slug: tyk
search_terms:
- capability
- paired
- with
- follow
- zero
slug: zero-touch-governance-tyk-companion
source_filename: zero-touch-governance-tyk-companion.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Tyk Zero Touch Governance Tyk Companion
    description: A capability paired with a follow-on to the Zero-Touch API Governance podcast, joining capability governance to gateway governance.
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
      namespace: zero-touch-governance-tyk-companion-rest
      description: REST API for Tyk Zero Touch Governance Tyk Companion.
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
      namespace: zero-touch-governance-tyk-companion-mcp
      description: MCP server exposing Tyk Zero Touch Governance Tyk Companion for AI agents.
      tools:
      - name: example
        description: A capability paired with a follow-on to the Zero-Touch API Governance podcast, joining capability governance to gateway governance.
        hints:
          readOnly: true
        call: tyk.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: zero-touch-governance-tyk-companion-skills
      description: Agent Skill bundle for Tyk Zero Touch Governance Tyk Companion.
      skills:
      - name: zero-touch-governance-tyk-companion
        description: A capability paired with a follow-on to the Zero-Touch API Governance podcast, joining capability governance to gateway governance.
        location: file:///opt/naftiko/skills/zero-touch-governance-tyk-companion
        allowed-tools: example
        tools:
        - name: example
          description: A capability paired with a follow-on to the Zero-Touch API Governance podcast, joining capability governance to gateway governance.
          from:
            sourceNamespace: zero-touch-governance-tyk-companion-mcp
            action: example
---

A capability paired with a follow-on to the Zero-Touch API Governance podcast, joining capability governance to gateway governance. He featured on that exact episode — the shared narrative is in market and ready to be deepened.
