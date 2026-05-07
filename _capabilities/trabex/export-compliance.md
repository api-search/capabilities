---
categories: []
consumed_apis: []
description: End-to-end export compliance workflow combining shipment management, restricted party screening, AES filing, and compliance document generation. Used by export compliance teams to automate EEI filing, screen trading partners, and generate required export documentation.
layout: capability
name: Trabex Export Compliance
operations:
- description: Retrieve export shipments with compliance status
  method: GET
  name: get-shipments
  path: /v1/shipments
- description: Submit an export shipment for compliance processing
  method: POST
  name: create-shipment
  path: /v1/shipments
- description: Retrieve a specific shipment with compliance details
  method: GET
  name: get-shipment
  path: /v1/shipments/{shipmentId}
- description: Screen a trading party against denied party lists
  method: POST
  name: screen-party
  path: /v1/screening
- description: Screen multiple parties simultaneously
  method: POST
  name: batch-screen-parties
  path: /v1/batch-screening
- description: Retrieve export documents for a shipment
  method: GET
  name: get-shipment-documents
  path: /v1/documents/{shipmentId}
- description: Retrieve AES filing history
  method: GET
  name: get-aes-filings
  path: /v1/aes-filings
- description: Submit AES filing for a shipment
  method: POST
  name: submit-aes-filing
  path: /v1/aes-filings/{shipmentId}
- description: Retrieve company records
  method: GET
  name: get-companies
  path: /v1/companies
- description: Create a company record
  method: POST
  name: create-company
  path: /v1/companies
personas: []
provider_name: Trabex
provider_slug: trabex
search_terms:
- create shipment
- logistics
- submit aes filing for a shipment
- screen party
- retrieve a specific shipment with compliance details
- retrieve export shipments with compliance status from trabex
- submit a new export shipment for trabex compliance processing
- retrieve trading party company records from trabex
- create company
- aes filing
- get aes filings
- export shipment management and compliance processing
- submit electronic export information to aes for a shipment
- submit an export shipment for compliance processing
- individual shipment operations
- retrieve aes filing history
- trade compliance
- compliance
- screen multiple trading parties simultaneously against compliance lists
- export compliance documents
- export control
- get shipment
- batch screen parties
- retrieve export compliance documents for a trabex shipment
- create a company record
- get shipments
- bulk restricted party screening
- screen a trading party against denied party lists
- get shipment documents
- screen a trading party against denied party and sanctions lists
- submit aes filing
- restricted party screening
- shipment management
- retrieve company records
- screen multiple parties simultaneously
- retrieve aes filing history and status
- aes filing submission
- get companies
- aes filing management
- retrieve compliance details for a specific trabex shipment
- restricted party screening operations
- trading party management
- create a company record in trabex for use in compliance workflows
- retrieve export shipments with compliance status
- retrieve export documents for a shipment
slug: export-compliance
source_filename: export-compliance.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Trabex Export Compliance\n  description: End-to-end export compliance workflow combining shipment management, restricted party screening, AES filing,\n    and compliance document generation. Used by export compliance teams to automate EEI filing, screen trading partners, and\n    generate required export documentation.\n  tags:\n  - AES Filing\n  - Compliance\n  - Export Control\n  - Logistics\n  - Restricted Party Screening\n  - Trade Compliance\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    TRABEX_API_KEY: TRABEX_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: trabex-trade-compliance\n    baseUri: https://api.trabex.io\n    description: Trabex trade compliance API for export shipment management and screening\n    authentication:\n      type: apikey\n      key: X-API-Key\n      value: '{{TRABEX_API_KEY}}'\n      placement: header\n    resources:\n    - name: shipments\n   \
  \   path: /v1/shipments\n      description: Export shipment management\n      operations:\n      - name: get-shipments\n        method: GET\n        description: Retrieve a list of export shipments\n        inputParameters:\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Filter by compliance status\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number\n        - name: pageSize\n          in: query\n          type: integer\n          required: false\n          description: Records per page\n        - name: fromDate\n          in: query\n          type: string\n          required: false\n          description: Filter from date (ISO 8601)\n        - name: toDate\n          in: query\n          type: string\n          required: false\n          description: Filter to date (ISO 8601)\n        outputRawFormat: json\n        outputParameters:\n \
  \       - name: result\n          type: object\n          value: $.\n      - name: create-shipment\n        method: POST\n        description: Submit an export shipment for compliance processing\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            shipper: '{{tools.shipper}}'\n            consignee: '{{tools.consignee}}'\n            destinationCountry: '{{tools.destination_country}}'\n            exportDate: '{{tools.export_date}}'\n            lineItems: '{{tools.line_items}}'\n      - name: get-shipment\n        method: GET\n        description: Retrieve a specific shipment\n        inputParameters:\n        - name: shipmentId\n          in: path\n          type: string\n          required: true\n          description: Shipment identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n      - name: update-shipment\n        method: PUT\n        description: Update an existing shipment\n        inputParameters:\n        - name: shipmentId\n          in: path\n          type: string\n          required: true\n          description: Shipment identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            shipper: '{{tools.shipper}}'\n            consignee: '{{tools.consignee}}'\n            destinationCountry: '{{tools.destination_country}}'\n            lineItems: '{{tools.line_items}}'\n    - name: screening\n      path: /v1/screening\n      description: Restricted party screening\n      operations:\n      - name: screen-party\n        method: POST\n        description: Perform restricted party screening for a single party\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n  \
  \        type: object\n          value: $.\n        body:\n          type: json\n          data:\n            party: '{{tools.party}}'\n            listTypes: '{{tools.list_types}}'\n      - name: batch-screen-parties\n        method: POST\n        description: Perform restricted party screening for multiple parties\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            parties: '{{tools.parties}}'\n    - name: documents\n      path: /v1/documents\n      description: Export compliance document retrieval\n      operations:\n      - name: get-shipment-documents\n        method: GET\n        description: Retrieve export compliance documents for a shipment\n        inputParameters:\n        - name: shipmentId\n          in: path\n          type: string\n          required: true\n          description: Shipment identifier\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: aes-filings\n      path: /v1/aes/filings\n      description: AES filing management\n      operations:\n      - name: get-aes-filings\n        method: GET\n        description: Retrieve AES filings\n        inputParameters:\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Filter by AES filing status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: submit-aes-filing\n        method: POST\n        description: Submit AES filing for a shipment\n        inputParameters:\n        - name: shipmentId\n          in: path\n          type: string\n          required: true\n          description: Shipment identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n       \
  \   value: $.\n    - name: companies\n      path: /v1/companies\n      description: Company and trading party management\n      operations:\n      - name: get-companies\n        method: GET\n        description: Retrieve company records\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-company\n        method: POST\n        description: Create a company record\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            country: '{{tools.country}}'\n            address: '{{tools.address}}'\n            role: '{{tools.role}}'\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: export-compliance-api\n    description: Unified REST API for Trabex export compliance workflows.\n    resources:\n    - path: /v1/shipments\n\
  \      name: shipments\n      description: Export shipment management and compliance processing\n      operations:\n      - method: GET\n        name: get-shipments\n        description: Retrieve export shipments with compliance status\n        call: trabex-trade-compliance.get-shipments\n        with:\n          status: rest.status\n          page: rest.page\n          fromDate: rest.fromDate\n          toDate: rest.toDate\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-shipment\n        description: Submit an export shipment for compliance processing\n        call: trabex-trade-compliance.create-shipment\n        with:\n          shipper: rest.shipper\n          consignee: rest.consignee\n          destination_country: rest.destinationCountry\n          export_date: rest.exportDate\n          line_items: rest.lineItems\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/shipments/{shipmentId}\n\
  \      name: shipment\n      description: Individual shipment operations\n      operations:\n      - method: GET\n        name: get-shipment\n        description: Retrieve a specific shipment with compliance details\n        call: trabex-trade-compliance.get-shipment\n        with:\n          shipmentId: rest.shipmentId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/screening\n      name: screening\n      description: Restricted party screening operations\n      operations:\n      - method: POST\n        name: screen-party\n        description: Screen a trading party against denied party lists\n        call: trabex-trade-compliance.screen-party\n        with:\n          party: rest.party\n          list_types: rest.listTypes\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/batch-screening\n      name: batch-screening\n      description: Bulk restricted party screening\n      operations:\n      - method:\
  \ POST\n        name: batch-screen-parties\n        description: Screen multiple parties simultaneously\n        call: trabex-trade-compliance.batch-screen-parties\n        with:\n          parties: rest.parties\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/documents/{shipmentId}\n      name: documents\n      description: Export compliance documents\n      operations:\n      - method: GET\n        name: get-shipment-documents\n        description: Retrieve export documents for a shipment\n        call: trabex-trade-compliance.get-shipment-documents\n        with:\n          shipmentId: rest.shipmentId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/aes-filings\n      name: aes-filings\n      description: AES filing management\n      operations:\n      - method: GET\n        name: get-aes-filings\n        description: Retrieve AES filing history\n        call: trabex-trade-compliance.get-aes-filings\n\
  \        with:\n          status: rest.status\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/aes-filings/{shipmentId}\n      name: aes-filing\n      description: AES filing submission\n      operations:\n      - method: POST\n        name: submit-aes-filing\n        description: Submit AES filing for a shipment\n        call: trabex-trade-compliance.submit-aes-filing\n        with:\n          shipmentId: rest.shipmentId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/companies\n      name: companies\n      description: Trading party management\n      operations:\n      - method: GET\n        name: get-companies\n        description: Retrieve company records\n        call: trabex-trade-compliance.get-companies\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-company\n        description: Create a company record\n        call: trabex-trade-compliance.create-company\n\
  \        with:\n          name: rest.name\n          country: rest.country\n          address: rest.address\n          role: rest.role\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: export-compliance-mcp\n    transport: http\n    description: MCP server for AI-assisted Trabex export compliance operations.\n    tools:\n    - name: get-shipments\n      description: Retrieve export shipments with compliance status from Trabex\n      hints:\n        readOnly: true\n        openWorld: false\n      call: trabex-trade-compliance.get-shipments\n      with:\n        status: tools.status\n        fromDate: tools.from_date\n        toDate: tools.to_date\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-shipment\n      description: Submit a new export shipment for Trabex compliance processing\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n\
  \      call: trabex-trade-compliance.create-shipment\n      with:\n        shipper: tools.shipper\n        consignee: tools.consignee\n        destination_country: tools.destination_country\n        export_date: tools.export_date\n        line_items: tools.line_items\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-shipment\n      description: Retrieve compliance details for a specific Trabex shipment\n      hints:\n        readOnly: true\n        openWorld: false\n      call: trabex-trade-compliance.get-shipment\n      with:\n        shipmentId: tools.shipment_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: screen-party\n      description: Screen a trading party against denied party and sanctions lists\n      hints:\n        readOnly: true\n        openWorld: true\n      call: trabex-trade-compliance.screen-party\n      with:\n        party: tools.party\n        list_types: tools.list_types\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: batch-screen-parties\n      description: Screen multiple trading parties simultaneously against compliance lists\n      hints:\n        readOnly: true\n        openWorld: true\n      call: trabex-trade-compliance.batch-screen-parties\n      with:\n        parties: tools.parties\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-shipment-documents\n      description: Retrieve export compliance documents for a Trabex shipment\n      hints:\n        readOnly: true\n        openWorld: false\n      call: trabex-trade-compliance.get-shipment-documents\n      with:\n        shipmentId: tools.shipment_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: submit-aes-filing\n      description: Submit Electronic Export Information to AES for a shipment\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: trabex-trade-compliance.submit-aes-filing\n\
  \      with:\n        shipmentId: tools.shipment_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-aes-filings\n      description: Retrieve AES filing history and status\n      hints:\n        readOnly: true\n        openWorld: false\n      call: trabex-trade-compliance.get-aes-filings\n      with:\n        status: tools.status\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-companies\n      description: Retrieve trading party company records from Trabex\n      hints:\n        readOnly: true\n        openWorld: false\n      call: trabex-trade-compliance.get-companies\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-company\n      description: Create a company record in Trabex for use in compliance workflows\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: trabex-trade-compliance.create-company\n      with:\n        name:\
  \ tools.name\n        country: tools.country\n        address: tools.address\n        role: tools.role\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/trabex/refs/heads/main/capabilities/export-compliance.yaml
tags:
- AES Filing
- Compliance
- Export Control
- Logistics
- Restricted Party Screening
- Trade Compliance
tools:
- description: Retrieve export shipments with compliance status from Trabex
  hints:
    openWorld: false
    readOnly: true
  name: get-shipments
- description: Submit a new export shipment for Trabex compliance processing
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-shipment
- description: Retrieve compliance details for a specific Trabex shipment
  hints:
    openWorld: false
    readOnly: true
  name: get-shipment
- description: Screen a trading party against denied party and sanctions lists
  hints:
    openWorld: true
    readOnly: true
  name: screen-party
- description: Screen multiple trading parties simultaneously against compliance lists
  hints:
    openWorld: true
    readOnly: true
  name: batch-screen-parties
- description: Retrieve export compliance documents for a Trabex shipment
  hints:
    openWorld: false
    readOnly: true
  name: get-shipment-documents
- description: Submit Electronic Export Information to AES for a shipment
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: submit-aes-filing
- description: Retrieve AES filing history and status
  hints:
    openWorld: false
    readOnly: true
  name: get-aes-filings
- description: Retrieve trading party company records from Trabex
  hints:
    openWorld: false
    readOnly: true
  name: get-companies
- description: Create a company record in Trabex for use in compliance workflows
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-company
---
