---
categories:
- document-processing
consumed_apis: []
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
- pdf creation from other formats
- combine multiple pdfs into a single document
- get asset metadata and download uri
- video
- accessibility tagging operations
- document management
- asset upload and management for pdf operations
- delete an uploaded asset
- document conversion
- linearize a pdf for fast web viewing
- combine multiple pdfs into one
- generate a document by merging json data into a template
- pdf export to other formats
- auto tag pdf
- pdf compression operations
- ocr
- get operation status
- photography
- ocr pdf
- apply ocr to a scanned pdf to make text searchable
- get metadata and download uri for an uploaded asset
- design
- graphics
- creative
- individual asset operations
- compress a pdf to reduce file size
- pdf linearization for web optimization
- export pdf
- pdf combination operations
- compress pdf
- auto-tag a pdf for accessibility compliance
- operation status polling
- get the status of a pdf operation
- auto-tag a pdf for accessibility compliance (pdf/ua and wcag)
- accessibility
- generate document
- export a pdf to word, excel, powerpoint, rtf, or text
- upload asset
- linearize pdf
- template-based document generation
- combine pdfs
- upload an asset for pdf operations
- ocr processing operations
- upload an asset for use in pdf operations
- permanently delete an uploaded asset
- pdf
- generate a document from a template and data
- get asset
- create pdf
- apply ocr to a scanned pdf
- get the status of a pdf services operation job
- adobe
- compress a pdf to reduce its file size
- delete asset
- create a pdf from word, excel, powerpoint, or html
slug: document-management
source_filename: document-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Adobe Document Management\n  description: PDF document lifecycle management workflow using Adobe PDF Services for creating, converting, combining, compressing,\n    OCR processing, accessibility tagging, and template-based document generation. Used by document workflow teams, compliance\n    officers, and developers building document processing pipelines.\n  tags:\n  - Adobe\n  - PDF\n  - Document Management\n  - Document Conversion\n  - OCR\n  - Accessibility\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    ADOBE_PDF_SERVICES_TOKEN: ADOBE_PDF_SERVICES_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: pdf-services\n    baseUri: https://pdf-services.adobe.io\n    description: Adobe PDF Services API for PDF document operations\n    authentication:\n      type: bearer\n      token: '{{ADOBE_PDF_SERVICES_TOKEN}}'\n    resources:\n    - name: assets\n      path: /assets\n      description:\
  \ Upload and manage input/output assets for PDF operations\n      operations:\n      - name: upload-asset\n        method: POST\n        description: Initiates an asset upload by returning a pre-signed upload URI and an asset ID\n        body:\n          type: json\n          data:\n            mediaType: '{{tools.media_type}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-asset\n        method: GET\n        path: /{assetID}\n        description: Retrieves metadata and a temporary download URI for a previously uploaded asset\n        inputParameters:\n        - name: assetID\n          in: path\n          type: string\n          required: true\n          description: Unique identifier of the asset to retrieve\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-asset\n        method: DELETE\n\
  \        path: /{assetID}\n        description: Permanently deletes an uploaded asset\n        inputParameters:\n        - name: assetID\n          in: path\n          type: string\n          required: true\n          description: Unique identifier of the asset to delete\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: pdf-creation\n      path: /operation\n      description: Create PDF documents from other formats\n      operations:\n      - name: create-pdf\n        method: POST\n        path: /createpdf\n        description: Creates a PDF document from a source file in formats such as Word, Excel, PowerPoint, or HTML\n        body:\n          type: json\n          data:\n            assetID: '{{tools.asset_id}}'\n            documentLanguage: '{{tools.document_language}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n    - name: pdf-export\n      path: /operation\n      description: Export PDF documents to other formats\n      operations:\n      - name: export-pdf\n        method: POST\n        path: /exportpdf\n        description: Exports a PDF document to Word, Excel, PowerPoint, RTF, or plain text\n        body:\n          type: json\n          data:\n            assetID: '{{tools.asset_id}}'\n            targetFormat: '{{tools.target_format}}'\n            exportOCRLocale: '{{tools.export_ocr_locale}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: pdf-combine\n      path: /operation\n      description: Combine multiple PDFs into one\n      operations:\n      - name: combine-pdfs\n        method: POST\n        path: /combinepdf\n        description: Combines two or more PDF documents into a single output PDF\n        body:\n          type: json\n          data:\n            assets: '{{tools.assets}}'\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: pdf-compress\n      path: /operation\n      description: Reduce PDF file size\n      operations:\n      - name: compress-pdf\n        method: POST\n        path: /compressPDF\n        description: Reduces the file size of a PDF document by applying compression\n        body:\n          type: json\n          data:\n            assetID: '{{tools.asset_id}}'\n            compressionLevel: '{{tools.compression_level}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: pdf-linearize\n      path: /operation\n      description: Optimize PDFs for fast web viewing\n      operations:\n      - name: linearize-pdf\n        method: POST\n        path: /linearizePDF\n        description: Linearizes a PDF document for fast web view optimization\n        body:\n          type:\
  \ json\n          data:\n            assetID: '{{tools.asset_id}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: pdf-ocr\n      path: /operation\n      description: Apply optical character recognition to scanned PDFs\n      operations:\n      - name: ocr-pdf\n        method: POST\n        path: /ocr\n        description: Applies OCR to a scanned or image-based PDF making text searchable and selectable\n        body:\n          type: json\n          data:\n            assetID: '{{tools.asset_id}}'\n            ocrLang: '{{tools.ocr_lang}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: pdf-accessibility\n      path: /operation\n      description: Auto-tag PDFs for accessibility compliance\n      operations:\n      - name: auto-tag-pdf\n        method: POST\n        path: /autotagpdf\n        description:\
  \ Automatically adds accessibility tags to a PDF document for PDF/UA and WCAG compliance\n        body:\n          type: json\n          data:\n            assetID: '{{tools.asset_id}}'\n            generateReport: '{{tools.generate_report}}'\n            shiftHeadings: '{{tools.shift_headings}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: document-generation\n      path: /operation\n      description: Generate documents from templates and data\n      operations:\n      - name: generate-document\n        method: POST\n        path: /documentgeneration\n        description: Generates a PDF or Word document by merging JSON data into a Word document template\n        body:\n          type: json\n          data:\n            assetID: '{{tools.asset_id}}'\n            outputFormat: '{{tools.output_format}}'\n            jsonDataForMerge: '{{tools.json_data}}'\n        outputRawFormat: json\n    \
  \    outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: operations\n      path: /operation\n      description: Check operation job status\n      operations:\n      - name: get-operation-status\n        method: GET\n        path: /{jobId}\n        description: Retrieves the current status of a PDF Services operation job\n        inputParameters:\n        - name: jobId\n          in: path\n          type: string\n          required: true\n          description: Unique identifier of the operation job to check\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8083\n    namespace: document-management-api\n    description: Unified REST API for PDF document lifecycle management using Adobe PDF Services.\n    resources:\n    - path: /v1/assets\n      name: assets\n      description: Asset upload and management for PDF operations\n\
  \      operations:\n      - method: POST\n        name: upload-asset\n        description: Upload an asset for PDF operations\n        call: pdf-services.upload-asset\n        with:\n          media_type: rest.media_type\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/assets/{assetID}\n      name: asset-detail\n      description: Individual asset operations\n      operations:\n      - method: GET\n        name: get-asset\n        description: Get asset metadata and download URI\n        call: pdf-services.get-asset\n        with:\n          assetID: rest.assetID\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-asset\n        description: Delete an uploaded asset\n        call: pdf-services.delete-asset\n        with:\n          assetID: rest.assetID\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/pdfs\n      name: pdfs\n      description:\
  \ PDF creation from other formats\n      operations:\n      - method: POST\n        name: create-pdf\n        description: Create a PDF from Word, Excel, PowerPoint, or HTML\n        call: pdf-services.create-pdf\n        with:\n          asset_id: rest.asset_id\n          document_language: rest.document_language\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/exports\n      name: exports\n      description: PDF export to other formats\n      operations:\n      - method: POST\n        name: export-pdf\n        description: Export a PDF to Word, Excel, PowerPoint, RTF, or text\n        call: pdf-services.export-pdf\n        with:\n          asset_id: rest.asset_id\n          target_format: rest.target_format\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/combinations\n      name: combinations\n      description: PDF combination operations\n      operations:\n      - method: POST\n        name: combine-pdfs\n\
  \        description: Combine multiple PDFs into one\n        call: pdf-services.combine-pdfs\n        with:\n          assets: rest.assets\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/compressions\n      name: compressions\n      description: PDF compression operations\n      operations:\n      - method: POST\n        name: compress-pdf\n        description: Compress a PDF to reduce file size\n        call: pdf-services.compress-pdf\n        with:\n          asset_id: rest.asset_id\n          compression_level: rest.compression_level\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/linearizations\n      name: linearizations\n      description: PDF linearization for web optimization\n      operations:\n      - method: POST\n        name: linearize-pdf\n        description: Linearize a PDF for fast web viewing\n        call: pdf-services.linearize-pdf\n        with:\n          asset_id: rest.asset_id\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/ocr-jobs\n      name: ocr-jobs\n      description: OCR processing operations\n      operations:\n      - method: POST\n        name: ocr-pdf\n        description: Apply OCR to a scanned PDF\n        call: pdf-services.ocr-pdf\n        with:\n          asset_id: rest.asset_id\n          ocr_lang: rest.ocr_lang\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/accessibility-tags\n      name: accessibility-tags\n      description: Accessibility tagging operations\n      operations:\n      - method: POST\n        name: auto-tag-pdf\n        description: Auto-tag a PDF for accessibility compliance\n        call: pdf-services.auto-tag-pdf\n        with:\n          asset_id: rest.asset_id\n          generate_report: rest.generate_report\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/document-generations\n      name: document-generations\n\
  \      description: Template-based document generation\n      operations:\n      - method: POST\n        name: generate-document\n        description: Generate a document from a template and data\n        call: pdf-services.generate-document\n        with:\n          asset_id: rest.asset_id\n          output_format: rest.output_format\n          json_data: rest.json_data\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/operations/{jobId}\n      name: operations\n      description: Operation status polling\n      operations:\n      - method: GET\n        name: get-operation-status\n        description: Get the status of a PDF operation\n        call: pdf-services.get-operation-status\n        with:\n          jobId: rest.jobId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9093\n    namespace: document-management-mcp\n    transport: http\n    description: MCP server for AI-assisted PDF document\
  \ management using Adobe PDF Services.\n    tools:\n    - name: upload-asset\n      description: Upload an asset for use in PDF operations\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: pdf-services.upload-asset\n      with:\n        media_type: tools.media_type\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-asset\n      description: Get metadata and download URI for an uploaded asset\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: pdf-services.get-asset\n      with:\n        assetID: tools.assetID\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-asset\n      description: Permanently delete an uploaded asset\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: pdf-services.delete-asset\n      with:\n        assetID: tools.assetID\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: create-pdf\n      description: Create a PDF from Word, Excel, PowerPoint, or HTML\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: pdf-services.create-pdf\n      with:\n        asset_id: tools.asset_id\n        document_language: tools.document_language\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: export-pdf\n      description: Export a PDF to Word, Excel, PowerPoint, RTF, or text\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: pdf-services.export-pdf\n      with:\n        asset_id: tools.asset_id\n        target_format: tools.target_format\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: combine-pdfs\n      description: Combine multiple PDFs into a single document\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent:\
  \ false\n      call: pdf-services.combine-pdfs\n      with:\n        assets: tools.assets\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: compress-pdf\n      description: Compress a PDF to reduce its file size\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: pdf-services.compress-pdf\n      with:\n        asset_id: tools.asset_id\n        compression_level: tools.compression_level\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: linearize-pdf\n      description: Linearize a PDF for fast web viewing\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: pdf-services.linearize-pdf\n      with:\n        asset_id: tools.asset_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: ocr-pdf\n      description: Apply OCR to a scanned PDF to make text searchable\n      hints:\n        readOnly:\
  \ false\n        destructive: false\n        idempotent: false\n      call: pdf-services.ocr-pdf\n      with:\n        asset_id: tools.asset_id\n        ocr_lang: tools.ocr_lang\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: auto-tag-pdf\n      description: Auto-tag a PDF for accessibility compliance (PDF/UA and WCAG)\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: pdf-services.auto-tag-pdf\n      with:\n        asset_id: tools.asset_id\n        generate_report: tools.generate_report\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: generate-document\n      description: Generate a document by merging JSON data into a template\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: pdf-services.generate-document\n      with:\n        asset_id: tools.asset_id\n        output_format: tools.output_format\n        json_data:\
  \ tools.json_data\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-operation-status\n      description: Get the status of a PDF Services operation job\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: pdf-services.get-operation-status\n      with:\n        jobId: tools.jobId\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
