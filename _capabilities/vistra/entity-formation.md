---
api_specs:
- filename: vistra-incorporations-openapi.yml
  format: yaml
  label: vistra-incorporations
  slug: vistra-incorporations
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/vistra/refs/heads/main/openapi/vistra-incorporations-openapi.yml
categories: []
consumed_apis:
- vistra-incorporations
description: 'Workflow capability for automating company entity formation and incorporation via the Vistra REST API. Covers the complete BVI incorporation workflow: document upload preparation, upload confirmation, and incorporation request submission with entity details, stakeholders, and compliance data. Used by legal teams, fund administrators, and corporate services professionals to programmatically incorporate entities in supported jurisdictions.'
layout: capability
name: Vistra Entity Formation
operations:
- description: List all submitted incorporation requests
  method: GET
  name: list-incorporations
  path: /v1/incorporations
- description: Submit a new company incorporation request
  method: POST
  name: create-incorporation
  path: /v1/incorporations
- description: Get status of a specific incorporation request
  method: GET
  name: get-incorporation
  path: /v1/incorporations/{id}
- description: Generate a pre-signed URL for document upload
  method: POST
  name: generate-document-upload-url
  path: /v1/documents/upload-url
- description: Notify that a document upload has completed
  method: POST
  name: complete-document-upload
  path: /v1/documents/{id}/upload-complete
personas: []
provider_name: Vistra
provider_slug: vistra
search_terms:
- get status of a specific incorporation request
- incorporation
- individual incorporation request
- notify vistra that a document upload to the pre-signed url has completed
- vistra
- list all incorporation requests with their current processing status
- generate a pre-signed s3 url for uploading a supporting document for an incorporation request
- get incorporation
- generate a pre-signed url for document upload
- finance
- company incorporation requests
- list incorporations
- complete document upload
- document upload url generation
- corporate services
- notify that a document upload has completed
- fortune 500
- create incorporation
- list all submitted incorporation requests
- legal
- generate document upload url
- bvi
- check the status and details of a specific incorporation request by id
- submit a new company incorporation request
- entity management
- document upload completion notification
- compliance
- submit a company incorporation request to vistra for bvi entity formation
slug: entity-formation
source_filename: entity-formation.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Vistra Entity Formation\"\n  description: >-\n    Workflow capability for automating company entity formation and incorporation\n    via the Vistra REST API. Covers the complete BVI incorporation workflow:\n    document upload preparation, upload confirmation, and incorporation request\n    submission with entity details, stakeholders, and compliance data. Used by\n    legal teams, fund administrators, and corporate services professionals to\n    programmatically incorporate entities in supported jurisdictions.\n  tags:\n    - BVI\n    - Compliance\n    - Corporate Services\n    - Entity Management\n    - Fortune 500\n    - Incorporation\n    - Legal\n    - Vistra\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      VISTRA_ACCESS_TOKEN: VISTRA_ACCESS_TOKEN\n\ncapability:\n  consumes:\n    - import: vistra-incorporations\n      location: ./shared/vistra-incorporations.yaml\n\n  exposes:\n\
  \    - type: rest\n      port: 8080\n      namespace: vistra-entity-formation-api\n      description: \"Unified REST API for Vistra entity formation and incorporation workflows.\"\n      resources:\n        - path: /v1/incorporations\n          name: incorporations\n          description: \"Company incorporation requests\"\n          operations:\n            - method: GET\n              name: list-incorporations\n              description: \"List all submitted incorporation requests\"\n              call: \"vistra-incorporations.list-incorporations\"\n              with:\n                status: \"rest.status\"\n                offset: \"rest.offset\"\n                limit: \"rest.limit\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-incorporation\n              description: \"Submit a new company incorporation request\"\n              call: \"vistra-incorporations.create-incorporation\"\
  \n              with:\n                jurisdiction: \"rest.jurisdiction\"\n                companyName: \"rest.companyName\"\n                entityType: \"rest.entityType\"\n                documentIds: \"rest.documentIds\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/incorporations/{id}\n          name: incorporation\n          description: \"Individual incorporation request\"\n          operations:\n            - method: GET\n              name: get-incorporation\n              description: \"Get status of a specific incorporation request\"\n              call: \"vistra-incorporations.get-incorporation\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/documents/upload-url\n          name: document-upload-url\n          description: \"Document upload URL generation\"\n          operations:\n\
  \            - method: POST\n              name: generate-document-upload-url\n              description: \"Generate a pre-signed URL for document upload\"\n              call: \"vistra-incorporations.generate-document-upload-url\"\n              with:\n                filename: \"rest.filename\"\n                contentType: \"rest.contentType\"\n                description: \"rest.description\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/documents/{id}/upload-complete\n          name: document-upload-complete\n          description: \"Document upload completion notification\"\n          operations:\n            - method: POST\n              name: complete-document-upload\n              description: \"Notify that a document upload has completed\"\n              call: \"vistra-incorporations.complete-document-upload\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n    \
  \            - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: vistra-entity-formation-mcp\n      transport: http\n      description: \"MCP server for AI-assisted entity formation and corporate compliance workflows.\"\n      tools:\n        - name: generate-document-upload-url\n          description: \"Generate a pre-signed S3 URL for uploading a supporting document for an incorporation request\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"vistra-incorporations.generate-document-upload-url\"\n          with:\n            filename: \"tools.filename\"\n            contentType: \"tools.contentType\"\n            description: \"tools.description\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: complete-document-upload\n          description: \"Notify Vistra that a document upload to the pre-signed URL has completed\"\n       \
  \   hints:\n            readOnly: false\n            idempotent: true\n          call: \"vistra-incorporations.complete-document-upload\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-incorporation\n          description: \"Submit a company incorporation request to Vistra for BVI entity formation\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"vistra-incorporations.create-incorporation\"\n          with:\n            jurisdiction: \"tools.jurisdiction\"\n            companyName: \"tools.companyName\"\n            entityType: \"tools.entityType\"\n            documentIds: \"tools.documentIds\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-incorporations\n          description: \"List all incorporation requests with their current processing status\"\n          hints:\n\
  \            readOnly: true\n            idempotent: true\n          call: \"vistra-incorporations.list-incorporations\"\n          with:\n            status: \"tools.status\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-incorporation\n          description: \"Check the status and details of a specific incorporation request by ID\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"vistra-incorporations.get-incorporation\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/vistra/refs/heads/main/capabilities/entity-formation.yaml
tags:
- BVI
- Compliance
- Corporate Services
- Entity Management
- Fortune 500
- Incorporation
- Legal
- Vistra
tools:
- description: Generate a pre-signed S3 URL for uploading a supporting document for an incorporation request
  hints:
    idempotent: false
    readOnly: false
  name: generate-document-upload-url
- description: Notify Vistra that a document upload to the pre-signed URL has completed
  hints:
    idempotent: true
    readOnly: false
  name: complete-document-upload
- description: Submit a company incorporation request to Vistra for BVI entity formation
  hints:
    idempotent: false
    readOnly: false
  name: create-incorporation
- description: List all incorporation requests with their current processing status
  hints:
    idempotent: true
    readOnly: true
  name: list-incorporations
- description: Check the status and details of a specific incorporation request by ID
  hints:
    idempotent: true
    readOnly: true
  name: get-incorporation
---
