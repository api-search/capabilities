---
categories: []
consumed_apis:
- bloomberg
description: A capability over Bloomberg EMSX (execution management) with explicit safety + effect tags + write-gate governance — the governance-automation runtime for the order-flow path.
layout: capability
naftiko_layer: service-anchored
naftiko_partner: Amit Mahale
name: Bloomberg Emsx Execution Governed Capability
operations: []
personas: []
provider_name: Bloomberg
provider_slug: bloomberg
search_terms:
- capability
- over
- bloomberg
- emsx
- execution
slug: emsx-execution-governed-capability
source_filename: emsx-execution-governed-capability.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Bloomberg Emsx Execution Governed Capability
    description: A capability over Bloomberg EMSX (execution management) with explicit safety + effect tags + write-gate governance — the governance-automation runtime for the order-flow path.
    tags:
    - Bloomberg
    created: '2026-04-30'
    modified: '2026-04-30'
  binds:
  - namespace: bloomberg-env
    description: Bloomberg credentials.
    keys:
      BLOOMBERG_API_KEY: BLOOMBERG_API_KEY
  capability:
    consumes:
    - namespace: bloomberg
      type: http
      baseUri: https://api.bloomberg.com
      authentication:
        type: bearer
        token: '{{BLOOMBERG_API_KEY}}'
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
      namespace: emsx-execution-governed-capability-rest
      description: REST API for Bloomberg Emsx Execution Governed Capability.
      resources:
      - name: example
        path: /example
        operations:
        - method: GET
          name: example-op
          call: bloomberg.example-op
    - type: mcp
      address: 0.0.0.0
      port: 3010
      namespace: emsx-execution-governed-capability-mcp
      description: MCP server exposing Bloomberg Emsx Execution Governed Capability for AI agents.
      tools:
      - name: example
        description: A capability over Bloomberg EMSX (execution management) with explicit safety + effect tags + write-gate governance — the governance-automation runtime for the order-flow path.
        hints:
          readOnly: true
        call: bloomberg.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: emsx-execution-governed-capability-skills
      description: Agent Skill bundle for Bloomberg Emsx Execution Governed Capability.
      skills:
      - name: emsx-execution-governed-capability
        description: A capability over Bloomberg EMSX (execution management) with explicit safety + effect tags + write-gate governance — the governance-automation runtime for the order-flow path.
        location: file:///opt/naftiko/skills/emsx-execution-governed-capability
        allowed-tools: example
        tools:
        - name: example
          description: A capability over Bloomberg EMSX (execution management) with explicit safety + effect tags + write-gate governance — the governance-automation runtime for the order-flow path.
          from:
            sourceNamespace: emsx-execution-governed-capability-mcp
            action: example
---

A capability over Bloomberg EMSX (execution management) with explicit safety + effect tags + write-gate governance — the governance-automation runtime for the order-flow path. His update was about Bloomberg's automation-of-governance work — EMSX is the highest-stakes write surface, the canonical place to demo governed automation.
