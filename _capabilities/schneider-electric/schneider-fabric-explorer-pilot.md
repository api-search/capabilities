---
categories: []
consumed_apis:
- schneider-electric
description: A pilot fabric configuration with NaftikoCapability CRD + Operator + Backstage NaftikoFabricExplorerPage managing the registry at scale.
layout: capability
naftiko_layer: proposed
naftiko_partner: Manu PK
name: Schneider Electric Schneider Fabric Explorer Pilot
operations: []
personas: []
provider_name: Schneider Electric
provider_slug: schneider-electric
search_terms:
- pilot
- fabric
- configuration
- with
- naftikocapability
slug: schneider-fabric-explorer-pilot
source_filename: schneider-fabric-explorer-pilot.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Schneider Electric Schneider Fabric Explorer Pilot
    description: A pilot fabric configuration with NaftikoCapability CRD + Operator + Backstage NaftikoFabricExplorerPage managing the registry at scale.
    tags:
    - Schneider Electric
    created: '2026-04-30'
    modified: '2026-04-30'
  binds:
  - namespace: schneider-electric-env
    description: Schneider Electric credentials.
    keys:
      SCHNEIDER_ELECTRIC_API_KEY: SCHNEIDER_ELECTRIC_API_KEY
  capability:
    consumes:
    - namespace: schneider-electric
      type: http
      baseUri: https://api.schneider-electric.com
      authentication:
        type: bearer
        token: '{{SCHNEIDER_ELECTRIC_API_KEY}}'
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
      namespace: schneider-fabric-explorer-pilot-rest
      description: REST API for Schneider Electric Schneider Fabric Explorer Pilot.
      resources:
      - name: example
        path: /example
        operations:
        - method: GET
          name: example-op
          call: schneider-electric.example-op
    - type: mcp
      address: 0.0.0.0
      port: 3010
      namespace: schneider-fabric-explorer-pilot-mcp
      description: MCP server exposing Schneider Electric Schneider Fabric Explorer Pilot for AI agents.
      tools:
      - name: example
        description: A pilot fabric configuration with NaftikoCapability CRD + Operator + Backstage NaftikoFabricExplorerPage managing the registry at scale.
        hints:
          readOnly: true
        call: schneider-electric.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: schneider-fabric-explorer-pilot-skills
      description: Agent Skill bundle for Schneider Electric Schneider Fabric Explorer Pilot.
      skills:
      - name: schneider-fabric-explorer-pilot
        description: A pilot fabric configuration with NaftikoCapability CRD + Operator + Backstage NaftikoFabricExplorerPage managing the registry at scale.
        location: file:///opt/naftiko/skills/schneider-fabric-explorer-pilot
        allowed-tools: example
        tools:
        - name: example
          description: A pilot fabric configuration with NaftikoCapability CRD + Operator + Backstage NaftikoFabricExplorerPage managing the registry at scale.
          from:
            sourceNamespace: schneider-fabric-explorer-pilot-mcp
            action: example
---

A pilot fabric configuration with NaftikoCapability CRD + Operator + Backstage NaftikoFabricExplorerPage managing the registry at scale. His thousands-of-services scale demands the Fabric Explorer + CRD layer.
