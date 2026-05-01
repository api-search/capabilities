---
categories: []
consumed_apis:
- arnica
description: A "secure capability" reference where Arnica's scanning + Naftiko's per-endpoint auth and tags-on-Exposes (data sensitivity, deprecation) co-demo on a shared capability.
layout: capability
naftiko_layer: proposed
naftiko_partner: Anna Daugherty
name: Arnica Naftiko Secure Capability Reference
operations: []
personas: []
provider_name: Arnica
provider_slug: arnica
search_terms:
- secure
- capability
- reference
- where
- arnica
slug: naftiko-secure-capability-reference
source_filename: naftiko-secure-capability-reference.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Arnica Naftiko Secure Capability Reference
    description: A "secure capability" reference where Arnica's scanning + Naftiko's per-endpoint auth and tags-on-Exposes (data sensitivity, deprecation) co-demo on a shared capability.
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
      namespace: naftiko-secure-capability-reference-rest
      description: REST API for Arnica Naftiko Secure Capability Reference.
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
      namespace: naftiko-secure-capability-reference-mcp
      description: MCP server exposing Arnica Naftiko Secure Capability Reference for AI agents.
      tools:
      - name: example
        description: A "secure capability" reference where Arnica's scanning + Naftiko's per-endpoint auth and tags-on-Exposes (data sensitivity, deprecation) co-demo on a shared capability.
        hints:
          readOnly: true
        call: arnica.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: naftiko-secure-capability-reference-skills
      description: Agent Skill bundle for Arnica Naftiko Secure Capability Reference.
      skills:
      - name: naftiko-secure-capability-reference
        description: A "secure capability" reference where Arnica's scanning + Naftiko's per-endpoint auth and tags-on-Exposes (data sensitivity, deprecation) co-demo on a shared capability.
        location: file:///opt/naftiko/skills/naftiko-secure-capability-reference
        allowed-tools: example
        tools:
        - name: example
          description: A "secure capability" reference where Arnica's scanning + Naftiko's per-endpoint auth and tags-on-Exposes (data sensitivity, deprecation) co-demo on a shared capability.
          from:
            sourceNamespace: naftiko-secure-capability-reference-mcp
            action: example
---

A "secure capability" reference where Arnica's scanning + Naftiko's per-endpoint auth and tags-on-Exposes (data sensitivity, deprecation) co-demo on a shared capability. Recorded podcast already established the relationship; a co-built artifact gives the partnership proposal teeth.
