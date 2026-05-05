---
categories:
- document-processing
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
- creative
- pdf
- compress pdf
- combine multiple pdfs into a single document
- pdf creation from other formats
- operation status polling
- generate a document by merging json data into a template
- adobe
- document management
- auto-tag a pdf for accessibility compliance (pdf/ua and wcag)
- ocr
- combine pdfs
- generate a document from a template and data
- document conversion
- get asset
- template-based document generation
- upload an asset for use in pdf operations
- get the status of a pdf operation
- design
- create a pdf from word, excel, powerpoint, or html
- accessibility tagging operations
- apply ocr to a scanned pdf to make text searchable
- get the status of a pdf services operation job
- pdf combination operations
- asset upload and management for pdf operations
- pdf linearization for web optimization
- upload asset
- permanently delete an uploaded asset
- auto-tag a pdf for accessibility compliance
- ocr pdf
- linearize a pdf for fast web viewing
- ocr processing operations
- get operation status
- photography
- compress a pdf to reduce its file size
- auto tag pdf
- delete asset
- export pdf
- individual asset operations
- create pdf
- apply ocr to a scanned pdf
- export a pdf to word, excel, powerpoint, rtf, or text
- pdf export to other formats
- combine multiple pdfs into one
- video
- graphics
- upload an asset for pdf operations
- get metadata and download uri for an uploaded asset
- delete an uploaded asset
- pdf compression operations
- generate document
- get asset metadata and download uri
- accessibility
- compress a pdf to reduce file size
- linearize pdf
slug: document-management
source_filename: document-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Adobe Document Management\"\n  description: \"PDF document lifecycle management workflow using Adobe PDF Services for creating, converting, combining, compressing, OCR processing, accessibility tagging, and template-based document generation. Used by document workflow teams, compliance officers, and developers building document processing pipelines.\"\n  tags:\n    - Adobe\n    - PDF\n    - Document Management\n    - Document Conversion\n    - OCR\n    - Accessibility\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      ADOBE_PDF_SERVICES_TOKEN: ADOBE_PDF_SERVICES_TOKEN\n\ncapability:\n  consumes:\n    - import: pdf-services\n      location: ./shared/pdf-services.yaml\n\n  exposes:\n    - type: rest\n      port: 8083\n      namespace: document-management-api\n      description: \"Unified REST API for PDF document lifecycle management using Adobe PDF Services.\"\n      resources:\n\
  \        - path: /v1/assets\n          name: assets\n          description: \"Asset upload and management for PDF operations\"\n          operations:\n            - method: POST\n              name: upload-asset\n              description: \"Upload an asset for PDF operations\"\n              call: \"pdf-services.upload-asset\"\n              with:\n                media_type: \"rest.media_type\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/assets/{assetID}\n          name: asset-detail\n          description: \"Individual asset operations\"\n          operations:\n            - method: GET\n              name: get-asset\n              description: \"Get asset metadata and download URI\"\n              call: \"pdf-services.get-asset\"\n              with:\n                assetID: \"rest.assetID\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n           \
  \ - method: DELETE\n              name: delete-asset\n              description: \"Delete an uploaded asset\"\n              call: \"pdf-services.delete-asset\"\n              with:\n                assetID: \"rest.assetID\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/pdfs\n          name: pdfs\n          description: \"PDF creation from other formats\"\n          operations:\n            - method: POST\n              name: create-pdf\n              description: \"Create a PDF from Word, Excel, PowerPoint, or HTML\"\n              call: \"pdf-services.create-pdf\"\n              with:\n                asset_id: \"rest.asset_id\"\n                document_language: \"rest.document_language\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/exports\n          name: exports\n          description: \"PDF export to other formats\"\n       \
  \   operations:\n            - method: POST\n              name: export-pdf\n              description: \"Export a PDF to Word, Excel, PowerPoint, RTF, or text\"\n              call: \"pdf-services.export-pdf\"\n              with:\n                asset_id: \"rest.asset_id\"\n                target_format: \"rest.target_format\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/combinations\n          name: combinations\n          description: \"PDF combination operations\"\n          operations:\n            - method: POST\n              name: combine-pdfs\n              description: \"Combine multiple PDFs into one\"\n              call: \"pdf-services.combine-pdfs\"\n              with:\n                assets: \"rest.assets\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/compressions\n          name: compressions\n          description:\
  \ \"PDF compression operations\"\n          operations:\n            - method: POST\n              name: compress-pdf\n              description: \"Compress a PDF to reduce file size\"\n              call: \"pdf-services.compress-pdf\"\n              with:\n                asset_id: \"rest.asset_id\"\n                compression_level: \"rest.compression_level\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/linearizations\n          name: linearizations\n          description: \"PDF linearization for web optimization\"\n          operations:\n            - method: POST\n              name: linearize-pdf\n              description: \"Linearize a PDF for fast web viewing\"\n              call: \"pdf-services.linearize-pdf\"\n              with:\n                asset_id: \"rest.asset_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/ocr-jobs\n\
  \          name: ocr-jobs\n          description: \"OCR processing operations\"\n          operations:\n            - method: POST\n              name: ocr-pdf\n              description: \"Apply OCR to a scanned PDF\"\n              call: \"pdf-services.ocr-pdf\"\n              with:\n                asset_id: \"rest.asset_id\"\n                ocr_lang: \"rest.ocr_lang\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/accessibility-tags\n          name: accessibility-tags\n          description: \"Accessibility tagging operations\"\n          operations:\n            - method: POST\n              name: auto-tag-pdf\n              description: \"Auto-tag a PDF for accessibility compliance\"\n              call: \"pdf-services.auto-tag-pdf\"\n              with:\n                asset_id: \"rest.asset_id\"\n                generate_report: \"rest.generate_report\"\n              outputParameters:\n             \
  \   - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/document-generations\n          name: document-generations\n          description: \"Template-based document generation\"\n          operations:\n            - method: POST\n              name: generate-document\n              description: \"Generate a document from a template and data\"\n              call: \"pdf-services.generate-document\"\n              with:\n                asset_id: \"rest.asset_id\"\n                output_format: \"rest.output_format\"\n                json_data: \"rest.json_data\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/operations/{jobId}\n          name: operations\n          description: \"Operation status polling\"\n          operations:\n            - method: GET\n              name: get-operation-status\n              description: \"Get the status of a PDF operation\"\n              call: \"pdf-services.get-operation-status\"\
  \n              with:\n                jobId: \"rest.jobId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9093\n      namespace: document-management-mcp\n      transport: http\n      description: \"MCP server for AI-assisted PDF document management using Adobe PDF Services.\"\n      tools:\n        - name: upload-asset\n          description: \"Upload an asset for use in PDF operations\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"pdf-services.upload-asset\"\n          with:\n            media_type: \"tools.media_type\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-asset\n          description: \"Get metadata and download URI for an uploaded asset\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n\
  \          call: \"pdf-services.get-asset\"\n          with:\n            assetID: \"tools.assetID\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: delete-asset\n          description: \"Permanently delete an uploaded asset\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"pdf-services.delete-asset\"\n          with:\n            assetID: \"tools.assetID\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-pdf\n          description: \"Create a PDF from Word, Excel, PowerPoint, or HTML\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"pdf-services.create-pdf\"\n          with:\n            asset_id: \"tools.asset_id\"\n            document_language: \"tools.document_language\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n\n        - name: export-pdf\n          description: \"Export a PDF to Word, Excel, PowerPoint, RTF, or text\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"pdf-services.export-pdf\"\n          with:\n            asset_id: \"tools.asset_id\"\n            target_format: \"tools.target_format\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: combine-pdfs\n          description: \"Combine multiple PDFs into a single document\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"pdf-services.combine-pdfs\"\n          with:\n            assets: \"tools.assets\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: compress-pdf\n          description: \"Compress a PDF\
  \ to reduce its file size\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"pdf-services.compress-pdf\"\n          with:\n            asset_id: \"tools.asset_id\"\n            compression_level: \"tools.compression_level\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: linearize-pdf\n          description: \"Linearize a PDF for fast web viewing\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"pdf-services.linearize-pdf\"\n          with:\n            asset_id: \"tools.asset_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: ocr-pdf\n          description: \"Apply OCR to a scanned PDF to make text searchable\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent:\
  \ false\n          call: \"pdf-services.ocr-pdf\"\n          with:\n            asset_id: \"tools.asset_id\"\n            ocr_lang: \"tools.ocr_lang\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: auto-tag-pdf\n          description: \"Auto-tag a PDF for accessibility compliance (PDF/UA and WCAG)\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"pdf-services.auto-tag-pdf\"\n          with:\n            asset_id: \"tools.asset_id\"\n            generate_report: \"tools.generate_report\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: generate-document\n          description: \"Generate a document by merging JSON data into a template\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"pdf-services.generate-document\"\
  \n          with:\n            asset_id: \"tools.asset_id\"\n            output_format: \"tools.output_format\"\n            json_data: \"tools.json_data\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-operation-status\n          description: \"Get the status of a PDF Services operation job\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"pdf-services.get-operation-status\"\n          with:\n            jobId: \"tools.jobId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/adobe-creative-suite/refs/heads/main/capabilities/document-management.yaml
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
