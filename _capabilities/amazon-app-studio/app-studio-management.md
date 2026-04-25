---
consumed_apis:
- amazon-app-studio
description: Workflow for managing App Studio low-code applications.
layout: capability
name: Amazon App Studio Application Management
operations:
- description: List applications.
  method: GET
  name: list-apps
  path: /v1/apps
personas: []
provider_name: Amazon App Studio
provider_slug: amazon-app-studio
search_terms:
- internal tools
- no-code
- app studio
- list apps
- aws
- list all amazon app studio applications in the account.
- business user building internal tools with app studio.
- IT Administrator
- list app studio apps
- Business Developer
- it admin managing app studio deployments and access.
- low-code
- amazon
- manage app studio low-code applications.
- get app studio app
- list applications.
- generative ai
- get details for a specific app studio application by id.
slug: app-studio-management
tags:
- Amazon
- App Studio
- AWS
- Low-Code
tools:
- description: List all Amazon App Studio applications in the account.
  hints:
    openWorld: false
    readOnly: true
  name: list-app-studio-apps
- description: Get details for a specific App Studio application by ID.
  hints:
    openWorld: false
    readOnly: true
  name: get-app-studio-app
---
