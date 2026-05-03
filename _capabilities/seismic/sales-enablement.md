---
categories: []
consumed_apis:
- seismic-content
- seismic-livedocs
- seismic-analytics
- seismic-users
description: Unified workflow capability for sales enablement workflows in Seismic — combining dynamic document generation, user management, analytics, and content delivery for sales reps, managers, and enablement teams.
layout: capability
name: Seismic Sales Enablement
operations:
- description: Generate a personalized LiveDoc.
  method: POST
  name: generate-livedoc
  path: /v1/documents/generate
- description: List LiveDoc templates.
  method: GET
  name: list-livedoc-templates
  path: /v1/documents/templates
- description: List generation jobs.
  method: GET
  name: list-generation-jobs
  path: /v1/documents/jobs
- description: List content items.
  method: GET
  name: list-content-items
  path: /v1/content
- description: Get user analytics.
  method: GET
  name: get-user-analytics
  path: /v1/analytics/users
- description: List reports.
  method: GET
  name: list-reports
  path: /v1/analytics/reports
- description: List users.
  method: GET
  name: list-users
  path: /v1/users
personas: []
provider_name: Seismic
provider_slug: seismic
search_terms:
- search seismic content library.
- list users.
- generate personalized sales documents.
- generate a personalized sales document by merging data into a seismic livedoc template.
- sales rep adoption analytics.
- list reports.
- list reports
- browse sales content.
- get analytics on content delivered to buyers.
- get livedoc template
- get details of a specific livedoc template.
- list generation jobs
- list generation jobs.
- analytics reports.
- get user analytics
- manage users.
- list available seismic analytics reports.
- list seismic platform users.
- list livedoc templates
- list users
- list available livedoc templates for document generation.
- get a shareable url for delivering content to prospects.
- user management
- reporting
- livedocs
- track document generation jobs.
- document generation
- get delivery analytics
- generate livedoc
- get livedoc template inputs
- list data sources
- list available document templates.
- check the status of an async livedoc generation job.
- get generation job
- list crm data sources available for livedoc generation.
- list content items
- get content url
- list content items.
- get required input fields for a livedoc template.
- sales enablement
- search content
- seismic
- generate a personalized livedoc.
- list livedoc templates.
- get sales rep adoption and usage analytics.
- get user analytics.
- browse available sales content in seismic.
slug: sales-enablement
source_filename: sales-enablement.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Seismic Sales Enablement\"\n  description: \"Unified workflow capability for sales enablement workflows in Seismic — combining dynamic document generation, user management, analytics, and content delivery for sales reps, managers, and enablement teams.\"\n  tags:\n    - Seismic\n    - Sales Enablement\n    - Document Generation\n    - LiveDocs\n    - User Management\n    - Reporting\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SEISMIC_ACCESS_TOKEN: SEISMIC_ACCESS_TOKEN\n\ncapability:\n  consumes:\n    - import: seismic-content\n      location: ./shared/content-api.yaml\n    - import: seismic-livedocs\n      location: ./shared/livedocs-api.yaml\n    - import: seismic-analytics\n      location: ./shared/analytics-api.yaml\n    - import: seismic-users\n      location: ./shared/user-management-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8081\n      namespace: seismic-sales-enablement-api\n\
  \      description: \"Unified REST API for Seismic sales enablement workflows.\"\n      resources:\n        - path: /v1/documents/generate\n          name: document-generation\n          description: \"Generate personalized sales documents.\"\n          operations:\n            - method: POST\n              name: generate-livedoc\n              description: \"Generate a personalized LiveDoc.\"\n              call: \"seismic-livedocs.generate-livedoc\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/documents/templates\n          name: document-templates\n          description: \"List available document templates.\"\n          operations:\n            - method: GET\n              name: list-livedoc-templates\n              description: \"List LiveDoc templates.\"\n              call: \"seismic-livedocs.list-livedoc-templates\"\n              outputParameters:\n                - type: object\n                  mapping:\
  \ \"$.\"\n        - path: /v1/documents/jobs\n          name: generation-jobs\n          description: \"Track document generation jobs.\"\n          operations:\n            - method: GET\n              name: list-generation-jobs\n              description: \"List generation jobs.\"\n              call: \"seismic-livedocs.list-generation-jobs\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/content\n          name: content-items\n          description: \"Browse sales content.\"\n          operations:\n            - method: GET\n              name: list-content-items\n              description: \"List content items.\"\n              call: \"seismic-content.list-content-items\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/analytics/users\n          name: user-analytics\n          description: \"Sales rep adoption analytics.\"\n          operations:\n\
  \            - method: GET\n              name: get-user-analytics\n              description: \"Get user analytics.\"\n              call: \"seismic-analytics.get-user-analytics\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/analytics/reports\n          name: reports\n          description: \"Analytics reports.\"\n          operations:\n            - method: GET\n              name: list-reports\n              description: \"List reports.\"\n              call: \"seismic-analytics.list-reports\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/users\n          name: users\n          description: \"Manage users.\"\n          operations:\n            - method: GET\n              name: list-users\n              description: \"List users.\"\n              call: \"seismic-users.list-users\"\n              outputParameters:\n                - type:\
  \ object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9091\n      namespace: seismic-sales-enablement-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Seismic sales enablement.\"\n      tools:\n        - name: generate-livedoc\n          description: \"Generate a personalized sales document by merging data into a Seismic LiveDoc template.\"\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"seismic-livedocs.generate-livedoc\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-livedoc-templates\n          description: \"List available LiveDoc templates for document generation.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"seismic-livedocs.list-livedoc-templates\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-livedoc-template\n\
  \          description: \"Get details of a specific LiveDoc template.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"seismic-livedocs.get-livedoc-template\"\n          with:\n            templateId: \"tools.templateId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-livedoc-template-inputs\n          description: \"Get required input fields for a LiveDoc template.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"seismic-livedocs.get-livedoc-template-inputs\"\n          with:\n            templateId: \"tools.templateId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-generation-job\n          description: \"Check the status of an async LiveDoc generation job.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"seismic-livedocs.get-generation-job\"\
  \n          with:\n            jobId: \"tools.jobId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-content-items\n          description: \"Browse available sales content in Seismic.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"seismic-content.list-content-items\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: search-content\n          description: \"Search Seismic content library.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"seismic-content.search-content\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-content-url\n          description: \"Get a shareable URL for delivering content to prospects.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"seismic-content.get-content-url\"\
  \n          with:\n            contentId: \"tools.contentId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-user-analytics\n          description: \"Get sales rep adoption and usage analytics.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"seismic-analytics.get-user-analytics\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-delivery-analytics\n          description: \"Get analytics on content delivered to buyers.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"seismic-analytics.get-delivery-analytics\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-reports\n          description: \"List available Seismic analytics reports.\"\n          hints:\n            readOnly: true\n            openWorld: true\n     \
  \     call: \"seismic-analytics.list-reports\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-users\n          description: \"List Seismic platform users.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"seismic-users.list-users\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-data-sources\n          description: \"List CRM data sources available for LiveDoc generation.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"seismic-livedocs.list-data-sources\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/seismic/refs/heads/main/capabilities/sales-enablement.yaml
tags:
- Seismic
- Sales Enablement
- Document Generation
- LiveDocs
- User Management
- Reporting
tools:
- description: Generate a personalized sales document by merging data into a Seismic LiveDoc template.
  hints:
    openWorld: false
    readOnly: false
  name: generate-livedoc
- description: List available LiveDoc templates for document generation.
  hints:
    openWorld: true
    readOnly: true
  name: list-livedoc-templates
- description: Get details of a specific LiveDoc template.
  hints:
    openWorld: false
    readOnly: true
  name: get-livedoc-template
- description: Get required input fields for a LiveDoc template.
  hints:
    openWorld: false
    readOnly: true
  name: get-livedoc-template-inputs
- description: Check the status of an async LiveDoc generation job.
  hints:
    openWorld: false
    readOnly: true
  name: get-generation-job
- description: Browse available sales content in Seismic.
  hints:
    openWorld: true
    readOnly: true
  name: list-content-items
- description: Search Seismic content library.
  hints:
    openWorld: true
    readOnly: true
  name: search-content
- description: Get a shareable URL for delivering content to prospects.
  hints:
    openWorld: false
    readOnly: true
  name: get-content-url
- description: Get sales rep adoption and usage analytics.
  hints:
    openWorld: true
    readOnly: true
  name: get-user-analytics
- description: Get analytics on content delivered to buyers.
  hints:
    openWorld: true
    readOnly: true
  name: get-delivery-analytics
- description: List available Seismic analytics reports.
  hints:
    openWorld: true
    readOnly: true
  name: list-reports
- description: List Seismic platform users.
  hints:
    openWorld: true
    readOnly: true
  name: list-users
- description: List CRM data sources available for LiveDoc generation.
  hints:
    openWorld: true
    readOnly: true
  name: list-data-sources
---
