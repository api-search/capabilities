---
categories: []
consumed_apis:
- ford
description: A capability that handles on-behalf-of token propagation across agent-to-agent calls, using Ford's Okta + Auth0 standards work to keep identity continuous through multi-step agent flows alongside the existing Microsoft Agent 365 bridge.
layout: capability
naftiko_layer: service-anchored
naftiko_partner: John Musser
name: Ford Okta Auth0 Obo Token Propagation Capability
operations: []
personas: []
provider_name: Ford
provider_slug: ford
search_terms:
- capability
- that
- handles
- behalf
- token
slug: okta-auth0-obo-token-propagation-capability
source_filename: okta-auth0-obo-token-propagation-capability.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Ford Okta Auth0 Obo Token Propagation Capability
    description: A capability that handles on-behalf-of token propagation across agent-to-agent calls, using Ford's Okta + Auth0 standards work to keep identity continuous through multi-step agent flows alongside the existing Microsoft Agent 365 bridge.
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
      namespace: okta-auth0-obo-token-propagation-capability-rest
      description: REST API for Ford Okta Auth0 Obo Token Propagation Capability.
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
      namespace: okta-auth0-obo-token-propagation-capability-mcp
      description: MCP server exposing Ford Okta Auth0 Obo Token Propagation Capability for AI agents.
      tools:
      - name: example
        description: A capability that handles on-behalf-of token propagation across agent-to-agent calls, using Ford's Okta + Auth0 standards work to keep identity continuous through multi-step agent flows alongside the existing Microsoft Agent 365 bridge.
        hints:
          readOnly: true
        call: ford.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: okta-auth0-obo-token-propagation-capability-skills
      description: Agent Skill bundle for Ford Okta Auth0 Obo Token Propagation Capability.
      skills:
      - name: okta-auth0-obo-token-propagation-capability
        description: A capability that handles on-behalf-of token propagation across agent-to-agent calls, using Ford's Okta + Auth0 standards work to keep identity continuous through multi-step agent flows alongside the existing Microsoft Agent 365 bridge.
        location: file:///opt/naftiko/skills/okta-auth0-obo-token-propagation-capability
        allowed-tools: example
        tools:
        - name: example
          description: A capability that handles on-behalf-of token propagation across agent-to-agent calls, using Ford's Okta + Auth0 standards work to keep identity continuous through multi-step agent flows alongside the existing Microsoft Agent 365 bridge.
          from:
            sourceNamespace: okta-auth0-obo-token-propagation-capability-mcp
            action: example
---

A capability that handles on-behalf-of token propagation across agent-to-agent calls, using Ford's Okta + Auth0 standards work to keep identity continuous through multi-step agent flows alongside the existing Microsoft Agent 365 bridge. OBO propagation was his #3 of four key enterprise challenges in the Nov 6 call; the existing Microsoft Agent 365 identity bridge covers Entra — this covers the Okta + Auth0 side of the federated identity estate.
