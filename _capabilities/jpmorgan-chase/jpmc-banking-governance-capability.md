---
categories: []
consumed_apis:
- jpmorgan-chase
description: 'A capability built specifically to show banking-grade governance: labels on info, tags on Consumes (data sensitivity, billing), Kyverno admission control, NIST/SOC2/PCI/GDPR continuous compliance.'
layout: capability
naftiko_layer: proposed
naftiko_partner: Mark McAllister
name: JPMorgan Chase Jpmc Banking Governance Capability
operations: []
personas: []
provider_name: JPMorgan Chase
provider_slug: jpmorgan-chase
search_terms:
- capability
- built
- specifically
- show
- banking
slug: jpmc-banking-governance-capability
source_filename: jpmc-banking-governance-capability.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: JPMorgan Chase Jpmc Banking Governance Capability
    description: 'A capability built specifically to show banking-grade governance: labels on info, tags on Consumes (data sensitivity, billing), Kyverno admission control, NIST/SOC2/PCI/GDPR continuous compliance.'
    tags:
    - JPMorgan Chase
    created: '2026-04-30'
    modified: '2026-04-30'
  binds:
  - namespace: jpmorgan-chase-env
    description: JPMorgan Chase credentials.
    keys:
      JPMORGAN_CHASE_API_KEY: JPMORGAN_CHASE_API_KEY
  capability:
    consumes:
    - namespace: jpmorgan-chase
      type: http
      baseUri: https://api.jpmorgan-chase.com
      authentication:
        type: bearer
        token: '{{JPMORGAN_CHASE_API_KEY}}'
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
      namespace: jpmc-banking-governance-capability-rest
      description: REST API for JPMorgan Chase Jpmc Banking Governance Capability.
      resources:
      - name: example
        path: /example
        operations:
        - method: GET
          name: example-op
          call: jpmorgan-chase.example-op
    - type: mcp
      address: 0.0.0.0
      port: 3010
      namespace: jpmc-banking-governance-capability-mcp
      description: MCP server exposing JPMorgan Chase Jpmc Banking Governance Capability for AI agents.
      tools:
      - name: example
        description: 'A capability built specifically to show banking-grade governance: labels on info, tags on Consumes (data sensitivity, billing), Kyverno admission control, NIST/SOC2/PCI/GDPR continuous compliance.'
        hints:
          readOnly: true
        call: jpmorgan-chase.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: jpmc-banking-governance-capability-skills
      description: Agent Skill bundle for JPMorgan Chase Jpmc Banking Governance Capability.
      skills:
      - name: jpmc-banking-governance-capability
        description: 'A capability built specifically to show banking-grade governance: labels on info, tags on Consumes (data sensitivity, billing), Kyverno admission control, NIST/SOC2/PCI/GDPR continuous compliance.'
        location: file:///opt/naftiko/skills/jpmc-banking-governance-capability
        allowed-tools: example
        tools:
        - name: example
          description: 'A capability built specifically to show banking-grade governance: labels on info, tags on Consumes (data sensitivity, billing), Kyverno admission control, NIST/SOC2/PCI/GDPR continuous compliance.'
          from:
            sourceNamespace: jpmc-banking-governance-capability-mcp
            action: example
---

A capability built specifically to show banking-grade governance: labels on info, tags on Consumes (data sensitivity, billing), Kyverno admission control, NIST/SOC2/PCI/GDPR continuous compliance. His updated proposal needs a banking-grade governance lead; this is the artifact that earns the response.
