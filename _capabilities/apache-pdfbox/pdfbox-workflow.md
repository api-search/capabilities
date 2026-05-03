---
categories:
- document-processing
consumed_apis: []
description: Workflow for creating, manipulating, extracting text from, and digitally signing PDF documents using Apache PDFBox.
layout: capability
name: Apache PDFBox Document Processing Workflow
operations:
- description: Create PDF document
  method: POST
  name: create-document
  path: /v1/documents
- description: Extract text from PDF
  method: GET
  name: extract-text
  path: /v1/documents/{documentId}/text
personas: []
provider_name: Apache PDFBox
provider_slug: apache-pdfbox
search_terms:
- apache pdfbox
- pdf
- list pages
- extract text
- open source
- sign document
- split a pdf document at specified page boundaries
- get metadata
- split document
- extract text content from a pdf document
- merge multiple pdf documents into one
- document processing
- create a new pdf document
- java
- apply a digital signature to a pdf document
- create pdf document
- get interactive form fields from a pdf document
- digital signatures
- create document
- list pages and their dimensions in a pdf
- extract text from pdf
- Document Manager
- Application Developer
- creates and manages pdf documents with metadata and signatures
- integrates pdf processing into applications
- text extraction
- merge documents
- get pdf document metadata (title, author, dates)
- get form fields
- apache
slug: pdfbox-workflow
source_filename: pdfbox-workflow.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\ninfo:\n  label: \"Apache PDFBox Document Processing Workflow\"\n  description: \"Workflow for creating, manipulating, extracting text from, and digitally signing PDF documents using Apache PDFBox.\"\n  tags:\n    - Apache PDFBox\n    - PDF\n    - Document Processing\n    - Digital Signatures\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\nbinds:\n  - namespace: env\n    keys:\n      PDFBOX_API_KEY: PDFBOX_API_KEY\ncapability:\n  consumes:\n    - type: http\n      namespace: pdfbox\n      baseUri: https://localhost:8080/pdfbox\n      description: \"Apache PDFBox REST API\"\n      resources:\n        - name: documents\n          path: /documents\n          description: \"Document operations\"\n          operations:\n            - name: createDocument\n              method: POST\n              description: \"Create a PDF document\"\n              outputRawFormat: json\n              outputParameters:\n                - name: result\n        \
  \          type: object\n                  value: \"$.\"\n            - name: extractText\n              method: GET\n              description: \"Extract text from PDF\"\n              outputRawFormat: json\n              outputParameters:\n                - name: result\n                  type: object\n                  value: \"$.\"\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: pdfbox-api\n      description: \"Unified REST API for PDF document processing.\"\n      resources:\n        - path: /v1/documents\n          name: documents\n          operations:\n            - method: POST\n              name: create-document\n              description: \"Create PDF document\"\n              call: \"pdfbox.createDocument\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/documents/{documentId}/text\n          name: text-extraction\n          operations:\n            - method: GET\n              name:\
  \ extract-text\n              description: \"Extract text from PDF\"\n              call: \"pdfbox.extractText\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n    - type: mcp\n      port: 9090\n      namespace: pdfbox-mcp\n      transport: http\n      description: \"MCP server for AI-assisted PDF document processing.\"\n      tools:\n        - name: create-document\n          description: \"Create a new PDF document\"\n          hints:\n            readOnly: false\n          call: \"pdfbox.createDocument\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: extract-text\n          description: \"Extract text content from a PDF document\"\n          hints:\n            readOnly: true\n          call: \"pdfbox.extractText\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-metadata\n          description: \"Get PDF document\
  \ metadata (title, author, dates)\"\n          hints:\n            readOnly: true\n          call: \"pdfbox.getMetadata\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-pages\n          description: \"List pages and their dimensions in a PDF\"\n          hints:\n            readOnly: true\n          call: \"pdfbox.listPages\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: merge-documents\n          description: \"Merge multiple PDF documents into one\"\n          hints:\n            readOnly: false\n          call: \"pdfbox.mergeDocuments\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: split-document\n          description: \"Split a PDF document at specified page boundaries\"\n          hints:\n            readOnly: false\n          call: \"pdfbox.splitDocument\"\n          outputParameters:\n            - type:\
  \ object\n              mapping: \"$.\"\n        - name: sign-document\n          description: \"Apply a digital signature to a PDF document\"\n          hints:\n            readOnly: false\n          call: \"pdfbox.signDocument\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-form-fields\n          description: \"Get interactive form fields from a PDF document\"\n          hints:\n            readOnly: true\n          call: \"pdfbox.getFormFields\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/apache-pdfbox/refs/heads/main/capabilities/pdfbox-workflow.yaml
tags:
- Apache PDFBox
- PDF
- Document Processing
- Digital Signatures
tools:
- description: Create a new PDF document
  hints:
    readOnly: false
  name: create-document
- description: Extract text content from a PDF document
  hints:
    readOnly: true
  name: extract-text
- description: Get PDF document metadata (title, author, dates)
  hints:
    readOnly: true
  name: get-metadata
- description: List pages and their dimensions in a PDF
  hints:
    readOnly: true
  name: list-pages
- description: Merge multiple PDF documents into one
  hints:
    readOnly: false
  name: merge-documents
- description: Split a PDF document at specified page boundaries
  hints:
    readOnly: false
  name: split-document
- description: Apply a digital signature to a PDF document
  hints:
    readOnly: false
  name: sign-document
- description: Get interactive form fields from a PDF document
  hints:
    readOnly: true
  name: get-form-fields
---
