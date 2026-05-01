---
categories: []
consumed_apis:
- ey
description: A capability over SAP S/4HANA financial close postings, exposing read-only MCP tools with continuous-compliance reporting (NIST/SOC2/PCI-style).
layout: capability
naftiko_layer: service-anchored
naftiko_partner: Ulrich Trinkaus
name: EY Sap S4hana Financial Close Governed Capability
operations: []
personas: []
provider_name: EY
provider_slug: ey
search_terms:
- capability
- over
- 4hana
- financial
- close
slug: sap-s4hana-financial-close-governed-capability
source_filename: sap-s4hana-financial-close-governed-capability.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: EY Sap S4hana Financial Close Governed Capability
    description: A capability over SAP S/4HANA financial close postings, exposing read-only MCP tools with continuous-compliance reporting (NIST/SOC2/PCI-style).
    tags:
    - EY
    created: '2026-04-30'
    modified: '2026-04-30'
  binds:
  - namespace: ey-env
    description: EY credentials.
    keys:
      EY_API_KEY: EY_API_KEY
  capability:
    consumes:
    - namespace: ey
      type: http
      baseUri: https://api.ey.com
      authentication:
        type: bearer
        token: '{{EY_API_KEY}}'
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
      namespace: sap-s4hana-financial-close-governed-capability-rest
      description: REST API for EY Sap S4hana Financial Close Governed Capability.
      resources:
      - name: example
        path: /example
        operations:
        - method: GET
          name: example-op
          call: ey.example-op
    - type: mcp
      address: 0.0.0.0
      port: 3010
      namespace: sap-s4hana-financial-close-governed-capability-mcp
      description: MCP server exposing EY Sap S4hana Financial Close Governed Capability for AI agents.
      tools:
      - name: example
        description: A capability over SAP S/4HANA financial close postings, exposing read-only MCP tools with continuous-compliance reporting (NIST/SOC2/PCI-style).
        hints:
          readOnly: true
        call: ey.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: sap-s4hana-financial-close-governed-capability-skills
      description: Agent Skill bundle for EY Sap S4hana Financial Close Governed Capability.
      skills:
      - name: sap-s4hana-financial-close-governed-capability
        description: A capability over SAP S/4HANA financial close postings, exposing read-only MCP tools with continuous-compliance reporting (NIST/SOC2/PCI-style).
        location: file:///opt/naftiko/skills/sap-s4hana-financial-close-governed-capability
        allowed-tools: example
        tools:
        - name: example
          description: A capability over SAP S/4HANA financial close postings, exposing read-only MCP tools with continuous-compliance reporting (NIST/SOC2/PCI-style).
          from:
            sourceNamespace: sap-s4hana-financial-close-governed-capability-mcp
            action: example
---

A capability over SAP S/4HANA financial close postings, exposing read-only MCP tools with continuous-compliance reporting (NIST/SOC2/PCI-style). Audit + advisory practice = governed reads on the audit substrate; SAP S/4HANA is the substrate.
