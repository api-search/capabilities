---
categories: []
consumed_apis:
- arnica
description: A capability where the Naftiko Spectral ruleset + blocking rules (auth required, HTTPS only, destructive-ops gate) + PII surface detection are wired in as the shift-left governance story.
layout: capability
naftiko_layer: proposed
naftiko_partner: Anna Daugherty
name: Arnica Devsecops Shift Left Governance Capability
operations: []
personas: []
provider_name: Arnica
provider_slug: arnica
search_terms:
- capability
- where
- naftiko
- spectral
- ruleset
slug: devsecops-shift-left-governance-capability
source_filename: devsecops-shift-left-governance-capability.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Arnica Devsecops Shift Left Governance Capability
    description: A capability where the Naftiko Spectral ruleset + blocking rules (auth required, HTTPS only, destructive-ops gate) + PII surface detection are wired in as the shift-left governance story.
    tags:
    - Arnica
    created: '2026-04-30'
    modified: '2026-04-30'
  binds:
  - namespace: arnica-env
    description: Arnica credentials.
    keys:
      ARNICA_API_KEY: ARNICA_API_KEY
  capability:
    consumes:
    - namespace: arnica
      type: http
      baseUri: https://api.arnica.com
      authentication:
        type: bearer
        token: '{{ARNICA_API_KEY}}'
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
      namespace: devsecops-shift-left-governance-capability-rest
      description: REST API for Arnica Devsecops Shift Left Governance Capability.
      resources:
      - name: example
        path: /example
        operations:
        - method: GET
          name: example-op
          call: arnica.example-op
    - type: mcp
      address: 0.0.0.0
      port: 3010
      namespace: devsecops-shift-left-governance-capability-mcp
      description: MCP server exposing Arnica Devsecops Shift Left Governance Capability for AI agents.
      tools:
      - name: example
        description: A capability where the Naftiko Spectral ruleset + blocking rules (auth required, HTTPS only, destructive-ops gate) + PII surface detection are wired in as the shift-left governance story.
        hints:
          readOnly: true
        call: arnica.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: devsecops-shift-left-governance-capability-skills
      description: Agent Skill bundle for Arnica Devsecops Shift Left Governance Capability.
      skills:
      - name: devsecops-shift-left-governance-capability
        description: A capability where the Naftiko Spectral ruleset + blocking rules (auth required, HTTPS only, destructive-ops gate) + PII surface detection are wired in as the shift-left governance story.
        location: file:///opt/naftiko/skills/devsecops-shift-left-governance-capability
        allowed-tools: example
        tools:
        - name: example
          description: A capability where the Naftiko Spectral ruleset + blocking rules (auth required, HTTPS only, destructive-ops gate) + PII surface detection are wired in as the shift-left governance story.
          from:
            sourceNamespace: devsecops-shift-left-governance-capability-mcp
            action: example
---

A capability where the Naftiko Spectral ruleset + blocking rules (auth required, HTTPS only, destructive-ops gate) + PII surface detection are wired in as the shift-left governance story. Arnica is DevEx + AI security; Naftiko's governance surface is the natural overlap as a joint message.
