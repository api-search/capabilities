---
categories: []
consumed_apis:
- deloitte
description: A capability over SAP S/4HANA fronted by MuleSoft, governance-tagged for regulated-industry use as the artifact-led re-nudge.
layout: capability
naftiko_layer: service-anchored
naftiko_partner: Fabrice Marque
name: Deloitte Sap S4hana Mulesoft Regulated Bridge
operations: []
personas: []
provider_name: Deloitte
provider_slug: deloitte
search_terms:
- capability
- over
- 4hana
- fronted
- mulesoft
slug: sap-s4hana-mulesoft-regulated-bridge
source_filename: sap-s4hana-mulesoft-regulated-bridge.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Deloitte Sap S4hana Mulesoft Regulated Bridge
    description: A capability over SAP S/4HANA fronted by MuleSoft, governance-tagged for regulated-industry use as the artifact-led re-nudge.
    tags:
    - Deloitte
    created: '2026-04-30'
    modified: '2026-04-30'
  binds:
  - namespace: deloitte-env
    description: Deloitte credentials.
    keys:
      DELOITTE_API_KEY: DELOITTE_API_KEY
  capability:
    consumes:
    - namespace: deloitte
      type: http
      baseUri: https://api.deloitte.com
      authentication:
        type: bearer
        token: '{{DELOITTE_API_KEY}}'
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
      namespace: sap-s4hana-mulesoft-regulated-bridge-rest
      description: REST API for Deloitte Sap S4hana Mulesoft Regulated Bridge.
      resources:
      - name: example
        path: /example
        operations:
        - method: GET
          name: example-op
          call: deloitte.example-op
    - type: mcp
      address: 0.0.0.0
      port: 3010
      namespace: sap-s4hana-mulesoft-regulated-bridge-mcp
      description: MCP server exposing Deloitte Sap S4hana Mulesoft Regulated Bridge for AI agents.
      tools:
      - name: example
        description: A capability over SAP S/4HANA fronted by MuleSoft, governance-tagged for regulated-industry use as the artifact-led re-nudge.
        hints:
          readOnly: true
        call: deloitte.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: sap-s4hana-mulesoft-regulated-bridge-skills
      description: Agent Skill bundle for Deloitte Sap S4hana Mulesoft Regulated Bridge.
      skills:
      - name: sap-s4hana-mulesoft-regulated-bridge
        description: A capability over SAP S/4HANA fronted by MuleSoft, governance-tagged for regulated-industry use as the artifact-led re-nudge.
        location: file:///opt/naftiko/skills/sap-s4hana-mulesoft-regulated-bridge
        allowed-tools: example
        tools:
        - name: example
          description: A capability over SAP S/4HANA fronted by MuleSoft, governance-tagged for regulated-industry use as the artifact-led re-nudge.
          from:
            sourceNamespace: sap-s4hana-mulesoft-regulated-bridge-mcp
            action: example
---

A capability over SAP S/4HANA fronted by MuleSoft, governance-tagged for regulated-industry use as the artifact-led re-nudge. His stalled thread reopens on a different artifact; SAP-on-MuleSoft is the canonical Deloitte-client integration shape.
