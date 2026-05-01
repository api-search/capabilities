---
categories: []
consumed_apis:
- halmstad-university
description: Wraps openEHR / EHDS APIs as a capability for clinical AI agents, with PII surface detection + HTTPS enforcement governance rules attached.
layout: capability
naftiko_layer: proposed
naftiko_partner: Farzaneh Etminani
name: Halmstad University Openehr Ehds Clinical Mcp Capability
operations: []
personas: []
provider_name: Halmstad University
provider_slug: halmstad-university
search_terms:
- wraps
- openehr
- ehds
- apis
- capability
slug: openehr-ehds-clinical-mcp-capability
source_filename: openehr-ehds-clinical-mcp-capability.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Halmstad University Openehr Ehds Clinical Mcp Capability
    description: Wraps openEHR / EHDS APIs as a capability for clinical AI agents, with PII surface detection + HTTPS enforcement governance rules attached.
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
      namespace: openehr-ehds-clinical-mcp-capability-rest
      description: REST API for Halmstad University Openehr Ehds Clinical Mcp Capability.
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
      namespace: openehr-ehds-clinical-mcp-capability-mcp
      description: MCP server exposing Halmstad University Openehr Ehds Clinical Mcp Capability for AI agents.
      tools:
      - name: example
        description: Wraps openEHR / EHDS APIs as a capability for clinical AI agents, with PII surface detection + HTTPS enforcement governance rules attached.
        hints:
          readOnly: true
        call: halmstad-university.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: openehr-ehds-clinical-mcp-capability-skills
      description: Agent Skill bundle for Halmstad University Openehr Ehds Clinical Mcp Capability.
      skills:
      - name: openehr-ehds-clinical-mcp-capability
        description: Wraps openEHR / EHDS APIs as a capability for clinical AI agents, with PII surface detection + HTTPS enforcement governance rules attached.
        location: file:///opt/naftiko/skills/openehr-ehds-clinical-mcp-capability
        allowed-tools: example
        tools:
        - name: example
          description: Wraps openEHR / EHDS APIs as a capability for clinical AI agents, with PII surface detection + HTTPS enforcement governance rules attached.
          from:
            sourceNamespace: openehr-ehds-clinical-mcp-capability-mcp
            action: example
---

Wraps openEHR / EHDS APIs as a capability for clinical AI agents, with PII surface detection + HTTPS enforcement governance rules attached. Her chronic-wound-care project is on openEHR + EHDS — meet the project at its standards.
