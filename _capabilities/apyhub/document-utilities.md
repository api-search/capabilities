---
categories:
- document-processing
consumed_apis:
- apyhub
description: Workflow capability for document processing utilities using ApyHub. Supports developers and content teams generating PDFs, converting documents, extracting text, and processing data without building custom infrastructure.
layout: capability
name: ApyHub Document Utilities
operations: []
personas: []
provider_name: ApyHub
provider_slug: apyhub
search_terms:
- integrates apyhub document utilities into web and mobile applications
- generating pdfs from html templates with dynamic data
- get exchange rate
- pdf generation
- extracting structured data from documents like pdfs
- gets the current exchange rate and converts a currency amount
- document processing
- generate invoice pdf
- uses apyhub to generate pdfs and process documents at scale
- convert, generate, and extract data from documents using apyhub
- generates a pdf invoice from an html template with dynamic order data
- extract document text
- developer utilities
- utility apis
- api platform
- apyhub
- document conversion
- convert webpage to pdf
- data processing
- extracts text content from a pdf document for processing
- converting documents between formats (html to pdf, word to pdf)
- data extraction
- converts a webpage or html document to pdf format
slug: document-utilities
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: ApyHub Document Utilities\n  description: >-\n    Workflow capability for document processing utilities using ApyHub. Supports\n    developers and content teams generating PDFs, converting documents, extracting\n    text, and processing data without building custom infrastructure.\n  tags:\n    - ApyHub\n    - Document Processing\n    - PDF Generation\n    - Data Extraction\n    - Developer Utilities\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      APYHUB_API_KEY: APYHUB_API_KEY\n\ncapability:\n  consumes:\n    - import: apyhub\n      location: ./shared/apyhub-api.yaml\n\n  exposes:\n    - type: mcp\n      port: 9090\n      namespace: document-utils-mcp\n      transport: http\n      description: MCP server for AI-assisted document processing with ApyHub utilities.\n      tools:\n        - name: generate-invoice-pdf\n          description: Generates a PDF invoice from an HTML template\
  \ with dynamic order data\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"apyhub.generate-pdf\"\n          with:\n            templateUrl: \"tools.templateUrl\"\n            data: \"tools.data\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: convert-webpage-to-pdf\n          description: Converts a webpage or HTML document to PDF format\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"apyhub.convert-html-to-pdf\"\n          with:\n            url: \"tools.url\"\n            filename: \"tools.filename\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: extract-document-text\n          description: Extracts text content from a PDF document for processing\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"apyhub.extract-text-from-pdf\"\
  \n          with:\n            url: \"tools.url\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-exchange-rate\n          description: Gets the current exchange rate and converts a currency amount\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"apyhub.convert-currency\"\n          with:\n            amount: \"tools.amount\"\n            source: \"tools.source\"\n            target: \"tools.target\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/apyhub/refs/heads/main/capabilities/document-utilities.yaml
tags:
- ApyHub
- Document Processing
- PDF Generation
- Data Extraction
- Developer Utilities
tools:
- description: Generates a PDF invoice from an HTML template with dynamic order data
  hints:
    destructive: false
    readOnly: false
  name: generate-invoice-pdf
- description: Converts a webpage or HTML document to PDF format
  hints:
    destructive: false
    readOnly: false
  name: convert-webpage-to-pdf
- description: Extracts text content from a PDF document for processing
  hints:
    idempotent: true
    readOnly: false
  name: extract-document-text
- description: Gets the current exchange rate and converts a currency amount
  hints:
    idempotent: true
    readOnly: false
  name: get-exchange-rate
---
