---
categories: []
consumed_apis:
- palo-alto-networks
description: A single capability used as the running example in framework-wiki Tutorial-Part-1, with the AI Assistance angle (AGENT.md, SKILL.md prompts) highlighted.
layout: capability
naftiko_layer: proposed
naftiko_partner: James DeVore
name: Palo Alto Networks Agent Md Skill Md Tutorial Capability
operations: []
personas: []
provider_name: Palo Alto Networks
provider_slug: palo-alto-networks
search_terms:
- single
- capability
- used
- running
- example
slug: agent-md-skill-md-tutorial-capability
source_filename: agent-md-skill-md-tutorial-capability.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Palo Alto Networks Agent Md Skill Md Tutorial Capability
    description: A single capability used as the running example in framework-wiki Tutorial-Part-1, with the AI Assistance angle (AGENT.md, SKILL.md prompts) highlighted.
    tags:
    - Palo Alto Networks
    created: '2026-04-30'
    modified: '2026-04-30'
  binds:
  - namespace: palo-alto-networks-env
    description: Palo Alto Networks credentials.
    keys:
      PALO_ALTO_NETWORKS_API_KEY: PALO_ALTO_NETWORKS_API_KEY
  capability:
    consumes:
    - namespace: palo-alto-networks
      type: http
      baseUri: https://api.palo-alto-networks.com
      authentication:
        type: bearer
        token: '{{PALO_ALTO_NETWORKS_API_KEY}}'
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
      namespace: agent-md-skill-md-tutorial-capability-rest
      description: REST API for Palo Alto Networks Agent Md Skill Md Tutorial Capability.
      resources:
      - name: example
        path: /example
        operations:
        - method: GET
          name: example-op
          call: palo-alto-networks.example-op
    - type: mcp
      address: 0.0.0.0
      port: 3010
      namespace: agent-md-skill-md-tutorial-capability-mcp
      description: MCP server exposing Palo Alto Networks Agent Md Skill Md Tutorial Capability for AI agents.
      tools:
      - name: example
        description: A single capability used as the running example in framework-wiki Tutorial-Part-1, with the AI Assistance angle (AGENT.md, SKILL.md prompts) highlighted.
        hints:
          readOnly: true
        call: palo-alto-networks.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: agent-md-skill-md-tutorial-capability-skills
      description: Agent Skill bundle for Palo Alto Networks Agent Md Skill Md Tutorial Capability.
      skills:
      - name: agent-md-skill-md-tutorial-capability
        description: A single capability used as the running example in framework-wiki Tutorial-Part-1, with the AI Assistance angle (AGENT.md, SKILL.md prompts) highlighted.
        location: file:///opt/naftiko/skills/agent-md-skill-md-tutorial-capability
        allowed-tools: example
        tools:
        - name: example
          description: A single capability used as the running example in framework-wiki Tutorial-Part-1, with the AI Assistance angle (AGENT.md, SKILL.md prompts) highlighted.
          from:
            sourceNamespace: agent-md-skill-md-tutorial-capability-mcp
            action: example
---

A single capability used as the running example in framework-wiki Tutorial-Part-1, with the AI Assistance angle (AGENT.md, SKILL.md prompts) highlighted. He said he'd share more on internal tools and AI workflow; this meets him in that frame.
