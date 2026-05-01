---
categories: []
consumed_apis:
- salesforce
description: A capability that exposes a Salesforce Einstein action triggered from Slack, packaged as a single MCP tool with safety + effect tags.
layout: capability
naftiko_layer: service-anchored
naftiko_partner: Kris Harrison
name: Salesforce Slack Einstein Action Capability
operations: []
personas: []
provider_name: Salesforce
provider_slug: salesforce
search_terms:
- capability
- that
- exposes
- salesforce
- einstein
slug: slack-einstein-action-capability
source_filename: slack-einstein-action-capability.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Salesforce Slack Einstein Action Capability
    description: A capability that exposes a Salesforce Einstein action triggered from Slack, packaged as a single MCP tool with safety + effect tags.
    tags:
    - Salesforce
    created: '2026-04-30'
    modified: '2026-04-30'
  binds:
  - namespace: salesforce-env
    description: Salesforce credentials.
    keys:
      SALESFORCE_API_KEY: SALESFORCE_API_KEY
  capability:
    consumes:
    - namespace: salesforce
      type: http
      baseUri: https://api.salesforce.com
      authentication:
        type: bearer
        token: '{{SALESFORCE_API_KEY}}'
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
      namespace: slack-einstein-action-capability-rest
      description: REST API for Salesforce Slack Einstein Action Capability.
      resources:
      - name: example
        path: /example
        operations:
        - method: GET
          name: example-op
          call: salesforce.example-op
    - type: mcp
      address: 0.0.0.0
      port: 3010
      namespace: slack-einstein-action-capability-mcp
      description: MCP server exposing Salesforce Slack Einstein Action Capability for AI agents.
      tools:
      - name: example
        description: A capability that exposes a Salesforce Einstein action triggered from Slack, packaged as a single MCP tool with safety + effect tags.
        hints:
          readOnly: true
        call: salesforce.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: slack-einstein-action-capability-skills
      description: Agent Skill bundle for Salesforce Slack Einstein Action Capability.
      skills:
      - name: slack-einstein-action-capability
        description: A capability that exposes a Salesforce Einstein action triggered from Slack, packaged as a single MCP tool with safety + effect tags.
        location: file:///opt/naftiko/skills/slack-einstein-action-capability
        allowed-tools: example
        tools:
        - name: example
          description: A capability that exposes a Salesforce Einstein action triggered from Slack, packaged as a single MCP tool with safety + effect tags.
          from:
            sourceNamespace: slack-einstein-action-capability-mcp
            action: example
---

A capability that exposes a Salesforce Einstein action triggered from Slack, packaged as a single MCP tool with safety + effect tags. Slack + Einstein crosses two Salesforce-owned brands and lands on the agent-safety story his governance role evaluates.
