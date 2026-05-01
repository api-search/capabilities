---
categories: []
consumed_apis:
- ford
description: A capability that ships a Backstage Software Template bundling the NaftikoCapability CRD scaffold, so Ford developers spin up a new governed capability from inside the developer portal without leaving Backstage.
layout: capability
naftiko_layer: service-anchored
naftiko_partner: John Musser
name: Ford Backstage Naftiko Capability Template Capability
operations: []
personas: []
provider_name: Ford
provider_slug: ford
search_terms:
- capability
- that
- ships
- backstage
- software
slug: backstage-naftiko-capability-template-capability
source_filename: backstage-naftiko-capability-template-capability.yaml
source_heading: Capability Spec
source_yaml: |
  naftiko: 1.0.0-alpha2
  info:
    title: Ford Backstage Naftiko Capability Template Capability
    description: A capability that ships a Backstage Software Template bundling the NaftikoCapability CRD scaffold, so Ford developers spin up a new governed capability from inside the developer portal without leaving Backstage.
    tags:
    - Ford
    created: '2026-04-30'
    modified: '2026-04-30'
  binds:
  - namespace: ford-env
    description: Ford credentials.
    keys:
      FORD_API_KEY: FORD_API_KEY
  capability:
    consumes:
    - namespace: ford
      type: http
      baseUri: https://api.ford.com
      authentication:
        type: bearer
        token: '{{FORD_API_KEY}}'
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
      namespace: backstage-naftiko-capability-template-capability-rest
      description: REST API for Ford Backstage Naftiko Capability Template Capability.
      resources:
      - name: example
        path: /example
        operations:
        - method: GET
          name: example-op
          call: ford.example-op
    - type: mcp
      address: 0.0.0.0
      port: 3010
      namespace: backstage-naftiko-capability-template-capability-mcp
      description: MCP server exposing Ford Backstage Naftiko Capability Template Capability for AI agents.
      tools:
      - name: example
        description: A capability that ships a Backstage Software Template bundling the NaftikoCapability CRD scaffold, so Ford developers spin up a new governed capability from inside the developer portal without leaving Backstage.
        hints:
          readOnly: true
        call: ford.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: backstage-naftiko-capability-template-capability-skills
      description: Agent Skill bundle for Ford Backstage Naftiko Capability Template Capability.
      skills:
      - name: backstage-naftiko-capability-template-capability
        description: A capability that ships a Backstage Software Template bundling the NaftikoCapability CRD scaffold, so Ford developers spin up a new governed capability from inside the developer portal without leaving Backstage.
        location: file:///opt/naftiko/skills/backstage-naftiko-capability-template-capability
        allowed-tools: example
        tools:
        - name: example
          description: A capability that ships a Backstage Software Template bundling the NaftikoCapability CRD scaffold, so Ford developers spin up a new governed capability from inside the developer portal without leaving Backstage.
          from:
            sourceNamespace: backstage-naftiko-capability-template-capability-mcp
            action: example
---

A capability that ships a Backstage Software Template bundling the NaftikoCapability CRD scaffold, so Ford developers spin up a new governed capability from inside the developer portal without leaving Backstage. His Fortune-50 fleet-scale story already names Backstage; this is the runnable scaffolder asset that backs the proposal and integrates with the developer portal team's existing pipeline.
