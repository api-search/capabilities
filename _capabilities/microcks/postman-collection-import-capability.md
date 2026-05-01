---
categories: []
consumed_apis:
- microcks
description: A capability that consumes a Postman collection imported into Microcks and exposes the mocked operations as MCP tools — letting Postman-using teams reach agent-callable parity through Microcks + Naftiko.
layout: capability
naftiko_layer: service-anchored
naftiko_partner: Laurent Broudoux
name: Microcks Postman Collection Import Capability
operations: []
personas: []
provider_name: Microcks
provider_slug: microcks
search_terms:
- capability
- that
- consumes
- postman
- collection
slug: postman-collection-import-capability
source_filename: postman-collection-import-capability.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Microcks Postman Collection Import Capability
    description: A capability that consumes a Postman collection imported into Microcks and exposes the mocked operations as MCP tools — letting Postman-using teams reach agent-callable parity through Microcks + Naftiko.
    tags:
    - Microcks
    created: '2026-04-30'
    modified: '2026-04-30'
  binds:
  - namespace: microcks-env
    description: Microcks credentials.
    keys:
      MICROCKS_API_KEY: MICROCKS_API_KEY
  capability:
    consumes:
    - namespace: microcks
      type: http
      baseUri: https://api.microcks.com
      authentication:
        type: bearer
        token: '{{MICROCKS_API_KEY}}'
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
      namespace: postman-collection-import-capability-rest
      description: REST API for Microcks Postman Collection Import Capability.
      resources:
      - name: example
        path: /example
        operations:
        - method: GET
          name: example-op
          call: microcks.example-op
    - type: mcp
      address: 0.0.0.0
      port: 3010
      namespace: postman-collection-import-capability-mcp
      description: MCP server exposing Microcks Postman Collection Import Capability for AI agents.
      tools:
      - name: example
        description: A capability that consumes a Postman collection imported into Microcks and exposes the mocked operations as MCP tools — letting Postman-using teams reach agent-callable parity through Microcks + Naftiko.
        hints:
          readOnly: true
        call: microcks.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: postman-collection-import-capability-skills
      description: Agent Skill bundle for Microcks Postman Collection Import Capability.
      skills:
      - name: postman-collection-import-capability
        description: A capability that consumes a Postman collection imported into Microcks and exposes the mocked operations as MCP tools — letting Postman-using teams reach agent-callable parity through Microcks + Naftiko.
        location: file:///opt/naftiko/skills/postman-collection-import-capability
        allowed-tools: example
        tools:
        - name: example
          description: A capability that consumes a Postman collection imported into Microcks and exposes the mocked operations as MCP tools — letting Postman-using teams reach agent-callable parity through Microcks + Naftiko.
          from:
            sourceNamespace: postman-collection-import-capability-mcp
            action: example
---

A capability that consumes a Postman collection imported into Microcks and exposes the mocked operations as MCP tools — letting Postman-using teams reach agent-callable parity through Microcks + Naftiko. Postman-import is Microcks's adoption funnel; bridging it into MCP via Naftiko is a clean partnership boundary that brings Postman users in too.
