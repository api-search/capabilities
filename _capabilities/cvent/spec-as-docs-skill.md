---
categories: []
consumed_apis:
- cvent
description: A capability whose YAML spec + AGENT.md + SKILL.md collectively *are* the documentation for the wrapped Cvent API, collapsing context-engineering and docs into one artifact.
layout: capability
naftiko_layer: proposed
naftiko_partner: Jeff Seifert
name: Cvent Spec As Docs Skill
operations: []
personas: []
provider_name: Cvent
provider_slug: cvent
search_terms:
- capability
- whose
- yaml
- spec
- agent
slug: spec-as-docs-skill
source_filename: spec-as-docs-skill.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Cvent Spec As Docs Skill
    description: A capability whose YAML spec + AGENT.md + SKILL.md collectively *are* the documentation for the wrapped Cvent API, collapsing context-engineering and docs into one artifact.
    tags:
    - Cvent
    created: '2026-04-30'
    modified: '2026-04-30'
  binds:
  - namespace: cvent-env
    description: Cvent credentials.
    keys:
      CVENT_API_KEY: CVENT_API_KEY
  capability:
    consumes:
    - namespace: cvent
      type: http
      baseUri: https://api.cvent.com
      authentication:
        type: bearer
        token: '{{CVENT_API_KEY}}'
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
      namespace: spec-as-docs-skill-rest
      description: REST API for Cvent Spec As Docs Skill.
      resources:
      - name: example
        path: /example
        operations:
        - method: GET
          name: example-op
          call: cvent.example-op
    - type: mcp
      address: 0.0.0.0
      port: 3010
      namespace: spec-as-docs-skill-mcp
      description: MCP server exposing Cvent Spec As Docs Skill for AI agents.
      tools:
      - name: example
        description: A capability whose YAML spec + AGENT.md + SKILL.md collectively *are* the documentation for the wrapped Cvent API, collapsing context-engineering and docs into one artifact.
        hints:
          readOnly: true
        call: cvent.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: spec-as-docs-skill-skills
      description: Agent Skill bundle for Cvent Spec As Docs Skill.
      skills:
      - name: spec-as-docs-skill
        description: A capability whose YAML spec + AGENT.md + SKILL.md collectively *are* the documentation for the wrapped Cvent API, collapsing context-engineering and docs into one artifact.
        location: file:///opt/naftiko/skills/spec-as-docs-skill
        allowed-tools: example
        tools:
        - name: example
          description: A capability whose YAML spec + AGENT.md + SKILL.md collectively *are* the documentation for the wrapped Cvent API, collapsing context-engineering and docs into one artifact.
          from:
            sourceNamespace: spec-as-docs-skill-mcp
            action: example
---

A capability whose YAML spec + AGENT.md + SKILL.md collectively *are* the documentation for the wrapped Cvent API, collapsing context-engineering and docs into one artifact. His ask combined context engineering AND documentation; this artifact merges both into the YAML.
