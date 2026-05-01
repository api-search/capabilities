---
categories: []
consumed_apis:
- deloitte
description: A small Deloitte-relevant regulated-industry capability used as the artifact-led re-nudge instead of re-sending the Signals page.
layout: capability
naftiko_layer: proposed
naftiko_partner: Fabrice Marque
name: Deloitte Regulated Industry Capability
operations: []
personas: []
provider_name: Deloitte
provider_slug: deloitte
search_terms:
- small
- deloitte
- relevant
- regulated
- industry
slug: regulated-industry-capability
source_filename: regulated-industry-capability.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Deloitte Regulated Industry Capability
    description: A small Deloitte-relevant regulated-industry capability used as the artifact-led re-nudge instead of re-sending the Signals page.
    tags:
    - Deloitte
    created: '2026-04-30'
    modified: '2026-04-30'
  binds:
  - namespace: deloitte-env
    description: Deloitte credentials.
    keys:
      DELOITTE_API_KEY: DELOITTE_API_KEY
  capability:
    consumes:
    - namespace: deloitte
      type: http
      baseUri: https://api.deloitte.com
      authentication:
        type: bearer
        token: '{{DELOITTE_API_KEY}}'
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
      namespace: regulated-industry-capability-rest
      description: REST API for Deloitte Regulated Industry Capability.
      resources:
      - name: example
        path: /example
        operations:
        - method: GET
          name: example-op
          call: deloitte.example-op
    - type: mcp
      address: 0.0.0.0
      port: 3010
      namespace: regulated-industry-capability-mcp
      description: MCP server exposing Deloitte Regulated Industry Capability for AI agents.
      tools:
      - name: example
        description: A small Deloitte-relevant regulated-industry capability used as the artifact-led re-nudge instead of re-sending the Signals page.
        hints:
          readOnly: true
        call: deloitte.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: regulated-industry-capability-skills
      description: Agent Skill bundle for Deloitte Regulated Industry Capability.
      skills:
      - name: regulated-industry-capability
        description: A small Deloitte-relevant regulated-industry capability used as the artifact-led re-nudge instead of re-sending the Signals page.
        location: file:///opt/naftiko/skills/regulated-industry-capability
        allowed-tools: example
        tools:
        - name: example
          description: A small Deloitte-relevant regulated-industry capability used as the artifact-led re-nudge instead of re-sending the Signals page.
          from:
            sourceNamespace: regulated-industry-capability-mcp
            action: example
---

A small Deloitte-relevant regulated-industry capability used as the artifact-led re-nudge instead of re-sending the Signals page. Stalled on the Signals page; a different artifact gets a different result.
