---
categories: []
consumed_apis:
- abn-amro
description: A capability with Compliance Frameworks (GDPR) + governance + tags-on-Exposes (network topology, data sensitivity) — the Dutch-banking pitch.
layout: capability
naftiko_layer: proposed
naftiko_partner: ABN AMRO Bank
name: ABN AMRO Bank Gdpr Governance Capability
operations: []
personas: []
provider_name: ABN AMRO Bank
provider_slug: abn-amro
search_terms:
- capability
- with
- compliance
- frameworks
- gdpr
slug: gdpr-governance-capability
source_filename: gdpr-governance-capability.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: ABN AMRO Bank Gdpr Governance Capability
    description: A capability with Compliance Frameworks (GDPR) + governance + tags-on-Exposes (network topology, data sensitivity) — the Dutch-banking pitch.
    tags:
    - ABN AMRO Bank
    created: '2026-04-30'
    modified: '2026-04-30'
  binds:
  - namespace: abn-amro-env
    description: ABN AMRO Bank credentials.
    keys:
      ABN_AMRO_API_KEY: ABN_AMRO_API_KEY
  capability:
    consumes:
    - namespace: abn-amro
      type: http
      baseUri: https://api.abn-amro.com
      authentication:
        type: bearer
        token: '{{ABN_AMRO_API_KEY}}'
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
      namespace: gdpr-governance-capability-rest
      description: REST API for ABN AMRO Bank Gdpr Governance Capability.
      resources:
      - name: example
        path: /example
        operations:
        - method: GET
          name: example-op
          call: abn-amro.example-op
    - type: mcp
      address: 0.0.0.0
      port: 3010
      namespace: gdpr-governance-capability-mcp
      description: MCP server exposing ABN AMRO Bank Gdpr Governance Capability for AI agents.
      tools:
      - name: example
        description: A capability with Compliance Frameworks (GDPR) + governance + tags-on-Exposes (network topology, data sensitivity) — the Dutch-banking pitch.
        hints:
          readOnly: true
        call: abn-amro.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: gdpr-governance-capability-skills
      description: Agent Skill bundle for ABN AMRO Bank Gdpr Governance Capability.
      skills:
      - name: gdpr-governance-capability
        description: A capability with Compliance Frameworks (GDPR) + governance + tags-on-Exposes (network topology, data sensitivity) — the Dutch-banking pitch.
        location: file:///opt/naftiko/skills/gdpr-governance-capability
        allowed-tools: example
        tools:
        - name: example
          description: A capability with Compliance Frameworks (GDPR) + governance + tags-on-Exposes (network topology, data sensitivity) — the Dutch-banking pitch.
          from:
            sourceNamespace: gdpr-governance-capability-mcp
            action: example
---

A capability with Compliance Frameworks (GDPR) + governance + tags-on-Exposes (network topology, data sensitivity) — the Dutch-banking pitch. Heavily regulated EU banking; GDPR + governance differentiates vs. generic API tooling.
