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
- add a paragraph to a document server-side.
- get document
- get document metadata.
- search for documents.
- graph list permissions
- document content operations.
- graph search documents
- productivity
- paragraph operations.
- graph delete document
- graph create folder
- convert document
- create a new folder in onedrive.
- delete a document.
- search documents
- builds automated document generation and processing pipelines.
- document format conversion.
- insert text into the document body.
- addin list comments
- delete document
- addin list paragraphs
- create a new word document server-side using open xml.
- office
- list comments
- graph list versions
- table operations.
- creates and edits word documents, manages formatting and content.
- list tables
- addin list content controls
- list files and folders in a onedrive directory.
- list versions
- document management
- Content Manager
- individual document operations.
- addin insert text
- graph get document
- list permissions
- openxml create document
- create a new word document.
- comment operations.
- create document
- insert a new table into the document.
- list tables in the document.
- convert to another format.
- convert a word document to pdf or other format.
- document lifecycle operations.
- word processing
- addin list tables
- get content
- list sharing permissions on a document.
- addin insert table
- microsoft word
- unified document lifecycle management combining cloud storage, content manipulation, and server-side processing.
- list content controls in the document.
- document search.
- version history operations.
- list tables.
- openxml convert document
- collaboration
- addin insert html
- create a sharing link for a document.
- permission and sharing operations.
- get metadata for a word document stored in onedrive/sharepoint.
- microsoft 365
- list version history of a document.
- list permissions.
- manages document templates, reviews, and publishing workflows.
- list comments.
- addin search text
- delete a document from onedrive/sharepoint.
- Automation Engineer
- list paragraphs
- get document body content.
- list paragraphs.
- list comments in the document.
- list version history.
- search for word documents in onedrive/sharepoint.
- addin get body
- graph list files
- automation
- documents
- Document Author
- insert html content into the document.
- search for text within the document.
- graph share document
- list all paragraphs in the document.
- get the body content of an open word document.
- openxml add paragraph
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
