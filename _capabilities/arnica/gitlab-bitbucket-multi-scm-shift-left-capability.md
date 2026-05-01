---
categories: []
consumed_apis:
- arnica
description: A capability that fans out across GitHub + GitLab + Bitbucket scan results from Arnica and exposes a unified MCP shift-left view.
layout: capability
naftiko_layer: service-anchored
naftiko_partner: Anna Daugherty
name: Arnica Gitlab Bitbucket Multi Scm Shift Left Capability
operations: []
personas: []
provider_name: Arnica
provider_slug: arnica
search_terms:
- capability
- that
- fans
- across
- github
slug: gitlab-bitbucket-multi-scm-shift-left-capability
source_filename: gitlab-bitbucket-multi-scm-shift-left-capability.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Arnica Gitlab Bitbucket Multi Scm Shift Left Capability
    description: A capability that fans out across GitHub + GitLab + Bitbucket scan results from Arnica and exposes a unified MCP shift-left view.
    tags:
    - Arnica
    created: '2026-04-30'
    modified: '2026-04-30'
  binds:
  - namespace: arnica-env
    description: Arnica credentials.
    keys:
      ARNICA_API_KEY: ARNICA_API_KEY
  capability:
    consumes:
    - namespace: arnica
      type: http
      baseUri: https://api.arnica.com
      authentication:
        type: bearer
        token: '{{ARNICA_API_KEY}}'
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
      namespace: gitlab-bitbucket-multi-scm-shift-left-capability-rest
      description: REST API for Arnica Gitlab Bitbucket Multi Scm Shift Left Capability.
      resources:
      - name: example
        path: /example
        operations:
        - method: GET
          name: example-op
          call: arnica.example-op
    - type: mcp
      address: 0.0.0.0
      port: 3010
      namespace: gitlab-bitbucket-multi-scm-shift-left-capability-mcp
      description: MCP server exposing Arnica Gitlab Bitbucket Multi Scm Shift Left Capability for AI agents.
      tools:
      - name: example
        description: A capability that fans out across GitHub + GitLab + Bitbucket scan results from Arnica and exposes a unified MCP shift-left view.
        hints:
          readOnly: true
        call: arnica.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: gitlab-bitbucket-multi-scm-shift-left-capability-skills
      description: Agent Skill bundle for Arnica Gitlab Bitbucket Multi Scm Shift Left Capability.
      skills:
      - name: gitlab-bitbucket-multi-scm-shift-left-capability
        description: A capability that fans out across GitHub + GitLab + Bitbucket scan results from Arnica and exposes a unified MCP shift-left view.
        location: file:///opt/naftiko/skills/gitlab-bitbucket-multi-scm-shift-left-capability
        allowed-tools: example
        tools:
        - name: example
          description: A capability that fans out across GitHub + GitLab + Bitbucket scan results from Arnica and exposes a unified MCP shift-left view.
          from:
            sourceNamespace: gitlab-bitbucket-multi-scm-shift-left-capability-mcp
            action: example
---

A capability that fans out across GitHub + GitLab + Bitbucket scan results from Arnica and exposes a unified MCP shift-left view. Multi-SCM Arnica coverage IS the differentiator she markets; making it agent-callable through one capability is the co-marketing artifact PMM-DevEx + AI Tools wants.
