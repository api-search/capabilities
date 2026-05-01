---
categories: []
consumed_apis:
- ey
description: A capability tied into the next iteration of the Professional Services Signals report, with the SDI "Operational Governance of AI" framing as the closing narrative.
layout: capability
naftiko_layer: proposed
naftiko_partner: Ulrich Trinkaus
name: EY Operational Governance Of Ai Companion
operations: []
personas: []
provider_name: EY
provider_slug: ey
search_terms:
- capability
- tied
- into
- next
- iteration
slug: operational-governance-of-ai-companion
source_filename: operational-governance-of-ai-companion.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: EY Operational Governance Of Ai Companion
    description: A capability tied into the next iteration of the Professional Services Signals report, with the SDI "Operational Governance of AI" framing as the closing narrative.
    tags:
    - EY
    created: '2026-04-30'
    modified: '2026-04-30'
  binds:
  - namespace: ey-env
    description: EY credentials.
    keys:
      EY_API_KEY: EY_API_KEY
  capability:
    consumes:
    - namespace: ey
      type: http
      baseUri: https://api.ey.com
      authentication:
        type: bearer
        token: '{{EY_API_KEY}}'
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
      namespace: operational-governance-of-ai-companion-rest
      description: REST API for EY Operational Governance Of Ai Companion.
      resources:
      - name: example
        path: /example
        operations:
        - method: GET
          name: example-op
          call: ey.example-op
    - type: mcp
      address: 0.0.0.0
      port: 3010
      namespace: operational-governance-of-ai-companion-mcp
      description: MCP server exposing EY Operational Governance Of Ai Companion for AI agents.
      tools:
      - name: example
        description: A capability tied into the next iteration of the Professional Services Signals report, with the SDI "Operational Governance of AI" framing as the closing narrative.
        hints:
          readOnly: true
        call: ey.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: operational-governance-of-ai-companion-skills
      description: Agent Skill bundle for EY Operational Governance Of Ai Companion.
      skills:
      - name: operational-governance-of-ai-companion
        description: A capability tied into the next iteration of the Professional Services Signals report, with the SDI "Operational Governance of AI" framing as the closing narrative.
        location: file:///opt/naftiko/skills/operational-governance-of-ai-companion
        allowed-tools: example
        tools:
        - name: example
          description: A capability tied into the next iteration of the Professional Services Signals report, with the SDI "Operational Governance of AI" framing as the closing narrative.
          from:
            sourceNamespace: operational-governance-of-ai-companion-mcp
            action: example
---

A capability tied into the next iteration of the Professional Services Signals report, with the SDI "Operational Governance of AI" framing as the closing narrative. That framing IS his "lead with governance and trust" ask in product language.
