---
categories: []
consumed_apis:
- halmstad-university
description: A capability annotated against the SDI "Research-Driven Context" principle, framed for an academic-industrial collaboration narrative.
layout: capability
naftiko_layer: proposed
naftiko_partner: Farzaneh Etminani
name: Halmstad University Research Driven Context Capability
operations: []
personas: []
provider_name: Halmstad University
provider_slug: halmstad-university
search_terms:
- capability
- annotated
- against
- research
- driven
slug: research-driven-context-capability
source_filename: research-driven-context-capability.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Halmstad University Research Driven Context Capability
    description: A capability annotated against the SDI "Research-Driven Context" principle, framed for an academic-industrial collaboration narrative.
    tags:
    - Halmstad University
    created: '2026-04-30'
    modified: '2026-04-30'
  binds:
  - namespace: halmstad-university-env
    description: Halmstad University credentials.
    keys:
      HALMSTAD_UNIVERSITY_API_KEY: HALMSTAD_UNIVERSITY_API_KEY
  capability:
    consumes:
    - namespace: halmstad-university
      type: http
      baseUri: https://api.halmstad-university.com
      authentication:
        type: bearer
        token: '{{HALMSTAD_UNIVERSITY_API_KEY}}'
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
      namespace: research-driven-context-capability-rest
      description: REST API for Halmstad University Research Driven Context Capability.
      resources:
      - name: example
        path: /example
        operations:
        - method: GET
          name: example-op
          call: halmstad-university.example-op
    - type: mcp
      address: 0.0.0.0
      port: 3010
      namespace: research-driven-context-capability-mcp
      description: MCP server exposing Halmstad University Research Driven Context Capability for AI agents.
      tools:
      - name: example
        description: A capability annotated against the SDI "Research-Driven Context" principle, framed for an academic-industrial collaboration narrative.
        hints:
          readOnly: true
        call: halmstad-university.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: research-driven-context-capability-skills
      description: Agent Skill bundle for Halmstad University Research Driven Context Capability.
      skills:
      - name: research-driven-context-capability
        description: A capability annotated against the SDI "Research-Driven Context" principle, framed for an academic-industrial collaboration narrative.
        location: file:///opt/naftiko/skills/research-driven-context-capability
        allowed-tools: example
        tools:
        - name: example
          description: A capability annotated against the SDI "Research-Driven Context" principle, framed for an academic-industrial collaboration narrative.
          from:
            sourceNamespace: research-driven-context-capability-mcp
            action: example
---

A capability annotated against the SDI "Research-Driven Context" principle, framed for an academic-industrial collaboration narrative. SDI's Research-Driven Context principle reads as written for healthcare research-industry partnerships.
