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
- list permissions.
- get document
- get metadata for a word document stored in onedrive/sharepoint.
- list all paragraphs in the document.
- list comments.
- Automation Engineer
- document search.
- graph share document
- openxml convert document
- list tables
- graph create folder
- addin list comments
- get document body content.
- creates and edits word documents, manages formatting and content.
- insert text into the document body.
- microsoft word
- addin search text
- search for word documents in onedrive/sharepoint.
- Content Manager
- graph get document
- addin insert table
- list version history.
- convert document
- individual document operations.
- create document
- convert to another format.
- Document Author
- list sharing permissions on a document.
- automation
- graph list files
- get the body content of an open word document.
- add a paragraph to a document server-side.
- manages document templates, reviews, and publishing workflows.
- addin list content controls
- graph delete document
- create a new word document.
- convert a word document to pdf or other format.
- table operations.
- list comments in the document.
- graph search documents
- create a new word document server-side using open xml.
- insert a new table into the document.
- list tables.
- document lifecycle operations.
- get content
- delete a document from onedrive/sharepoint.
- addin insert text
- addin list tables
- paragraph operations.
- openxml create document
- addin list paragraphs
- search for text within the document.
- delete document
- comment operations.
- create a new folder in onedrive.
- document content operations.
- addin insert html
- documents
- list paragraphs.
- graph list versions
- list permissions
- create a sharing link for a document.
- builds automated document generation and processing pipelines.
- collaboration
- list comments
- word processing
- list files and folders in a onedrive directory.
- list version history of a document.
- document management
- document format conversion.
- get document metadata.
- search documents
- list versions
- microsoft 365
- search for documents.
- unified document lifecycle management combining cloud storage, content manipulation, and server-side processing.
- list paragraphs
- addin get body
- insert html content into the document.
- list content controls in the document.
- openxml add paragraph
- version history operations.
- graph list permissions
- delete a document.
- permission and sharing operations.
- list tables in the document.
- productivity
- office
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
