---
categories: []
consumed_apis:
- cvent
description: A capability that surfaces ServiceNow incident counts on the matching Backstage entity card, joining ticketing to the catalog.
layout: capability
naftiko_layer: service-anchored
naftiko_partner: Jeff Seifert
name: Cvent Servicenow Incident To Backstage Runbook
operations: []
personas: []
provider_name: Cvent
provider_slug: cvent
search_terms:
- capability
- that
- surfaces
- servicenow
- incident
slug: servicenow-incident-to-backstage-runbook
source_filename: servicenow-incident-to-backstage-runbook.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Cvent Servicenow Incident To Backstage Runbook
    description: A capability that surfaces ServiceNow incident counts on the matching Backstage entity card, joining ticketing to the catalog.
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
      namespace: servicenow-incident-to-backstage-runbook-rest
      description: REST API for Cvent Servicenow Incident To Backstage Runbook.
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
      namespace: servicenow-incident-to-backstage-runbook-mcp
      description: MCP server exposing Cvent Servicenow Incident To Backstage Runbook for AI agents.
      tools:
      - name: example
        description: A capability that surfaces ServiceNow incident counts on the matching Backstage entity card, joining ticketing to the catalog.
        hints:
          readOnly: true
        call: cvent.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: servicenow-incident-to-backstage-runbook-skills
      description: Agent Skill bundle for Cvent Servicenow Incident To Backstage Runbook.
      skills:
      - name: servicenow-incident-to-backstage-runbook
        description: A capability that surfaces ServiceNow incident counts on the matching Backstage entity card, joining ticketing to the catalog.
        location: file:///opt/naftiko/skills/servicenow-incident-to-backstage-runbook
        allowed-tools: example
        tools:
        - name: example
          description: A capability that surfaces ServiceNow incident counts on the matching Backstage entity card, joining ticketing to the catalog.
          from:
            sourceNamespace: servicenow-incident-to-backstage-runbook-mcp
            action: example
---

A capability that surfaces ServiceNow incident counts on the matching Backstage entity card, joining ticketing to the catalog. He named ticketing as one of the four enrichment systems; this is the demo of that fourth integration.
