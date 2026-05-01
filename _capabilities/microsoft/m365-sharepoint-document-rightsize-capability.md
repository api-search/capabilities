---
categories: []
consumed_apis:
- microsoft
description: A capability over SharePoint document search that rightsizes the response to a token-budgeted Copilot context object.
layout: capability
naftiko_layer: service-anchored
naftiko_partner: Sébastien Levert
name: Microsoft M365 Sharepoint Document Rightsize Capability
operations: []
personas: []
provider_name: Microsoft
provider_slug: microsoft
search_terms:
- capability
- over
- sharepoint
- document
- search
slug: m365-sharepoint-document-rightsize-capability
source_filename: m365-sharepoint-document-rightsize-capability.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Microsoft M365 Sharepoint Document Rightsize Capability
    description: A capability over SharePoint document search that rightsizes the response to a token-budgeted Copilot context object.
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
      namespace: m365-sharepoint-document-rightsize-capability-rest
      description: REST API for Microsoft M365 Sharepoint Document Rightsize Capability.
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
      namespace: m365-sharepoint-document-rightsize-capability-mcp
      description: MCP server exposing Microsoft M365 Sharepoint Document Rightsize Capability for AI agents.
      tools:
      - name: example
        description: A capability over SharePoint document search that rightsizes the response to a token-budgeted Copilot context object.
        hints:
          readOnly: true
        call: microsoft.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: m365-sharepoint-document-rightsize-capability-skills
      description: Agent Skill bundle for Microsoft M365 Sharepoint Document Rightsize Capability.
      skills:
      - name: m365-sharepoint-document-rightsize-capability
        description: A capability over SharePoint document search that rightsizes the response to a token-budgeted Copilot context object.
        location: file:///opt/naftiko/skills/m365-sharepoint-document-rightsize-capability
        allowed-tools: example
        tools:
        - name: example
          description: A capability over SharePoint document search that rightsizes the response to a token-budgeted Copilot context object.
          from:
            sourceNamespace: m365-sharepoint-document-rightsize-capability-mcp
            action: example
---

A capability over SharePoint document search that rightsizes the response to a token-budgeted Copilot context object. SharePoint is the heaviest verbose surface in M365; rightsizing it is the canonical Copilot DevX pain his role owns.
