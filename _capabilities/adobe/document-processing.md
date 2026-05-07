---
categories:
- document-processing
consumed_apis: []
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
- export pdf to other formats
- combine multiple pdfs into a single document
- get pdf metadata and document properties
- analytics
- upload a document for processing
- export pdf to docx, pptx, xlsx, or images
- work management
- automation
- extract text, tables, and figures from a pdf
- delete pages
- delete an uploaded asset
- pdf conversion operations
- upload and manage document assets
- experience cloud
- rotate pages
- auto tag pdf
- e-signatures
- auto-tag pdf for accessibility compliance
- document services
- replace pages in a pdf with pages from another
- ocr pdf
- optimize pdf for fast web viewing
- extract structured content from pdf
- generate documents from templates with dynamic data
- add password protection to a pdf
- split pdf
- digital asset management
- compress a pdf to reduce file size
- export pdf
- compress pdf
- split a pdf into multiple documents
- remove password protection from a pdf
- e-commerce
- delete asset
- documents
- generate document
- insert pages from one pdf into another
- upload asset
- linearize pdf
- generative ai
- delete an asset
- get asset download uri
- get job status
- apply ocr to make scanned pdfs searchable
- reorder pages within a pdf
- delete specific pages from a pdf
- rotate pages in a pdf
- check the status of an asynchronous pdf operation
- pdf content extraction
- pdf
- combine pdf
- job status
- remove protection
- reorder pages
- marketing
- get pdf properties
- get asset
- create pdf
- adobe
- insert pages
- pdf export operations
- creative cloud
- protect pdf
- extract pdf
- replace pages
- create a pdf from supported file formats
slug: document-processing
source_filename: document-processing.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Adobe Document Processing\n  description: Process PDF documents at scale including creation, conversion, extraction, manipulation, and accessibility\n    tagging. Used by document automation engineers and content teams.\n  tags:\n  - Adobe\n  - Documents\n  - PDF\n  - Automation\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    ADOBE_CLIENT_ID: ADOBE_CLIENT_ID\n    ADOBE_CLIENT_SECRET: ADOBE_CLIENT_SECRET\ncapability:\n  consumes:\n  - type: http\n    namespace: pdf-services\n    baseUri: https://pdf-services.adobe.io\n    description: Adobe PDF Services API\n    authentication:\n      type: bearer\n      token: '{{ADOBE_CLIENT_SECRET}}'\n    resources:\n    - name: assets\n      path: /assets\n      description: Manage document assets\n      operations:\n      - name: upload-asset\n        method: POST\n        description: Upload a document for processing\n        outputRawFormat: json\n     \
  \   outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            mediaType: '{{tools.mediaType}}'\n      - name: get-asset\n        method: GET\n        description: Get asset download URI\n        inputParameters:\n        - name: assetId\n          in: path\n          type: string\n          required: true\n          description: The asset ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-asset\n        method: DELETE\n        description: Delete an asset\n        inputParameters:\n        - name: assetId\n          in: path\n          type: string\n          required: true\n          description: The asset ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: pdf-operations\n      path: /operation\n    \
  \  description: PDF document operations\n      operations:\n      - name: create-pdf\n        method: POST\n        description: Create a PDF from supported formats\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: export-pdf\n        method: POST\n        description: Export PDF to other formats\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: combine-pdf\n        method: POST\n        description: Combine multiple PDFs into one\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: split-pdf\n        method: POST\n        description: Split a PDF into multiple documents\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: ocr-pdf\n\
  \        method: POST\n        description: Apply OCR to make scanned PDFs searchable\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: compress-pdf\n        method: POST\n        description: Compress a PDF to reduce file size\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: protect-pdf\n        method: POST\n        description: Add password protection to a PDF\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: remove-protection\n        method: POST\n        description: Remove password protection from a PDF\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: linearize-pdf\n        method: POST\n        description: Optimize\
  \ PDF for fast web viewing\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: extract-pdf\n        method: POST\n        description: Extract text, tables, and figures from a PDF\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: auto-tag-pdf\n        method: POST\n        description: Auto-tag PDF for accessibility\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: generate-document\n        method: POST\n        description: Generate documents from templates with data\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-pdf-properties\n        method: POST\n        description: Get PDF metadata and properties\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: reorder-pages\n        method: POST\n        description: Reorder pages in a PDF\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-pages\n        method: POST\n        description: Delete pages from a PDF\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: rotate-pages\n        method: POST\n        description: Rotate pages in a PDF\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: insert-pages\n        method: POST\n        description: Insert pages from one PDF into another\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n      - name: replace-pages\n        method: POST\n        description: Replace pages in a PDF\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: jobs\n      path: /operation\n      description: Job status polling\n      operations:\n      - name: get-job-status\n        method: GET\n        description: Get the status of an asynchronous job\n        inputParameters:\n        - name: jobId\n          in: path\n          type: string\n          required: true\n          description: The job ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: adobe-document-api\n    description: Unified REST API for Adobe document processing workflows.\n    resources:\n    - path: /v1/assets\n      name: assets\n      description: Upload and manage document assets\n      operations:\n\
  \      - method: POST\n        name: upload-asset\n        description: Upload a document for processing\n        call: pdf-services.upload-asset\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: get-asset\n        description: Get asset download URI\n        call: pdf-services.get-asset\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-asset\n        description: Delete an asset\n        call: pdf-services.delete-asset\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/convert\n      name: conversion\n      description: PDF conversion operations\n      operations:\n      - method: POST\n        name: create-pdf\n        description: Create PDF from supported formats\n        call: pdf-services.create-pdf\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/export\n      name: export\n\
  \      description: PDF export operations\n      operations:\n      - method: POST\n        name: export-pdf\n        description: Export PDF to other formats\n        call: pdf-services.export-pdf\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/extract\n      name: extraction\n      description: PDF content extraction\n      operations:\n      - method: POST\n        name: extract-pdf\n        description: Extract structured content from PDF\n        call: pdf-services.extract-pdf\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/jobs/{jobId}\n      name: jobs\n      description: Job status\n      operations:\n      - method: GET\n        name: get-job-status\n        description: Get job status\n        call: pdf-services.get-job-status\n        with:\n          jobId: rest.jobId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: adobe-document-mcp\n\
  \    transport: http\n    description: MCP server for AI-assisted Adobe document processing.\n    tools:\n    - name: upload-asset\n      description: Upload a document for processing\n      hints:\n        readOnly: false\n      call: pdf-services.upload-asset\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-asset\n      description: Get asset download URI\n      hints:\n        readOnly: true\n      call: pdf-services.get-asset\n      with:\n        assetId: tools.assetId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-asset\n      description: Delete an uploaded asset\n      hints:\n        destructive: true\n        idempotent: true\n      call: pdf-services.delete-asset\n      with:\n        assetId: tools.assetId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-pdf\n      description: Create a PDF from supported file formats\n      hints:\n        readOnly: false\n \
  \     call: pdf-services.create-pdf\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: export-pdf\n      description: Export PDF to DOCX, PPTX, XLSX, or images\n      hints:\n        readOnly: false\n      call: pdf-services.export-pdf\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: combine-pdf\n      description: Combine multiple PDFs into a single document\n      hints:\n        readOnly: false\n      call: pdf-services.combine-pdf\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: split-pdf\n      description: Split a PDF into multiple documents\n      hints:\n        readOnly: false\n      call: pdf-services.split-pdf\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: ocr-pdf\n      description: Apply OCR to make scanned PDFs searchable\n      hints:\n        readOnly: false\n      call: pdf-services.ocr-pdf\n      outputParameters:\n      - type: object\n    \
  \    mapping: $.\n    - name: compress-pdf\n      description: Compress a PDF to reduce file size\n      hints:\n        readOnly: false\n      call: pdf-services.compress-pdf\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: protect-pdf\n      description: Add password protection to a PDF\n      hints:\n        readOnly: false\n      call: pdf-services.protect-pdf\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: remove-protection\n      description: Remove password protection from a PDF\n      hints:\n        readOnly: false\n      call: pdf-services.remove-protection\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: linearize-pdf\n      description: Optimize PDF for fast web viewing\n      hints:\n        readOnly: false\n      call: pdf-services.linearize-pdf\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: extract-pdf\n      description: Extract text, tables,\
  \ and figures from a PDF\n      hints:\n        readOnly: true\n      call: pdf-services.extract-pdf\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: auto-tag-pdf\n      description: Auto-tag PDF for accessibility compliance\n      hints:\n        readOnly: false\n      call: pdf-services.auto-tag-pdf\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: generate-document\n      description: Generate documents from templates with dynamic data\n      hints:\n        readOnly: false\n      call: pdf-services.generate-document\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-pdf-properties\n      description: Get PDF metadata and document properties\n      hints:\n        readOnly: true\n      call: pdf-services.get-pdf-properties\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: reorder-pages\n      description: Reorder pages within a PDF\n      hints:\n        readOnly:\
  \ false\n      call: pdf-services.reorder-pages\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-pages\n      description: Delete specific pages from a PDF\n      hints:\n        readOnly: false\n      call: pdf-services.delete-pages\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: rotate-pages\n      description: Rotate pages in a PDF\n      hints:\n        readOnly: false\n      call: pdf-services.rotate-pages\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: insert-pages\n      description: Insert pages from one PDF into another\n      hints:\n        readOnly: false\n      call: pdf-services.insert-pages\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: replace-pages\n      description: Replace pages in a PDF with pages from another\n      hints:\n        readOnly: false\n      call: pdf-services.replace-pages\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n    - name: get-job-status\n      description: Check the status of an asynchronous PDF operation\n      hints:\n        readOnly: true\n        idempotent: true\n      call: pdf-services.get-job-status\n      with:\n        jobId: tools.jobId\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
