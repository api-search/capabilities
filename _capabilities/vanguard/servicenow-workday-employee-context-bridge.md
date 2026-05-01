---
categories: []
consumed_apis:
- vanguard
description: A composed capability across ServiceNow + Workday for an employee-context HR-AI agent at Vanguard's charitable arm, with /metrics + /health exposed.
layout: capability
naftiko_layer: service-anchored
naftiko_partner: Vanguard
name: Vanguard Servicenow Workday Employee Context Bridge
operations: []
personas: []
provider_name: Vanguard
provider_slug: vanguard
search_terms:
- composed
- capability
- across
- servicenow
- workday
slug: servicenow-workday-employee-context-bridge
source_filename: servicenow-workday-employee-context-bridge.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Vanguard Servicenow Workday Employee Context Bridge
    description: A composed capability across ServiceNow + Workday for an employee-context HR-AI agent at Vanguard's charitable arm, with /metrics + /health exposed.
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
      namespace: servicenow-workday-employee-context-bridge-rest
      description: REST API for Vanguard Servicenow Workday Employee Context Bridge.
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
      namespace: servicenow-workday-employee-context-bridge-mcp
      description: MCP server exposing Vanguard Servicenow Workday Employee Context Bridge for AI agents.
      tools:
      - name: example
        description: A composed capability across ServiceNow + Workday for an employee-context HR-AI agent at Vanguard's charitable arm, with /metrics + /health exposed.
        hints:
          readOnly: true
        call: vanguard.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: servicenow-workday-employee-context-bridge-skills
      description: Agent Skill bundle for Vanguard Servicenow Workday Employee Context Bridge.
      skills:
      - name: servicenow-workday-employee-context-bridge
        description: A composed capability across ServiceNow + Workday for an employee-context HR-AI agent at Vanguard's charitable arm, with /metrics + /health exposed.
        location: file:///opt/naftiko/skills/servicenow-workday-employee-context-bridge
        allowed-tools: example
        tools:
        - name: example
          description: A composed capability across ServiceNow + Workday for an employee-context HR-AI agent at Vanguard's charitable arm, with /metrics + /health exposed.
          from:
            sourceNamespace: servicenow-workday-employee-context-bridge-mcp
            action: example
---

A composed capability across ServiceNow + Workday for an employee-context HR-AI agent at Vanguard's charitable arm, with /metrics + /health exposed. **Paul Tihansky's** Solutions Architect rubric (orchestration + JSONPath + observability) runs cleanly across ServiceNow + Workday — the SA evaluation lands here.
