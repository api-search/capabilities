---
categories: []
consumed_apis:
- port-of-context
description: Naftiko-generated Port of Context capabilities cross-listed in a Backstage catalog scaffold, making the joint demo portable.
layout: capability
naftiko_layer: proposed
naftiko_partner: Patrick Kelly
name: Port of Context Shared Backstage Catalog
operations: []
personas: []
provider_name: Port of Context
provider_slug: port-of-context
search_terms:
- naftiko
- generated
- port
- context
- capabilities
slug: shared-backstage-catalog
source_filename: shared-backstage-catalog.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Port of Context Shared Backstage Catalog
    description: Naftiko-generated Port of Context capabilities cross-listed in a Backstage catalog scaffold, making the joint demo portable.
    tags:
    - Port of Context
    created: '2026-04-30'
    modified: '2026-04-30'
  binds:
  - namespace: port-of-context-env
    description: Port of Context credentials.
    keys:
      PORT_OF_CONTEXT_API_KEY: PORT_OF_CONTEXT_API_KEY
  capability:
    consumes:
    - namespace: port-of-context
      type: http
      baseUri: https://api.port-of-context.com
      authentication:
        type: bearer
        token: '{{PORT_OF_CONTEXT_API_KEY}}'
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
      namespace: shared-backstage-catalog-rest
      description: REST API for Port of Context Shared Backstage Catalog.
      resources:
      - name: example
        path: /example
        operations:
        - method: GET
          name: example-op
          call: port-of-context.example-op
    - type: mcp
      address: 0.0.0.0
      port: 3010
      namespace: shared-backstage-catalog-mcp
      description: MCP server exposing Port of Context Shared Backstage Catalog for AI agents.
      tools:
      - name: example
        description: Naftiko-generated Port of Context capabilities cross-listed in a Backstage catalog scaffold, making the joint demo portable.
        hints:
          readOnly: true
        call: port-of-context.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: shared-backstage-catalog-skills
      description: Agent Skill bundle for Port of Context Shared Backstage Catalog.
      skills:
      - name: shared-backstage-catalog
        description: Naftiko-generated Port of Context capabilities cross-listed in a Backstage catalog scaffold, making the joint demo portable.
        location: file:///opt/naftiko/skills/shared-backstage-catalog
        allowed-tools: example
        tools:
        - name: example
          description: Naftiko-generated Port of Context capabilities cross-listed in a Backstage catalog scaffold, making the joint demo portable.
          from:
            sourceNamespace: shared-backstage-catalog-mcp
            action: example
---

Naftiko-generated Port of Context capabilities cross-listed in a Backstage catalog scaffold, making the joint demo portable. Both companies sit at the MCP layer; a shared catalog gives the partnership a tangible surface.
