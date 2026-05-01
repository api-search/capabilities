---
categories: []
consumed_apis:
- halmstad-university
description: A self-contained runnable sandbox that mocks a Mölnlycke wound-care device data source and exposes openEHR + FHIR via the Avenga-introduction-ready capability.
layout: capability
naftiko_layer: service-anchored
naftiko_partner: Farzaneh Etminani
name: Halmstad University Halmstad Molnlycke Avenga Wound Care Sandbox
operations: []
personas: []
provider_name: Halmstad University
provider_slug: halmstad-university
search_terms:
- self
- contained
- runnable
- sandbox
- that
slug: halmstad-molnlycke-avenga-wound-care-sandbox
source_filename: halmstad-molnlycke-avenga-wound-care-sandbox.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Halmstad University Halmstad Molnlycke Avenga Wound Care Sandbox
    description: A self-contained runnable sandbox that mocks a Mölnlycke wound-care device data source and exposes openEHR + FHIR via the Avenga-introduction-ready capability.
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
      namespace: halmstad-molnlycke-avenga-wound-care-sandbox-rest
      description: REST API for Halmstad University Halmstad Molnlycke Avenga Wound Care Sandbox.
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
      namespace: halmstad-molnlycke-avenga-wound-care-sandbox-mcp
      description: MCP server exposing Halmstad University Halmstad Molnlycke Avenga Wound Care Sandbox for AI agents.
      tools:
      - name: example
        description: A self-contained runnable sandbox that mocks a Mölnlycke wound-care device data source and exposes openEHR + FHIR via the Avenga-introduction-ready capability.
        hints:
          readOnly: true
        call: halmstad-university.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: halmstad-molnlycke-avenga-wound-care-sandbox-skills
      description: Agent Skill bundle for Halmstad University Halmstad Molnlycke Avenga Wound Care Sandbox.
      skills:
      - name: halmstad-molnlycke-avenga-wound-care-sandbox
        description: A self-contained runnable sandbox that mocks a Mölnlycke wound-care device data source and exposes openEHR + FHIR via the Avenga-introduction-ready capability.
        location: file:///opt/naftiko/skills/halmstad-molnlycke-avenga-wound-care-sandbox
        allowed-tools: example
        tools:
        - name: example
          description: A self-contained runnable sandbox that mocks a Mölnlycke wound-care device data source and exposes openEHR + FHIR via the Avenga-introduction-ready capability.
          from:
            sourceNamespace: halmstad-molnlycke-avenga-wound-care-sandbox-mcp
            action: example
---

A self-contained runnable sandbox that mocks a Mölnlycke wound-care device data source and exposes openEHR + FHIR via the Avenga-introduction-ready capability. She offered to intro Naftiko to Avenga — arming her with the named-partners' sandbox makes the intro a one-click demo.
