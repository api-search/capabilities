---
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
- crm
- analytics
- marketing
- get token metadata
- oauth
- automation
- marketing automation
- developer
- oauth token metadata
- operations
- customer service
- platform
- get access token metadata
- sales
- content
- commerce
- retrieve metadata for an oauth access token
- email marketing
slug: developer-platform
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
