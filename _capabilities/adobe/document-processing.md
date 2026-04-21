---
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
- get pdf metadata and document properties
- extract structured content from pdf
- replace pages
- extract pdf
- remove protection
- rotate pages
- rotate pages in a pdf
- delete an uploaded asset
- remove password protection from a pdf
- reorder pages within a pdf
- digital asset management
- compress a pdf to reduce file size
- create pdf
- e-signatures
- check the status of an asynchronous pdf operation
- extract text, tables, and figures from a pdf
- optimize pdf for fast web viewing
- experience cloud
- automation
- replace pages in a pdf with pages from another
- document services
- pdf export operations
- export pdf to docx, pptx, xlsx, or images
- get pdf properties
- pdf
- pdf conversion operations
- export pdf to other formats
- delete pages
- adobe
- protect pdf
- split a pdf into multiple documents
- creative cloud
- generate documents from templates with dynamic data
- generative ai
- marketing
- split pdf
- pdf content extraction
- get job status
- apply ocr to make scanned pdfs searchable
- ocr pdf
- reorder pages
- auto tag pdf
- auto-tag pdf for accessibility compliance
- get asset download uri
- documents
- insert pages from one pdf into another
- delete asset
- combine multiple pdfs into a single document
- compress pdf
- add password protection to a pdf
- e-commerce
- generate document
- export pdf
- upload asset
- get asset
- combine pdf
- work management
- create pdf from supported formats
- delete an asset
- linearize pdf
- analytics
- delete specific pages from a pdf
- job status
- upload and manage document assets
- create a pdf from supported file formats
- upload a document for processing
- insert pages
slug: document-processing
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
