---
categories: []
consumed_apis:
- ey
description: A capability over ServiceNow ITSM/HRSD records that exposes engagement-workflow tools to an EY consulting-AI assistant with governance + agent-safety tags.
layout: capability
naftiko_layer: service-anchored
naftiko_partner: Ulrich Trinkaus
name: EY Servicenow Engagement Workflow Mcp
operations: []
personas: []
provider_name: EY
provider_slug: ey
search_terms:
- capability
- over
- servicenow
- itsm
- hrsd
slug: servicenow-engagement-workflow-mcp
source_filename: servicenow-engagement-workflow-mcp.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: EY Servicenow Engagement Workflow Mcp
    description: A capability over ServiceNow ITSM/HRSD records that exposes engagement-workflow tools to an EY consulting-AI assistant with governance + agent-safety tags.
    tags:
    - EY
    created: '2026-04-30'
    modified: '2026-04-30'
  binds:
  - namespace: ey-env
    description: EY credentials.
    keys:
      EY_API_KEY: EY_API_KEY
  capability:
    consumes:
    - namespace: ey
      type: http
      baseUri: https://api.ey.com
      authentication:
        type: bearer
        token: '{{EY_API_KEY}}'
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
      namespace: servicenow-engagement-workflow-mcp-rest
      description: REST API for EY Servicenow Engagement Workflow Mcp.
      resources:
      - name: example
        path: /example
        operations:
        - method: GET
          name: example-op
          call: ey.example-op
    - type: mcp
      address: 0.0.0.0
      port: 3010
      namespace: servicenow-engagement-workflow-mcp-mcp
      description: MCP server exposing EY Servicenow Engagement Workflow Mcp for AI agents.
      tools:
      - name: example
        description: A capability over ServiceNow ITSM/HRSD records that exposes engagement-workflow tools to an EY consulting-AI assistant with governance + agent-safety tags.
        hints:
          readOnly: true
        call: ey.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: servicenow-engagement-workflow-mcp-skills
      description: Agent Skill bundle for EY Servicenow Engagement Workflow Mcp.
      skills:
      - name: servicenow-engagement-workflow-mcp
        description: A capability over ServiceNow ITSM/HRSD records that exposes engagement-workflow tools to an EY consulting-AI assistant with governance + agent-safety tags.
        location: file:///opt/naftiko/skills/servicenow-engagement-workflow-mcp
        allowed-tools: example
        tools:
        - name: example
          description: A capability over ServiceNow ITSM/HRSD records that exposes engagement-workflow tools to an EY consulting-AI assistant with governance + agent-safety tags.
          from:
            sourceNamespace: servicenow-engagement-workflow-mcp-mcp
            action: example
---

A capability over ServiceNow ITSM/HRSD records that exposes engagement-workflow tools to an EY consulting-AI assistant with governance + agent-safety tags. Professional Services engagements run on ServiceNow at this scale — agent-safe access to records is the "client-perspective" framing he asked for.
