---
categories: []
consumed_apis:
- vanguard
description: A federated capability across Datadog + Splunk + New Relic exposed as one fabric-wide observability MCP tool.
layout: capability
naftiko_layer: service-anchored
naftiko_partner: Vanguard
name: Vanguard Datadog Splunk Observability Fabric Capability
operations: []
personas: []
provider_name: Vanguard
provider_slug: vanguard
search_terms:
- federated
- capability
- across
- datadog
- splunk
slug: datadog-splunk-observability-fabric-capability
source_filename: datadog-splunk-observability-fabric-capability.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Vanguard Datadog Splunk Observability Fabric Capability
    description: A federated capability across Datadog + Splunk + New Relic exposed as one fabric-wide observability MCP tool.
    tags:
    - Vanguard
    created: '2026-04-30'
    modified: '2026-04-30'
  binds:
  - namespace: vanguard-env
    description: Vanguard credentials.
    keys:
      VANGUARD_API_KEY: VANGUARD_API_KEY
  capability:
    consumes:
    - namespace: vanguard
      type: http
      baseUri: https://api.vanguard.com
      authentication:
        type: bearer
        token: '{{VANGUARD_API_KEY}}'
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
      namespace: datadog-splunk-observability-fabric-capability-rest
      description: REST API for Vanguard Datadog Splunk Observability Fabric Capability.
      resources:
      - name: example
        path: /example
        operations:
        - method: GET
          name: example-op
          call: vanguard.example-op
    - type: mcp
      address: 0.0.0.0
      port: 3010
      namespace: datadog-splunk-observability-fabric-capability-mcp
      description: MCP server exposing Vanguard Datadog Splunk Observability Fabric Capability for AI agents.
      tools:
      - name: example
        description: A federated capability across Datadog + Splunk + New Relic exposed as one fabric-wide observability MCP tool.
        hints:
          readOnly: true
        call: vanguard.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: datadog-splunk-observability-fabric-capability-skills
      description: Agent Skill bundle for Vanguard Datadog Splunk Observability Fabric Capability.
      skills:
      - name: datadog-splunk-observability-fabric-capability
        description: A federated capability across Datadog + Splunk + New Relic exposed as one fabric-wide observability MCP tool.
        location: file:///opt/naftiko/skills/datadog-splunk-observability-fabric-capability
        allowed-tools: example
        tools:
        - name: example
          description: A federated capability across Datadog + Splunk + New Relic exposed as one fabric-wide observability MCP tool.
          from:
            sourceNamespace: datadog-splunk-observability-fabric-capability-mcp
            action: example
---

A federated capability across Datadog + Splunk + New Relic exposed as one fabric-wide observability MCP tool. Fabric-wide visibility across three observability tools is the role-agnostic shared message — useful for **Sesha Raman / Andrea Sugano** while role is captured.
