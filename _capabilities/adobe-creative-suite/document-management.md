---
consumed_apis:
- pdf-services
description: PDF document lifecycle management workflow using Adobe PDF Services for creating, converting, combining, compressing, OCR processing, accessibility tagging, and template-based document generation. Used by document workflow teams, compliance officers, and developers building document processing pipelines.
layout: capability
name: Adobe Document Management
operations:
- description: Upload an asset for PDF operations
  method: POST
  name: upload-asset
  path: /v1/assets
- description: Get asset metadata and download URI
  method: GET
  name: get-asset
  path: /v1/assets/{assetID}
- description: Delete an uploaded asset
  method: DELETE
  name: delete-asset
  path: /v1/assets/{assetID}
- description: Create a PDF from Word, Excel, PowerPoint, or HTML
  method: POST
  name: create-pdf
  path: /v1/pdfs
- description: Export a PDF to Word, Excel, PowerPoint, RTF, or text
  method: POST
  name: export-pdf
  path: /v1/exports
- description: Combine multiple PDFs into one
  method: POST
  name: combine-pdfs
  path: /v1/combinations
- description: Compress a PDF to reduce file size
  method: POST
  name: compress-pdf
  path: /v1/compressions
- description: Linearize a PDF for fast web viewing
  method: POST
  name: linearize-pdf
  path: /v1/linearizations
- description: Apply OCR to a scanned PDF
  method: POST
  name: ocr-pdf
  path: /v1/ocr-jobs
- description: Auto-tag a PDF for accessibility compliance
  method: POST
  name: auto-tag-pdf
  path: /v1/accessibility-tags
- description: Generate a document from a template and data
  method: POST
  name: generate-document
  path: /v1/document-generations
- description: Get the status of a PDF operation
  method: GET
  name: get-operation-status
  path: /v1/operations/{jobId}
personas: []
provider_name: Adobe Creative Suite
provider_slug: adobe-creative-suite
search_terms:
- generate a document by merging json data into a template
- ocr
- asset upload and management for pdf operations
- upload an asset for pdf operations
- pdf
- accessibility tagging operations
- export a pdf to word, excel, powerpoint, rtf, or text
- generate a document from a template and data
- combine multiple pdfs into a single document
- auto-tag a pdf for accessibility compliance (pdf/ua and wcag)
- delete asset
- ocr pdf
- creative
- photography
- upload asset
- permanently delete an uploaded asset
- template-based document generation
- auto tag pdf
- create pdf
- accessibility
- pdf linearization for web optimization
- design
- pdf export to other formats
- pdf creation from other formats
- individual asset operations
- apply ocr to a scanned pdf to make text searchable
- auto-tag a pdf for accessibility compliance
- create a pdf from word, excel, powerpoint, or html
- get asset
- get asset metadata and download uri
- compress a pdf to reduce file size
- document management
- video
- linearize a pdf for fast web viewing
- get metadata and download uri for an uploaded asset
- adobe
- combine multiple pdfs into one
- generate document
- operation status polling
- export pdf
- pdf compression operations
- apply ocr to a scanned pdf
- compress pdf
- document conversion
- combine pdfs
- get operation status
- pdf combination operations
- graphics
- compress a pdf to reduce its file size
- linearize pdf
- ocr processing operations
- upload an asset for use in pdf operations
- get the status of a pdf services operation job
- delete an uploaded asset
- get the status of a pdf operation
slug: document-management
tags:
- Adobe
- PDF
- Document Management
- Document Conversion
- OCR
- Accessibility
tools:
- description: Upload an asset for use in PDF operations
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: upload-asset
- description: Get metadata and download URI for an uploaded asset
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-asset
- description: Permanently delete an uploaded asset
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-asset
- description: Create a PDF from Word, Excel, PowerPoint, or HTML
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-pdf
- description: Export a PDF to Word, Excel, PowerPoint, RTF, or text
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: export-pdf
- description: Combine multiple PDFs into a single document
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: combine-pdfs
- description: Compress a PDF to reduce its file size
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: compress-pdf
- description: Linearize a PDF for fast web viewing
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: linearize-pdf
- description: Apply OCR to a scanned PDF to make text searchable
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: ocr-pdf
- description: Auto-tag a PDF for accessibility compliance (PDF/UA and WCAG)
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: auto-tag-pdf
- description: Generate a document by merging JSON data into a template
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: generate-document
- description: Get the status of a PDF Services operation job
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-operation-status
---
