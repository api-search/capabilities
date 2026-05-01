---
categories: []
consumed_apis:
- ford
description: A capability authored to deploy via NaftikoCapability CRD + CapabilityClass, paired with a Backstage template, used to demonstrate "thousands of capabilities under one fleet."
layout: capability
naftiko_layer: proposed
naftiko_partner: John Musser
name: Ford Fortune50 Fleet Scale Demo
operations: []
personas: []
provider_name: Ford
provider_slug: ford
search_terms:
- capability
- authored
- deploy
- naftikocapability
- capabilityclass
slug: fortune50-fleet-scale-demo
source_filename: fortune50-fleet-scale-demo.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Ford Fortune50 Fleet Scale Demo
    description: A capability authored to deploy via NaftikoCapability CRD + CapabilityClass, paired with a Backstage template, used to demonstrate "thousands of capabilities under one fleet."
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
      namespace: fortune50-fleet-scale-demo-rest
      description: REST API for Ford Fortune50 Fleet Scale Demo.
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
      namespace: fortune50-fleet-scale-demo-mcp
      description: MCP server exposing Ford Fortune50 Fleet Scale Demo for AI agents.
      tools:
      - name: example
        description: A capability authored to deploy via NaftikoCapability CRD + CapabilityClass, paired with a Backstage template, used to demonstrate "thousands of capabilities under one fleet."
        hints:
          readOnly: true
        call: ford.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: fortune50-fleet-scale-demo-skills
      description: Agent Skill bundle for Ford Fortune50 Fleet Scale Demo.
      skills:
      - name: fortune50-fleet-scale-demo
        description: A capability authored to deploy via NaftikoCapability CRD + CapabilityClass, paired with a Backstage template, used to demonstrate "thousands of capabilities under one fleet."
        location: file:///opt/naftiko/skills/fortune50-fleet-scale-demo
        allowed-tools: example
        tools:
        - name: example
          description: A capability authored to deploy via NaftikoCapability CRD + CapabilityClass, paired with a Backstage template, used to demonstrate "thousands of capabilities under one fleet."
          from:
            sourceNamespace: fortune50-fleet-scale-demo-mcp
            action: example
---

A capability authored to deploy via NaftikoCapability CRD + CapabilityClass, paired with a Backstage template, used to demonstrate "thousands of capabilities under one fleet." His scope is enterprise-AI architecture for a Fortune 50; the fleet/CRD layer is what makes the proposal credible at that scale.
