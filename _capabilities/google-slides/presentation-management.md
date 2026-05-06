---
categories: []
consumed_apis: []
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
- get a specific page.
- presentations
- google workspace
- get presentation
- batch update
- get a page thumbnail.
- batch update presentation
- get a thumbnail image of a presentation page.
- google
- access individual pages and thumbnails.
- apply batch updates to a presentation (add slides, insert text, create shapes, embed images).
- apply batch updates.
- slides
- productivity
- create and manage presentations.
- create presentation
- content creation
- get a presentation by id.
- create a new blank google slides presentation.
- get a specific page from a presentation.
- get page thumbnail
- get a presentation by id with all slides, masters, and layouts.
- collaboration
- get page
- create a new presentation.
slug: presentation-management
source_filename: presentation-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google Slides Presentation Management\n  description: Unified presentation management workflow for creating, reading, editing, and generating thumbnails of Google\n    Slides presentations for content creators and automation engineers.\n  tags:\n  - Google\n  - Slides\n  - Presentations\n  - Content Creation\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    GOOGLE_OAUTH_TOKEN: GOOGLE_OAUTH_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: slides-api\n    baseUri: https://slides.googleapis.com\n    description: Google Slides API for creating and editing presentations.\n    authentication:\n      type: bearer\n      token: '{{GOOGLE_OAUTH_TOKEN}}'\n    resources:\n    - name: presentations\n      path: /v1/presentations\n      description: Manage presentations.\n      operations:\n      - name: create-presentation\n        method: POST\n        description: Create a blank presentation.\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            title: '{{tools.title}}'\n      - name: get-presentation\n        method: GET\n        description: Get a presentation by ID.\n        inputParameters:\n        - name: presentationId\n          in: path\n          type: string\n          required: true\n          description: Presentation ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: batch-update-presentation\n        method: POST\n        description: Apply batch updates to a presentation.\n        inputParameters:\n        - name: presentationId\n          in: path\n          type: string\n          required: true\n          description: Presentation ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n       \
  \   type: object\n          value: $.\n        body:\n          type: json\n          data:\n            requests: '{{tools.requests}}'\n    - name: pages\n      path: /v1/presentations/{presentationId}/pages\n      description: Manage pages within presentations.\n      operations:\n      - name: get-page\n        method: GET\n        description: Get a specific page.\n        inputParameters:\n        - name: presentationId\n          in: path\n          type: string\n          required: true\n          description: Presentation ID.\n        - name: pageObjectId\n          in: path\n          type: string\n          required: true\n          description: Page object ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-page-thumbnail\n        method: GET\n        description: Get a thumbnail image of a page.\n        inputParameters:\n        - name: presentationId\n          in: path\n   \
  \       type: string\n          required: true\n          description: Presentation ID.\n        - name: pageObjectId\n          in: path\n          type: string\n          required: true\n          description: Page object ID.\n        - name: thumbnailProperties.mimeType\n          in: query\n          type: string\n          required: false\n          description: Thumbnail MIME type (PNG).\n        - name: thumbnailProperties.thumbnailSize\n          in: query\n          type: string\n          required: false\n          description: Thumbnail size.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: presentation-api\n    description: Unified REST API for Google Slides presentation management.\n    resources:\n    - path: /v1/presentations\n      name: presentations\n      description: Create and manage presentations.\n      operations:\n      - method:\
  \ POST\n        name: create-presentation\n        description: Create a new presentation.\n        call: slides-api.create-presentation\n        with:\n          title: rest.title\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: get-presentation\n        description: Get a presentation by ID.\n        call: slides-api.get-presentation\n        with:\n          presentationId: rest.presentationId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: batch-update\n        description: Apply batch updates.\n        call: slides-api.batch-update-presentation\n        with:\n          presentationId: rest.presentationId\n          requests: rest.requests\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/pages\n      name: pages\n      description: Access individual pages and thumbnails.\n      operations:\n      - method: GET\n     \
  \   name: get-page\n        description: Get a specific page.\n        call: slides-api.get-page\n        with:\n          presentationId: rest.presentationId\n          pageObjectId: rest.pageObjectId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: get-page-thumbnail\n        description: Get a page thumbnail.\n        call: slides-api.get-page-thumbnail\n        with:\n          presentationId: rest.presentationId\n          pageObjectId: rest.pageObjectId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: presentation-mcp\n    transport: http\n    description: MCP server for AI-assisted Google Slides presentation creation and editing.\n    tools:\n    - name: create-presentation\n      description: Create a new blank Google Slides presentation.\n      hints:\n        readOnly: false\n      call: slides-api.create-presentation\n      with:\n        title:\
  \ tools.title\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-presentation\n      description: Get a presentation by ID with all slides, masters, and layouts.\n      hints:\n        readOnly: true\n      call: slides-api.get-presentation\n      with:\n        presentationId: tools.presentationId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: batch-update-presentation\n      description: Apply batch updates to a presentation (add slides, insert text, create shapes, embed images).\n      hints:\n        readOnly: false\n      call: slides-api.batch-update-presentation\n      with:\n        presentationId: tools.presentationId\n        requests: tools.requests\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-page\n      description: Get a specific page from a presentation.\n      hints:\n        readOnly: true\n      call: slides-api.get-page\n      with:\n        presentationId: tools.presentationId\n\
  \        pageObjectId: tools.pageObjectId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-page-thumbnail\n      description: Get a thumbnail image of a presentation page.\n      hints:\n        readOnly: true\n      call: slides-api.get-page-thumbnail\n      with:\n        presentationId: tools.presentationId\n        pageObjectId: tools.pageObjectId\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
