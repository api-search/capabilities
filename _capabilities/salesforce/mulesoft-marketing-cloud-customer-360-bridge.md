---
categories: []
consumed_apis:
- salesforce
description: A composed Customer-360 capability over Salesforce + MuleSoft + Marketing Cloud that returns one shaped agent context object.
layout: capability
naftiko_layer: service-anchored
naftiko_partner: Kris Harrison
name: Salesforce Mulesoft Marketing Cloud Customer 360 Bridge
operations: []
personas: []
provider_name: Salesforce
provider_slug: salesforce
search_terms:
- composed
- customer
- capability
- over
- salesforce
slug: mulesoft-marketing-cloud-customer-360-bridge
source_filename: mulesoft-marketing-cloud-customer-360-bridge.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Salesforce Mulesoft Marketing Cloud Customer 360 Bridge
    description: A composed Customer-360 capability over Salesforce + MuleSoft + Marketing Cloud that returns one shaped agent context object.
    tags:
    - Salesforce
    created: '2026-04-30'
    modified: '2026-04-30'
  binds:
  - namespace: salesforce-env
    description: Salesforce credentials.
    keys:
      SALESFORCE_API_KEY: SALESFORCE_API_KEY
  capability:
    consumes:
    - namespace: salesforce
      type: http
      baseUri: https://api.salesforce.com
      authentication:
        type: bearer
        token: '{{SALESFORCE_API_KEY}}'
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
      namespace: mulesoft-marketing-cloud-customer-360-bridge-rest
      description: REST API for Salesforce Mulesoft Marketing Cloud Customer 360 Bridge.
      resources:
      - name: example
        path: /example
        operations:
        - method: GET
          name: example-op
          call: salesforce.example-op
    - type: mcp
      address: 0.0.0.0
      port: 3010
      namespace: mulesoft-marketing-cloud-customer-360-bridge-mcp
      description: MCP server exposing Salesforce Mulesoft Marketing Cloud Customer 360 Bridge for AI agents.
      tools:
      - name: example
        description: A composed Customer-360 capability over Salesforce + MuleSoft + Marketing Cloud that returns one shaped agent context object.
        hints:
          readOnly: true
        call: salesforce.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: mulesoft-marketing-cloud-customer-360-bridge-skills
      description: Agent Skill bundle for Salesforce Mulesoft Marketing Cloud Customer 360 Bridge.
      skills:
      - name: mulesoft-marketing-cloud-customer-360-bridge
        description: A composed Customer-360 capability over Salesforce + MuleSoft + Marketing Cloud that returns one shaped agent context object.
        location: file:///opt/naftiko/skills/mulesoft-marketing-cloud-customer-360-bridge
        allowed-tools: example
        tools:
        - name: example
          description: A composed Customer-360 capability over Salesforce + MuleSoft + Marketing Cloud that returns one shaped agent context object.
          from:
            sourceNamespace: mulesoft-marketing-cloud-customer-360-bridge-mcp
            action: example
---

A composed Customer-360 capability over Salesforce + MuleSoft + Marketing Cloud that returns one shaped agent context object. Customer-360 is the canonical Salesforce narrative; the composition crosses Salesforce-owned brands and is internally pitchable.
