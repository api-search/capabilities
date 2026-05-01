---
categories: []
consumed_apis:
- peter-townsend-stealth
description: A capability shaped like the Bloomberg / PitchBook public-data distribution patterns Peter knows, used as a "this is how an API-forward financial product looks for agents" reference for his stealth team.
layout: capability
naftiko_layer: service-anchored
naftiko_partner: Peter Townsend
name: Peter Townsend Stealth Stealth Bloomberg Pitchbook Style Financial Data Mirror
operations: []
personas: []
provider_name: Peter Townsend Stealth
provider_slug: peter-townsend-stealth
search_terms:
- capability
- shaped
- like
- bloomberg
- pitchbook
slug: stealth-bloomberg-pitchbook-style-financial-data-mirror
source_filename: stealth-bloomberg-pitchbook-style-financial-data-mirror.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Peter Townsend Stealth Stealth Bloomberg Pitchbook Style Financial Data Mirror
    description: A capability shaped like the Bloomberg / PitchBook public-data distribution patterns Peter knows, used as a "this is how an API-forward financial product looks for agents" reference for his stealth team.
    tags:
    - Peter Townsend Stealth
    created: '2026-04-30'
    modified: '2026-04-30'
  binds:
  - namespace: peter-townsend-stealth-env
    description: Peter Townsend Stealth credentials.
    keys:
      PETER_TOWNSEND_STEALTH_API_KEY: PETER_TOWNSEND_STEALTH_API_KEY
  capability:
    consumes:
    - namespace: peter-townsend-stealth
      type: http
      baseUri: https://api.peter-townsend-stealth.com
      authentication:
        type: bearer
        token: '{{PETER_TOWNSEND_STEALTH_API_KEY}}'
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
      namespace: stealth-bloomberg-pitchbook-style-financial-data-mirror-rest
      description: REST API for Peter Townsend Stealth Stealth Bloomberg Pitchbook Style Financial Data Mirror.
      resources:
      - name: example
        path: /example
        operations:
        - method: GET
          name: example-op
          call: peter-townsend-stealth.example-op
    - type: mcp
      address: 0.0.0.0
      port: 3010
      namespace: stealth-bloomberg-pitchbook-style-financial-data-mirror-mcp
      description: MCP server exposing Peter Townsend Stealth Stealth Bloomberg Pitchbook Style Financial Data Mirror for AI agents.
      tools:
      - name: example
        description: A capability shaped like the Bloomberg / PitchBook public-data distribution patterns Peter knows, used as a "this is how an API-forward financial product looks for agents" reference for his stealth team.
        hints:
          readOnly: true
        call: peter-townsend-stealth.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: stealth-bloomberg-pitchbook-style-financial-data-mirror-skills
      description: Agent Skill bundle for Peter Townsend Stealth Stealth Bloomberg Pitchbook Style Financial Data Mirror.
      skills:
      - name: stealth-bloomberg-pitchbook-style-financial-data-mirror
        description: A capability shaped like the Bloomberg / PitchBook public-data distribution patterns Peter knows, used as a "this is how an API-forward financial product looks for agents" reference for his stealth team.
        location: file:///opt/naftiko/skills/stealth-bloomberg-pitchbook-style-financial-data-mirror
        allowed-tools: example
        tools:
        - name: example
          description: A capability shaped like the Bloomberg / PitchBook public-data distribution patterns Peter knows, used as a "this is how an API-forward financial product looks for agents" reference for his stealth team.
          from:
            sourceNamespace: stealth-bloomberg-pitchbook-style-financial-data-mirror-mcp
            action: example
---

A capability shaped like the Bloomberg / PitchBook public-data distribution patterns Peter knows, used as a "this is how an API-forward financial product looks for agents" reference for his stealth team. He builds in financial data; mirroring the distribution shape he already understands de-risks the proposal.
