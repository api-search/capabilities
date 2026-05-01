---
categories: []
consumed_apis:
- microsoft
description: A capability that wraps Work IQ as an MCP tool consumed from the Copilot CLI to produce a daily "what changed that impacts my work" briefing across meetings, chats, emails, and tasks.
layout: capability
naftiko_layer: service-anchored
naftiko_partner: Sébastien Levert
name: Microsoft M365 Copilot Cli Work Iq Daily Briefing Capability
operations: []
personas: []
provider_name: Microsoft
provider_slug: microsoft
search_terms:
- capability
- that
- wraps
- work
- tool
slug: m365-copilot-cli-work-iq-daily-briefing-capability
source_filename: m365-copilot-cli-work-iq-daily-briefing-capability.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Microsoft M365 Copilot Cli Work Iq Daily Briefing Capability
    description: A capability that wraps Work IQ as an MCP tool consumed from the Copilot CLI to produce a daily "what changed that impacts my work" briefing across meetings, chats, emails, and tasks.
    tags:
    - Microsoft
    created: '2026-04-30'
    modified: '2026-04-30'
  binds:
  - namespace: microsoft-env
    description: Microsoft credentials.
    keys:
      MICROSOFT_API_KEY: MICROSOFT_API_KEY
  capability:
    consumes:
    - namespace: microsoft
      type: http
      baseUri: https://api.microsoft.com
      authentication:
        type: bearer
        token: '{{MICROSOFT_API_KEY}}'
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
      namespace: m365-copilot-cli-work-iq-daily-briefing-capability-rest
      description: REST API for Microsoft M365 Copilot Cli Work Iq Daily Briefing Capability.
      resources:
      - name: example
        path: /example
        operations:
        - method: GET
          name: example-op
          call: microsoft.example-op
    - type: mcp
      address: 0.0.0.0
      port: 3010
      namespace: m365-copilot-cli-work-iq-daily-briefing-capability-mcp
      description: MCP server exposing Microsoft M365 Copilot Cli Work Iq Daily Briefing Capability for AI agents.
      tools:
      - name: example
        description: A capability that wraps Work IQ as an MCP tool consumed from the Copilot CLI to produce a daily "what changed that impacts my work" briefing across meetings, chats, emails, and tasks.
        hints:
          readOnly: true
        call: microsoft.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: m365-copilot-cli-work-iq-daily-briefing-capability-skills
      description: Agent Skill bundle for Microsoft M365 Copilot Cli Work Iq Daily Briefing Capability.
      skills:
      - name: m365-copilot-cli-work-iq-daily-briefing-capability
        description: A capability that wraps Work IQ as an MCP tool consumed from the Copilot CLI to produce a daily "what changed that impacts my work" briefing across meetings, chats, emails, and tasks.
        location: file:///opt/naftiko/skills/m365-copilot-cli-work-iq-daily-briefing-capability
        allowed-tools: example
        tools:
        - name: example
          description: A capability that wraps Work IQ as an MCP tool consumed from the Copilot CLI to produce a daily "what changed that impacts my work" briefing across meetings, chats, emails, and tasks.
          from:
            sourceNamespace: m365-copilot-cli-work-iq-daily-briefing-capability-mcp
            action: example
---

A capability that wraps Work IQ as an MCP tool consumed from the Copilot CLI to produce a daily "what changed that impacts my work" briefing across meetings, chats, emails, and tasks. He explicitly named the Copilot CLI as his preferred Work IQ surface and the daily-briefing pattern as the killer use case — this is the artifact that ships exactly that.
