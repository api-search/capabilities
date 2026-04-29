---
categories:
- automation
consumed_apis:
- docs-api
description: Unified workflow for creating, reading, and editing Google Docs documents including content manipulation, formatting, and template automation. Used by developers automating document workflows.
layout: capability
name: Google Docs Document Management
operations:
- description: Create a new document.
  method: POST
  name: create-document
  path: /v1/documents
- description: Get a document by ID.
  method: GET
  name: get-document
  path: /v1/documents/{id}
- description: Apply batch updates to a document.
  method: POST
  name: batch-update-document
  path: /v1/documents/{id}/batch-update
personas: []
provider_name: Google Docs
provider_slug: google-docs
search_terms:
- google workspace
- apply batch updates to insert, replace, or delete content in a document.
- documents
- document batch updates.
- collaboration
- automation
- word processing
- create a new google docs document with a title.
- batch update document
- productivity
- create document
- document management
- get a document by id.
- get document
- document creation.
- apply batch updates to a document.
- document retrieval and updates.
- google docs
- create a new document.
- retrieve a google docs document by its id.
slug: document-management
source_filename: document-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Google Docs Document Management\"\n  description: \"Unified workflow for creating, reading, and editing Google Docs documents including content manipulation, formatting, and template automation. Used by developers automating document workflows.\"\n  tags:\n    - Google Docs\n    - Document Management\n    - Google Workspace\n    - Automation\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      GOOGLE_OAUTH_TOKEN: GOOGLE_OAUTH_TOKEN\n\ncapability:\n  consumes:\n    - import: docs-api\n      location: ./shared/docs-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: docs-management-api\n      description: \"Unified REST API for Google Docs document management.\"\n      resources:\n        - path: /v1/documents\n          name: documents\n          description: \"Document creation.\"\n          operations:\n            - method: POST\n              name: create-document\n\
  \              description: \"Create a new document.\"\n              call: \"docs-api.create-document\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/documents/{id}\n          name: document-details\n          description: \"Document retrieval and updates.\"\n          operations:\n            - method: GET\n              name: get-document\n              description: \"Get a document by ID.\"\n              call: \"docs-api.get-document\"\n              with:\n                documentId: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/documents/{id}/batch-update\n          name: document-updates\n          description: \"Document batch updates.\"\n          operations:\n            - method: POST\n              name: batch-update-document\n              description: \"Apply batch updates to a document.\"\n              call: \"\
  docs-api.batch-update-document\"\n              with:\n                documentId: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: docs-management-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Google Docs document management.\"\n      tools:\n        - name: create-document\n          description: \"Create a new Google Docs document with a title.\"\n          hints:\n            readOnly: false\n          call: \"docs-api.create-document\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-document\n          description: \"Retrieve a Google Docs document by its ID.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"docs-api.get-document\"\n          with:\n            documentId: \"tools.documentId\"\n          outputParameters:\n     \
  \       - type: object\n              mapping: \"$.\"\n        - name: batch-update-document\n          description: \"Apply batch updates to insert, replace, or delete content in a document.\"\n          hints:\n            readOnly: false\n          call: \"docs-api.batch-update-document\"\n          with:\n            documentId: \"tools.documentId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-docs/refs/heads/main/capabilities/document-management.yaml
tags:
- Google Docs
- Document Management
- Google Workspace
- Automation
tools:
- description: Create a new Google Docs document with a title.
  hints:
    readOnly: false
  name: create-document
- description: Retrieve a Google Docs document by its ID.
  hints:
    idempotent: true
    readOnly: true
  name: get-document
- description: Apply batch updates to insert, replace, or delete content in a document.
  hints:
    readOnly: false
  name: batch-update-document
---
