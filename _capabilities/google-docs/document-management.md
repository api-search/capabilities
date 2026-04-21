---
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
- get a document by id.
- get document
- google docs
- google workspace
- create a new document.
- apply batch updates to a document.
- word processing
- document retrieval and updates.
- retrieve a google docs document by its id.
- document creation.
- document batch updates.
- productivity
- apply batch updates to insert, replace, or delete content in a document.
- batch update document
- document management
- create a new google docs document with a title.
- automation
- documents
- collaboration
- create document
slug: document-management
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
