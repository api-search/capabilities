---
categories: []
consumed_apis: []
description: The GunTab REST API allows online firearms marketplaces and retail websites to integrate safe and convenient firearms payment processing, manage invoices (payment requests), confirm and fulfill orders, validate FFLs, and receive webhook events for transaction lifecycle changes.
layout: capability
name: GunTab REST API
operations:
- description: Create an invoice
  method: POST
  name: createinvoice
  path: /invoices
- description: Read an invoice
  method: GET
  name: readinvoice
  path: /invoices/{id}
- description: Cancel an invoice
  method: POST
  name: cancelinvoice
  path: /invoices/{id}/cancels
- description: Confirm an invoice as the platform
  method: POST
  name: platformconfirminvoice
  path: /invoices/{id}/platform_confirmations
- description: Confirm an invoice as the seller
  method: POST
  name: sellerconfirminvoice
  path: /invoices/{id}/seller_confirmations
- description: Fulfill an invoice
  method: POST
  name: fulfillinvoice
  path: /invoices/{id}/fulfillments
- description: Read a user
  method: GET
  name: readuser
  path: /users/{email}
- description: Trigger FFL verification call
  method: POST
  name: callfflverification
  path: /ffls/{license_number}/claim_verification_code_calls
- description: Create webhook (deprecated)
  method: POST
  name: createwebhook
  path: /webhooks
- description: Read webhook (deprecated)
  method: GET
  name: readwebhook
  path: /webhooks/{id}
- description: Delete webhook (deprecated)
  method: DELETE
  name: deletewebhook
  path: /webhooks/{id}
personas: []
provider_name: GunTab
provider_slug: guntab
search_terms:
- confirm an invoice as the platform
- create webhook (deprecated)
- readwebhook
- readinvoice
- api
- readuser
- fulfill an invoice
- createwebhook
- confirm an invoice as the seller
- trigger ffl verification call
- cancelinvoice
- cancel an invoice
- e-commerce
- marketplace
- read a user
- read an invoice
- firearms
- read webhook (deprecated)
- fulfillinvoice
- create an invoice
- sellerconfirminvoice
- guntab
- platformconfirminvoice
- payments
- deletewebhook
- delete webhook (deprecated)
- createinvoice
- callfflverification
slug: guntab-capability
source_filename: guntab-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: GunTab REST API\n  description: The GunTab REST API allows online firearms marketplaces and retail websites to integrate safe and convenient\n    firearms payment processing, manage invoices (payment requests), confirm and fulfill orders, validate FFLs, and receive\n    webhook events for transaction lifecycle changes.\n  tags:\n  - Guntab\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: guntab\n    baseUri: https://api.guntab.com/v1\n    description: GunTab REST API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: Authorization\n      value: '{{GUNTAB_TOKEN}}'\n    resources:\n    - name: invoices\n      path: /invoices\n      operations:\n      - name: createinvoice\n        method: POST\n        description: Create an invoice\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n    - name: invoices-id\n      path: /invoices/{id}\n      operations:\n      - name: readinvoice\n        method: GET\n        description: Read an invoice\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: invoices-id-cancels\n      path: /invoices/{id}/cancels\n      operations:\n      - name: cancelinvoice\n        method: POST\n        description: Cancel an invoice\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: invoices-id-platform-confirmations\n      path: /invoices/{id}/platform_confirmations\n      operations:\n      - name: platformconfirminvoice\n        method: POST\n        description: Confirm an invoice as the platform\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: invoices-id-seller-confirmations\n\
  \      path: /invoices/{id}/seller_confirmations\n      operations:\n      - name: sellerconfirminvoice\n        method: POST\n        description: Confirm an invoice as the seller\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: invoices-id-fulfillments\n      path: /invoices/{id}/fulfillments\n      operations:\n      - name: fulfillinvoice\n        method: POST\n        description: Fulfill an invoice\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users-email\n      path: /users/{email}\n      operations:\n      - name: readuser\n        method: GET\n        description: Read a user\n        inputParameters:\n        - name: email\n          in: path\n          type: string\n          required: true\n          description: URL-encoded email address.\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: ffls-license-number-claim-verification-code-call\n      path: /ffls/{license_number}/claim_verification_code_calls\n      operations:\n      - name: callfflverification\n        method: POST\n        description: Trigger FFL verification call\n        inputParameters:\n        - name: license_number\n          in: path\n          type: string\n          required: true\n          description: FFL license number.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: webhooks\n      path: /webhooks\n      operations:\n      - name: createwebhook\n        method: POST\n        description: Create webhook (deprecated)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: webhooks-id\n      path: /webhooks/{id}\n      operations:\n      - name:\
  \ readwebhook\n        method: GET\n        description: Read webhook (deprecated)\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletewebhook\n        method: DELETE\n        description: Delete webhook (deprecated)\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: guntab-rest\n    description: REST adapter for GunTab REST API.\n    resources:\n    - path: /invoices\n      name: createinvoice\n      operations:\n      - method: POST\n        name: createinvoice\n        description: Create an invoice\n        call: guntab.createinvoice\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /invoices/{id}\n      name: readinvoice\n      operations:\n      - method: GET\n        name: readinvoice\n        description: Read an invoice\n        call: guntab.readinvoice\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /invoices/{id}/cancels\n      name: cancelinvoice\n      operations:\n      - method: POST\n        name: cancelinvoice\n        description: Cancel an invoice\n        call: guntab.cancelinvoice\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /invoices/{id}/platform_confirmations\n      name: platformconfirminvoice\n      operations:\n      - method: POST\n        name: platformconfirminvoice\n        description: Confirm an invoice as the platform\n        call: guntab.platformconfirminvoice\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /invoices/{id}/seller_confirmations\n\
  \      name: sellerconfirminvoice\n      operations:\n      - method: POST\n        name: sellerconfirminvoice\n        description: Confirm an invoice as the seller\n        call: guntab.sellerconfirminvoice\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /invoices/{id}/fulfillments\n      name: fulfillinvoice\n      operations:\n      - method: POST\n        name: fulfillinvoice\n        description: Fulfill an invoice\n        call: guntab.fulfillinvoice\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users/{email}\n      name: readuser\n      operations:\n      - method: GET\n        name: readuser\n        description: Read a user\n        call: guntab.readuser\n        with:\n          email: rest.email\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /ffls/{license_number}/claim_verification_code_calls\n      name: callfflverification\n      operations:\n      - method:\
  \ POST\n        name: callfflverification\n        description: Trigger FFL verification call\n        call: guntab.callfflverification\n        with:\n          license_number: rest.license_number\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /webhooks\n      name: createwebhook\n      operations:\n      - method: POST\n        name: createwebhook\n        description: Create webhook (deprecated)\n        call: guntab.createwebhook\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /webhooks/{id}\n      name: readwebhook\n      operations:\n      - method: GET\n        name: readwebhook\n        description: Read webhook (deprecated)\n        call: guntab.readwebhook\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /webhooks/{id}\n      name: deletewebhook\n      operations:\n      - method: DELETE\n        name: deletewebhook\n     \
  \   description: Delete webhook (deprecated)\n        call: guntab.deletewebhook\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: guntab-mcp\n    transport: http\n    description: MCP adapter for GunTab REST API for AI agent use.\n    tools:\n    - name: createinvoice\n      description: Create an invoice\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: guntab.createinvoice\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: readinvoice\n      description: Read an invoice\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: guntab.readinvoice\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: cancelinvoice\n      description: Cancel an invoice\n      hints:\n        readOnly: false\n        destructive: false\n\
  \        idempotent: false\n      call: guntab.cancelinvoice\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: platformconfirminvoice\n      description: Confirm an invoice as the platform\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: guntab.platformconfirminvoice\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: sellerconfirminvoice\n      description: Confirm an invoice as the seller\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: guntab.sellerconfirminvoice\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: fulfillinvoice\n      description: Fulfill an invoice\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: guntab.fulfillinvoice\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: readuser\n\
  \      description: Read a user\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: guntab.readuser\n      with:\n        email: tools.email\n      inputParameters:\n      - name: email\n        type: string\n        description: URL-encoded email address.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: callfflverification\n      description: Trigger FFL verification call\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: guntab.callfflverification\n      with:\n        license_number: tools.license_number\n      inputParameters:\n      - name: license_number\n        type: string\n        description: FFL license number.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createwebhook\n      description: Create webhook (deprecated)\n      hints:\n        readOnly: false\n\
  \        destructive: false\n        idempotent: false\n      call: guntab.createwebhook\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: readwebhook\n      description: Read webhook (deprecated)\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: guntab.readwebhook\n      with:\n        id: tools.id\n      inputParameters:\n      - name: id\n        type: string\n        description: id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletewebhook\n      description: Delete webhook (deprecated)\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: guntab.deletewebhook\n      with:\n        id: tools.id\n      inputParameters:\n      - name: id\n        type: string\n        description: id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace:\
  \ env\n  keys:\n    GUNTAB_TOKEN: GUNTAB_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/guntab/refs/heads/main/capabilities/guntab-capability.yaml
tags:
- Guntab
- API
tools:
- description: Create an invoice
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createinvoice
- description: Read an invoice
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: readinvoice
- description: Cancel an invoice
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: cancelinvoice
- description: Confirm an invoice as the platform
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: platformconfirminvoice
- description: Confirm an invoice as the seller
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: sellerconfirminvoice
- description: Fulfill an invoice
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: fulfillinvoice
- description: Read a user
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: readuser
- description: Trigger FFL verification call
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: callfflverification
- description: Create webhook (deprecated)
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createwebhook
- description: Read webhook (deprecated)
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: readwebhook
- description: Delete webhook (deprecated)
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletewebhook
---
