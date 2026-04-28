---
categories:
- collaboration
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
- graph search documents
- graph delete document
- insert text into the document body.
- search documents
- get document
- addin search text
- addin insert text
- graph list versions
- get document body content.
- table operations.
- list files and folders in a onedrive directory.
- addin list tables
- search for text within the document.
- list tables.
- insert a new table into the document.
- list comments.
- Document Author
- documents
- list paragraphs.
- get content
- microsoft word
- create a new word document.
- delete a document.
- openxml add paragraph
- office
- graph list permissions
- microsoft 365
- list content controls in the document.
- list tables in the document.
- list comments
- manages document templates, reviews, and publishing workflows.
- list all paragraphs in the document.
- addin insert table
- list permissions.
- addin list paragraphs
- version history operations.
- permission and sharing operations.
- document search.
- list sharing permissions on a document.
- create a sharing link for a document.
- document format conversion.
- graph create folder
- create document
- get document metadata.
- document content operations.
- list tables
- add a paragraph to a document server-side.
- document lifecycle operations.
- search for documents.
- delete a document from onedrive/sharepoint.
- graph share document
- list permissions
- convert to another format.
- delete document
- builds automated document generation and processing pipelines.
- paragraph operations.
- list version history.
- get metadata for a word document stored in onedrive/sharepoint.
- openxml convert document
- convert a word document to pdf or other format.
- comment operations.
- graph get document
- openxml create document
- addin insert html
- unified document lifecycle management combining cloud storage, content manipulation, and server-side processing.
- list paragraphs
- document management
- insert html content into the document.
- addin list comments
- create a new folder in onedrive.
- create a new word document server-side using open xml.
- automation
- word processing
- individual document operations.
- addin get body
- get the body content of an open word document.
- convert document
- addin list content controls
- search for word documents in onedrive/sharepoint.
- productivity
- Automation Engineer
- Content Manager
- list comments in the document.
- collaboration
- creates and edits word documents, manages formatting and content.
- list versions
- list version history of a document.
- graph list files
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
