---
categories: []
consumed_apis:
- vonage
description: A capability with Per-Endpoint Auth + governance rules (PII surface detection, HTTPS enforcement) as the differentiator for a Vonage MCP play.
layout: capability
naftiko_layer: proposed
naftiko_partner: Vonage
name: Vonage Pii Governance Capability
operations: []
personas: []
provider_name: Vonage
provider_slug: vonage
search_terms:
- capability
- with
- endpoint
- auth
- governance
slug: pii-governance-capability
source_filename: pii-governance-capability.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Vonage Pii Governance Capability
    description: A capability with Per-Endpoint Auth + governance rules (PII surface detection, HTTPS enforcement) as the differentiator for a Vonage MCP play.
    tags:
    - Vonage
    created: '2026-04-30'
    modified: '2026-04-30'
  binds:
  - namespace: vonage-env
    description: Vonage credentials.
    keys:
      VONAGE_API_KEY: VONAGE_API_KEY
  capability:
    consumes:
    - namespace: vonage
      type: http
      baseUri: https://api.vonage.com
      authentication:
        type: bearer
        token: '{{VONAGE_API_KEY}}'
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
      namespace: pii-governance-capability-rest
      description: REST API for Vonage Pii Governance Capability.
      resources:
      - name: example
        path: /example
        operations:
        - method: GET
          name: example-op
          call: vonage.example-op
    - type: mcp
      address: 0.0.0.0
      port: 3010
      namespace: pii-governance-capability-mcp
      description: MCP server exposing Vonage Pii Governance Capability for AI agents.
      tools:
      - name: example
        description: A capability with Per-Endpoint Auth + governance rules (PII surface detection, HTTPS enforcement) as the differentiator for a Vonage MCP play.
        hints:
          readOnly: true
        call: vonage.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: pii-governance-capability-skills
      description: Agent Skill bundle for Vonage Pii Governance Capability.
      skills:
      - name: pii-governance-capability
        description: A capability with Per-Endpoint Auth + governance rules (PII surface detection, HTTPS enforcement) as the differentiator for a Vonage MCP play.
        location: file:///opt/naftiko/skills/pii-governance-capability
        allowed-tools: example
        tools:
        - name: example
          description: A capability with Per-Endpoint Auth + governance rules (PII surface detection, HTTPS enforcement) as the differentiator for a Vonage MCP play.
          from:
            sourceNamespace: pii-governance-capability-mcp
            action: example
---

A capability with Per-Endpoint Auth + governance rules (PII surface detection, HTTPS enforcement) as the differentiator for a Vonage MCP play. Communications APIs touch PII; leading with governance suits an Ericsson-owned regulated-comms business.
