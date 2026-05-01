---
categories: []
consumed_apis:
- northwestern-mutual
description: A reference capability paired with a wiki addendum to the Zero-Touch episode, citing framework-wiki/Specification-Rules.
layout: capability
naftiko_layer: proposed
naftiko_partner: Supreet Nagi
name: Northwestern Mutual Spec Rules Wiki Companion Capability
operations: []
personas: []
provider_name: Northwestern Mutual
provider_slug: northwestern-mutual
search_terms:
- reference
- capability
- paired
- with
- wiki
slug: spec-rules-wiki-companion-capability
source_filename: spec-rules-wiki-companion-capability.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Northwestern Mutual Spec Rules Wiki Companion Capability
    description: A reference capability paired with a wiki addendum to the Zero-Touch episode, citing framework-wiki/Specification-Rules.
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
      namespace: spec-rules-wiki-companion-capability-rest
      description: REST API for Northwestern Mutual Spec Rules Wiki Companion Capability.
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
      namespace: spec-rules-wiki-companion-capability-mcp
      description: MCP server exposing Northwestern Mutual Spec Rules Wiki Companion Capability for AI agents.
      tools:
      - name: example
        description: A reference capability paired with a wiki addendum to the Zero-Touch episode, citing framework-wiki/Specification-Rules.
        hints:
          readOnly: true
        call: northwestern-mutual.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: spec-rules-wiki-companion-capability-skills
      description: Agent Skill bundle for Northwestern Mutual Spec Rules Wiki Companion Capability.
      skills:
      - name: spec-rules-wiki-companion-capability
        description: A reference capability paired with a wiki addendum to the Zero-Touch episode, citing framework-wiki/Specification-Rules.
        location: file:///opt/naftiko/skills/spec-rules-wiki-companion-capability
        allowed-tools: example
        tools:
        - name: example
          description: A reference capability paired with a wiki addendum to the Zero-Touch episode, citing framework-wiki/Specification-Rules.
          from:
            sourceNamespace: spec-rules-wiki-companion-capability-mcp
            action: example
---

A reference capability paired with a wiki addendum to the Zero-Touch episode, citing framework-wiki/Specification-Rules. Co-publishing closes the loop from podcast into product canon.
