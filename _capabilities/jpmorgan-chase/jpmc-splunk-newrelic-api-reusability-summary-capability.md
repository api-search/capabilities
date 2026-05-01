---
categories: []
consumed_apis:
- jpmorgan-chase
description: A capability that consumes API-call telemetry from Splunk + New Relic + Datadog and produces a deterministic API-reusability summary.
layout: capability
naftiko_layer: service-anchored
naftiko_partner: Mark McAllister
name: JPMorgan Chase Jpmc Splunk Newrelic Api Reusability Summary Capability
operations: []
personas: []
provider_name: JPMorgan Chase
provider_slug: jpmorgan-chase
search_terms:
- capability
- that
- consumes
- call
- telemetry
slug: jpmc-splunk-newrelic-api-reusability-summary-capability
source_filename: jpmc-splunk-newrelic-api-reusability-summary-capability.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: JPMorgan Chase Jpmc Splunk Newrelic Api Reusability Summary Capability
    description: A capability that consumes API-call telemetry from Splunk + New Relic + Datadog and produces a deterministic API-reusability summary.
    tags:
    - JPMorgan Chase
    created: '2026-04-30'
    modified: '2026-04-30'
  binds:
  - namespace: jpmorgan-chase-env
    description: JPMorgan Chase credentials.
    keys:
      JPMORGAN_CHASE_API_KEY: JPMORGAN_CHASE_API_KEY
  capability:
    consumes:
    - namespace: jpmorgan-chase
      type: http
      baseUri: https://api.jpmorgan-chase.com
      authentication:
        type: bearer
        token: '{{JPMORGAN_CHASE_API_KEY}}'
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
      namespace: jpmc-splunk-newrelic-api-reusability-summary-capability-rest
      description: REST API for JPMorgan Chase Jpmc Splunk Newrelic Api Reusability Summary Capability.
      resources:
      - name: example
        path: /example
        operations:
        - method: GET
          name: example-op
          call: jpmorgan-chase.example-op
    - type: mcp
      address: 0.0.0.0
      port: 3010
      namespace: jpmc-splunk-newrelic-api-reusability-summary-capability-mcp
      description: MCP server exposing JPMorgan Chase Jpmc Splunk Newrelic Api Reusability Summary Capability for AI agents.
      tools:
      - name: example
        description: A capability that consumes API-call telemetry from Splunk + New Relic + Datadog and produces a deterministic API-reusability summary.
        hints:
          readOnly: true
        call: jpmorgan-chase.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: jpmc-splunk-newrelic-api-reusability-summary-capability-skills
      description: Agent Skill bundle for JPMorgan Chase Jpmc Splunk Newrelic Api Reusability Summary Capability.
      skills:
      - name: jpmc-splunk-newrelic-api-reusability-summary-capability
        description: A capability that consumes API-call telemetry from Splunk + New Relic + Datadog and produces a deterministic API-reusability summary.
        location: file:///opt/naftiko/skills/jpmc-splunk-newrelic-api-reusability-summary-capability
        allowed-tools: example
        tools:
        - name: example
          description: A capability that consumes API-call telemetry from Splunk + New Relic + Datadog and produces a deterministic API-reusability summary.
          from:
            sourceNamespace: jpmc-splunk-newrelic-api-reusability-summary-capability-mcp
            action: example
---

A capability that consumes API-call telemetry from Splunk + New Relic + Datadog and produces a deterministic API-reusability summary. His ask verbatim — "Publishing API reusability summary from Splunk, New Relic, and Datadog".
