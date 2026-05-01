---
categories: []
consumed_apis:
- cvent
description: A capability that ingests Azure DevOps build + release events and auto-fills Backstage entity TechDocs/CI annotations for the relevant service.
layout: capability
naftiko_layer: service-anchored
naftiko_partner: Jeff Seifert
name: Cvent Azure Devops Pipeline To Backstage Entity
operations: []
personas: []
provider_name: Cvent
provider_slug: cvent
search_terms:
- capability
- that
- ingests
- azure
- devops
slug: azure-devops-pipeline-to-backstage-entity
source_filename: azure-devops-pipeline-to-backstage-entity.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Cvent Azure Devops Pipeline To Backstage Entity
    description: A capability that ingests Azure DevOps build + release events and auto-fills Backstage entity TechDocs/CI annotations for the relevant service.
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
      namespace: azure-devops-pipeline-to-backstage-entity-rest
      description: REST API for Cvent Azure Devops Pipeline To Backstage Entity.
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
      namespace: azure-devops-pipeline-to-backstage-entity-mcp
      description: MCP server exposing Cvent Azure Devops Pipeline To Backstage Entity for AI agents.
      tools:
      - name: example
        description: A capability that ingests Azure DevOps build + release events and auto-fills Backstage entity TechDocs/CI annotations for the relevant service.
        hints:
          readOnly: true
        call: cvent.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: azure-devops-pipeline-to-backstage-entity-skills
      description: Agent Skill bundle for Cvent Azure Devops Pipeline To Backstage Entity.
      skills:
      - name: azure-devops-pipeline-to-backstage-entity
        description: A capability that ingests Azure DevOps build + release events and auto-fills Backstage entity TechDocs/CI annotations for the relevant service.
        location: file:///opt/naftiko/skills/azure-devops-pipeline-to-backstage-entity
        allowed-tools: example
        tools:
        - name: example
          description: A capability that ingests Azure DevOps build + release events and auto-fills Backstage entity TechDocs/CI annotations for the relevant service.
          from:
            sourceNamespace: azure-devops-pipeline-to-backstage-entity-mcp
            action: example
---

A capability that ingests Azure DevOps build + release events and auto-fills Backstage entity TechDocs/CI annotations for the relevant service. His Backstage philosophy hangs on auto-catalog; Cvent runs Azure DevOps so the integration is concrete and demoable.
