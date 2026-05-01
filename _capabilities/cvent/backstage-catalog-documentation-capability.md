---
categories: []
consumed_apis:
- cvent
description: A "documentation capability" that exposes capability metadata (specs, tags, lifecycle) via REST + MCP for Backstage catalog enrichment.
layout: capability
naftiko_layer: proposed
naftiko_partner: Jeff Seifert
name: Cvent Backstage Catalog Documentation Capability
operations: []
personas: []
provider_name: Cvent
provider_slug: cvent
search_terms:
- documentation
- capability
- that
- exposes
- metadata
slug: backstage-catalog-documentation-capability
source_filename: backstage-catalog-documentation-capability.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Cvent Backstage Catalog Documentation Capability
    description: A "documentation capability" that exposes capability metadata (specs, tags, lifecycle) via REST + MCP for Backstage catalog enrichment.
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
      namespace: backstage-catalog-documentation-capability-rest
      description: REST API for Cvent Backstage Catalog Documentation Capability.
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
      namespace: backstage-catalog-documentation-capability-mcp
      description: MCP server exposing Cvent Backstage Catalog Documentation Capability for AI agents.
      tools:
      - name: example
        description: A "documentation capability" that exposes capability metadata (specs, tags, lifecycle) via REST + MCP for Backstage catalog enrichment.
        hints:
          readOnly: true
        call: cvent.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: backstage-catalog-documentation-capability-skills
      description: Agent Skill bundle for Cvent Backstage Catalog Documentation Capability.
      skills:
      - name: backstage-catalog-documentation-capability
        description: A "documentation capability" that exposes capability metadata (specs, tags, lifecycle) via REST + MCP for Backstage catalog enrichment.
        location: file:///opt/naftiko/skills/backstage-catalog-documentation-capability
        allowed-tools: example
        tools:
        - name: example
          description: A "documentation capability" that exposes capability metadata (specs, tags, lifecycle) via REST + MCP for Backstage catalog enrichment.
          from:
            sourceNamespace: backstage-catalog-documentation-capability-mcp
            action: example
---

A "documentation capability" that exposes capability metadata (specs, tags, lifecycle) via REST + MCP for Backstage catalog enrichment. His next-step explicitly says "documentation capabilities" alongside Backstage and Kubernetes.
