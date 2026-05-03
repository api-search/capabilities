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
- insert html content into the document.
- comment operations.
- creates and edits word documents, manages formatting and content.
- create a sharing link for a document.
- list content controls in the document.
- permission and sharing operations.
- graph delete document
- Content Manager
- add a paragraph to a document server-side.
- list tables in the document.
- productivity
- document format conversion.
- insert text into the document body.
- document search.
- openxml convert document
- list sharing permissions on a document.
- get metadata for a word document stored in onedrive/sharepoint.
- unified document lifecycle management combining cloud storage, content manipulation, and server-side processing.
- addin insert table
- openxml create document
- list paragraphs
- list permissions
- automation
- individual document operations.
- addin search text
- addin insert text
- document content operations.
- search documents
- addin list paragraphs
- convert document
- microsoft word
- documents
- graph list versions
- search for text within the document.
- version history operations.
- insert a new table into the document.
- addin list comments
- graph list permissions
- office
- convert to another format.
- graph create folder
- addin list content controls
- list comments.
- collaboration
- convert a word document to pdf or other format.
- search for documents.
- delete a document.
- list comments in the document.
- document lifecycle operations.
- list all paragraphs in the document.
- list paragraphs.
- list comments
- search for word documents in onedrive/sharepoint.
- create a new word document.
- get content
- builds automated document generation and processing pipelines.
- addin get body
- delete a document from onedrive/sharepoint.
- list files and folders in a onedrive directory.
- Document Author
- delete document
- manages document templates, reviews, and publishing workflows.
- create a new word document server-side using open xml.
- list version history.
- get the body content of an open word document.
- get document metadata.
- document management
- graph search documents
- word processing
- openxml add paragraph
- addin list tables
- Automation Engineer
- graph share document
- list versions
- table operations.
- list tables
- create a new folder in onedrive.
- paragraph operations.
- list permissions.
- addin insert html
- get document body content.
- microsoft 365
- list tables.
- get document
- list version history of a document.
- graph list files
- graph get document
- create document
slug: document-management
source_filename: document-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Microsoft Word Document Management\"\n  description: \"Unified workflow for Word document creation, editing, collaboration, conversion, and lifecycle management. Combines Microsoft Graph for cloud storage and sharing, JavaScript API for content manipulation, and Open XML SDK for server-side processing. Used by document authors, content managers, and automation engineers.\"\n  tags:\n    - Microsoft Word\n    - Document Management\n    - Collaboration\n    - Automation\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      MICROSOFT_GRAPH_TOKEN: MICROSOFT_GRAPH_TOKEN\n      OFFICE_ADDIN_TOKEN: OFFICE_ADDIN_TOKEN\n      OPENXML_API_KEY: OPENXML_API_KEY\n\ncapability:\n  consumes:\n    - import: graph-api\n      location: ./shared/graph-api.yaml\n    - import: javascript-api\n      location: ./shared/javascript-api.yaml\n    - import: open-xml-sdk\n      location: ./shared/open-xml-sdk.yaml\n\
  \n  exposes:\n    - type: rest\n      port: 8080\n      namespace: word-document-mgmt-api\n      description: \"Unified REST API for Microsoft Word document management across cloud, add-in, and server-side processing.\"\n      resources:\n        - path: /v1/documents\n          name: documents\n          description: \"Document lifecycle operations.\"\n          operations:\n            - method: POST\n              name: create-document\n              description: \"Create a new Word document.\"\n              call: \"open-xml-sdk.create-document\"\n              with:\n                filename: \"rest.filename\"\n                title: \"rest.title\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/documents/{document-id}\n          name: document-detail\n          description: \"Individual document operations.\"\n          operations:\n            - method: GET\n              name: get-document\n              description:\
  \ \"Get document metadata.\"\n              call: \"graph-api.get-drive-item\"\n              with:\n                item-id: \"rest.document-id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-document\n              description: \"Delete a document.\"\n              call: \"graph-api.delete-drive-item\"\n              with:\n                item-id: \"rest.document-id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/documents/{document-id}/content\n          name: content\n          description: \"Document content operations.\"\n          operations:\n            - method: GET\n              name: get-content\n              description: \"Get document body content.\"\n              call: \"javascript-api.get-body\"\n              with:\n                document-id: \"rest.document-id\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n        - path: /v1/documents/{document-id}/paragraphs\n          name: paragraphs\n          description: \"Paragraph operations.\"\n          operations:\n            - method: GET\n              name: list-paragraphs\n              description: \"List paragraphs.\"\n              call: \"javascript-api.list-paragraphs\"\n              with:\n                document-id: \"rest.document-id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/documents/{document-id}/tables\n          name: tables\n          description: \"Table operations.\"\n          operations:\n            - method: GET\n              name: list-tables\n              description: \"List tables.\"\n              call: \"javascript-api.list-tables\"\n              with:\n                document-id: \"rest.document-id\"\n              outputParameters:\n                - type: object\n\
  \                  mapping: \"$.\"\n        - path: /v1/documents/{document-id}/comments\n          name: comments\n          description: \"Comment operations.\"\n          operations:\n            - method: GET\n              name: list-comments\n              description: \"List comments.\"\n              call: \"javascript-api.list-comments\"\n              with:\n                document-id: \"rest.document-id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/documents/{document-id}/permissions\n          name: permissions\n          description: \"Permission and sharing operations.\"\n          operations:\n            - method: GET\n              name: list-permissions\n              description: \"List permissions.\"\n              call: \"graph-api.list-permissions\"\n              with:\n                item-id: \"rest.document-id\"\n              outputParameters:\n                - type: object\n     \
  \             mapping: \"$.\"\n        - path: /v1/documents/{document-id}/versions\n          name: versions\n          description: \"Version history operations.\"\n          operations:\n            - method: GET\n              name: list-versions\n              description: \"List version history.\"\n              call: \"graph-api.list-versions\"\n              with:\n                item-id: \"rest.document-id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/documents/{document-id}/convert\n          name: convert\n          description: \"Document format conversion.\"\n          operations:\n            - method: POST\n              name: convert-document\n              description: \"Convert to another format.\"\n              call: \"open-xml-sdk.convert-document\"\n              with:\n                document-id: \"rest.document-id\"\n                targetFormat: \"rest.targetFormat\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n        - path: /v1/search\n          name: search\n          description: \"Document search.\"\n          operations:\n            - method: GET\n              name: search-documents\n              description: \"Search for documents.\"\n              call: \"graph-api.search-drive-items\"\n              with:\n                search-text: \"rest.q\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: word-document-mgmt-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Word document management, combining cloud, add-in, and server-side capabilities.\"\n      tools:\n        - name: graph-get-document\n          description: \"Get metadata for a Word document stored in OneDrive/SharePoint.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"graph-api.get-drive-item\"\
  \n          with:\n            item-id: \"tools.item-id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: graph-list-files\n          description: \"List files and folders in a OneDrive directory.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"graph-api.list-children\"\n          with:\n            item-id: \"tools.item-id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: graph-search-documents\n          description: \"Search for Word documents in OneDrive/SharePoint.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"graph-api.search-drive-items\"\n          with:\n            search-text: \"tools.search-text\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: graph-create-folder\n          description: \"Create a new folder\
  \ in OneDrive.\"\n          hints:\n            readOnly: false\n          call: \"graph-api.create-folder\"\n          with:\n            item-id: \"tools.item-id\"\n            name: \"tools.name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: graph-share-document\n          description: \"Create a sharing link for a document.\"\n          hints:\n            readOnly: false\n          call: \"graph-api.create-sharing-link\"\n          with:\n            item-id: \"tools.item-id\"\n            type: \"tools.type\"\n            scope: \"tools.scope\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: graph-list-permissions\n          description: \"List sharing permissions on a document.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"graph-api.list-permissions\"\n          with:\n            item-id: \"tools.item-id\"\n    \
  \      outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: graph-list-versions\n          description: \"List version history of a document.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"graph-api.list-versions\"\n          with:\n            item-id: \"tools.item-id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: graph-delete-document\n          description: \"Delete a document from OneDrive/SharePoint.\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"graph-api.delete-drive-item\"\n          with:\n            item-id: \"tools.item-id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: addin-get-body\n          description: \"Get the body content of an open Word document.\"\n          hints:\n         \
  \   readOnly: true\n            idempotent: true\n          call: \"javascript-api.get-body\"\n          with:\n            document-id: \"tools.document-id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: addin-insert-text\n          description: \"Insert text into the document body.\"\n          hints:\n            readOnly: false\n          call: \"javascript-api.insert-text\"\n          with:\n            document-id: \"tools.document-id\"\n            text: \"tools.text\"\n            location: \"tools.location\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: addin-insert-html\n          description: \"Insert HTML content into the document.\"\n          hints:\n            readOnly: false\n          call: \"javascript-api.insert-html\"\n          with:\n            document-id: \"tools.document-id\"\n            html: \"tools.html\"\n            location: \"tools.location\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: addin-list-paragraphs\n          description: \"List all paragraphs in the document.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"javascript-api.list-paragraphs\"\n          with:\n            document-id: \"tools.document-id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: addin-list-content-controls\n          description: \"List content controls in the document.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"javascript-api.list-content-controls\"\n          with:\n            document-id: \"tools.document-id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: addin-list-tables\n          description: \"List tables in the document.\"\n          hints:\n            readOnly:\
  \ true\n            idempotent: true\n          call: \"javascript-api.list-tables\"\n          with:\n            document-id: \"tools.document-id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: addin-insert-table\n          description: \"Insert a new table into the document.\"\n          hints:\n            readOnly: false\n          call: \"javascript-api.insert-table\"\n          with:\n            document-id: \"tools.document-id\"\n            rowCount: \"tools.rowCount\"\n            columnCount: \"tools.columnCount\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: addin-list-comments\n          description: \"List comments in the document.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"javascript-api.list-comments\"\n          with:\n            document-id: \"tools.document-id\"\n          outputParameters:\n   \
  \         - type: object\n              mapping: \"$.\"\n        - name: addin-search-text\n          description: \"Search for text within the document.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"javascript-api.search-document\"\n          with:\n            document-id: \"tools.document-id\"\n            searchText: \"tools.searchText\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: openxml-create-document\n          description: \"Create a new Word document server-side using Open XML.\"\n          hints:\n            readOnly: false\n          call: \"open-xml-sdk.create-document\"\n          with:\n            filename: \"tools.filename\"\n            title: \"tools.title\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: openxml-convert-document\n          description: \"Convert a Word document to PDF or other format.\"\
  \n          hints:\n            readOnly: false\n          call: \"open-xml-sdk.convert-document\"\n          with:\n            document-id: \"tools.document-id\"\n            targetFormat: \"tools.targetFormat\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: openxml-add-paragraph\n          description: \"Add a paragraph to a document server-side.\"\n          hints:\n            readOnly: false\n          call: \"open-xml-sdk.add-paragraph\"\n          with:\n            document-id: \"tools.document-id\"\n            text: \"tools.text\"\n            styleId: \"tools.styleId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/microsoft-word/refs/heads/main/capabilities/document-management.yaml
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
