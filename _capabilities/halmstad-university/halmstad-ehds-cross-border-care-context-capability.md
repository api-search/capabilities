---
categories: []
consumed_apis:
- halmstad-university
description: A capability shaped to the EHDS cross-border patient-care + research data-sharing flow with consent + provenance tags.
layout: capability
naftiko_layer: service-anchored
naftiko_partner: Farzaneh Etminani
name: Halmstad University Halmstad Ehds Cross Border Care Context Capability
operations: []
personas: []
provider_name: Halmstad University
provider_slug: halmstad-university
search_terms:
- capability
- shaped
- ehds
- cross
- border
slug: halmstad-ehds-cross-border-care-context-capability
source_filename: halmstad-ehds-cross-border-care-context-capability.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Halmstad University Halmstad Ehds Cross Border Care Context Capability
    description: A capability shaped to the EHDS cross-border patient-care + research data-sharing flow with consent + provenance tags.
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
      namespace: halmstad-ehds-cross-border-care-context-capability-rest
      description: REST API for Halmstad University Halmstad Ehds Cross Border Care Context Capability.
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
      namespace: halmstad-ehds-cross-border-care-context-capability-mcp
      description: MCP server exposing Halmstad University Halmstad Ehds Cross Border Care Context Capability for AI agents.
      tools:
      - name: example
        description: A capability shaped to the EHDS cross-border patient-care + research data-sharing flow with consent + provenance tags.
        hints:
          readOnly: true
        call: halmstad-university.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: halmstad-ehds-cross-border-care-context-capability-skills
      description: Agent Skill bundle for Halmstad University Halmstad Ehds Cross Border Care Context Capability.
      skills:
      - name: halmstad-ehds-cross-border-care-context-capability
        description: A capability shaped to the EHDS cross-border patient-care + research data-sharing flow with consent + provenance tags.
        location: file:///opt/naftiko/skills/halmstad-ehds-cross-border-care-context-capability
        allowed-tools: example
        tools:
        - name: example
          description: A capability shaped to the EHDS cross-border patient-care + research data-sharing flow with consent + provenance tags.
          from:
            sourceNamespace: halmstad-ehds-cross-border-care-context-capability-mcp
            action: example
---

A capability shaped to the EHDS cross-border patient-care + research data-sharing flow with consent + provenance tags. EHDS is the regulatory tailwind for her project; a built artifact lands at the policy beat.
