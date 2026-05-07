---
categories: []
consumed_apis: []
description: The Pitney Bowes Shipping API enables businesses to integrate shipping, rating, tracking, address validation, manifesting, and pickup operations directly into their applications. Authentication uses OAuth 2.0 client credentials.
layout: capability
name: Pitney Bowes Shipping API
operations:
- description: Get OAuth access token
  method: POST
  name: getoauthtoken
  path: /oauth/token
- description: Rate a parcel
  method: POST
  name: rateparcel
  path: /shippingservices/v1/rates
- description: Create a shipment
  method: POST
  name: createshipment
  path: /shippingservices/v1/shipments
- description: Reprint a shipment label
  method: GET
  name: reprintshipment
  path: /shippingservices/v1/shipments/{shipmentId}
- description: Void a shipment
  method: DELETE
  name: voidshipment
  path: /shippingservices/v1/shipments/{shipmentId}
- description: Create a manifest
  method: POST
  name: createmanifest
  path: /shippingservices/v1/manifests
- description: Track a parcel
  method: GET
  name: trackparcel
  path: /shippingservices/v1/tracking/{trackingNumber}
- description: Validate and suggest addresses
  method: POST
  name: verifyaddress
  path: /shippingservices/v1/addresses/verify
- description: Schedule a pickup
  method: POST
  name: schedulepickup
  path: /shippingservices/v1/pickups
- description: Cancel a pickup
  method: DELETE
  name: cancelpickup
  path: /shippingservices/v1/pickups/{pickupId}
- description: Retrieve transaction report
  method: GET
  name: gettransactionreport
  path: /shippingservices/v1/ledger/transactions/reports
personas: []
provider_name: Pitney Bowes
provider_slug: pitney-bowes
search_terms:
- create a shipment
- verifyaddress
- void a shipment
- getoauthtoken
- api
- trackparcel
- reprintshipment
- create a manifest
- createmanifest
- mailing
- get oauth access token
- cancelpickup
- schedule a pickup
- gettransactionreport
- rate a parcel
- createshipment
- track a parcel
- validate and suggest addresses
- cancel a pickup
- bowes
- reprint a shipment label
- retrieve transaction report
- schedulepickup
- pitney
- shipping
- voidshipment
- rateparcel
slug: pitney-bowes-capability
source_filename: pitney-bowes-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Pitney Bowes Shipping API\n  description: The Pitney Bowes Shipping API enables businesses to integrate shipping, rating, tracking, address validation,\n    manifesting, and pickup operations directly into their applications. Authentication uses OAuth 2.0 client credentials.\n  tags:\n  - Pitney\n  - Bowes\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: pitney-bowes\n    baseUri: https://shipping-api.pitneybowes.com\n    description: Pitney Bowes Shipping API HTTP API.\n    authentication:\n      type: basic\n      username: '{{PITNEY_BOWES_USERNAME}}'\n      password: '{{PITNEY_BOWES_PASSWORD}}'\n    resources:\n    - name: oauth-token\n      path: /oauth/token\n      operations:\n      - name: getoauthtoken\n        method: POST\n        description: Get OAuth access token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n         \
  \ type: object\n          value: $.\n    - name: shippingservices-v1-rates\n      path: /shippingservices/v1/rates\n      operations:\n      - name: rateparcel\n        method: POST\n        description: Rate a parcel\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: shippingservices-v1-shipments\n      path: /shippingservices/v1/shipments\n      operations:\n      - name: createshipment\n        method: POST\n        description: Create a shipment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: shippingservices-v1-shipments-shipmentid\n      path: /shippingservices/v1/shipments/{shipmentId}\n      operations:\n      - name: reprintshipment\n        method: GET\n        description: Reprint a shipment label\n        inputParameters:\n        - name: shipmentId\n          in: path\n          type: string\n \
  \         required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: voidshipment\n        method: DELETE\n        description: Void a shipment\n        inputParameters:\n        - name: shipmentId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: shippingservices-v1-manifests\n      path: /shippingservices/v1/manifests\n      operations:\n      - name: createmanifest\n        method: POST\n        description: Create a manifest\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: shippingservices-v1-tracking-trackingnumber\n      path: /shippingservices/v1/tracking/{trackingNumber}\n      operations:\n      - name: trackparcel\n        method: GET\n\
  \        description: Track a parcel\n        inputParameters:\n        - name: trackingNumber\n          in: path\n          type: string\n          required: true\n        - name: carrier\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: shippingservices-v1-addresses-verify\n      path: /shippingservices/v1/addresses/verify\n      operations:\n      - name: verifyaddress\n        method: POST\n        description: Validate and suggest addresses\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: shippingservices-v1-pickups\n      path: /shippingservices/v1/pickups\n      operations:\n      - name: schedulepickup\n        method: POST\n        description: Schedule a pickup\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n         \
  \ type: object\n          value: $.\n    - name: shippingservices-v1-pickups-pickupid\n      path: /shippingservices/v1/pickups/{pickupId}\n      operations:\n      - name: cancelpickup\n        method: DELETE\n        description: Cancel a pickup\n        inputParameters:\n        - name: pickupId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: shippingservices-v1-ledger-transactions-reports\n      path: /shippingservices/v1/ledger/transactions/reports\n      operations:\n      - name: gettransactionreport\n        method: GET\n        description: Retrieve transaction report\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: pitney-bowes-rest\n    description: REST adapter for Pitney Bowes Shipping\
  \ API.\n    resources:\n    - path: /oauth/token\n      name: getoauthtoken\n      operations:\n      - method: POST\n        name: getoauthtoken\n        description: Get OAuth access token\n        call: pitney-bowes.getoauthtoken\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /shippingservices/v1/rates\n      name: rateparcel\n      operations:\n      - method: POST\n        name: rateparcel\n        description: Rate a parcel\n        call: pitney-bowes.rateparcel\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /shippingservices/v1/shipments\n      name: createshipment\n      operations:\n      - method: POST\n        name: createshipment\n        description: Create a shipment\n        call: pitney-bowes.createshipment\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /shippingservices/v1/shipments/{shipmentId}\n      name: reprintshipment\n      operations:\n      -\
  \ method: GET\n        name: reprintshipment\n        description: Reprint a shipment label\n        call: pitney-bowes.reprintshipment\n        with:\n          shipmentId: rest.shipmentId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /shippingservices/v1/shipments/{shipmentId}\n      name: voidshipment\n      operations:\n      - method: DELETE\n        name: voidshipment\n        description: Void a shipment\n        call: pitney-bowes.voidshipment\n        with:\n          shipmentId: rest.shipmentId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /shippingservices/v1/manifests\n      name: createmanifest\n      operations:\n      - method: POST\n        name: createmanifest\n        description: Create a manifest\n        call: pitney-bowes.createmanifest\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /shippingservices/v1/tracking/{trackingNumber}\n      name: trackparcel\n\
  \      operations:\n      - method: GET\n        name: trackparcel\n        description: Track a parcel\n        call: pitney-bowes.trackparcel\n        with:\n          trackingNumber: rest.trackingNumber\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /shippingservices/v1/addresses/verify\n      name: verifyaddress\n      operations:\n      - method: POST\n        name: verifyaddress\n        description: Validate and suggest addresses\n        call: pitney-bowes.verifyaddress\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /shippingservices/v1/pickups\n      name: schedulepickup\n      operations:\n      - method: POST\n        name: schedulepickup\n        description: Schedule a pickup\n        call: pitney-bowes.schedulepickup\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /shippingservices/v1/pickups/{pickupId}\n      name: cancelpickup\n      operations:\n     \
  \ - method: DELETE\n        name: cancelpickup\n        description: Cancel a pickup\n        call: pitney-bowes.cancelpickup\n        with:\n          pickupId: rest.pickupId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /shippingservices/v1/ledger/transactions/reports\n      name: gettransactionreport\n      operations:\n      - method: GET\n        name: gettransactionreport\n        description: Retrieve transaction report\n        call: pitney-bowes.gettransactionreport\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: pitney-bowes-mcp\n    transport: http\n    description: MCP adapter for Pitney Bowes Shipping API for AI agent use.\n    tools:\n    - name: getoauthtoken\n      description: Get OAuth access token\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: pitney-bowes.getoauthtoken\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: rateparcel\n      description: Rate a parcel\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: pitney-bowes.rateparcel\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createshipment\n      description: Create a shipment\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: pitney-bowes.createshipment\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: reprintshipment\n      description: Reprint a shipment label\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: pitney-bowes.reprintshipment\n      with:\n        shipmentId: tools.shipmentId\n      inputParameters:\n      - name: shipmentId\n        type: string\n        description: shipmentId\n        required: true\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n    - name: voidshipment\n      description: Void a shipment\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: pitney-bowes.voidshipment\n      with:\n        shipmentId: tools.shipmentId\n      inputParameters:\n      - name: shipmentId\n        type: string\n        description: shipmentId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createmanifest\n      description: Create a manifest\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: pitney-bowes.createmanifest\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: trackparcel\n      description: Track a parcel\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: pitney-bowes.trackparcel\n      with:\n        trackingNumber: tools.trackingNumber\n        carrier: tools.carrier\n\
  \      inputParameters:\n      - name: trackingNumber\n        type: string\n        description: trackingNumber\n        required: true\n      - name: carrier\n        type: string\n        description: carrier\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: verifyaddress\n      description: Validate and suggest addresses\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: pitney-bowes.verifyaddress\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: schedulepickup\n      description: Schedule a pickup\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: pitney-bowes.schedulepickup\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: cancelpickup\n      description: Cancel a pickup\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: pitney-bowes.cancelpickup\n\
  \      with:\n        pickupId: tools.pickupId\n      inputParameters:\n      - name: pickupId\n        type: string\n        description: pickupId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: gettransactionreport\n      description: Retrieve transaction report\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: pitney-bowes.gettransactionreport\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    PITNEY_BOWES_USERNAME: PITNEY_BOWES_USERNAME\n    PITNEY_BOWES_PASSWORD: PITNEY_BOWES_PASSWORD\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/pitney-bowes/refs/heads/main/capabilities/pitney-bowes-capability.yaml
tags:
- Pitney
- Bowes
- API
tools:
- description: Get OAuth access token
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: getoauthtoken
- description: Rate a parcel
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: rateparcel
- description: Create a shipment
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createshipment
- description: Reprint a shipment label
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: reprintshipment
- description: Void a shipment
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: voidshipment
- description: Create a manifest
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createmanifest
- description: Track a parcel
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: trackparcel
- description: Validate and suggest addresses
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: verifyaddress
- description: Schedule a pickup
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: schedulepickup
- description: Cancel a pickup
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: cancelpickup
- description: Retrieve transaction report
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettransactionreport
---
