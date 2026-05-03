---
api_specs:
- filename: veryfi-ocr-openapi.yml
  format: yaml
  label: veryfi
  slug: veryfi
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/veryfi/refs/heads/main/openapi/veryfi-ocr-openapi.yml
categories: []
consumed_apis:
- veryfi
description: Unified financial document processing capability using the Veryfi OCR API. Enables accounts payable teams, tax professionals, lenders, and finance teams to extract structured data from receipts, invoices, bank statements, checks, W-2s, W-9s, and custom documents through a single REST and MCP interface. Supports 91 currencies and 38 languages.
layout: capability
name: Veryfi Financial Document Processing
operations:
- description: Process a Document
  method: POST
  name: process-document
  path: /v1/documents
- description: List All Documents
  method: GET
  name: list-documents
  path: /v1/documents
- description: Get a Document
  method: GET
  name: get-document
  path: /v1/documents/{documentId}
- description: Delete a Document
  method: DELETE
  name: delete-document
  path: /v1/documents/{documentId}
- description: Process a Bank Statement
  method: POST
  name: process-bank-statement
  path: /v1/bank-statements
- description: List All Bank Statements
  method: GET
  name: list-bank-statements
  path: /v1/bank-statements
- description: Get a Bank Statement
  method: GET
  name: get-bank-statement
  path: /v1/bank-statements/{documentId}
- description: Process a Check
  method: POST
  name: process-check
  path: /v1/checks
- description: List All Checks
  method: GET
  name: list-checks
  path: /v1/checks
- description: Process a W-2 Form
  method: POST
  name: process-w2
  path: /v1/w2s
- description: List All W-2 Forms
  method: GET
  name: list-w2s
  path: /v1/w2s
- description: Process a W-9 Form
  method: POST
  name: process-w9
  path: /v1/w9s
- description: Process Any Document
  method: POST
  name: process-any-document
  path: /v1/any-documents
- description: Classify a Document
  method: POST
  name: classify-document
  path: /v1/classify
personas: []
provider_name: Veryfi
provider_slug: veryfi
search_terms:
- process and retrieve w-2 tax forms
- single document operations
- process w2
- get details for a specific processed document by its numeric id.
- classify document
- list all previously processed receipts and invoices.
- list all w-2 forms
- accounts payable
- extract data from any document type using a named veryfi extraction blueprint. useful for contracts, custom forms, and non-standard documents.
- receipts
- checks
- list documents
- permanently delete a processed document and its extracted data.
- single bank statement operations
- process and retrieve w-9 tax forms
- delete document
- list checks
- extract structured transaction data, account information, and balances from a bank statement pdf or image url.
- process a check
- list all checks
- extract wages, tax withholdings, employer ein, and employee information from a w-2 tax form.
- list all documents
- process and retrieve bank statements
- process any document
- list bank statements
- process receipts, invoices, and bills
- get a document
- finance
- process a bank statement
- process receipt invoice
- get document
- process bank statement
- get a bank statement
- process and retrieve checks
- extract routing number, account number, check number, payee, and amount from a check image url.
- bank statements
- delete a document
- tax forms
- ocr
- process a w-2 form
- classify documents before processing
- ai
- classify a document
- process custom documents with blueprints
- process a document
- list all bank statements
- get bank statement
- process document
- list w2s
- process w9
- process check
- extract structured data from a receipt or invoice. provide a publicly accessible url to the document. returns vendor details, line items, taxes, totals, and currency in 91 currencies and 38 languages.
- list all previously processed bank statements.
- extract taxpayer name, tin, entity type, and certification details from a w-9 form.
- classify a document to determine its type before processing. optionally restrict to specific document types (receipt, invoice, bank_statement, w2, w9, check).
- veryfi
- invoices
- process a w-9 form
- document processing
slug: financial-document-processing
source_filename: financial-document-processing.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Veryfi Financial Document Processing\"\n  description: >-\n    Unified financial document processing capability using the Veryfi OCR API.\n    Enables accounts payable teams, tax professionals, lenders, and finance\n    teams to extract structured data from receipts, invoices, bank statements,\n    checks, W-2s, W-9s, and custom documents through a single REST and MCP\n    interface. Supports 91 currencies and 38 languages.\n  tags:\n    - AI\n    - Accounts Payable\n    - Bank Statements\n    - Checks\n    - Document Processing\n    - Finance\n    - Invoices\n    - OCR\n    - Receipts\n    - Tax Forms\n    - Veryfi\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      VERYFI_CLIENT_ID: VERYFI_CLIENT_ID\n      VERYFI_API_KEY: VERYFI_API_KEY\n      VERYFI_USERNAME: VERYFI_USERNAME\n\ncapability:\n  consumes:\n    - import: veryfi\n      location: ./shared/veryfi-ocr.yaml\n\n  exposes:\n\
  \    - type: rest\n      port: 8080\n      namespace: financial-document-processing-api\n      description: \"Unified REST API for AI-powered financial document data extraction.\"\n      resources:\n        - path: /v1/documents\n          name: documents\n          description: \"Process receipts, invoices, and bills\"\n          operations:\n            - method: POST\n              name: process-document\n              description: \"Process a Document\"\n              call: \"veryfi.process-document\"\n              with:\n                file_url: \"rest.file_url\"\n                tags: \"rest.tags\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n            - method: GET\n              name: list-documents\n              description: \"List All Documents\"\n              call: \"veryfi.list-documents\"\n              with:\n                created_date__gt: \"rest.created_date__gt\"\n              outputParameters:\n      \
  \          - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/documents/{documentId}\n          name: document\n          description: \"Single document operations\"\n          operations:\n            - method: GET\n              name: get-document\n              description: \"Get a Document\"\n              call: \"veryfi.get-document\"\n              with:\n                documentId: \"rest.documentId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n            - method: DELETE\n              name: delete-document\n              description: \"Delete a Document\"\n              call: \"veryfi.delete-document\"\n              with:\n                documentId: \"rest.documentId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/bank-statements\n          name: bank-statements\n          description: \"Process and retrieve bank statements\"\
  \n          operations:\n            - method: POST\n              name: process-bank-statement\n              description: \"Process a Bank Statement\"\n              call: \"veryfi.process-bank-statement\"\n              with:\n                file_url: \"rest.file_url\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n            - method: GET\n              name: list-bank-statements\n              description: \"List All Bank Statements\"\n              call: \"veryfi.list-bank-statements\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/bank-statements/{documentId}\n          name: bank-statement\n          description: \"Single bank statement operations\"\n          operations:\n            - method: GET\n              name: get-bank-statement\n              description: \"Get a Bank Statement\"\n              call: \"veryfi.get-bank-statement\"\n    \
  \          with:\n                documentId: \"rest.documentId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/checks\n          name: checks\n          description: \"Process and retrieve checks\"\n          operations:\n            - method: POST\n              name: process-check\n              description: \"Process a Check\"\n              call: \"veryfi.process-check\"\n              with:\n                file_url: \"rest.file_url\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n            - method: GET\n              name: list-checks\n              description: \"List All Checks\"\n              call: \"veryfi.list-checks\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/w2s\n          name: w2s\n          description: \"Process and retrieve W-2 tax forms\"\n          operations:\n\
  \            - method: POST\n              name: process-w2\n              description: \"Process a W-2 Form\"\n              call: \"veryfi.process-w2\"\n              with:\n                file_url: \"rest.file_url\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n            - method: GET\n              name: list-w2s\n              description: \"List All W-2 Forms\"\n              call: \"veryfi.list-w2s\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/w9s\n          name: w9s\n          description: \"Process and retrieve W-9 tax forms\"\n          operations:\n            - method: POST\n              name: process-w9\n              description: \"Process a W-9 Form\"\n              call: \"veryfi.process-w9\"\n              with:\n                file_url: \"rest.file_url\"\n              outputParameters:\n                - type: object\n        \
  \          mapping: \"$.\"\n\n        - path: /v1/any-documents\n          name: any-documents\n          description: \"Process custom documents with blueprints\"\n          operations:\n            - method: POST\n              name: process-any-document\n              description: \"Process Any Document\"\n              call: \"veryfi.process-any-document\"\n              with:\n                file_url: \"rest.file_url\"\n                blueprint_name: \"rest.blueprint_name\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/classify\n          name: classify\n          description: \"Classify documents before processing\"\n          operations:\n            - method: POST\n              name: classify-document\n              description: \"Classify a Document\"\n              call: \"veryfi.classify-document\"\n              with:\n                file_url: \"rest.file_url\"\n                document_types:\
  \ \"rest.document_types\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9080\n      namespace: financial-document-processing-mcp\n      transport: http\n      description: \"MCP server for AI-assisted financial document data extraction.\"\n      tools:\n        - name: process-receipt-invoice\n          description: >-\n            Extract structured data from a receipt or invoice. Provide a\n            publicly accessible URL to the document. Returns vendor details,\n            line items, taxes, totals, and currency in 91 currencies and 38\n            languages.\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"veryfi.process-document\"\n          with:\n            file_url: \"tools.file_url\"\n            tags: \"tools.tags\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-documents\n \
  \         description: \"List all previously processed receipts and invoices.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"veryfi.list-documents\"\n          with:\n            created_date__gt: \"tools.created_date__gt\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-document\n          description: \"Get details for a specific processed document by its numeric ID.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"veryfi.get-document\"\n          with:\n            documentId: \"tools.documentId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: delete-document\n          description: \"Permanently delete a processed document and its extracted data.\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n         \
  \ call: \"veryfi.delete-document\"\n          with:\n            documentId: \"tools.documentId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: process-bank-statement\n          description: >-\n            Extract structured transaction data, account information, and\n            balances from a bank statement PDF or image URL.\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"veryfi.process-bank-statement\"\n          with:\n            file_url: \"tools.file_url\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-bank-statements\n          description: \"List all previously processed bank statements.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"veryfi.list-bank-statements\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n  \
  \      - name: process-check\n          description: >-\n            Extract routing number, account number, check number, payee,\n            and amount from a check image URL.\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"veryfi.process-check\"\n          with:\n            file_url: \"tools.file_url\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: process-w2\n          description: >-\n            Extract wages, tax withholdings, employer EIN, and employee\n            information from a W-2 tax form.\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"veryfi.process-w2\"\n          with:\n            file_url: \"tools.file_url\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: process-w9\n          description: >-\n            Extract taxpayer name, TIN, entity type, and certification\n\
  \            details from a W-9 form.\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"veryfi.process-w9\"\n          with:\n            file_url: \"tools.file_url\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: process-any-document\n          description: >-\n            Extract data from any document type using a named Veryfi\n            extraction blueprint. Useful for contracts, custom forms, and\n            non-standard documents.\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"veryfi.process-any-document\"\n          with:\n            file_url: \"tools.file_url\"\n            blueprint_name: \"tools.blueprint_name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: classify-document\n          description: >-\n            Classify a document to determine its type before\
  \ processing.\n            Optionally restrict to specific document types (receipt, invoice,\n            bank_statement, w2, w9, check).\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"veryfi.classify-document\"\n          with:\n            file_url: \"tools.file_url\"\n            document_types: \"tools.document_types\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/veryfi/refs/heads/main/capabilities/financial-document-processing.yaml
tags:
- AI
- Accounts Payable
- Bank Statements
- Checks
- Document Processing
- Finance
- Invoices
- OCR
- Receipts
- Tax Forms
- Veryfi
tools:
- description: Extract structured data from a receipt or invoice. Provide a publicly accessible URL to the document. Returns vendor details, line items, taxes, totals, and currency in 91 currencies and 38 languages.
  hints:
    openWorld: false
    readOnly: false
  name: process-receipt-invoice
- description: List all previously processed receipts and invoices.
  hints:
    openWorld: true
    readOnly: true
  name: list-documents
- description: Get details for a specific processed document by its numeric ID.
  hints:
    openWorld: false
    readOnly: true
  name: get-document
- description: Permanently delete a processed document and its extracted data.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-document
- description: Extract structured transaction data, account information, and balances from a bank statement PDF or image URL.
  hints:
    openWorld: false
    readOnly: false
  name: process-bank-statement
- description: List all previously processed bank statements.
  hints:
    openWorld: true
    readOnly: true
  name: list-bank-statements
- description: Extract routing number, account number, check number, payee, and amount from a check image URL.
  hints:
    openWorld: false
    readOnly: false
  name: process-check
- description: Extract wages, tax withholdings, employer EIN, and employee information from a W-2 tax form.
  hints:
    openWorld: false
    readOnly: false
  name: process-w2
- description: Extract taxpayer name, TIN, entity type, and certification details from a W-9 form.
  hints:
    openWorld: false
    readOnly: false
  name: process-w9
- description: Extract data from any document type using a named Veryfi extraction blueprint. Useful for contracts, custom forms, and non-standard documents.
  hints:
    openWorld: false
    readOnly: false
  name: process-any-document
- description: Classify a document to determine its type before processing. Optionally restrict to specific document types (receipt, invoice, bank_statement, w2, w9, check).
  hints:
    openWorld: false
    readOnly: true
  name: classify-document
---
