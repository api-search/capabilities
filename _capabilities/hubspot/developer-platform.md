---
categories:
- automation
consumed_apis:
- custom-workflow-actions
- feature-flags
- source-code
- oauth
description: Unified workflow for developers to manage custom workflow actions, feature flags, CMS source code, and OAuth authentication. Combines automation, deployment, and auth APIs for HubSpot platform development.
layout: capability
name: HubSpot Developer Platform
operations:
- description: Get access token metadata
  method: GET
  name: get-token-metadata
  path: /v1/access-tokens/{token}
personas: []
provider_name: HubSpot
provider_slug: hubspot
search_terms:
- hubspot
- developer
- get access token metadata
- automation
- oauth token metadata
- marketing automation
- sales
- commerce
- customer service
- platform
- content
- crm
- marketing
- operations
- analytics
- email marketing
- get token metadata
- oauth
- retrieve metadata for an oauth access token
slug: developer-platform
source_filename: developer-platform.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"HubSpot Developer Platform\"\n  description: \"Unified workflow for developers to manage custom workflow actions, feature flags, CMS source code, and OAuth authentication. Combines automation, deployment, and auth APIs for HubSpot platform development.\"\n  tags:\n    - HubSpot\n    - Developer\n    - Platform\n    - Automation\n    - OAuth\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      HUBSPOT_ACCESS_TOKEN: HUBSPOT_ACCESS_TOKEN\n      HUBSPOT_API_KEY: HUBSPOT_API_KEY\n\ncapability:\n  consumes:\n    - import: custom-workflow-actions\n      location: ./shared/custom-workflow-actions-api.yaml\n    - import: feature-flags\n      location: ./shared/crm-feature-flags-api.yaml\n    - import: source-code\n      location: ./shared/source-code-api.yaml\n    - import: oauth\n      location: ./shared/oauth-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8083\n      namespace:\
  \ developer-platform-api\n      description: \"Unified REST API for HubSpot platform development, workflow customization, and deployment.\"\n      resources:\n        - path: /v1/access-tokens/{token}\n          name: access-token\n          description: \"OAuth token metadata\"\n          operations:\n            - method: GET\n              name: get-token-metadata\n              description: \"Get access token metadata\"\n              call: \"oauth.getAccessTokenMetadata\"\n              with:\n                token: \"rest.token\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9093\n      namespace: developer-platform-mcp\n      transport: http\n      description: \"MCP server for AI-assisted HubSpot platform development, workflow automation, and feature management.\"\n      tools:\n        - name: get-access-token-metadata\n          description: \"Retrieve metadata for an OAuth access token\"\n\
  \          hints:\n            readOnly: true\n            idempotent: true\n          call: \"oauth.getAccessTokenMetadata\"\n          with:\n            token: \"tools.token\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/hubspot/refs/heads/main/capabilities/developer-platform.yaml
tags:
- HubSpot
- Developer
- Platform
- Automation
- OAuth
tools:
- description: Retrieve metadata for an OAuth access token
  hints:
    idempotent: true
    readOnly: true
  name: get-access-token-metadata
---
