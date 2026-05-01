---
categories: []
consumed_apis:
- port-of-context
description: A capability that wraps a Port of Context SDK-gen pipeline output as a Naftiko-runnable adapter, demonstrating the SDK-techniques-applied-to-context idea on one shared spec.
layout: capability
naftiko_layer: service-anchored
naftiko_partner: Patrick Kelly
name: Port of Context Sdk Gen Pipeline Mirror Capability
operations: []
personas: []
provider_name: Port of Context
provider_slug: port-of-context
search_terms:
- capability
- that
- wraps
- port
- context
slug: sdk-gen-pipeline-mirror-capability
source_filename: sdk-gen-pipeline-mirror-capability.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Port of Context Sdk Gen Pipeline Mirror Capability
    description: A capability that wraps a Port of Context SDK-gen pipeline output as a Naftiko-runnable adapter, demonstrating the SDK-techniques-applied-to-context idea on one shared spec.
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
      namespace: sdk-gen-pipeline-mirror-capability-rest
      description: REST API for Port of Context Sdk Gen Pipeline Mirror Capability.
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
      namespace: sdk-gen-pipeline-mirror-capability-mcp
      description: MCP server exposing Port of Context Sdk Gen Pipeline Mirror Capability for AI agents.
      tools:
      - name: example
        description: A capability that wraps a Port of Context SDK-gen pipeline output as a Naftiko-runnable adapter, demonstrating the SDK-techniques-applied-to-context idea on one shared spec.
        hints:
          readOnly: true
        call: port-of-context.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: sdk-gen-pipeline-mirror-capability-skills
      description: Agent Skill bundle for Port of Context Sdk Gen Pipeline Mirror Capability.
      skills:
      - name: sdk-gen-pipeline-mirror-capability
        description: A capability that wraps a Port of Context SDK-gen pipeline output as a Naftiko-runnable adapter, demonstrating the SDK-techniques-applied-to-context idea on one shared spec.
        location: file:///opt/naftiko/skills/sdk-gen-pipeline-mirror-capability
        allowed-tools: example
        tools:
        - name: example
          description: A capability that wraps a Port of Context SDK-gen pipeline output as a Naftiko-runnable adapter, demonstrating the SDK-techniques-applied-to-context idea on one shared spec.
          from:
            sourceNamespace: sdk-gen-pipeline-mirror-capability-mcp
            action: example
---

A capability that wraps a Port of Context SDK-gen pipeline output as a Naftiko-runnable adapter, demonstrating the SDK-techniques-applied-to-context idea on one shared spec. His pivot story is "SDK gen → context engineering"; this capability is that story end-to-end.
