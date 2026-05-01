---
categories: []
consumed_apis:
- northwestern-mutual
description: A capability over Bloomberg AIM portfolio positions, packaged as an Agent Skill folder with explicit safety + effect tags for the financial-advisor agent context.
layout: capability
naftiko_layer: service-anchored
naftiko_partner: Supreet Nagi
name: Northwestern Mutual Nwm Bloomberg Aim Portfolio Position Agent Skill
operations: []
personas: []
provider_name: Northwestern Mutual
provider_slug: northwestern-mutual
search_terms:
- capability
- over
- bloomberg
- portfolio
- positions
slug: nwm-bloomberg-aim-portfolio-position-agent-skill
source_filename: nwm-bloomberg-aim-portfolio-position-agent-skill.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Northwestern Mutual Nwm Bloomberg Aim Portfolio Position Agent Skill
    description: A capability over Bloomberg AIM portfolio positions, packaged as an Agent Skill folder with explicit safety + effect tags for the financial-advisor agent context.
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
      namespace: nwm-bloomberg-aim-portfolio-position-agent-skill-rest
      description: REST API for Northwestern Mutual Nwm Bloomberg Aim Portfolio Position Agent Skill.
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
      namespace: nwm-bloomberg-aim-portfolio-position-agent-skill-mcp
      description: MCP server exposing Northwestern Mutual Nwm Bloomberg Aim Portfolio Position Agent Skill for AI agents.
      tools:
      - name: example
        description: A capability over Bloomberg AIM portfolio positions, packaged as an Agent Skill folder with explicit safety + effect tags for the financial-advisor agent context.
        hints:
          readOnly: true
        call: northwestern-mutual.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: nwm-bloomberg-aim-portfolio-position-agent-skill-skills
      description: Agent Skill bundle for Northwestern Mutual Nwm Bloomberg Aim Portfolio Position Agent Skill.
      skills:
      - name: nwm-bloomberg-aim-portfolio-position-agent-skill
        description: A capability over Bloomberg AIM portfolio positions, packaged as an Agent Skill folder with explicit safety + effect tags for the financial-advisor agent context.
        location: file:///opt/naftiko/skills/nwm-bloomberg-aim-portfolio-position-agent-skill
        allowed-tools: example
        tools:
        - name: example
          description: A capability over Bloomberg AIM portfolio positions, packaged as an Agent Skill folder with explicit safety + effect tags for the financial-advisor agent context.
          from:
            sourceNamespace: nwm-bloomberg-aim-portfolio-position-agent-skill-mcp
            action: example
---

A capability over Bloomberg AIM portfolio positions, packaged as an Agent Skill folder with explicit safety + effect tags for the financial-advisor agent context. NWM's investment management runs on Bloomberg AIM; agent-safety tagging on portfolio-position reads is the integration she'd actually approve.
