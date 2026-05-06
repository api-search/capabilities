---
categories:
- document-processing
consumed_apis: []
description: Workflow capability for document processing utilities using ApyHub. Supports developers and content teams generating PDFs, converting documents, extracting text, and processing data without building custom infrastructure.
layout: capability
name: ApyHub Document Utilities
operations: []
personas: []
provider_name: ApyHub
provider_slug: apyhub
search_terms:
- utility apis
- pdf generation
- convert, generate, and extract data from documents using apyhub
- converting documents between formats (html to pdf, word to pdf)
- extract document text
- document processing
- uses apyhub to generate pdfs and process documents at scale
- data extraction
- generating pdfs from html templates with dynamic data
- document conversion
- get exchange rate
- converts a webpage or html document to pdf format
- extracts text content from a pdf document for processing
- apyhub
- generate invoice pdf
- integrates apyhub document utilities into web and mobile applications
- generates a pdf invoice from an html template with dynamic order data
- extracting structured data from documents like pdfs
- convert webpage to pdf
- api platform
- gets the current exchange rate and converts a currency amount
- developer utilities
- data processing
slug: document-utilities
source_filename: document-utilities.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: ApyHub Document Utilities\n  description: Workflow capability for document processing utilities using ApyHub. Supports developers and content teams generating\n    PDFs, converting documents, extracting text, and processing data without building custom infrastructure.\n  tags:\n  - ApyHub\n  - Document Processing\n  - PDF Generation\n  - Data Extraction\n  - Developer Utilities\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    APYHUB_API_KEY: APYHUB_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: apyhub\n    baseUri: https://api.apyhub.com\n    description: ApyHub utility API platform\n    authentication:\n      type: apikey\n      header: apy-token\n      key: '{{APYHUB_API_KEY}}'\n    resources:\n    - name: convert-html-pdf\n      path: /convert/html/pdf\n      description: HTML to PDF conversion\n      operations:\n      - name: convert-html-to-pdf\n        method: POST\n \
  \       description: Converts HTML to PDF\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            url: '{{tools.url}}'\n            filename: '{{tools.filename}}'\n    - name: generate-pdf\n      path: /generate/pdf\n      description: PDF generation from templates\n      operations:\n      - name: generate-pdf\n        method: POST\n        description: Generates a PDF from a template\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            templateUrl: '{{tools.templateUrl}}'\n            data: '{{tools.data}}'\n    - name: currency-convert\n      path: /data/currency/convert\n      description: Currency conversion\n      operations:\n      - name: convert-currency\n        method: POST\n        description: Converts\
  \ currency amounts\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            amount: '{{tools.amount}}'\n            source: '{{tools.source}}'\n            target: '{{tools.target}}'\n    - name: extract-text\n      path: /extract/text/pdf\n      description: Text extraction from PDFs\n      operations:\n      - name: extract-text-from-pdf\n        method: POST\n        description: Extracts text from a PDF\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            url: '{{tools.url}}'\n  exposes:\n  - type: mcp\n    port: 9090\n    namespace: document-utils-mcp\n    transport: http\n    description: MCP server for AI-assisted document processing with ApyHub utilities.\n    tools:\n    - name: generate-invoice-pdf\n  \
  \    description: Generates a PDF invoice from an HTML template with dynamic order data\n      hints:\n        readOnly: false\n        destructive: false\n      call: apyhub.generate-pdf\n      with:\n        templateUrl: tools.templateUrl\n        data: tools.data\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: convert-webpage-to-pdf\n      description: Converts a webpage or HTML document to PDF format\n      hints:\n        readOnly: false\n        destructive: false\n      call: apyhub.convert-html-to-pdf\n      with:\n        url: tools.url\n        filename: tools.filename\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: extract-document-text\n      description: Extracts text content from a PDF document for processing\n      hints:\n        readOnly: false\n        idempotent: true\n      call: apyhub.extract-text-from-pdf\n      with:\n        url: tools.url\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: get-exchange-rate\n      description: Gets the current exchange rate and converts a currency amount\n      hints:\n        readOnly: false\n        idempotent: true\n      call: apyhub.convert-currency\n      with:\n        amount: tools.amount\n        source: tools.source\n        target: tools.target\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
