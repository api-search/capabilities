---
categories: []
consumed_apis:
- schneider-electric
description: A capability that wraps Atlassian Jira MCP with admin-side observability — agent-attribution, hot endpoints, call-rate, sized-for-API-administrator dashboards — answering the "API administration angle" pain Manu articulated.
layout: capability
naftiko_layer: service-anchored
naftiko_partner: Manu PK
name: Schneider Electric Schneider Atlassian Jira Admin Side Observability Capability
operations: []
personas: []
provider_name: Schneider Electric
provider_slug: schneider-electric
search_terms:
- capability
- that
- wraps
- atlassian
- jira
slug: schneider-atlassian-jira-admin-side-observability-capability
source_filename: schneider-atlassian-jira-admin-side-observability-capability.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Schneider Electric Schneider Atlassian Jira Admin Side Observability Capability
    description: A capability that wraps Atlassian Jira MCP with admin-side observability — agent-attribution, hot endpoints, call-rate, sized-for-API-administrator dashboards — answering the "API administration angle" pain Manu articulated.
    tags:
    - Schneider Electric
    created: '2026-04-30'
    modified: '2026-04-30'
  binds:
  - namespace: schneider-electric-env
    description: Schneider Electric credentials.
    keys:
      SCHNEIDER_ELECTRIC_API_KEY: SCHNEIDER_ELECTRIC_API_KEY
  capability:
    consumes:
    - namespace: schneider-electric
      type: http
      baseUri: https://api.schneider-electric.com
      authentication:
        type: bearer
        token: '{{SCHNEIDER_ELECTRIC_API_KEY}}'
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
      namespace: schneider-atlassian-jira-admin-side-observability-capability-rest
      description: REST API for Schneider Electric Schneider Atlassian Jira Admin Side Observability Capability.
      resources:
      - name: example
        path: /example
        operations:
        - method: GET
          name: example-op
          call: schneider-electric.example-op
    - type: mcp
      address: 0.0.0.0
      port: 3010
      namespace: schneider-atlassian-jira-admin-side-observability-capability-mcp
      description: MCP server exposing Schneider Electric Schneider Atlassian Jira Admin Side Observability Capability for AI agents.
      tools:
      - name: example
        description: A capability that wraps Atlassian Jira MCP with admin-side observability — agent-attribution, hot endpoints, call-rate, sized-for-API-administrator dashboards — answering the "API administration angle" pain Manu articulated.
        hints:
          readOnly: true
        call: schneider-electric.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: schneider-atlassian-jira-admin-side-observability-capability-skills
      description: Agent Skill bundle for Schneider Electric Schneider Atlassian Jira Admin Side Observability Capability.
      skills:
      - name: schneider-atlassian-jira-admin-side-observability-capability
        description: A capability that wraps Atlassian Jira MCP with admin-side observability — agent-attribution, hot endpoints, call-rate, sized-for-API-administrator dashboards — answering the "API administration angle" pain Manu articulated.
        location: file:///opt/naftiko/skills/schneider-atlassian-jira-admin-side-observability-capability
        allowed-tools: example
        tools:
        - name: example
          description: A capability that wraps Atlassian Jira MCP with admin-side observability — agent-attribution, hot endpoints, call-rate, sized-for-API-administrator dashboards — answering the "API administration angle" pain Manu articulated.
          from:
            sourceNamespace: schneider-atlassian-jira-admin-side-observability-capability-mcp
            action: example
---

A capability that wraps Atlassian Jira MCP with admin-side observability — agent-attribution, hot endpoints, call-rate, sized-for-API-administrator dashboards — answering the "API administration angle" pain Manu articulated. He named the use case verbatim — agents fanning out to dedupe a 300-issue backlog at 5K-developer scale — AND framed the receiving-side API administration angle as a missing observability layer. One capability that closes both ends is the artifact that proves the pattern.
