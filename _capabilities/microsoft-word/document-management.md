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
- addin list tables
- search for word documents in onedrive/sharepoint.
- productivity
- list version history.
- document content operations.
- list sharing permissions on a document.
- insert text into the document body.
- get content
- openxml create document
- list tables in the document.
- delete document
- list tables
- get document
- get document metadata.
- list content controls in the document.
- add a paragraph to a document server-side.
- list files and folders in a onedrive directory.
- graph list files
- list paragraphs.
- addin get body
- table operations.
- microsoft word
- addin insert html
- graph share document
- openxml convert document
- word processing
- list version history of a document.
- list all paragraphs in the document.
- addin search text
- document lifecycle operations.
- list comments.
- search documents
- addin list comments
- version history operations.
- list permissions
- create a new word document.
- graph delete document
- convert a word document to pdf or other format.
- document management
- graph create folder
- comment operations.
- paragraph operations.
- list versions
- create a new word document server-side using open xml.
- office
- list permissions.
- search for text within the document.
- openxml add paragraph
- collaboration
- convert to another format.
- individual document operations.
- microsoft 365
- manages document templates, reviews, and publishing workflows.
- delete a document from onedrive/sharepoint.
- document format conversion.
- delete a document.
- get metadata for a word document stored in onedrive/sharepoint.
- addin list content controls
- list comments in the document.
- unified document lifecycle management combining cloud storage, content manipulation, and server-side processing.
- Document Author
- insert html content into the document.
- builds automated document generation and processing pipelines.
- addin insert table
- search for documents.
- insert a new table into the document.
- Automation Engineer
- permission and sharing operations.
- list paragraphs
- graph get document
- graph list versions
- get the body content of an open word document.
- list comments
- list tables.
- convert document
- documents
- graph list permissions
- automation
- graph search documents
- addin insert text
- Content Manager
- create a new folder in onedrive.
- create a sharing link for a document.
- get document body content.
- addin list paragraphs
- document search.
- creates and edits word documents, manages formatting and content.
- create document
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
