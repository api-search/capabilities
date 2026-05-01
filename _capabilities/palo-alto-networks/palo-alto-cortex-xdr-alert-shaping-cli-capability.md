---
categories: []
consumed_apis:
- palo-alto-networks
description: A CLI-runnable capability wrapping the Palo Alto Cortex XDR alerts API, returning a shaped agent context object — designed to bypass the Docker container startup blocker.
layout: capability
naftiko_layer: service-anchored
naftiko_partner: James DeVore
name: Palo Alto Networks Palo Alto Cortex Xdr Alert Shaping Cli Capability
operations: []
personas: []
provider_name: Palo Alto Networks
provider_slug: palo-alto-networks
search_terms:
- runnable
- capability
- wrapping
- palo
- alto
slug: palo-alto-cortex-xdr-alert-shaping-cli-capability
source_filename: palo-alto-cortex-xdr-alert-shaping-cli-capability.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Palo Alto Networks Palo Alto Cortex Xdr Alert Shaping Cli Capability
    description: A CLI-runnable capability wrapping the Palo Alto Cortex XDR alerts API, returning a shaped agent context object — designed to bypass the Docker container startup blocker.
    tags:
    - Palo Alto Networks
    created: '2026-04-30'
    modified: '2026-04-30'
  binds:
  - namespace: palo-alto-networks-env
    description: Palo Alto Networks credentials.
    keys:
      PALO_ALTO_NETWORKS_API_KEY: PALO_ALTO_NETWORKS_API_KEY
  capability:
    consumes:
    - namespace: palo-alto-networks
      type: http
      baseUri: https://api.palo-alto-networks.com
      authentication:
        type: bearer
        token: '{{PALO_ALTO_NETWORKS_API_KEY}}'
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
      namespace: palo-alto-cortex-xdr-alert-shaping-cli-capability-rest
      description: REST API for Palo Alto Networks Palo Alto Cortex Xdr Alert Shaping Cli Capability.
      resources:
      - name: example
        path: /example
        operations:
        - method: GET
          name: example-op
          call: palo-alto-networks.example-op
    - type: mcp
      address: 0.0.0.0
      port: 3010
      namespace: palo-alto-cortex-xdr-alert-shaping-cli-capability-mcp
      description: MCP server exposing Palo Alto Networks Palo Alto Cortex Xdr Alert Shaping Cli Capability for AI agents.
      tools:
      - name: example
        description: A CLI-runnable capability wrapping the Palo Alto Cortex XDR alerts API, returning a shaped agent context object — designed to bypass the Docker container startup blocker.
        hints:
          readOnly: true
        call: palo-alto-networks.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: palo-alto-cortex-xdr-alert-shaping-cli-capability-skills
      description: Agent Skill bundle for Palo Alto Networks Palo Alto Cortex Xdr Alert Shaping Cli Capability.
      skills:
      - name: palo-alto-cortex-xdr-alert-shaping-cli-capability
        description: A CLI-runnable capability wrapping the Palo Alto Cortex XDR alerts API, returning a shaped agent context object — designed to bypass the Docker container startup blocker.
        location: file:///opt/naftiko/skills/palo-alto-cortex-xdr-alert-shaping-cli-capability
        allowed-tools: example
        tools:
        - name: example
          description: A CLI-runnable capability wrapping the Palo Alto Cortex XDR alerts API, returning a shaped agent context object — designed to bypass the Docker container startup blocker.
          from:
            sourceNamespace: palo-alto-cortex-xdr-alert-shaping-cli-capability-mcp
            action: example
---

A CLI-runnable capability wrapping the Palo Alto Cortex XDR alerts API, returning a shaped agent context object — designed to bypass the Docker container startup blocker. His next-step is blocked on container startup AND he documents Cortex APIs — a CLI path on the API he writes about unblocks both.
