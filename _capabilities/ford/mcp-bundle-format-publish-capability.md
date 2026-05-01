---
categories: []
consumed_apis:
- ford
description: A capability that publishes Ford's Naftiko-governed capability set in the November 2025 MCP Bundle Format spec so they can be installed into any compliant agent runtime as a unit.
layout: capability
naftiko_layer: service-anchored
naftiko_partner: John Musser
name: Ford Mcp Bundle Format Publish Capability
operations: []
personas: []
provider_name: Ford
provider_slug: ford
search_terms:
- capability
- that
- publishes
- ford
- naftiko
slug: mcp-bundle-format-publish-capability
source_filename: mcp-bundle-format-publish-capability.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Ford Mcp Bundle Format Publish Capability
    description: A capability that publishes Ford's Naftiko-governed capability set in the November 2025 MCP Bundle Format spec so they can be installed into any compliant agent runtime as a unit.
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
      namespace: mcp-bundle-format-publish-capability-rest
      description: REST API for Ford Mcp Bundle Format Publish Capability.
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
      namespace: mcp-bundle-format-publish-capability-mcp
      description: MCP server exposing Ford Mcp Bundle Format Publish Capability for AI agents.
      tools:
      - name: example
        description: A capability that publishes Ford's Naftiko-governed capability set in the November 2025 MCP Bundle Format spec so they can be installed into any compliant agent runtime as a unit.
        hints:
          readOnly: true
        call: ford.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: mcp-bundle-format-publish-capability-skills
      description: Agent Skill bundle for Ford Mcp Bundle Format Publish Capability.
      skills:
      - name: mcp-bundle-format-publish-capability
        description: A capability that publishes Ford's Naftiko-governed capability set in the November 2025 MCP Bundle Format spec so they can be installed into any compliant agent runtime as a unit.
        location: file:///opt/naftiko/skills/mcp-bundle-format-publish-capability
        allowed-tools: example
        tools:
        - name: example
          description: A capability that publishes Ford's Naftiko-governed capability set in the November 2025 MCP Bundle Format spec so they can be installed into any compliant agent runtime as a unit.
          from:
            sourceNamespace: mcp-bundle-format-publish-capability-mcp
            action: example
---

A capability that publishes Ford's Naftiko-governed capability set in the November 2025 MCP Bundle Format spec so they can be installed into any compliant agent runtime as a unit. Both he and Kin are tracking the new spec; a Ford-shaped bundle is the artifact that proves the new format and the Naftiko publish pipeline align cleanly without bespoke conversion.
