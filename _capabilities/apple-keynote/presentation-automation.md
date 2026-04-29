---
api_specs:
- filename: apple-keynote-icloud-openapi.yaml
  format: yaml
  label: keynote-icloud
  slug: keynote-icloud
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/apple-keynote/refs/heads/main/openapi/apple-keynote-icloud-openapi.yaml
categories:
- automation
consumed_apis:
- keynote-icloud
description: Workflow capability for automating Keynote presentation creation and management via iCloud. Combines presentation lifecycle management, slide operations, theme selection, and multi-format export into a unified workflow for content creators, marketing teams, and business presenters.
layout: capability
name: Apple Keynote Presentation Automation
operations:
- description: List all Keynote presentations in iCloud
  method: GET
  name: list-presentations
  path: /v1/presentations
- description: Create a new presentation with title and theme
  method: POST
  name: create-presentation
  path: /v1/presentations
- description: List slides in a presentation
  method: GET
  name: list-slides
  path: /v1/slides
- description: Export a presentation to PDF, PPTX, or images
  method: POST
  name: export-presentation
  path: /v1/export
- description: List available Keynote themes
  method: GET
  name: list-themes
  path: /v1/themes
personas: []
provider_name: Apple Keynote
provider_slug: apple-keynote
search_terms:
- Marketing Professional
- marketing team member creating brand presentations, pitch decks, and sales materials
- list keynote presentations
- export keynote to pdf
- individual creating presentations for training, education, or personal use
- Content Creator
- iwork
- export presentation
- creating, organizing, and managing keynote presentation documents
- list presentations
- presentation lifecycle management
- exports a keynote presentation to pdf format with optional presenter notes
- keynote
- creates a new keynote presentation with a specified title and optional theme
- list available keynote themes
- create keynote presentation
- lists all available keynote themes and templates for new presentations
- create presentation
- design
- themes, layouts, and visual styling of presentations
- automation
- add slide to presentation
- apple
- list keynote themes
- end-to-end keynote presentation creation and management via icloud
- slide management within presentations
- productivity
- adds a new slide to a keynote presentation at a specified position with a chosen layout
- converting and sharing presentations in different formats
- list themes
- lists all slides in a keynote presentation with their titles and layouts
- presentations
- list slides in a presentation
- create a new presentation with title and theme
- list presentation slides
- export a presentation to pdf, pptx, or images
- list all keynote presentations in icloud
- list slides
- presentation export to different formats
- icloud
- available themes and templates
- slides
- lists all keynote presentations stored in the user's icloud account
slug: presentation-automation
source_filename: presentation-automation.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: Apple Keynote Presentation Automation\n  description: >-\n    Workflow capability for automating Keynote presentation creation and management\n    via iCloud. Combines presentation lifecycle management, slide operations, theme\n    selection, and multi-format export into a unified workflow for content creators,\n    marketing teams, and business presenters.\n  tags:\n    - Apple\n    - Keynote\n    - Presentations\n    - Automation\n    - Productivity\n    - iCloud\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      ICLOUD_AUTH_TOKEN: ICLOUD_AUTH_TOKEN\n\ncapability:\n  consumes:\n    - import: keynote-icloud\n      location: ./shared/apple-keynote-icloud.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: keynote-automation-api\n      description: Unified REST API for Keynote presentation automation.\n      resources:\n        - path: /v1/presentations\n   \
  \       name: presentations\n          description: Presentation lifecycle management\n          operations:\n            - method: GET\n              name: list-presentations\n              description: List all Keynote presentations in iCloud\n              call: \"keynote-icloud.list-presentations\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-presentation\n              description: Create a new presentation with title and theme\n              call: \"keynote-icloud.create-presentation\"\n              with:\n                title: \"rest.title\"\n                theme: \"rest.theme\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/slides\n          name: slides\n          description: Slide management within presentations\n          operations:\n            - method: GET\n              name: list-slides\n\
  \              description: List slides in a presentation\n              call: \"keynote-icloud.list-slides\"\n              with:\n                presentationId: \"rest.presentationId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/export\n          name: export\n          description: Presentation export to different formats\n          operations:\n            - method: POST\n              name: export-presentation\n              description: Export a presentation to PDF, PPTX, or images\n              call: \"keynote-icloud.export-presentation\"\n              with:\n                presentationId: \"rest.presentationId\"\n                format: \"rest.format\"\n                includeNotes: \"rest.includeNotes\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/themes\n          name: themes\n          description: Available themes\
  \ and templates\n          operations:\n            - method: GET\n              name: list-themes\n              description: List available Keynote themes\n              call: \"keynote-icloud.list-themes\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: keynote-automation-mcp\n      transport: http\n      description: MCP server for AI-assisted Keynote presentation creation and management.\n      tools:\n        - name: list-keynote-presentations\n          description: Lists all Keynote presentations stored in the user's iCloud account\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"keynote-icloud.list-presentations\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-keynote-presentation\n          description: Creates a new Keynote presentation with a specified title\
  \ and optional theme\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"keynote-icloud.create-presentation\"\n          with:\n            title: \"tools.title\"\n            theme: \"tools.theme\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-presentation-slides\n          description: Lists all slides in a Keynote presentation with their titles and layouts\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"keynote-icloud.list-slides\"\n          with:\n            presentationId: \"tools.presentationId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: add-slide-to-presentation\n          description: Adds a new slide to a Keynote presentation at a specified position with a chosen layout\n          hints:\n            readOnly: false\n            destructive: false\n     \
  \     call: \"keynote-icloud.add-slide\"\n          with:\n            presentationId: \"tools.presentationId\"\n            layout: \"tools.layout\"\n            position: \"tools.position\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: export-keynote-to-pdf\n          description: Exports a Keynote presentation to PDF format with optional presenter notes\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"keynote-icloud.export-presentation\"\n          with:\n            presentationId: \"tools.presentationId\"\n            format: \"tools.format\"\n            includeNotes: \"tools.includeNotes\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-keynote-themes\n          description: Lists all available Keynote themes and templates for new presentations\n          hints:\n            readOnly: true\n            idempotent:\
  \ true\n          call: \"keynote-icloud.list-themes\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/apple-keynote/refs/heads/main/capabilities/presentation-automation.yaml
tags:
- Apple
- Keynote
- Presentations
- Automation
- Productivity
- iCloud
tools:
- description: Lists all Keynote presentations stored in the user's iCloud account
  hints:
    idempotent: true
    readOnly: true
  name: list-keynote-presentations
- description: Creates a new Keynote presentation with a specified title and optional theme
  hints:
    destructive: false
    readOnly: false
  name: create-keynote-presentation
- description: Lists all slides in a Keynote presentation with their titles and layouts
  hints:
    idempotent: true
    readOnly: true
  name: list-presentation-slides
- description: Adds a new slide to a Keynote presentation at a specified position with a chosen layout
  hints:
    destructive: false
    readOnly: false
  name: add-slide-to-presentation
- description: Exports a Keynote presentation to PDF format with optional presenter notes
  hints:
    idempotent: true
    readOnly: true
  name: export-keynote-to-pdf
- description: Lists all available Keynote themes and templates for new presentations
  hints:
    idempotent: true
    readOnly: true
  name: list-keynote-themes
---
