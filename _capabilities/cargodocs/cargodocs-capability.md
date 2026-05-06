---
categories: []
consumed_apis: []
description: The CargoDocs Customer Data/Docs API enables exporters to draft trade and shipping documents, including tanker, bulker, or barge bills of lading from data imported from an ERP system, CTRM, TMS, WMS, etc. It also enables any party using CargoDocs to download copy docs and data to automate various back-office steps.
layout: capability
name: CargoDocs Customer Data/Docs API
operations:
- description: CargoDocs Import Shipment Data
  method: POST
  name: importshipmentdata
  path: /common/import
- description: CargoDocs Find Transactions
  method: GET
  name: findtransactions
  path: /customer/transactions
- description: CargoDocs Find Transaction Documents
  method: GET
  name: finddocuments
  path: /customer/transactions/{transactionId}/documents
- description: CargoDocs Download Document PDF
  method: GET
  name: downloaddocumentpdf
  path: /customer/documents/{documentId}/pdf
personas: []
provider_name: CargoDocs
provider_slug: cargodocs
search_terms:
- finddocuments
- bills of lading
- importshipmentdata
- mletr
- downloaddocumentpdf
- trade
- cargodocs find transaction documents
- warehouse warrants
- findtransactions
- ebol
- documentation
- trade finance
- supply chain
- cargodocs
- shipping
- api
- cargodocs import shipment data
- cargodocs download document pdf
- essdocs
- cargodocs find transactions
slug: cargodocs-capability
source_filename: cargodocs-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: CargoDocs Customer Data/Docs API\n  description: The CargoDocs Customer Data/Docs API enables exporters to draft trade and shipping documents, including tanker,\n    bulker, or barge bills of lading from data imported from an ERP system, CTRM, TMS, WMS, etc. It also enables any party\n    using CargoDocs to download copy docs and data to automate various back-office steps.\n  tags:\n  - Cargodocs\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: cargodocs\n    baseUri: https://api-test.cargodocs.com/v3\n    description: CargoDocs Customer Data/Docs API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{CARGODOCS_TOKEN}}'\n    resources:\n    - name: common-import\n      path: /common/import\n      operations:\n      - name: importshipmentdata\n        method: POST\n        description: CargoDocs Import Shipment Data\n        inputParameters:\n        -\
  \ name: importRef\n          in: query\n          type: string\n          required: true\n          description: The import reference identifier (e.g., LNGBL559)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: customer-transactions\n      path: /customer/transactions\n      operations:\n      - name: findtransactions\n        method: GET\n        description: CargoDocs Find Transactions\n        inputParameters:\n        - name: status\n          in: query\n          type: string\n          description: Filter by transaction status\n        - name: page\n          in: query\n          type: integer\n          description: Page number for pagination\n        - name: pageSize\n          in: query\n          type: integer\n          description: Number of items per page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n \
  \   - name: customer-transactions-transactionid-documents\n      path: /customer/transactions/{transactionId}/documents\n      operations:\n      - name: finddocuments\n        method: GET\n        description: CargoDocs Find Transaction Documents\n        inputParameters:\n        - name: transactionId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier for the transaction\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: customer-documents-documentid-pdf\n      path: /customer/documents/{documentId}/pdf\n      operations:\n      - name: downloaddocumentpdf\n        method: GET\n        description: CargoDocs Download Document PDF\n        inputParameters:\n        - name: documentId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier for the document\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: cargodocs-rest\n    description: REST adapter for CargoDocs Customer Data/Docs API.\n    resources:\n    - path: /common/import\n      name: importshipmentdata\n      operations:\n      - method: POST\n        name: importshipmentdata\n        description: CargoDocs Import Shipment Data\n        call: cargodocs.importshipmentdata\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /customer/transactions\n      name: findtransactions\n      operations:\n      - method: GET\n        name: findtransactions\n        description: CargoDocs Find Transactions\n        call: cargodocs.findtransactions\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /customer/transactions/{transactionId}/documents\n      name: finddocuments\n      operations:\n      - method: GET\n\
  \        name: finddocuments\n        description: CargoDocs Find Transaction Documents\n        call: cargodocs.finddocuments\n        with:\n          transactionId: rest.transactionId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /customer/documents/{documentId}/pdf\n      name: downloaddocumentpdf\n      operations:\n      - method: GET\n        name: downloaddocumentpdf\n        description: CargoDocs Download Document PDF\n        call: cargodocs.downloaddocumentpdf\n        with:\n          documentId: rest.documentId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: cargodocs-mcp\n    transport: http\n    description: MCP adapter for CargoDocs Customer Data/Docs API for AI agent use.\n    tools:\n    - name: importshipmentdata\n      description: CargoDocs Import Shipment Data\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n\
  \      call: cargodocs.importshipmentdata\n      with:\n        importRef: tools.importRef\n      inputParameters:\n      - name: importRef\n        type: string\n        description: The import reference identifier (e.g., LNGBL559)\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: findtransactions\n      description: CargoDocs Find Transactions\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: cargodocs.findtransactions\n      with:\n        status: tools.status\n        page: tools.page\n        pageSize: tools.pageSize\n      inputParameters:\n      - name: status\n        type: string\n        description: Filter by transaction status\n      - name: page\n        type: integer\n        description: Page number for pagination\n      - name: pageSize\n        type: integer\n        description: Number of items per page\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: finddocuments\n      description: CargoDocs Find Transaction Documents\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: cargodocs.finddocuments\n      with:\n        transactionId: tools.transactionId\n      inputParameters:\n      - name: transactionId\n        type: string\n        description: The unique identifier for the transaction\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: downloaddocumentpdf\n      description: CargoDocs Download Document PDF\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: cargodocs.downloaddocumentpdf\n      with:\n        documentId: tools.documentId\n      inputParameters:\n      - name: documentId\n        type: string\n        description: The unique identifier for the document\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n\
  binds:\n- namespace: env\n  keys:\n    CARGODOCS_TOKEN: CARGODOCS_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/cargodocs/refs/heads/main/capabilities/cargodocs-capability.yaml
tags:
- Cargodocs
- API
tools:
- description: CargoDocs Import Shipment Data
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: importshipmentdata
- description: CargoDocs Find Transactions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: findtransactions
- description: CargoDocs Find Transaction Documents
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: finddocuments
- description: CargoDocs Download Document PDF
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: downloaddocumentpdf
---
