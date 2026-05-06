---
categories: []
consumed_apis: []
description: United Rentals equipment rental and fleet management capability combining equipment catalog browsing, rental reservations, fleet tracking, invoice management, and procure-to-pay automation. Designed for integration with customer ERP and procurement systems via the Total Control platform.
layout: capability
name: United Rentals Equipment Rental
operations:
- description: Browse equipment catalog by category and location
  method: GET
  name: list-equipment
  path: /v1/equipment
- description: Get equipment details and pricing
  method: GET
  name: get-equipment
  path: /v1/equipment/{id}
- description: Check availability for a date range
  method: GET
  name: check-equipment-availability
  path: /v1/equipment/{id}/availability
- description: Create a rental reservation
  method: POST
  name: create-rental
  path: /v1/rentals
- description: List rental orders
  method: GET
  name: list-rentals
  path: /v1/rentals
- description: Get rental details
  method: GET
  name: get-rental
  path: /v1/rentals/{id}
- description: Extend an active rental
  method: POST
  name: extend-rental
  path: /v1/rentals/{id}/extend
- description: Initiate equipment return
  method: POST
  name: return-rental
  path: /v1/rentals/{id}/return
- description: Get real-time fleet status
  method: GET
  name: get-fleet
  path: /v1/fleet
- description: List invoices for payment processing
  method: GET
  name: list-invoices
  path: /v1/invoices
- description: Get invoice details
  method: GET
  name: get-invoice
  path: /v1/invoices/{id}
- description: Submit payment for an invoice
  method: POST
  name: pay-invoice
  path: /v1/invoices/{id}/pay
- description: Find nearby United Rentals branches
  method: GET
  name: list-locations
  path: /v1/locations
personas: []
provider_name: United Rentals
provider_slug: united-rentals
search_terms:
- create rental
- construction
- list equipment
- equipment availability check
- get invoice details
- check availability for a date range
- extend an active rental
- individual invoice operations
- get invoice
- check if equipment is available for a specific date range and location
- initiate the return of rented equipment
- initiate equipment return
- return rental
- invoice management
- individual equipment details
- rental reservation management
- get full details for a specific rental order
- erp integration
- get full details for a specific rental invoice
- pay invoice
- procure to pay
- submit payment for an invoice
- list locations
- branch location search
- submit payment (ach, credit card, or check) for a rental invoice
- fleet management
- get equipment
- equipment catalog and availability
- get rental details
- get details and rental rates for specific equipment
- find nearby united rentals branches
- check equipment availability
- browse the united rentals equipment catalog by category, type, and location
- supply chain
- create an equipment rental reservation linked to a purchase order
- individual rental operations
- get real-time fleet overview across all active rentals and job sites
- extend the end date of an active equipment rental
- list invoices for payment processing
- browse equipment catalog by category and location
- list rentals
- find united rentals branch locations near a zip code or in a state
- extend rental
- get equipment details and pricing
- fortune 500
- equipment return
- create a rental reservation
- get rental
- rental extension
- list rental invoices filtered by status or purchase order number
- list active and historical rental orders by job site or status
- invoice payment
- list invoices
- get real-time fleet status
- fleet overview and worksite management
- equipment rental
- list rental orders
- get fleet
- procurement
slug: equipment-rental
source_filename: equipment-rental.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: United Rentals Equipment Rental\n  description: United Rentals equipment rental and fleet management capability combining equipment catalog browsing, rental\n    reservations, fleet tracking, invoice management, and procure-to-pay automation. Designed for integration with customer\n    ERP and procurement systems via the Total Control platform.\n  tags:\n  - Equipment Rental\n  - Procurement\n  - Fleet Management\n  - Construction\n  - ERP Integration\n  - Procure To Pay\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    UNITED_RENTALS_API_KEY: UNITED_RENTALS_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: united-rentals-total-control\n    baseUri: https://api.unitedrentals.com/v1\n    description: United Rentals Total Control API for equipment rental and fleet management.\n    authentication:\n      type: apikey\n      key: X-API-Key\n      value: '{{UNITED_RENTALS_API_KEY}}'\n\
  \      placement: header\n    resources:\n    - name: equipment\n      path: /equipment\n      description: Equipment catalog and availability\n      operations:\n      - name: list-equipment\n        method: GET\n        description: Browse the United Rentals equipment catalog\n        inputParameters:\n        - name: category\n          in: query\n          type: string\n          required: false\n          description: Equipment category\n        - name: available\n          in: query\n          type: boolean\n          required: false\n          description: Filter for available equipment only\n        - name: branchId\n          in: query\n          type: string\n          required: false\n          description: Filter by branch location\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number\n        - name: pageSize\n          in: query\n          type: integer\n          required: false\n          description:\
  \ Results per page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-equipment\n        method: GET\n        description: Get details for specific equipment\n        inputParameters:\n        - name: equipmentId\n          in: path\n          type: string\n          required: true\n          description: Equipment identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: check-equipment-availability\n        method: GET\n        description: Check equipment availability for a date range\n        inputParameters:\n        - name: equipmentId\n          in: path\n          type: string\n          required: true\n          description: Equipment identifier\n        - name: startDate\n          in: query\n          type: string\n          required: true\n          description: Rental start date\n     \
  \   - name: endDate\n          in: query\n          type: string\n          required: true\n          description: Rental end date\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: rentals\n      path: /rentals\n      description: Rental reservations and management\n      operations:\n      - name: create-rental\n        method: POST\n        description: Create a new rental reservation with PO\n        inputParameters:\n        - name: equipmentId\n          in: body\n          type: string\n          required: true\n          description: Equipment to rent\n        - name: startDate\n          in: body\n          type: string\n          required: true\n          description: Rental start date\n        - name: endDate\n          in: body\n          type: string\n          required: true\n          description: Rental end date\n        - name: jobSite\n          in: body\n          type: string\n\
  \          required: true\n          description: Job site name\n        - name: purchaseOrderNumber\n          in: body\n          type: string\n          required: true\n          description: Customer PO number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-rentals\n        method: GET\n        description: Retrieve rental orders for the account\n        inputParameters:\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Rental status filter\n        - name: jobSite\n          in: query\n          type: string\n          required: false\n          description: Filter by job site\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-rental\n        method: GET\n        description: Get details for a specific rental\n        inputParameters:\n\
  \        - name: rentalId\n          in: path\n          type: string\n          required: true\n          description: Rental order identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: extend-rental\n        method: POST\n        description: Extend the duration of an active rental\n        inputParameters:\n        - name: rentalId\n          in: path\n          type: string\n          required: true\n          description: Rental order identifier\n        - name: newEndDate\n          in: body\n          type: string\n          required: true\n          description: New return date\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: return-rental\n        method: POST\n        description: Initiate equipment return\n        inputParameters:\n        - name: rentalId\n          in: path\n        \
  \  type: string\n          required: true\n          description: Rental order identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: fleet\n      path: /fleet\n      description: Fleet and worksite management\n      operations:\n      - name: get-fleet\n        method: GET\n        description: Get real-time fleet overview for all active rentals\n        inputParameters:\n        - name: jobSite\n          in: query\n          type: string\n          required: false\n          description: Filter by job site\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Filter by equipment status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: invoices\n      path: /invoices\n      description: Invoice and billing management\n      operations:\n\
  \      - name: list-invoices\n        method: GET\n        description: Retrieve invoices for billing management\n        inputParameters:\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Invoice status filter\n        - name: purchaseOrderNumber\n          in: query\n          type: string\n          required: false\n          description: Filter by PO number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-invoice\n        method: GET\n        description: Get details for a specific invoice\n        inputParameters:\n        - name: invoiceId\n          in: path\n          type: string\n          required: true\n          description: Invoice identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: pay-invoice\n        method:\
  \ POST\n        description: Submit payment for an invoice\n        inputParameters:\n        - name: invoiceId\n          in: path\n          type: string\n          required: true\n          description: Invoice identifier\n        - name: amount\n          in: body\n          type: number\n          required: true\n          description: Payment amount\n        - name: paymentMethod\n          in: body\n          type: string\n          required: true\n          description: Payment method (ach, credit-card, check)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: locations\n      path: /locations\n      description: Branch location search\n      operations:\n      - name: list-locations\n        method: GET\n        description: Find United Rentals branch locations\n        inputParameters:\n        - name: zipCode\n          in: query\n          type: string\n          required: false\n     \
  \     description: Filter by zip code proximity\n        - name: state\n          in: query\n          type: string\n          required: false\n          description: Filter by state\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: united-rentals-equipment-api\n    description: Unified REST API for United Rentals equipment rental and fleet management.\n    resources:\n    - path: /v1/equipment\n      name: equipment\n      description: Equipment catalog and availability\n      operations:\n      - method: GET\n        name: list-equipment\n        description: Browse equipment catalog by category and location\n        call: united-rentals-total-control.list-equipment\n        with:\n          category: rest.category\n          available: rest.available\n          branchId: rest.branchId\n          page: rest.page\n          pageSize: rest.pageSize\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/equipment/{id}\n      name: equipment-detail\n      description: Individual equipment details\n      operations:\n      - method: GET\n        name: get-equipment\n        description: Get equipment details and pricing\n        call: united-rentals-total-control.get-equipment\n        with:\n          equipmentId: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/equipment/{id}/availability\n      name: equipment-availability\n      description: Equipment availability check\n      operations:\n      - method: GET\n        name: check-equipment-availability\n        description: Check availability for a date range\n        call: united-rentals-total-control.check-equipment-availability\n        with:\n          equipmentId: rest.id\n          startDate: rest.startDate\n          endDate: rest.endDate\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n    - path: /v1/rentals\n      name: rentals\n      description: Rental reservation management\n      operations:\n      - method: POST\n        name: create-rental\n        description: Create a rental reservation\n        call: united-rentals-total-control.create-rental\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: list-rentals\n        description: List rental orders\n        call: united-rentals-total-control.list-rentals\n        with:\n          status: rest.status\n          jobSite: rest.jobSite\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/rentals/{id}\n      name: rental\n      description: Individual rental operations\n      operations:\n      - method: GET\n        name: get-rental\n        description: Get rental details\n        call: united-rentals-total-control.get-rental\n        with:\n          rentalId: rest.id\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /v1/rentals/{id}/extend\n      name: rental-extension\n      description: Rental extension\n      operations:\n      - method: POST\n        name: extend-rental\n        description: Extend an active rental\n        call: united-rentals-total-control.extend-rental\n        with:\n          rentalId: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/rentals/{id}/return\n      name: rental-return\n      description: Equipment return\n      operations:\n      - method: POST\n        name: return-rental\n        description: Initiate equipment return\n        call: united-rentals-total-control.return-rental\n        with:\n          rentalId: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/fleet\n      name: fleet\n      description: Fleet overview and worksite management\n      operations:\n      - method: GET\n        name: get-fleet\n\
  \        description: Get real-time fleet status\n        call: united-rentals-total-control.get-fleet\n        with:\n          jobSite: rest.jobSite\n          status: rest.status\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/invoices\n      name: invoices\n      description: Invoice management\n      operations:\n      - method: GET\n        name: list-invoices\n        description: List invoices for payment processing\n        call: united-rentals-total-control.list-invoices\n        with:\n          status: rest.status\n          purchaseOrderNumber: rest.purchaseOrderNumber\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/invoices/{id}\n      name: invoice\n      description: Individual invoice operations\n      operations:\n      - method: GET\n        name: get-invoice\n        description: Get invoice details\n        call: united-rentals-total-control.get-invoice\n        with:\n          invoiceId:\
  \ rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/invoices/{id}/pay\n      name: invoice-payment\n      description: Invoice payment\n      operations:\n      - method: POST\n        name: pay-invoice\n        description: Submit payment for an invoice\n        call: united-rentals-total-control.pay-invoice\n        with:\n          invoiceId: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/locations\n      name: locations\n      description: Branch location search\n      operations:\n      - method: GET\n        name: list-locations\n        description: Find nearby United Rentals branches\n        call: united-rentals-total-control.list-locations\n        with:\n          zipCode: rest.zipCode\n          state: rest.state\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9080\n    namespace: united-rentals-equipment-mcp\n    transport:\
  \ http\n    description: MCP server for AI-assisted equipment rental and fleet management.\n    tools:\n    - name: list-equipment\n      description: Browse the United Rentals equipment catalog by category, type, and location\n      hints:\n        readOnly: true\n        openWorld: true\n      call: united-rentals-total-control.list-equipment\n      with:\n        category: tools.category\n        available: tools.available\n        branchId: tools.branchId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-equipment\n      description: Get details and rental rates for specific equipment\n      hints:\n        readOnly: true\n        openWorld: false\n      call: united-rentals-total-control.get-equipment\n      with:\n        equipmentId: tools.equipmentId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: check-equipment-availability\n      description: Check if equipment is available for a specific date range and location\n\
  \      hints:\n        readOnly: true\n        openWorld: true\n      call: united-rentals-total-control.check-equipment-availability\n      with:\n        equipmentId: tools.equipmentId\n        startDate: tools.startDate\n        endDate: tools.endDate\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-rental\n      description: Create an equipment rental reservation linked to a purchase order\n      hints:\n        readOnly: false\n        destructive: false\n      call: united-rentals-total-control.create-rental\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-rentals\n      description: List active and historical rental orders by job site or status\n      hints:\n        readOnly: true\n        openWorld: false\n      call: united-rentals-total-control.list-rentals\n      with:\n        status: tools.status\n        jobSite: tools.jobSite\n      outputParameters:\n      - type: object\n        mapping: $.\n\
  \    - name: get-rental\n      description: Get full details for a specific rental order\n      hints:\n        readOnly: true\n        openWorld: false\n      call: united-rentals-total-control.get-rental\n      with:\n        rentalId: tools.rentalId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: extend-rental\n      description: Extend the end date of an active equipment rental\n      hints:\n        readOnly: false\n        destructive: false\n      call: united-rentals-total-control.extend-rental\n      with:\n        rentalId: tools.rentalId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: return-rental\n      description: Initiate the return of rented equipment\n      hints:\n        readOnly: false\n        destructive: false\n      call: united-rentals-total-control.return-rental\n      with:\n        rentalId: tools.rentalId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-fleet\n\
  \      description: Get real-time fleet overview across all active rentals and job sites\n      hints:\n        readOnly: true\n        openWorld: false\n      call: united-rentals-total-control.get-fleet\n      with:\n        jobSite: tools.jobSite\n        status: tools.status\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-invoices\n      description: List rental invoices filtered by status or purchase order number\n      hints:\n        readOnly: true\n        openWorld: false\n      call: united-rentals-total-control.list-invoices\n      with:\n        status: tools.status\n        purchaseOrderNumber: tools.purchaseOrderNumber\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-invoice\n      description: Get full details for a specific rental invoice\n      hints:\n        readOnly: true\n        openWorld: false\n      call: united-rentals-total-control.get-invoice\n      with:\n        invoiceId: tools.invoiceId\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: pay-invoice\n      description: Submit payment (ACH, credit card, or check) for a rental invoice\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: united-rentals-total-control.pay-invoice\n      with:\n        invoiceId: tools.invoiceId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-locations\n      description: Find United Rentals branch locations near a zip code or in a state\n      hints:\n        readOnly: true\n        openWorld: true\n      call: united-rentals-total-control.list-locations\n      with:\n        zipCode: tools.zipCode\n        state: tools.state\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/united-rentals/refs/heads/main/capabilities/equipment-rental.yaml
tags:
- Equipment Rental
- Procurement
- Fleet Management
- Construction
- ERP Integration
- Procure To Pay
tools:
- description: Browse the United Rentals equipment catalog by category, type, and location
  hints:
    openWorld: true
    readOnly: true
  name: list-equipment
- description: Get details and rental rates for specific equipment
  hints:
    openWorld: false
    readOnly: true
  name: get-equipment
- description: Check if equipment is available for a specific date range and location
  hints:
    openWorld: true
    readOnly: true
  name: check-equipment-availability
- description: Create an equipment rental reservation linked to a purchase order
  hints:
    destructive: false
    readOnly: false
  name: create-rental
- description: List active and historical rental orders by job site or status
  hints:
    openWorld: false
    readOnly: true
  name: list-rentals
- description: Get full details for a specific rental order
  hints:
    openWorld: false
    readOnly: true
  name: get-rental
- description: Extend the end date of an active equipment rental
  hints:
    destructive: false
    readOnly: false
  name: extend-rental
- description: Initiate the return of rented equipment
  hints:
    destructive: false
    readOnly: false
  name: return-rental
- description: Get real-time fleet overview across all active rentals and job sites
  hints:
    openWorld: false
    readOnly: true
  name: get-fleet
- description: List rental invoices filtered by status or purchase order number
  hints:
    openWorld: false
    readOnly: true
  name: list-invoices
- description: Get full details for a specific rental invoice
  hints:
    openWorld: false
    readOnly: true
  name: get-invoice
- description: Submit payment (ACH, credit card, or check) for a rental invoice
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: pay-invoice
- description: Find United Rentals branch locations near a zip code or in a state
  hints:
    openWorld: true
    readOnly: true
  name: list-locations
---
