---
categories: []
consumed_apis:
- cvent
description: A capability deployed via the NaftikoCapability CRD that simultaneously exposes MCP Tools/Resources/Prompts, demonstrating MCP-as-platform-resource end-to-end.
layout: capability
naftiko_layer: proposed
naftiko_partner: Jeff Seifert
name: Cvent Mcp As K8s Resource Demo
operations: []
personas: []
provider_name: Cvent
provider_slug: cvent
search_terms:
- capability
- deployed
- naftikocapability
- that
- simultaneously
slug: mcp-as-k8s-resource-demo
source_filename: mcp-as-k8s-resource-demo.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Cvent Mcp As K8s Resource Demo
    description: A capability deployed via the NaftikoCapability CRD that simultaneously exposes MCP Tools/Resources/Prompts, demonstrating MCP-as-platform-resource end-to-end.
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
      namespace: mcp-as-k8s-resource-demo-rest
      description: REST API for Cvent Mcp As K8s Resource Demo.
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
      namespace: mcp-as-k8s-resource-demo-mcp
      description: MCP server exposing Cvent Mcp As K8s Resource Demo for AI agents.
      tools:
      - name: example
        description: A capability deployed via the NaftikoCapability CRD that simultaneously exposes MCP Tools/Resources/Prompts, demonstrating MCP-as-platform-resource end-to-end.
        hints:
          readOnly: true
        call: cvent.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: mcp-as-k8s-resource-demo-skills
      description: Agent Skill bundle for Cvent Mcp As K8s Resource Demo.
      skills:
      - name: mcp-as-k8s-resource-demo
        description: A capability deployed via the NaftikoCapability CRD that simultaneously exposes MCP Tools/Resources/Prompts, demonstrating MCP-as-platform-resource end-to-end.
        location: file:///opt/naftiko/skills/mcp-as-k8s-resource-demo
        allowed-tools: example
        tools:
        - name: example
          description: A capability deployed via the NaftikoCapability CRD that simultaneously exposes MCP Tools/Resources/Prompts, demonstrating MCP-as-platform-resource end-to-end.
          from:
            sourceNamespace: mcp-as-k8s-resource-demo-mcp
            action: example
---

A capability deployed via the NaftikoCapability CRD that simultaneously exposes MCP Tools/Resources/Prompts, demonstrating MCP-as-platform-resource end-to-end. His ask is MCP grounded in platform definitions; this shows the spec, the CRD, and the running MCP server as one chain.
