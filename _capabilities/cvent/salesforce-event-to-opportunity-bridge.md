---
categories: []
consumed_apis:
- cvent
description: A capability that consumes a Cvent attendee event and pushes it as a Salesforce Opportunity update via Salesforce Lightning, with shaped agent output for sales follow-up.
layout: capability
naftiko_layer: service-anchored
naftiko_partner: Jeff Seifert
name: Cvent Salesforce Event To Opportunity Bridge
operations: []
personas: []
provider_name: Cvent
provider_slug: cvent
search_terms:
- capability
- that
- consumes
- cvent
- attendee
slug: salesforce-event-to-opportunity-bridge
source_filename: salesforce-event-to-opportunity-bridge.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Cvent Salesforce Event To Opportunity Bridge
    description: A capability that consumes a Cvent attendee event and pushes it as a Salesforce Opportunity update via Salesforce Lightning, with shaped agent output for sales follow-up.
    tags:
    - Cvent
    created: '2026-04-30'
    modified: '2026-04-30'
  binds:
  - namespace: cvent-env
    description: Cvent credentials.
    keys:
      CVENT_API_KEY: CVENT_API_KEY
  capability:
    consumes:
    - namespace: cvent
      type: http
      baseUri: https://api.cvent.com
      authentication:
        type: bearer
        token: '{{CVENT_API_KEY}}'
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
      namespace: salesforce-event-to-opportunity-bridge-rest
      description: REST API for Cvent Salesforce Event To Opportunity Bridge.
      resources:
      - name: example
        path: /example
        operations:
        - method: GET
          name: example-op
          call: cvent.example-op
    - type: mcp
      address: 0.0.0.0
      port: 3010
      namespace: salesforce-event-to-opportunity-bridge-mcp
      description: MCP server exposing Cvent Salesforce Event To Opportunity Bridge for AI agents.
      tools:
      - name: example
        description: A capability that consumes a Cvent attendee event and pushes it as a Salesforce Opportunity update via Salesforce Lightning, with shaped agent output for sales follow-up.
        hints:
          readOnly: true
        call: cvent.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: salesforce-event-to-opportunity-bridge-skills
      description: Agent Skill bundle for Cvent Salesforce Event To Opportunity Bridge.
      skills:
      - name: salesforce-event-to-opportunity-bridge
        description: A capability that consumes a Cvent attendee event and pushes it as a Salesforce Opportunity update via Salesforce Lightning, with shaped agent output for sales follow-up.
        location: file:///opt/naftiko/skills/salesforce-event-to-opportunity-bridge
        allowed-tools: example
        tools:
        - name: example
          description: A capability that consumes a Cvent attendee event and pushes it as a Salesforce Opportunity update via Salesforce Lightning, with shaped agent output for sales follow-up.
          from:
            sourceNamespace: salesforce-event-to-opportunity-bridge-mcp
            action: example
---

A capability that consumes a Cvent attendee event and pushes it as a Salesforce Opportunity update via Salesforce Lightning, with shaped agent output for sales follow-up. Salesforce sits high on Cvent's services profile; bridging Cvent → Salesforce is the canonical mashup their event business runs daily.
