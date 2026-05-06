---
categories: []
consumed_apis: []
description: Unified shipping fulfillment workflow combining address validation, multi-carrier rate shopping, label generation, and package tracking. Designed for ecommerce developers and operations teams needing end-to-end shipping automation.
layout: capability
name: Shippo Shipping Fulfillment
operations:
- description: List all addresses
  method: GET
  name: list-addresses
  path: /v1/addresses
- description: Create a new shipping address
  method: POST
  name: create-address
  path: /v1/addresses
- description: Validate address deliverability
  method: GET
  name: validate-address
  path: /v1/addresses/{id}/validate
- description: List all shipments
  method: GET
  name: list-shipments
  path: /v1/shipments
- description: Create a shipment to compare carrier rates
  method: POST
  name: create-shipment
  path: /v1/shipments
- description: Get available rates for a shipment
  method: GET
  name: get-rates
  path: /v1/shipments/{id}/rates
- description: List all purchased labels
  method: GET
  name: list-labels
  path: /v1/labels
- description: Purchase a shipping label
  method: POST
  name: purchase-label
  path: /v1/labels
- description: Get real-time tracking status
  method: GET
  name: track-shipment
  path: /v1/tracking/{carrier}/{tracking-number}
- description: Request a label refund
  method: POST
  name: request-refund
  path: /v1/refunds
- description: List connected carrier accounts
  method: GET
  name: list-carriers
  path: /v1/carriers
personas: []
provider_name: Shippo
provider_slug: shippo
search_terms:
- get shipping rates
- request refund
- logistics
- manage carrier account connections
- validate address
- request a label refund
- create shipments and retrieve carrier rates
- create shipping address
- returns
- create a shipment to compare carrier rates
- list all purchased shipping labels with tracking status
- create a new shipping address
- list all purchased labels
- list carrier accounts
- get real-time tracking status
- get carrier shipping rates
- purchase shipping label
- list all shipments with optional status filter
- labels
- request a refund for a purchased but unused shipping label
- fulfillment
- track shipments across carriers
- list all shipments
- track shipment
- validate a shipping address
- list connected carrier accounts
- ecommerce
- shipping
- create address
- list carriers
- create a new shipment from origin to destination to get available carrier rates
- manage and validate shipping addresses
- list all connected carrier accounts and their status
- validate that a shipping address is deliverable by carriers
- track package
- create shipment
- purchase label
- validate address deliverability
- list labels
- request label refunds
- get available carrier rates for a shipment including price and transit time
- get rates
- get available rates for a shipment
- purchase and manage shipping labels
- purchase a shipping label
- get real-time tracking status for a shipped package
- list addresses
- validate shipping address
- purchase a shipping label from a selected carrier rate
- list all addresses
- create a new shipping address for use in shipments
- request label refund
- list shipments
- tracking
- list purchased labels
slug: shipping-fulfillment
source_filename: shipping-fulfillment.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Shippo Shipping Fulfillment\n  description: Unified shipping fulfillment workflow combining address validation, multi-carrier rate shopping, label generation,\n    and package tracking. Designed for ecommerce developers and operations teams needing end-to-end shipping automation.\n  tags:\n  - Shipping\n  - Ecommerce\n  - Labels\n  - Tracking\n  - Logistics\n  - Fulfillment\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SHIPPO_API_TOKEN: SHIPPO_API_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: shippo\n    baseUri: https://api.goshippo.com\n    description: Shippo multi-carrier shipping API\n    authentication:\n      type: bearer\n      token: '{{SHIPPO_API_TOKEN}}'\n    resources:\n    - name: addresses\n      path: /addresses\n      description: Manage and validate shipping addresses\n      operations:\n      - name: list-addresses\n        method: GET\n        description:\
  \ List all address objects\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number\n        - name: results\n          in: query\n          type: integer\n          required: false\n          description: Results per page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-address\n        method: POST\n        description: Create a new shipping address\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            street1: '{{tools.street1}}'\n            city: '{{tools.city}}'\n            state: '{{tools.state}}'\n            zip: '{{tools.zip}}'\n            country: '{{tools.country}}'\n      - name: validate-address\n   \
  \     method: GET\n        description: Validate an existing address\n        inputParameters:\n        - name: AddressId\n          in: path\n          type: string\n          required: true\n          description: Address object ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: shipments\n      path: /shipments\n      description: Create and manage shipments\n      operations:\n      - name: list-shipments\n        method: GET\n        description: List all shipments\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number\n        - name: results\n          in: query\n          type: integer\n          required: false\n          description: Results per page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name:\
  \ create-shipment\n        method: POST\n        description: Create a shipment to retrieve carrier rates\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            address_from: '{{tools.address_from}}'\n            address_to: '{{tools.address_to}}'\n            parcels: '{{tools.parcels}}'\n    - name: rates\n      path: /shipments/{ShipmentId}/rates\n      description: Retrieve shipping rates for a shipment\n      operations:\n      - name: get-shipment-rates\n        method: GET\n        description: Get all carrier rates for a shipment\n        inputParameters:\n        - name: ShipmentId\n          in: path\n          type: string\n          required: true\n          description: Shipment object ID\n        - name: currency_code\n          in: query\n          type: string\n          required: false\n          description: Currency code for rate\
  \ amounts\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: transactions\n      path: /transactions\n      description: Purchase shipping labels\n      operations:\n      - name: list-transactions\n        method: GET\n        description: List all purchased labels\n        inputParameters:\n        - name: tracking_status\n          in: query\n          type: string\n          required: false\n          description: Filter by tracking status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: purchase-label\n        method: POST\n        description: Purchase a shipping label from a selected rate\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            rate: '{{tools.rate_id}}'\n\
  \            label_file_type: '{{tools.label_file_type}}'\n    - name: tracking\n      path: /tracks/{Carrier}/{TrackingNumber}\n      description: Track shipments across carriers\n      operations:\n      - name: get-tracking-status\n        method: GET\n        description: Get real-time tracking status for a shipment\n        inputParameters:\n        - name: Carrier\n          in: path\n          type: string\n          required: true\n          description: Carrier code (e.g., usps, fedex, ups)\n        - name: TrackingNumber\n          in: path\n          type: string\n          required: true\n          description: Shipment tracking number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: refunds\n      path: /refunds\n      description: Request label refunds\n      operations:\n      - name: create-refund\n        method: POST\n        description: Request a refund for a purchased label\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            transaction: '{{tools.transaction_id}}'\n    - name: carrier-accounts\n      path: /carrier_accounts\n      description: Manage carrier account integrations\n      operations:\n      - name: list-carrier-accounts\n        method: GET\n        description: List all connected carrier accounts\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: webhooks\n      path: /webhooks\n      description: Manage webhook subscriptions\n      operations:\n      - name: list-webhooks\n        method: GET\n        description: List all webhook subscriptions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-webhook\n        method:\
  \ POST\n        description: Create a new webhook subscription\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            url: '{{tools.webhook_url}}'\n            event: '{{tools.event_type}}'\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: shippo-fulfillment-api\n    description: Unified REST API for end-to-end shipping fulfillment with multi-carrier support.\n    resources:\n    - path: /v1/addresses\n      name: addresses\n      description: Manage and validate shipping addresses\n      operations:\n      - method: GET\n        name: list-addresses\n        description: List all addresses\n        call: shippo.list-addresses\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-address\n        description: Create a new shipping address\n        call: shippo.create-address\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/addresses/{id}/validate\n      name: address-validation\n      description: Validate a shipping address\n      operations:\n      - method: GET\n        name: validate-address\n        description: Validate address deliverability\n        call: shippo.validate-address\n        with:\n          AddressId: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/shipments\n      name: shipments\n      description: Create shipments and retrieve carrier rates\n      operations:\n      - method: GET\n        name: list-shipments\n        description: List all shipments\n        call: shippo.list-shipments\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-shipment\n        description: Create a shipment to compare carrier rates\n        call: shippo.create-shipment\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /v1/shipments/{id}/rates\n      name: rates\n      description: Get carrier shipping rates\n      operations:\n      - method: GET\n        name: get-rates\n        description: Get available rates for a shipment\n        call: shippo.get-shipment-rates\n        with:\n          ShipmentId: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/labels\n      name: labels\n      description: Purchase and manage shipping labels\n      operations:\n      - method: GET\n        name: list-labels\n        description: List all purchased labels\n        call: shippo.list-transactions\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: purchase-label\n        description: Purchase a shipping label\n        call: shippo.purchase-label\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/tracking/{carrier}/{tracking-number}\n\
  \      name: tracking\n      description: Track shipments across carriers\n      operations:\n      - method: GET\n        name: track-shipment\n        description: Get real-time tracking status\n        call: shippo.get-tracking-status\n        with:\n          Carrier: rest.carrier\n          TrackingNumber: rest.tracking-number\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/refunds\n      name: refunds\n      description: Request label refunds\n      operations:\n      - method: POST\n        name: request-refund\n        description: Request a label refund\n        call: shippo.create-refund\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/carriers\n      name: carriers\n      description: Manage carrier account connections\n      operations:\n      - method: GET\n        name: list-carriers\n        description: List connected carrier accounts\n        call: shippo.list-carrier-accounts\n      \
  \  outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: shippo-fulfillment-mcp\n    transport: http\n    description: MCP server for AI-assisted shipping fulfillment and logistics operations.\n    tools:\n    - name: validate-shipping-address\n      description: Validate that a shipping address is deliverable by carriers\n      hints:\n        readOnly: true\n        openWorld: true\n      call: shippo.validate-address\n      with:\n        AddressId: tools.address_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-shipping-address\n      description: Create a new shipping address for use in shipments\n      hints:\n        readOnly: false\n      call: shippo.create-address\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-shipment\n      description: Create a new shipment from origin to destination to get available carrier rates\n      hints:\n     \
  \   readOnly: false\n      call: shippo.create-shipment\n      with:\n        address_from: tools.address_from\n        address_to: tools.address_to\n        parcels: tools.parcels\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-shipping-rates\n      description: Get available carrier rates for a shipment including price and transit time\n      hints:\n        readOnly: true\n      call: shippo.get-shipment-rates\n      with:\n        ShipmentId: tools.shipment_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: purchase-shipping-label\n      description: Purchase a shipping label from a selected carrier rate\n      hints:\n        readOnly: false\n      call: shippo.purchase-label\n      with:\n        rate_id: tools.rate_id\n        label_file_type: tools.label_file_type\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: track-package\n      description: Get real-time tracking status for\
  \ a shipped package\n      hints:\n        readOnly: true\n        openWorld: true\n      call: shippo.get-tracking-status\n      with:\n        Carrier: tools.carrier_code\n        TrackingNumber: tools.tracking_number\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-shipments\n      description: List all shipments with optional status filter\n      hints:\n        readOnly: true\n      call: shippo.list-shipments\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-purchased-labels\n      description: List all purchased shipping labels with tracking status\n      hints:\n        readOnly: true\n      call: shippo.list-transactions\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: request-label-refund\n      description: Request a refund for a purchased but unused shipping label\n      hints:\n        readOnly: false\n        destructive: false\n      call: shippo.create-refund\n     \
  \ with:\n        transaction_id: tools.transaction_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-carrier-accounts\n      description: List all connected carrier accounts and their status\n      hints:\n        readOnly: true\n      call: shippo.list-carrier-accounts\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/shippo/refs/heads/main/capabilities/shipping-fulfillment.yaml
tags:
- Shipping
- Ecommerce
- Labels
- Tracking
- Logistics
- Fulfillment
tools:
- description: Validate that a shipping address is deliverable by carriers
  hints:
    openWorld: true
    readOnly: true
  name: validate-shipping-address
- description: Create a new shipping address for use in shipments
  hints:
    readOnly: false
  name: create-shipping-address
- description: Create a new shipment from origin to destination to get available carrier rates
  hints:
    readOnly: false
  name: create-shipment
- description: Get available carrier rates for a shipment including price and transit time
  hints:
    readOnly: true
  name: get-shipping-rates
- description: Purchase a shipping label from a selected carrier rate
  hints:
    readOnly: false
  name: purchase-shipping-label
- description: Get real-time tracking status for a shipped package
  hints:
    openWorld: true
    readOnly: true
  name: track-package
- description: List all shipments with optional status filter
  hints:
    readOnly: true
  name: list-shipments
- description: List all purchased shipping labels with tracking status
  hints:
    readOnly: true
  name: list-purchased-labels
- description: Request a refund for a purchased but unused shipping label
  hints:
    destructive: false
    readOnly: false
  name: request-label-refund
- description: List all connected carrier accounts and their status
  hints:
    readOnly: true
  name: list-carrier-accounts
---
