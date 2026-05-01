---
categories: []
consumed_apis:
- elsevier
description: Wraps an Elsevier publication API as a capability with the Agent Skills adapter, packaged as a downloadable Skill folder via Control API and installed via CLI.
layout: capability
naftiko_layer: proposed
naftiko_partner: Joyce Stack
name: Elsevier Agent Skills Publication Capability
operations: []
personas: []
provider_name: Elsevier
provider_slug: elsevier
search_terms:
- wraps
- elsevier
- publication
- capability
- with
slug: agent-skills-publication-capability
source_filename: agent-skills-publication-capability.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Elsevier Agent Skills Publication Capability
    description: Wraps an Elsevier publication API as a capability with the Agent Skills adapter, packaged as a downloadable Skill folder via Control API and installed via CLI.
    tags:
    - Elsevier
    created: '2026-04-30'
    modified: '2026-04-30'
  binds:
  - namespace: elsevier-env
    description: Elsevier credentials.
    keys:
      ELSEVIER_API_KEY: ELSEVIER_API_KEY
  capability:
    consumes:
    - namespace: elsevier
      type: http
      baseUri: https://api.elsevier.com
      authentication:
        type: bearer
        token: '{{ELSEVIER_API_KEY}}'
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
      namespace: agent-skills-publication-capability-rest
      description: REST API for Elsevier Agent Skills Publication Capability.
      resources:
      - name: example
        path: /example
        operations:
        - method: GET
          name: example-op
          call: elsevier.example-op
    - type: mcp
      address: 0.0.0.0
      port: 3010
      namespace: agent-skills-publication-capability-mcp
      description: MCP server exposing Elsevier Agent Skills Publication Capability for AI agents.
      tools:
      - name: example
        description: Wraps an Elsevier publication API as a capability with the Agent Skills adapter, packaged as a downloadable Skill folder via Control API and installed via CLI.
        hints:
          readOnly: true
        call: elsevier.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: agent-skills-publication-capability-skills
      description: Agent Skill bundle for Elsevier Agent Skills Publication Capability.
      skills:
      - name: agent-skills-publication-capability
        description: Wraps an Elsevier publication API as a capability with the Agent Skills adapter, packaged as a downloadable Skill folder via Control API and installed via CLI.
        location: file:///opt/naftiko/skills/agent-skills-publication-capability
        allowed-tools: example
        tools:
        - name: example
          description: Wraps an Elsevier publication API as a capability with the Agent Skills adapter, packaged as a downloadable Skill folder via Control API and installed via CLI.
          from:
            sourceNamespace: agent-skills-publication-capability-mcp
            action: example
---

Wraps an Elsevier publication API as a capability with the Agent Skills adapter, packaged as a downloadable Skill folder via Control API and installed via CLI. Agent skills was one of her two named asks; a runnable flow beats a feature description.
