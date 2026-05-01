---
categories: []
consumed_apis:
- northwestern-mutual
description: A capability that fires Naftiko governance findings into ServiceNow change/incident records as advisory + blocking gates, so the policy actually has a system of action.
layout: capability
naftiko_layer: service-anchored
naftiko_partner: Supreet Nagi
name: Northwestern Mutual Nwm Servicenow Zero Touch Governance Flow
operations: []
personas: []
provider_name: Northwestern Mutual
provider_slug: northwestern-mutual
search_terms:
- capability
- that
- fires
- naftiko
- governance
slug: nwm-servicenow-zero-touch-governance-flow
source_filename: nwm-servicenow-zero-touch-governance-flow.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Northwestern Mutual Nwm Servicenow Zero Touch Governance Flow
    description: A capability that fires Naftiko governance findings into ServiceNow change/incident records as advisory + blocking gates, so the policy actually has a system of action.
    tags:
    - Northwestern Mutual
    created: '2026-04-30'
    modified: '2026-04-30'
  binds:
  - namespace: northwestern-mutual-env
    description: Northwestern Mutual credentials.
    keys:
      NORTHWESTERN_MUTUAL_API_KEY: NORTHWESTERN_MUTUAL_API_KEY
  capability:
    consumes:
    - namespace: northwestern-mutual
      type: http
      baseUri: https://api.northwestern-mutual.com
      authentication:
        type: bearer
        token: '{{NORTHWESTERN_MUTUAL_API_KEY}}'
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
      namespace: nwm-servicenow-zero-touch-governance-flow-rest
      description: REST API for Northwestern Mutual Nwm Servicenow Zero Touch Governance Flow.
      resources:
      - name: example
        path: /example
        operations:
        - method: GET
          name: example-op
          call: northwestern-mutual.example-op
    - type: mcp
      address: 0.0.0.0
      port: 3010
      namespace: nwm-servicenow-zero-touch-governance-flow-mcp
      description: MCP server exposing Northwestern Mutual Nwm Servicenow Zero Touch Governance Flow for AI agents.
      tools:
      - name: example
        description: A capability that fires Naftiko governance findings into ServiceNow change/incident records as advisory + blocking gates, so the policy actually has a system of action.
        hints:
          readOnly: true
        call: northwestern-mutual.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: nwm-servicenow-zero-touch-governance-flow-skills
      description: Agent Skill bundle for Northwestern Mutual Nwm Servicenow Zero Touch Governance Flow.
      skills:
      - name: nwm-servicenow-zero-touch-governance-flow
        description: A capability that fires Naftiko governance findings into ServiceNow change/incident records as advisory + blocking gates, so the policy actually has a system of action.
        location: file:///opt/naftiko/skills/nwm-servicenow-zero-touch-governance-flow
        allowed-tools: example
        tools:
        - name: example
          description: A capability that fires Naftiko governance findings into ServiceNow change/incident records as advisory + blocking gates, so the policy actually has a system of action.
          from:
            sourceNamespace: nwm-servicenow-zero-touch-governance-flow-mcp
            action: example
---

A capability that fires Naftiko governance findings into ServiceNow change/incident records as advisory + blocking gates, so the policy actually has a system of action. Co-author of "From Chaos to Connectivity" — chaos meets governance at the workflow system; ServiceNow is NWM's.
