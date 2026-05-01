---
categories: []
consumed_apis:
- abn-amro
description: A capability over their open banking / PSD2 surface, sent as the re-nudge artifact.
layout: capability
naftiko_layer: proposed
naftiko_partner: ABN AMRO Bank
name: ABN AMRO Bank Psd2 Open Banking Capability
operations: []
personas: []
provider_name: ABN AMRO Bank
provider_slug: abn-amro
search_terms:
- capability
- over
- their
- open
- banking
slug: psd2-open-banking-capability
source_filename: psd2-open-banking-capability.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: ABN AMRO Bank Psd2 Open Banking Capability
    description: A capability over their open banking / PSD2 surface, sent as the re-nudge artifact.
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
      namespace: psd2-open-banking-capability-rest
      description: REST API for ABN AMRO Bank Psd2 Open Banking Capability.
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
      namespace: psd2-open-banking-capability-mcp
      description: MCP server exposing ABN AMRO Bank Psd2 Open Banking Capability for AI agents.
      tools:
      - name: example
        description: A capability over their open banking / PSD2 surface, sent as the re-nudge artifact.
        hints:
          readOnly: true
        call: abn-amro.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: psd2-open-banking-capability-skills
      description: Agent Skill bundle for ABN AMRO Bank Psd2 Open Banking Capability.
      skills:
      - name: psd2-open-banking-capability
        description: A capability over their open banking / PSD2 surface, sent as the re-nudge artifact.
        location: file:///opt/naftiko/skills/psd2-open-banking-capability
        allowed-tools: example
        tools:
        - name: example
          description: A capability over their open banking / PSD2 surface, sent as the re-nudge artifact.
          from:
            sourceNamespace: psd2-open-banking-capability-mcp
            action: example
---

A capability over their open banking / PSD2 surface, sent as the re-nudge artifact. A built capability against their actual API shape changes the conversation Signals alone couldn't move.
