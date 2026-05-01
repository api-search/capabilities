---
categories: []
consumed_apis:
- northwestern-mutual
description: 'A capability that operationalizes the book''s thesis: full governance ruleset, Spectral rules, Kyverno mirrors, advisory + blocking gates.'
layout: capability
naftiko_layer: proposed
naftiko_partner: Supreet Nagi
name: Northwestern Mutual Zero Touch Governance Runtime Capability
operations: []
personas: []
provider_name: Northwestern Mutual
provider_slug: northwestern-mutual
search_terms:
- capability
- that
- operationalizes
- book
- thesis
slug: zero-touch-governance-runtime-capability
source_filename: zero-touch-governance-runtime-capability.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Northwestern Mutual Zero Touch Governance Runtime Capability
    description: 'A capability that operationalizes the book''s thesis: full governance ruleset, Spectral rules, Kyverno mirrors, advisory + blocking gates.'
    tags:
    - Northwestern Mutual
    created: '2026-04-30'
    modified: '2026-04-30'
  binds:
  - namespace: northwestern-mutual-env
    description: Northwestern Mutual credentials.
    keys:
      NORTHWESTERN_MUTUAL_API_KEY: NORTHWESTERN_MUTUAL_API_KEY
  capability:
    consumes:
    - namespace: northwestern-mutual
      type: http
      baseUri: https://api.northwestern-mutual.com
      authentication:
        type: bearer
        token: '{{NORTHWESTERN_MUTUAL_API_KEY}}'
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
      namespace: zero-touch-governance-runtime-capability-rest
      description: REST API for Northwestern Mutual Zero Touch Governance Runtime Capability.
      resources:
      - name: example
        path: /example
        operations:
        - method: GET
          name: example-op
          call: northwestern-mutual.example-op
    - type: mcp
      address: 0.0.0.0
      port: 3010
      namespace: zero-touch-governance-runtime-capability-mcp
      description: MCP server exposing Northwestern Mutual Zero Touch Governance Runtime Capability for AI agents.
      tools:
      - name: example
        description: 'A capability that operationalizes the book''s thesis: full governance ruleset, Spectral rules, Kyverno mirrors, advisory + blocking gates.'
        hints:
          readOnly: true
        call: northwestern-mutual.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: zero-touch-governance-runtime-capability-skills
      description: Agent Skill bundle for Northwestern Mutual Zero Touch Governance Runtime Capability.
      skills:
      - name: zero-touch-governance-runtime-capability
        description: 'A capability that operationalizes the book''s thesis: full governance ruleset, Spectral rules, Kyverno mirrors, advisory + blocking gates.'
        location: file:///opt/naftiko/skills/zero-touch-governance-runtime-capability
        allowed-tools: example
        tools:
        - name: example
          description: 'A capability that operationalizes the book''s thesis: full governance ruleset, Spectral rules, Kyverno mirrors, advisory + blocking gates.'
          from:
            sourceNamespace: zero-touch-governance-runtime-capability-mcp
            action: example
---

A capability that operationalizes the book's thesis: full governance ruleset, Spectral rules, Kyverno mirrors, advisory + blocking gates. She co-authored the "From Chaos to Connectivity" thesis; Naftiko is the runtime that makes it executable.
