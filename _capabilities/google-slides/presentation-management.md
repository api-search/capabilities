---
categories: []
consumed_apis:
- slides-api
description: Unified presentation management workflow for creating, reading, editing, and generating thumbnails of Google Slides presentations for content creators and automation engineers.
layout: capability
name: Google Slides Presentation Management
operations:
- description: Create a new presentation.
  method: POST
  name: create-presentation
  path: /v1/presentations
- description: Get a presentation by ID.
  method: GET
  name: get-presentation
  path: /v1/presentations
- description: Apply batch updates.
  method: POST
  name: batch-update
  path: /v1/presentations
- description: Get a specific page.
  method: GET
  name: get-page
  path: /v1/pages
- description: Get a page thumbnail.
  method: GET
  name: get-page-thumbnail
  path: /v1/pages
personas: []
provider_name: Google Slides
provider_slug: google-slides
search_terms:
- apply batch updates to a presentation (add slides, insert text, create shapes, embed images).
- slides
- batch update
- create a new blank google slides presentation.
- presentations
- get a specific page.
- apply batch updates.
- get a thumbnail image of a presentation page.
- get page thumbnail
- access individual pages and thumbnails.
- get a specific page from a presentation.
- get presentation
- batch update presentation
- get page
- get a page thumbnail.
- create and manage presentations.
- google
- google workspace
- create a new presentation.
- productivity
- content creation
- collaboration
- get a presentation by id.
- create presentation
- get a presentation by id with all slides, masters, and layouts.
slug: presentation-management
source_filename: presentation-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Google Slides Presentation Management\"\n  description: \"Unified presentation management workflow for creating, reading, editing, and generating thumbnails of Google Slides presentations for content creators and automation engineers.\"\n  tags:\n    - Google\n    - Slides\n    - Presentations\n    - Content Creation\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      GOOGLE_OAUTH_TOKEN: GOOGLE_OAUTH_TOKEN\n\ncapability:\n  consumes:\n    - import: slides-api\n      location: ./shared/slides-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: presentation-api\n      description: \"Unified REST API for Google Slides presentation management.\"\n      resources:\n        - path: /v1/presentations\n          name: presentations\n          description: \"Create and manage presentations.\"\n          operations:\n            - method: POST\n              name:\
  \ create-presentation\n              description: \"Create a new presentation.\"\n              call: \"slides-api.create-presentation\"\n              with:\n                title: \"rest.title\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: GET\n              name: get-presentation\n              description: \"Get a presentation by ID.\"\n              call: \"slides-api.get-presentation\"\n              with:\n                presentationId: \"rest.presentationId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: batch-update\n              description: \"Apply batch updates.\"\n              call: \"slides-api.batch-update-presentation\"\n              with:\n                presentationId: \"rest.presentationId\"\n                requests: \"rest.requests\"\n              outputParameters:\n              \
  \  - type: object\n                  mapping: \"$.\"\n        - path: /v1/pages\n          name: pages\n          description: \"Access individual pages and thumbnails.\"\n          operations:\n            - method: GET\n              name: get-page\n              description: \"Get a specific page.\"\n              call: \"slides-api.get-page\"\n              with:\n                presentationId: \"rest.presentationId\"\n                pageObjectId: \"rest.pageObjectId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: GET\n              name: get-page-thumbnail\n              description: \"Get a page thumbnail.\"\n              call: \"slides-api.get-page-thumbnail\"\n              with:\n                presentationId: \"rest.presentationId\"\n                pageObjectId: \"rest.pageObjectId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type:\
  \ mcp\n      port: 9090\n      namespace: presentation-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Google Slides presentation creation and editing.\"\n      tools:\n        - name: create-presentation\n          description: \"Create a new blank Google Slides presentation.\"\n          hints:\n            readOnly: false\n          call: \"slides-api.create-presentation\"\n          with:\n            title: \"tools.title\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-presentation\n          description: \"Get a presentation by ID with all slides, masters, and layouts.\"\n          hints:\n            readOnly: true\n          call: \"slides-api.get-presentation\"\n          with:\n            presentationId: \"tools.presentationId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: batch-update-presentation\n          description: \"Apply\
  \ batch updates to a presentation (add slides, insert text, create shapes, embed images).\"\n          hints:\n            readOnly: false\n          call: \"slides-api.batch-update-presentation\"\n          with:\n            presentationId: \"tools.presentationId\"\n            requests: \"tools.requests\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-page\n          description: \"Get a specific page from a presentation.\"\n          hints:\n            readOnly: true\n          call: \"slides-api.get-page\"\n          with:\n            presentationId: \"tools.presentationId\"\n            pageObjectId: \"tools.pageObjectId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-page-thumbnail\n          description: \"Get a thumbnail image of a presentation page.\"\n          hints:\n            readOnly: true\n          call: \"slides-api.get-page-thumbnail\"\n  \
  \        with:\n            presentationId: \"tools.presentationId\"\n            pageObjectId: \"tools.pageObjectId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-slides/refs/heads/main/capabilities/presentation-management.yaml
tags:
- Google
- Slides
- Presentations
- Content Creation
tools:
- description: Create a new blank Google Slides presentation.
  hints:
    readOnly: false
  name: create-presentation
- description: Get a presentation by ID with all slides, masters, and layouts.
  hints:
    readOnly: true
  name: get-presentation
- description: Apply batch updates to a presentation (add slides, insert text, create shapes, embed images).
  hints:
    readOnly: false
  name: batch-update-presentation
- description: Get a specific page from a presentation.
  hints:
    readOnly: true
  name: get-page
- description: Get a thumbnail image of a presentation page.
  hints:
    readOnly: true
  name: get-page-thumbnail
---
