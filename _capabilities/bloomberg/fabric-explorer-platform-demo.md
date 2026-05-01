---
categories: []
consumed_apis:
- bloomberg
description: A capability bundle wired into NaftikoFabricExplorerPage + Federation Across Fabrics, framed as Bloomberg-Terminal-grade for API platform leadership.
layout: capability
naftiko_layer: proposed
naftiko_partner: Amit Mahale
name: Bloomberg Fabric Explorer Platform Demo
operations: []
personas: []
provider_name: Bloomberg
provider_slug: bloomberg
search_terms:
- capability
- bundle
- wired
- into
- naftikofabricexplorerpage
slug: fabric-explorer-platform-demo
source_filename: fabric-explorer-platform-demo.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Bloomberg Fabric Explorer Platform Demo
    description: A capability bundle wired into NaftikoFabricExplorerPage + Federation Across Fabrics, framed as Bloomberg-Terminal-grade for API platform leadership.
    tags:
    - Bloomberg
    created: '2026-04-30'
    modified: '2026-04-30'
  binds:
  - namespace: bloomberg-env
    description: Bloomberg credentials.
    keys:
      BLOOMBERG_API_KEY: BLOOMBERG_API_KEY
  capability:
    consumes:
    - namespace: bloomberg
      type: http
      baseUri: https://api.bloomberg.com
      authentication:
        type: bearer
        token: '{{BLOOMBERG_API_KEY}}'
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
      namespace: fabric-explorer-platform-demo-rest
      description: REST API for Bloomberg Fabric Explorer Platform Demo.
      resources:
      - name: example
        path: /example
        operations:
        - method: GET
          name: example-op
          call: bloomberg.example-op
    - type: mcp
      address: 0.0.0.0
      port: 3010
      namespace: fabric-explorer-platform-demo-mcp
      description: MCP server exposing Bloomberg Fabric Explorer Platform Demo for AI agents.
      tools:
      - name: example
        description: A capability bundle wired into NaftikoFabricExplorerPage + Federation Across Fabrics, framed as Bloomberg-Terminal-grade for API platform leadership.
        hints:
          readOnly: true
        call: bloomberg.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: fabric-explorer-platform-demo-skills
      description: Agent Skill bundle for Bloomberg Fabric Explorer Platform Demo.
      skills:
      - name: fabric-explorer-platform-demo
        description: A capability bundle wired into NaftikoFabricExplorerPage + Federation Across Fabrics, framed as Bloomberg-Terminal-grade for API platform leadership.
        location: file:///opt/naftiko/skills/fabric-explorer-platform-demo
        allowed-tools: example
        tools:
        - name: example
          description: A capability bundle wired into NaftikoFabricExplorerPage + Federation Across Fabrics, framed as Bloomberg-Terminal-grade for API platform leadership.
          from:
            sourceNamespace: fabric-explorer-platform-demo-mcp
            action: example
---

A capability bundle wired into NaftikoFabricExplorerPage + Federation Across Fabrics, framed as Bloomberg-Terminal-grade for API platform leadership. Head of API Platform at Bloomberg = federated, observable, governed at scale.
