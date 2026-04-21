---
consumed_apis:
- graph-api
- javascript-api
- open-xml-sdk
description: Unified workflow for Word document creation, editing, collaboration, conversion, and lifecycle management. Combines Microsoft Graph for cloud storage and sharing, JavaScript API for content manipulation, and Open XML SDK for server-side processing. Used by document authors, content managers, and automation engineers.
layout: capability
name: Microsoft Word Document Management
operations:
- description: Create a new Word document.
  method: POST
  name: create-document
  path: /v1/documents
- description: Get document metadata.
  method: GET
  name: get-document
  path: /v1/documents/{document-id}
- description: Delete a document.
  method: DELETE
  name: delete-document
  path: /v1/documents/{document-id}
- description: Get document body content.
  method: GET
  name: get-content
  path: /v1/documents/{document-id}/content
- description: List paragraphs.
  method: GET
  name: list-paragraphs
  path: /v1/documents/{document-id}/paragraphs
- description: List tables.
  method: GET
  name: list-tables
  path: /v1/documents/{document-id}/tables
- description: List comments.
  method: GET
  name: list-comments
  path: /v1/documents/{document-id}/comments
- description: List permissions.
  method: GET
  name: list-permissions
  path: /v1/documents/{document-id}/permissions
- description: List version history.
  method: GET
  name: list-versions
  path: /v1/documents/{document-id}/versions
- description: Convert to another format.
  method: POST
  name: convert-document
  path: /v1/documents/{document-id}/convert
- description: Search for documents.
  method: GET
  name: search-documents
  path: /v1/search
personas: []
provider_name: Microsoft Word
provider_slug: microsoft-word
search_terms:
- list content controls in the document.
- list permissions.
- individual document operations.
- list version history.
- search for word documents in onedrive/sharepoint.
- graph share document
- graph list files
- table operations.
- create document
- document lifecycle operations.
- openxml add paragraph
- builds automated document generation and processing pipelines.
- graph create folder
- convert document
- graph get document
- document management
- list tables in the document.
- addin list tables
- document search.
- addin list content controls
- permission and sharing operations.
- document content operations.
- search documents
- graph list versions
- version history operations.
- get document
- unified document lifecycle management combining cloud storage, content manipulation, and server-side processing.
- office
- create a new word document.
- word processing
- insert text into the document body.
- convert a word document to pdf or other format.
- create a new word document server-side using open xml.
- list files and folders in a onedrive directory.
- create a sharing link for a document.
- paragraph operations.
- automation
- collaboration
- list tables
- addin list comments
- comment operations.
- documents
- create a new folder in onedrive.
- addin insert html
- insert a new table into the document.
- Document Author
- list comments
- openxml create document
- delete a document from onedrive/sharepoint.
- list sharing permissions on a document.
- search for text within the document.
- get document metadata.
- list permissions
- Content Manager
- addin insert text
- insert html content into the document.
- addin get body
- get document body content.
- document format conversion.
- list version history of a document.
- delete document
- list paragraphs
- list all paragraphs in the document.
- openxml convert document
- Automation Engineer
- get content
- list paragraphs.
- addin list paragraphs
- add a paragraph to a document server-side.
- get metadata for a word document stored in onedrive/sharepoint.
- list comments.
- creates and edits word documents, manages formatting and content.
- graph list permissions
- search for documents.
- convert to another format.
- get the body content of an open word document.
- microsoft 365
- microsoft word
- manages document templates, reviews, and publishing workflows.
- list tables.
- addin search text
- productivity
- addin insert table
- graph delete document
- delete a document.
- graph search documents
- list comments in the document.
- list versions
slug: document-management
tags:
- Microsoft Word
- Document Management
- Collaboration
- Automation
tools:
- description: Get metadata for a Word document stored in OneDrive/SharePoint.
  hints:
    idempotent: true
    readOnly: true
  name: graph-get-document
- description: List files and folders in a OneDrive directory.
  hints:
    idempotent: true
    readOnly: true
  name: graph-list-files
- description: Search for Word documents in OneDrive/SharePoint.
  hints:
    idempotent: true
    readOnly: true
  name: graph-search-documents
- description: Create a new folder in OneDrive.
  hints:
    readOnly: false
  name: graph-create-folder
- description: Create a sharing link for a document.
  hints:
    readOnly: false
  name: graph-share-document
- description: List sharing permissions on a document.
  hints:
    idempotent: true
    readOnly: true
  name: graph-list-permissions
- description: List version history of a document.
  hints:
    idempotent: true
    readOnly: true
  name: graph-list-versions
- description: Delete a document from OneDrive/SharePoint.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: graph-delete-document
- description: Get the body content of an open Word document.
  hints:
    idempotent: true
    readOnly: true
  name: addin-get-body
- description: Insert text into the document body.
  hints:
    readOnly: false
  name: addin-insert-text
- description: Insert HTML content into the document.
  hints:
    readOnly: false
  name: addin-insert-html
- description: List all paragraphs in the document.
  hints:
    idempotent: true
    readOnly: true
  name: addin-list-paragraphs
- description: List content controls in the document.
  hints:
    idempotent: true
    readOnly: true
  name: addin-list-content-controls
- description: List tables in the document.
  hints:
    idempotent: true
    readOnly: true
  name: addin-list-tables
- description: Insert a new table into the document.
  hints:
    readOnly: false
  name: addin-insert-table
- description: List comments in the document.
  hints:
    idempotent: true
    readOnly: true
  name: addin-list-comments
- description: Search for text within the document.
  hints:
    idempotent: true
    readOnly: true
  name: addin-search-text
- description: Create a new Word document server-side using Open XML.
  hints:
    readOnly: false
  name: openxml-create-document
- description: Convert a Word document to PDF or other format.
  hints:
    readOnly: false
  name: openxml-convert-document
- description: Add a paragraph to a document server-side.
  hints:
    readOnly: false
  name: openxml-add-paragraph
---
