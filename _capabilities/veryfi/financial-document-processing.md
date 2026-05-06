---
categories: []
consumed_apis: []
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
- process receipts, invoices, and bills
- list all bank statements
- classify a document to determine its type before processing. optionally restrict to specific document types (receipt, invoice, bank_statement, w2, w9, check).
- process a check
- accounts payable
- extract data from any document type using a named veryfi extraction blueprint. useful for contracts, custom forms, and non-standard documents.
- delete a document
- process a bank statement
- extract structured data from a receipt or invoice. provide a publicly accessible url to the document. returns vendor details, line items, taxes, totals, and currency in 91 currencies and 38 languages.
- process any document
- get document
- invoices
- process document
- list all previously processed receipts and invoices.
- single bank statement operations
- document processing
- process bank statement
- get details for a specific processed document by its numeric id.
- process and retrieve checks
- list documents
- finance
- list all previously processed bank statements.
- veryfi
- get a document
- delete document
- get bank statement
- list all documents
- list checks
- process a document
- process w2
- list w2s
- process w9
- ai
- list all w-2 forms
- permanently delete a processed document and its extracted data.
- get a bank statement
- list bank statements
- classify a document
- single document operations
- list all checks
- process a w-9 form
- receipts
- tax forms
- process receipt invoice
- extract structured transaction data, account information, and balances from a bank statement pdf or image url.
- extract routing number, account number, check number, payee, and amount from a check image url.
- extract wages, tax withholdings, employer ein, and employee information from a w-2 tax form.
- process check
- process and retrieve bank statements
- extract taxpayer name, tin, entity type, and certification details from a w-9 form.
- process custom documents with blueprints
- process a w-2 form
- checks
- process and retrieve w-2 tax forms
- process and retrieve w-9 tax forms
- classify document
- ocr
- classify documents before processing
- bank statements
slug: financial-document-processing
source_filename: financial-document-processing.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Veryfi Financial Document Processing\n  description: Unified financial document processing capability using the Veryfi OCR API. Enables accounts payable teams,\n    tax professionals, lenders, and finance teams to extract structured data from receipts, invoices, bank statements, checks,\n    W-2s, W-9s, and custom documents through a single REST and MCP interface. Supports 91 currencies and 38 languages.\n  tags:\n  - AI\n  - Accounts Payable\n  - Bank Statements\n  - Checks\n  - Document Processing\n  - Finance\n  - Invoices\n  - OCR\n  - Receipts\n  - Tax Forms\n  - Veryfi\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    VERYFI_CLIENT_ID: VERYFI_CLIENT_ID\n    VERYFI_API_KEY: VERYFI_API_KEY\n    VERYFI_USERNAME: VERYFI_USERNAME\ncapability:\n  consumes:\n  - type: http\n    namespace: veryfi\n    baseUri: https://api.veryfi.com/api/v8\n    description: Veryfi OCR API v8 for document data extraction\n\
  \    authentication:\n      type: apikey\n      key: AUTHORIZATION\n      value: apikey {{env.VERYFI_USERNAME}}:{{env.VERYFI_API_KEY}}\n      placement: header\n    resources:\n    - name: documents\n      path: /partner/documents\n      description: Receipts and invoices processing\n      operations:\n      - name: process-document\n        method: POST\n        description: Process a Document\n        body:\n          type: json\n          data:\n            file_url: '{{tools.file_url}}'\n            tags: '{{tools.tags}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-documents\n        method: GET\n        description: List All Documents\n        inputParameters:\n        - name: created_date__gt\n          in: query\n          type: string\n          required: false\n          description: Filter by creation date\n        outputRawFormat: json\n        outputParameters:\n        -\
  \ name: result\n          type: object\n          value: $.\n      - name: get-document\n        method: GET\n        description: Get a Document\n        inputParameters:\n        - name: documentId\n          in: path\n          type: integer\n          required: true\n          description: Document ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-document\n        method: DELETE\n        description: Delete a Document\n        inputParameters:\n        - name: documentId\n          in: path\n          type: integer\n          required: true\n          description: Document ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: bank-statements\n      path: /partner/bank-statements\n      description: Bank statement processing\n      operations:\n      - name: process-bank-statement\n        method:\
  \ POST\n        description: Process a Bank Statement\n        body:\n          type: json\n          data:\n            file_url: '{{tools.file_url}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-bank-statements\n        method: GET\n        description: List All Bank Statements\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-bank-statement\n        method: GET\n        description: Get a Bank Statement\n        inputParameters:\n        - name: documentId\n          in: path\n          type: integer\n          required: true\n          description: Bank statement ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-bank-statement\n        method: DELETE\n        description: Delete a Bank Statement\n\
  \        inputParameters:\n        - name: documentId\n          in: path\n          type: integer\n          required: true\n          description: Bank statement ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: checks\n      path: /partner/checks\n      description: Check processing\n      operations:\n      - name: process-check\n        method: POST\n        description: Process a Check\n        body:\n          type: json\n          data:\n            file_url: '{{tools.file_url}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-checks\n        method: GET\n        description: List All Checks\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-check\n        method: GET\n        description: Get a\
  \ Check\n        inputParameters:\n        - name: documentId\n          in: path\n          type: integer\n          required: true\n          description: Check ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: w2s\n      path: /partner/w2s\n      description: W-2 tax form processing\n      operations:\n      - name: process-w2\n        method: POST\n        description: Process a W-2 Form\n        body:\n          type: json\n          data:\n            file_url: '{{tools.file_url}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-w2s\n        method: GET\n        description: List All W-2 Forms\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-w2\n        method: GET\n        description: Get a W-2\
  \ Form\n        inputParameters:\n        - name: documentId\n          in: path\n          type: integer\n          required: true\n          description: W-2 form ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: w9s\n      path: /partner/w9s\n      description: W-9 tax form processing\n      operations:\n      - name: process-w9\n        method: POST\n        description: Process a W-9 Form\n        body:\n          type: json\n          data:\n            file_url: '{{tools.file_url}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-w9s\n        method: GET\n        description: List All W-9 Forms\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-w9\n        method: GET\n        description: Get a W-9\
  \ Form\n        inputParameters:\n        - name: documentId\n          in: path\n          type: integer\n          required: true\n          description: W-9 form ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: any-documents\n      path: /partner/any-documents\n      description: Custom blueprint document processing\n      operations:\n      - name: process-any-document\n        method: POST\n        description: Process Any Document\n        body:\n          type: json\n          data:\n            file_url: '{{tools.file_url}}'\n            blueprint_name: '{{tools.blueprint_name}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-any-documents\n        method: GET\n        description: List Any Documents\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n    \
  \      type: object\n          value: $.\n    - name: classify\n      path: /partner/classify\n      description: Document type classification\n      operations:\n      - name: classify-document\n        method: POST\n        description: Classify a Document\n        body:\n          type: json\n          data:\n            file_url: '{{tools.file_url}}'\n            document_types: '{{tools.document_types}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: financial-document-processing-api\n    description: Unified REST API for AI-powered financial document data extraction.\n    resources:\n    - path: /v1/documents\n      name: documents\n      description: Process receipts, invoices, and bills\n      operations:\n      - method: POST\n        name: process-document\n        description: Process a Document\n        call: veryfi.process-document\n \
  \       with:\n          file_url: rest.file_url\n          tags: rest.tags\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: list-documents\n        description: List All Documents\n        call: veryfi.list-documents\n        with:\n          created_date__gt: rest.created_date__gt\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/documents/{documentId}\n      name: document\n      description: Single document operations\n      operations:\n      - method: GET\n        name: get-document\n        description: Get a Document\n        call: veryfi.get-document\n        with:\n          documentId: rest.documentId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-document\n        description: Delete a Document\n        call: veryfi.delete-document\n        with:\n          documentId: rest.documentId\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /v1/bank-statements\n      name: bank-statements\n      description: Process and retrieve bank statements\n      operations:\n      - method: POST\n        name: process-bank-statement\n        description: Process a Bank Statement\n        call: veryfi.process-bank-statement\n        with:\n          file_url: rest.file_url\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: list-bank-statements\n        description: List All Bank Statements\n        call: veryfi.list-bank-statements\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/bank-statements/{documentId}\n      name: bank-statement\n      description: Single bank statement operations\n      operations:\n      - method: GET\n        name: get-bank-statement\n        description: Get a Bank Statement\n        call: veryfi.get-bank-statement\n        with:\n          documentId:\
  \ rest.documentId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/checks\n      name: checks\n      description: Process and retrieve checks\n      operations:\n      - method: POST\n        name: process-check\n        description: Process a Check\n        call: veryfi.process-check\n        with:\n          file_url: rest.file_url\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: list-checks\n        description: List All Checks\n        call: veryfi.list-checks\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/w2s\n      name: w2s\n      description: Process and retrieve W-2 tax forms\n      operations:\n      - method: POST\n        name: process-w2\n        description: Process a W-2 Form\n        call: veryfi.process-w2\n        with:\n          file_url: rest.file_url\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n      - method: GET\n        name: list-w2s\n        description: List All W-2 Forms\n        call: veryfi.list-w2s\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/w9s\n      name: w9s\n      description: Process and retrieve W-9 tax forms\n      operations:\n      - method: POST\n        name: process-w9\n        description: Process a W-9 Form\n        call: veryfi.process-w9\n        with:\n          file_url: rest.file_url\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/any-documents\n      name: any-documents\n      description: Process custom documents with blueprints\n      operations:\n      - method: POST\n        name: process-any-document\n        description: Process Any Document\n        call: veryfi.process-any-document\n        with:\n          file_url: rest.file_url\n          blueprint_name: rest.blueprint_name\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /v1/classify\n      name: classify\n      description: Classify documents before processing\n      operations:\n      - method: POST\n        name: classify-document\n        description: Classify a Document\n        call: veryfi.classify-document\n        with:\n          file_url: rest.file_url\n          document_types: rest.document_types\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9080\n    namespace: financial-document-processing-mcp\n    transport: http\n    description: MCP server for AI-assisted financial document data extraction.\n    tools:\n    - name: process-receipt-invoice\n      description: Extract structured data from a receipt or invoice. Provide a publicly accessible URL to the document. Returns\n        vendor details, line items, taxes, totals, and currency in 91 currencies and 38 languages.\n      hints:\n        readOnly: false\n        openWorld: false\n      call: veryfi.process-document\n\
  \      with:\n        file_url: tools.file_url\n        tags: tools.tags\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-documents\n      description: List all previously processed receipts and invoices.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: veryfi.list-documents\n      with:\n        created_date__gt: tools.created_date__gt\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-document\n      description: Get details for a specific processed document by its numeric ID.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: veryfi.get-document\n      with:\n        documentId: tools.documentId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-document\n      description: Permanently delete a processed document and its extracted data.\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n\
  \      call: veryfi.delete-document\n      with:\n        documentId: tools.documentId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: process-bank-statement\n      description: Extract structured transaction data, account information, and balances from a bank statement PDF or image\n        URL.\n      hints:\n        readOnly: false\n        openWorld: false\n      call: veryfi.process-bank-statement\n      with:\n        file_url: tools.file_url\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-bank-statements\n      description: List all previously processed bank statements.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: veryfi.list-bank-statements\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: process-check\n      description: Extract routing number, account number, check number, payee, and amount from a check image URL.\n      hints:\n        readOnly:\
  \ false\n        openWorld: false\n      call: veryfi.process-check\n      with:\n        file_url: tools.file_url\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: process-w2\n      description: Extract wages, tax withholdings, employer EIN, and employee information from a W-2 tax form.\n      hints:\n        readOnly: false\n        openWorld: false\n      call: veryfi.process-w2\n      with:\n        file_url: tools.file_url\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: process-w9\n      description: Extract taxpayer name, TIN, entity type, and certification details from a W-9 form.\n      hints:\n        readOnly: false\n        openWorld: false\n      call: veryfi.process-w9\n      with:\n        file_url: tools.file_url\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: process-any-document\n      description: Extract data from any document type using a named Veryfi extraction blueprint.\
  \ Useful for contracts, custom\n        forms, and non-standard documents.\n      hints:\n        readOnly: false\n        openWorld: false\n      call: veryfi.process-any-document\n      with:\n        file_url: tools.file_url\n        blueprint_name: tools.blueprint_name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: classify-document\n      description: Classify a document to determine its type before processing. Optionally restrict to specific document types\n        (receipt, invoice, bank_statement, w2, w9, check).\n      hints:\n        readOnly: true\n        openWorld: false\n      call: veryfi.classify-document\n      with:\n        file_url: tools.file_url\n        document_types: tools.document_types\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
