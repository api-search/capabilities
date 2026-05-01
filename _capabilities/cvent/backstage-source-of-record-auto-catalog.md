---
categories: []
consumed_apis:
- cvent
description: A capability that walks GitHub + Datadog + ServiceNow as systems-of-record and auto-publishes Backstage catalog entities so developers never enter catalog data manually (Mark's stated zero-manual-work principle).
layout: capability
naftiko_layer: service-anchored
naftiko_partner: Jeff Seifert
name: Cvent Backstage Source Of Record Auto Catalog
operations: []
personas: []
provider_name: Cvent
provider_slug: cvent
search_terms:
- capability
- that
- walks
- github
- datadog
slug: backstage-source-of-record-auto-catalog
source_filename: backstage-source-of-record-auto-catalog.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Cvent Backstage Source Of Record Auto Catalog
    description: A capability that walks GitHub + Datadog + ServiceNow as systems-of-record and auto-publishes Backstage catalog entities so developers never enter catalog data manually (Mark's stated zero-manual-work principle).
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
      namespace: backstage-source-of-record-auto-catalog-rest
      description: REST API for Cvent Backstage Source Of Record Auto Catalog.
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
      namespace: backstage-source-of-record-auto-catalog-mcp
      description: MCP server exposing Cvent Backstage Source Of Record Auto Catalog for AI agents.
      tools:
      - name: example
        description: A capability that walks GitHub + Datadog + ServiceNow as systems-of-record and auto-publishes Backstage catalog entities so developers never enter catalog data manually (Mark's stated zero-manual-work principle).
        hints:
          readOnly: true
        call: cvent.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: backstage-source-of-record-auto-catalog-skills
      description: Agent Skill bundle for Cvent Backstage Source Of Record Auto Catalog.
      skills:
      - name: backstage-source-of-record-auto-catalog
        description: A capability that walks GitHub + Datadog + ServiceNow as systems-of-record and auto-publishes Backstage catalog entities so developers never enter catalog data manually (Mark's stated zero-manual-work principle).
        location: file:///opt/naftiko/skills/backstage-source-of-record-auto-catalog
        allowed-tools: example
        tools:
        - name: example
          description: A capability that walks GitHub + Datadog + ServiceNow as systems-of-record and auto-publishes Backstage catalog entities so developers never enter catalog data manually (Mark's stated zero-manual-work principle).
          from:
            sourceNamespace: backstage-source-of-record-auto-catalog-mcp
            action: example
---

A capability that walks GitHub + Datadog + ServiceNow as systems-of-record and auto-publishes Backstage catalog entities so developers never enter catalog data manually (Mark's stated zero-manual-work principle). His 2026-01-08 conversation IS this design — make it a runnable Naftiko capability.
