---
categories: []
consumed_apis:
- cvent
description: A composite MCP tool that mashes Cvent Event Cloud attendee + session + registration endpoints into one business-case-driven agent surface (per Jeff's "composite tools, not 1:1 mirrors").
layout: capability
naftiko_layer: service-anchored
naftiko_partner: Jeff Seifert
name: Cvent Event Cloud Attendee Context Mashup
operations: []
personas: []
provider_name: Cvent
provider_slug: cvent
search_terms:
- composite
- tool
- that
- mashes
- cvent
slug: event-cloud-attendee-context-mashup
source_filename: event-cloud-attendee-context-mashup.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Cvent Event Cloud Attendee Context Mashup
    description: A composite MCP tool that mashes Cvent Event Cloud attendee + session + registration endpoints into one business-case-driven agent surface (per Jeff's "composite tools, not 1:1 mirrors").
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
      namespace: event-cloud-attendee-context-mashup-rest
      description: REST API for Cvent Event Cloud Attendee Context Mashup.
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
      namespace: event-cloud-attendee-context-mashup-mcp
      description: MCP server exposing Cvent Event Cloud Attendee Context Mashup for AI agents.
      tools:
      - name: example
        description: A composite MCP tool that mashes Cvent Event Cloud attendee + session + registration endpoints into one business-case-driven agent surface (per Jeff's "composite tools, not 1:1 mirrors").
        hints:
          readOnly: true
        call: cvent.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: event-cloud-attendee-context-mashup-skills
      description: Agent Skill bundle for Cvent Event Cloud Attendee Context Mashup.
      skills:
      - name: event-cloud-attendee-context-mashup
        description: A composite MCP tool that mashes Cvent Event Cloud attendee + session + registration endpoints into one business-case-driven agent surface (per Jeff's "composite tools, not 1:1 mirrors").
        location: file:///opt/naftiko/skills/event-cloud-attendee-context-mashup
        allowed-tools: example
        tools:
        - name: example
          description: A composite MCP tool that mashes Cvent Event Cloud attendee + session + registration endpoints into one business-case-driven agent surface (per Jeff's "composite tools, not 1:1 mirrors").
          from:
            sourceNamespace: event-cloud-attendee-context-mashup-mcp
            action: example
---

A composite MCP tool that mashes Cvent Event Cloud attendee + session + registration endpoints into one business-case-driven agent surface (per Jeff's "composite tools, not 1:1 mirrors"). His 2026-01-08 conversation explicitly argued composite MCP over 1:1 mirroring — this is that pattern on Cvent's own product surface.
