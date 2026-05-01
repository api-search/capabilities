---
categories: []
consumed_apis:
- schneider-electric
description: A capability that exposes a curated set of M365 Copilot skills to Schneider's non-developer business side, paralleling the developer GitHub Copilot path.
layout: capability
naftiko_layer: service-anchored
naftiko_partner: Manu PK
name: Schneider Electric Schneider M365 Copilot Non Developer Skill Bridge
operations: []
personas: []
provider_name: Schneider Electric
provider_slug: schneider-electric
search_terms:
- capability
- that
- exposes
- curated
- m365
slug: schneider-m365-copilot-non-developer-skill-bridge
source_filename: schneider-m365-copilot-non-developer-skill-bridge.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Schneider Electric Schneider M365 Copilot Non Developer Skill Bridge
    description: A capability that exposes a curated set of M365 Copilot skills to Schneider's non-developer business side, paralleling the developer GitHub Copilot path.
    tags:
    - Schneider Electric
    created: '2026-04-30'
    modified: '2026-04-30'
  binds:
  - namespace: schneider-electric-env
    description: Schneider Electric credentials.
    keys:
      SCHNEIDER_ELECTRIC_API_KEY: SCHNEIDER_ELECTRIC_API_KEY
  capability:
    consumes:
    - namespace: schneider-electric
      type: http
      baseUri: https://api.schneider-electric.com
      authentication:
        type: bearer
        token: '{{SCHNEIDER_ELECTRIC_API_KEY}}'
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
      namespace: schneider-m365-copilot-non-developer-skill-bridge-rest
      description: REST API for Schneider Electric Schneider M365 Copilot Non Developer Skill Bridge.
      resources:
      - name: example
        path: /example
        operations:
        - method: GET
          name: example-op
          call: schneider-electric.example-op
    - type: mcp
      address: 0.0.0.0
      port: 3010
      namespace: schneider-m365-copilot-non-developer-skill-bridge-mcp
      description: MCP server exposing Schneider Electric Schneider M365 Copilot Non Developer Skill Bridge for AI agents.
      tools:
      - name: example
        description: A capability that exposes a curated set of M365 Copilot skills to Schneider's non-developer business side, paralleling the developer GitHub Copilot path.
        hints:
          readOnly: true
        call: schneider-electric.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: schneider-m365-copilot-non-developer-skill-bridge-skills
      description: Agent Skill bundle for Schneider Electric Schneider M365 Copilot Non Developer Skill Bridge.
      skills:
      - name: schneider-m365-copilot-non-developer-skill-bridge
        description: A capability that exposes a curated set of M365 Copilot skills to Schneider's non-developer business side, paralleling the developer GitHub Copilot path.
        location: file:///opt/naftiko/skills/schneider-m365-copilot-non-developer-skill-bridge
        allowed-tools: example
        tools:
        - name: example
          description: A capability that exposes a curated set of M365 Copilot skills to Schneider's non-developer business side, paralleling the developer GitHub Copilot path.
          from:
            sourceNamespace: schneider-m365-copilot-non-developer-skill-bridge-mcp
            action: example
---

A capability that exposes a curated set of M365 Copilot skills to Schneider's non-developer business side, paralleling the developer GitHub Copilot path. He named the two-tier audience explicitly; covering both halves matches the policy preference he described.
