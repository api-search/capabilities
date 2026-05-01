---
categories: []
consumed_apis:
- elsevier
description: 'A reference capability tied to Guide-Use-Cases #9 (Capability-first API reusability), used as the dual-track proposal anchor.'
layout: capability
naftiko_layer: proposed
naftiko_partner: Joyce Stack
name: Elsevier Capability First Reusability Reference
operations: []
personas: []
provider_name: Elsevier
provider_slug: elsevier
search_terms:
- reference
- capability
- tied
- guide
- cases
slug: capability-first-reusability-reference
source_filename: capability-first-reusability-reference.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Elsevier Capability First Reusability Reference
    description: 'A reference capability tied to Guide-Use-Cases #9 (Capability-first API reusability), used as the dual-track proposal anchor.'
    tags:
    - Elsevier
    created: '2026-04-30'
    modified: '2026-04-30'
  binds:
  - namespace: elsevier-env
    description: Elsevier credentials.
    keys:
      ELSEVIER_API_KEY: ELSEVIER_API_KEY
  capability:
    consumes:
    - namespace: elsevier
      type: http
      baseUri: https://api.elsevier.com
      authentication:
        type: bearer
        token: '{{ELSEVIER_API_KEY}}'
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
      namespace: capability-first-reusability-reference-rest
      description: REST API for Elsevier Capability First Reusability Reference.
      resources:
      - name: example
        path: /example
        operations:
        - method: GET
          name: example-op
          call: elsevier.example-op
    - type: mcp
      address: 0.0.0.0
      port: 3010
      namespace: capability-first-reusability-reference-mcp
      description: MCP server exposing Elsevier Capability First Reusability Reference for AI agents.
      tools:
      - name: example
        description: 'A reference capability tied to Guide-Use-Cases #9 (Capability-first API reusability), used as the dual-track proposal anchor.'
        hints:
          readOnly: true
        call: elsevier.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: capability-first-reusability-reference-skills
      description: Agent Skill bundle for Elsevier Capability First Reusability Reference.
      skills:
      - name: capability-first-reusability-reference
        description: 'A reference capability tied to Guide-Use-Cases #9 (Capability-first API reusability), used as the dual-track proposal anchor.'
        location: file:///opt/naftiko/skills/capability-first-reusability-reference
        allowed-tools: example
        tools:
        - name: example
          description: 'A reference capability tied to Guide-Use-Cases #9 (Capability-first API reusability), used as the dual-track proposal anchor.'
          from:
            sourceNamespace: capability-first-reusability-reference-mcp
            action: example
---

A reference capability tied to Guide-Use-Cases #9 (Capability-first API reusability), used as the dual-track proposal anchor. Use case #9 is written for her exact second ask; named alignment is highest-signal.
