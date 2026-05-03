---
categories:
- document-processing
consumed_apis:
- pdf-services
description: Process PDF documents at scale including creation, conversion, extraction, manipulation, and accessibility tagging. Used by document automation engineers and content teams.
layout: capability
name: Adobe Document Processing
operations:
- description: Upload a document for processing
  method: POST
  name: upload-asset
  path: /v1/assets
- description: Get asset download URI
  method: GET
  name: get-asset
  path: /v1/assets
- description: Delete an asset
  method: DELETE
  name: delete-asset
  path: /v1/assets
- description: Create PDF from supported formats
  method: POST
  name: create-pdf
  path: /v1/convert
- description: Export PDF to other formats
  method: POST
  name: export-pdf
  path: /v1/export
- description: Extract structured content from PDF
  method: POST
  name: extract-pdf
  path: /v1/extract
- description: Get job status
  method: GET
  name: get-job-status
  path: /v1/jobs/{jobId}
personas: []
provider_name: Adobe
provider_slug: adobe
search_terms:
- create pdf from supported formats
- extract pdf
- split pdf
- reorder pages
- upload and manage document assets
- generate documents from templates with dynamic data
- work management
- linearize pdf
- pdf
- automation
- generative ai
- extract text, tables, and figures from a pdf
- delete pages
- reorder pages within a pdf
- rotate pages in a pdf
- remove password protection from a pdf
- insert pages from one pdf into another
- delete an uploaded asset
- export pdf to docx, pptx, xlsx, or images
- protect pdf
- get asset
- digital asset management
- e-commerce
- apply ocr to make scanned pdfs searchable
- pdf content extraction
- extract structured content from pdf
- e-signatures
- auto-tag pdf for accessibility compliance
- check the status of an asynchronous pdf operation
- delete an asset
- get job status
- optimize pdf for fast web viewing
- get pdf properties
- get pdf metadata and document properties
- upload a document for processing
- compress a pdf to reduce file size
- adobe
- pdf conversion operations
- delete specific pages from a pdf
- replace pages in a pdf with pages from another
- marketing
- ocr pdf
- generate document
- combine multiple pdfs into a single document
- compress pdf
- analytics
- pdf export operations
- combine pdf
- remove protection
- create pdf
- replace pages
- add password protection to a pdf
- create a pdf from supported file formats
- experience cloud
- document services
- delete asset
- auto tag pdf
- creative cloud
- upload asset
- insert pages
- export pdf
- rotate pages
- job status
- get asset download uri
- documents
- split a pdf into multiple documents
- export pdf to other formats
slug: document-processing
source_filename: document-processing.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Adobe Document Processing\"\n  description: \"Process PDF documents at scale including creation, conversion, extraction, manipulation, and accessibility tagging. Used by document automation engineers and content teams.\"\n  tags:\n    - Adobe\n    - Documents\n    - PDF\n    - Automation\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      ADOBE_CLIENT_ID: ADOBE_CLIENT_ID\n      ADOBE_CLIENT_SECRET: ADOBE_CLIENT_SECRET\n\ncapability:\n  consumes:\n    - import: pdf-services\n      location: ./shared/pdf-services.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: adobe-document-api\n      description: \"Unified REST API for Adobe document processing workflows.\"\n      resources:\n        - path: /v1/assets\n          name: assets\n          description: \"Upload and manage document assets\"\n          operations:\n            - method: POST\n              name:\
  \ upload-asset\n              description: \"Upload a document for processing\"\n              call: \"pdf-services.upload-asset\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: GET\n              name: get-asset\n              description: \"Get asset download URI\"\n              call: \"pdf-services.get-asset\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-asset\n              description: \"Delete an asset\"\n              call: \"pdf-services.delete-asset\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/convert\n          name: conversion\n          description: \"PDF conversion operations\"\n          operations:\n            - method: POST\n              name: create-pdf\n              description: \"Create PDF from supported\
  \ formats\"\n              call: \"pdf-services.create-pdf\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/export\n          name: export\n          description: \"PDF export operations\"\n          operations:\n            - method: POST\n              name: export-pdf\n              description: \"Export PDF to other formats\"\n              call: \"pdf-services.export-pdf\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/extract\n          name: extraction\n          description: \"PDF content extraction\"\n          operations:\n            - method: POST\n              name: extract-pdf\n              description: \"Extract structured content from PDF\"\n              call: \"pdf-services.extract-pdf\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/jobs/{jobId}\n\
  \          name: jobs\n          description: \"Job status\"\n          operations:\n            - method: GET\n              name: get-job-status\n              description: \"Get job status\"\n              call: \"pdf-services.get-job-status\"\n              with:\n                jobId: \"rest.jobId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: adobe-document-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Adobe document processing.\"\n      tools:\n        - name: upload-asset\n          description: \"Upload a document for processing\"\n          hints:\n            readOnly: false\n          call: \"pdf-services.upload-asset\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-asset\n          description: \"Get asset download URI\"\n          hints:\n            readOnly: true\n     \
  \     call: \"pdf-services.get-asset\"\n          with:\n            assetId: \"tools.assetId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-asset\n          description: \"Delete an uploaded asset\"\n          hints:\n            destructive: true\n            idempotent: true\n          call: \"pdf-services.delete-asset\"\n          with:\n            assetId: \"tools.assetId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-pdf\n          description: \"Create a PDF from supported file formats\"\n          hints:\n            readOnly: false\n          call: \"pdf-services.create-pdf\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: export-pdf\n          description: \"Export PDF to DOCX, PPTX, XLSX, or images\"\n          hints:\n            readOnly: false\n          call: \"pdf-services.export-pdf\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: combine-pdf\n          description: \"Combine multiple PDFs into a single document\"\n          hints:\n            readOnly: false\n          call: \"pdf-services.combine-pdf\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: split-pdf\n          description: \"Split a PDF into multiple documents\"\n          hints:\n            readOnly: false\n          call: \"pdf-services.split-pdf\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: ocr-pdf\n          description: \"Apply OCR to make scanned PDFs searchable\"\n          hints:\n            readOnly: false\n          call: \"pdf-services.ocr-pdf\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: compress-pdf\n          description: \"Compress a PDF to reduce file\
  \ size\"\n          hints:\n            readOnly: false\n          call: \"pdf-services.compress-pdf\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: protect-pdf\n          description: \"Add password protection to a PDF\"\n          hints:\n            readOnly: false\n          call: \"pdf-services.protect-pdf\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: remove-protection\n          description: \"Remove password protection from a PDF\"\n          hints:\n            readOnly: false\n          call: \"pdf-services.remove-protection\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: linearize-pdf\n          description: \"Optimize PDF for fast web viewing\"\n          hints:\n            readOnly: false\n          call: \"pdf-services.linearize-pdf\"\n          outputParameters:\n            - type: object\n   \
  \           mapping: \"$.\"\n        - name: extract-pdf\n          description: \"Extract text, tables, and figures from a PDF\"\n          hints:\n            readOnly: true\n          call: \"pdf-services.extract-pdf\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: auto-tag-pdf\n          description: \"Auto-tag PDF for accessibility compliance\"\n          hints:\n            readOnly: false\n          call: \"pdf-services.auto-tag-pdf\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: generate-document\n          description: \"Generate documents from templates with dynamic data\"\n          hints:\n            readOnly: false\n          call: \"pdf-services.generate-document\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-pdf-properties\n          description: \"Get PDF metadata and document properties\"\n\
  \          hints:\n            readOnly: true\n          call: \"pdf-services.get-pdf-properties\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: reorder-pages\n          description: \"Reorder pages within a PDF\"\n          hints:\n            readOnly: false\n          call: \"pdf-services.reorder-pages\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-pages\n          description: \"Delete specific pages from a PDF\"\n          hints:\n            readOnly: false\n          call: \"pdf-services.delete-pages\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: rotate-pages\n          description: \"Rotate pages in a PDF\"\n          hints:\n            readOnly: false\n          call: \"pdf-services.rotate-pages\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n       \
  \ - name: insert-pages\n          description: \"Insert pages from one PDF into another\"\n          hints:\n            readOnly: false\n          call: \"pdf-services.insert-pages\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: replace-pages\n          description: \"Replace pages in a PDF with pages from another\"\n          hints:\n            readOnly: false\n          call: \"pdf-services.replace-pages\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-job-status\n          description: \"Check the status of an asynchronous PDF operation\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"pdf-services.get-job-status\"\n          with:\n            jobId: \"tools.jobId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/adobe/refs/heads/main/capabilities/document-processing.yaml
tags:
- Adobe
- Documents
- PDF
- Automation
tools:
- description: Upload a document for processing
  hints:
    readOnly: false
  name: upload-asset
- description: Get asset download URI
  hints:
    readOnly: true
  name: get-asset
- description: Delete an uploaded asset
  hints:
    destructive: true
    idempotent: true
  name: delete-asset
- description: Create a PDF from supported file formats
  hints:
    readOnly: false
  name: create-pdf
- description: Export PDF to DOCX, PPTX, XLSX, or images
  hints:
    readOnly: false
  name: export-pdf
- description: Combine multiple PDFs into a single document
  hints:
    readOnly: false
  name: combine-pdf
- description: Split a PDF into multiple documents
  hints:
    readOnly: false
  name: split-pdf
- description: Apply OCR to make scanned PDFs searchable
  hints:
    readOnly: false
  name: ocr-pdf
- description: Compress a PDF to reduce file size
  hints:
    readOnly: false
  name: compress-pdf
- description: Add password protection to a PDF
  hints:
    readOnly: false
  name: protect-pdf
- description: Remove password protection from a PDF
  hints:
    readOnly: false
  name: remove-protection
- description: Optimize PDF for fast web viewing
  hints:
    readOnly: false
  name: linearize-pdf
- description: Extract text, tables, and figures from a PDF
  hints:
    readOnly: true
  name: extract-pdf
- description: Auto-tag PDF for accessibility compliance
  hints:
    readOnly: false
  name: auto-tag-pdf
- description: Generate documents from templates with dynamic data
  hints:
    readOnly: false
  name: generate-document
- description: Get PDF metadata and document properties
  hints:
    readOnly: true
  name: get-pdf-properties
- description: Reorder pages within a PDF
  hints:
    readOnly: false
  name: reorder-pages
- description: Delete specific pages from a PDF
  hints:
    readOnly: false
  name: delete-pages
- description: Rotate pages in a PDF
  hints:
    readOnly: false
  name: rotate-pages
- description: Insert pages from one PDF into another
  hints:
    readOnly: false
  name: insert-pages
- description: Replace pages in a PDF with pages from another
  hints:
    readOnly: false
  name: replace-pages
- description: Check the status of an asynchronous PDF operation
  hints:
    idempotent: true
    readOnly: true
  name: get-job-status
---
