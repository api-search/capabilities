---
categories: []
consumed_apis: []
description: The Bandwidth Emergency Calling API provides programmatic access to provision and manage 911 endpoints and locations for emergency services routing. It supports Dynamic Location Routing (DLR) for real-time address validation and location updates, ensuring compliance with Kari's Law and RAY BAUM's Act requirements. Bandwidth is the only CPaaS provider that also operates its own emergency services network, providing direct connectivity to public safety answering points (PSAPs) across the United States and Canada.
layout: capability
name: Bandwidth Emergency Calling API
operations:
- description: List E911 endpoints
  method: GET
  name: listendpoints
  path: /accounts/{accountId}/e911s
- description: Create an E911 endpoint
  method: POST
  name: createendpoint
  path: /accounts/{accountId}/e911s
- description: Get E911 endpoint details
  method: GET
  name: getendpoint
  path: /accounts/{accountId}/e911s/{endpointId}
- description: Update an E911 endpoint
  method: PUT
  name: updateendpoint
  path: /accounts/{accountId}/e911s/{endpointId}
- description: Delete an E911 endpoint
  method: DELETE
  name: deleteendpoint
  path: /accounts/{accountId}/e911s/{endpointId}
- description: List E911 locations
  method: GET
  name: listlocations
  path: /accounts/{accountId}/e911s/locations
- description: Create an E911 location
  method: POST
  name: createlocation
  path: /accounts/{accountId}/e911s/locations
- description: Get E911 location details
  method: GET
  name: getlocation
  path: /accounts/{accountId}/e911s/locations/{locationId}
- description: Update an E911 location
  method: PUT
  name: updatelocation
  path: /accounts/{accountId}/e911s/locations/{locationId}
- description: Delete an E911 location
  method: DELETE
  name: deletelocation
  path: /accounts/{accountId}/e911s/locations/{locationId}
- description: List emergency notification recipients
  method: GET
  name: listnotificationrecipients
  path: /accounts/{accountId}/e911s/notificationRecipients
- description: Create a notification recipient
  method: POST
  name: createnotificationrecipient
  path: /accounts/{accountId}/e911s/notificationRecipients
personas: []
provider_name: Bandwidth
provider_slug: bandwidth
search_terms:
- createendpoint
- listlocations
- list e911 endpoints
- deletelocation
- create an e911 location
- search, order, and manage telephone numbers
- mfa
- delete an e911 location
- api
- multi-factor authentication via voice or sms
- administrator managing bandwidth account, numbers, and compliance
- createlocation
- outbound and inbound voice call management and recording
- deleteendpoint
- update an e911 location
- Application Developer
- bandwidth
- telephony
- listendpoints
- list e911 locations
- create a notification recipient
- createnotificationrecipient
- sms
- cpaas
- update an e911 endpoint
- delete an e911 endpoint
- getendpoint
- get e911 location details
- developer building communication-enabled web or mobile applications
- list emergency notification recipients
- getlocation
- get e911 endpoint details
- Platform Administrator
- engineer designing and operating telephony and messaging infrastructure
- unified voice, messaging, mfa, phone numbers, e911, and toll-free management
- voice
- create an e911 endpoint
- sms and mms message delivery and media management
- e911 endpoint registration and management
- messaging
- updatelocation
- listnotificationrecipients
- updateendpoint
- Communications Engineer
- communications
slug: bandwidth-capability
source_filename: bandwidth-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Bandwidth Emergency Calling API\n  description: The Bandwidth Emergency Calling API provides programmatic access to provision and manage 911 endpoints and\n    locations for emergency services routing. It supports Dynamic Location Routing (DLR) for real-time address validation\n    and location updates, ensuring compliance with Kari's Law and RAY BAUM's Act requirements. Bandwidth is the only CPaaS\n    provider that also operates its own emergency services network, providing direct connectivity to public safety answering\n    points (PSAPs) across the United States and Canada.\n  tags:\n  - Bandwidth\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: bandwidth\n    baseUri: https://dashboard.bandwidth.com/api\n    description: Bandwidth Emergency Calling API HTTP API.\n    authentication:\n      type: basic\n      username: '{{BANDWIDTH_USERNAME}}'\n      password: '{{BANDWIDTH_PASSWORD}}'\n\
  \    resources:\n    - name: accounts-accountid-e911s\n      path: /accounts/{accountId}/e911s\n      operations:\n      - name: listendpoints\n        method: GET\n        description: List E911 endpoints\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createendpoint\n        method: POST\n        description: Create an E911 endpoint\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounts-accountid-e911s-endpointid\n      path: /accounts/{accountId}/e911s/{endpointId}\n      operations:\n      - name: getendpoint\n        method: GET\n        description: Get E911 endpoint details\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateendpoint\n        method: PUT\n        description: Update an E911 endpoint\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteendpoint\n        method: DELETE\n        description: Delete an E911 endpoint\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounts-accountid-e911s-locations\n      path: /accounts/{accountId}/e911s/locations\n      operations:\n      - name: listlocations\n        method: GET\n        description: List E911 locations\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createlocation\n        method: POST\n        description: Create an E911 location\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounts-accountid-e911s-locations-locationid\n      path: /accounts/{accountId}/e911s/locations/{locationId}\n\
  \      operations:\n      - name: getlocation\n        method: GET\n        description: Get E911 location details\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatelocation\n        method: PUT\n        description: Update an E911 location\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletelocation\n        method: DELETE\n        description: Delete an E911 location\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounts-accountid-e911s-notificationrecipients\n      path: /accounts/{accountId}/e911s/notificationRecipients\n      operations:\n      - name: listnotificationrecipients\n        method: GET\n        description: List emergency notification recipients\n        outputRawFormat: json\n      \
  \  outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createnotificationrecipient\n        method: POST\n        description: Create a notification recipient\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: bandwidth-rest\n    description: REST adapter for Bandwidth Emergency Calling API.\n    resources:\n    - path: /accounts/{accountId}/e911s\n      name: listendpoints\n      operations:\n      - method: GET\n        name: listendpoints\n        description: List E911 endpoints\n        call: bandwidth.listendpoints\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounts/{accountId}/e911s\n      name: createendpoint\n      operations:\n      - method: POST\n        name: createendpoint\n        description: Create an E911 endpoint\n        call: bandwidth.createendpoint\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounts/{accountId}/e911s/{endpointId}\n      name: getendpoint\n      operations:\n      - method: GET\n        name: getendpoint\n        description: Get E911 endpoint details\n        call: bandwidth.getendpoint\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounts/{accountId}/e911s/{endpointId}\n      name: updateendpoint\n      operations:\n      - method: PUT\n        name: updateendpoint\n        description: Update an E911 endpoint\n        call: bandwidth.updateendpoint\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounts/{accountId}/e911s/{endpointId}\n      name: deleteendpoint\n      operations:\n      - method: DELETE\n        name: deleteendpoint\n        description: Delete an E911 endpoint\n        call: bandwidth.deleteendpoint\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /accounts/{accountId}/e911s/locations\n      name: listlocations\n      operations:\n      - method: GET\n        name: listlocations\n        description: List E911 locations\n        call: bandwidth.listlocations\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounts/{accountId}/e911s/locations\n      name: createlocation\n      operations:\n      - method: POST\n        name: createlocation\n        description: Create an E911 location\n        call: bandwidth.createlocation\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounts/{accountId}/e911s/locations/{locationId}\n      name: getlocation\n      operations:\n      - method: GET\n        name: getlocation\n        description: Get E911 location details\n        call: bandwidth.getlocation\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounts/{accountId}/e911s/locations/{locationId}\n  \
  \    name: updatelocation\n      operations:\n      - method: PUT\n        name: updatelocation\n        description: Update an E911 location\n        call: bandwidth.updatelocation\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounts/{accountId}/e911s/locations/{locationId}\n      name: deletelocation\n      operations:\n      - method: DELETE\n        name: deletelocation\n        description: Delete an E911 location\n        call: bandwidth.deletelocation\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounts/{accountId}/e911s/notificationRecipients\n      name: listnotificationrecipients\n      operations:\n      - method: GET\n        name: listnotificationrecipients\n        description: List emergency notification recipients\n        call: bandwidth.listnotificationrecipients\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounts/{accountId}/e911s/notificationRecipients\n\
  \      name: createnotificationrecipient\n      operations:\n      - method: POST\n        name: createnotificationrecipient\n        description: Create a notification recipient\n        call: bandwidth.createnotificationrecipient\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: bandwidth-mcp\n    transport: http\n    description: MCP adapter for Bandwidth Emergency Calling API for AI agent use.\n    tools:\n    - name: listendpoints\n      description: List E911 endpoints\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: bandwidth.listendpoints\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createendpoint\n      description: Create an E911 endpoint\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: bandwidth.createendpoint\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n    - name: getendpoint\n      description: Get E911 endpoint details\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: bandwidth.getendpoint\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateendpoint\n      description: Update an E911 endpoint\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: bandwidth.updateendpoint\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteendpoint\n      description: Delete an E911 endpoint\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: bandwidth.deleteendpoint\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listlocations\n      description: List E911 locations\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call:\
  \ bandwidth.listlocations\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createlocation\n      description: Create an E911 location\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: bandwidth.createlocation\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getlocation\n      description: Get E911 location details\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: bandwidth.getlocation\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatelocation\n      description: Update an E911 location\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: bandwidth.updatelocation\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletelocation\n      description: Delete an E911 location\n      hints:\n        readOnly:\
  \ false\n        destructive: true\n        idempotent: true\n      call: bandwidth.deletelocation\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listnotificationrecipients\n      description: List emergency notification recipients\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: bandwidth.listnotificationrecipients\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createnotificationrecipient\n      description: Create a notification recipient\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: bandwidth.createnotificationrecipient\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    BANDWIDTH_USERNAME: BANDWIDTH_USERNAME\n    BANDWIDTH_PASSWORD: BANDWIDTH_PASSWORD\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/bandwidth/refs/heads/main/capabilities/bandwidth-capability.yaml
tags:
- Bandwidth
- API
tools:
- description: List E911 endpoints
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listendpoints
- description: Create an E911 endpoint
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createendpoint
- description: Get E911 endpoint details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getendpoint
- description: Update an E911 endpoint
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateendpoint
- description: Delete an E911 endpoint
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteendpoint
- description: List E911 locations
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listlocations
- description: Create an E911 location
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createlocation
- description: Get E911 location details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getlocation
- description: Update an E911 location
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatelocation
- description: Delete an E911 location
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletelocation
- description: List emergency notification recipients
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listnotificationrecipients
- description: Create a notification recipient
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createnotificationrecipient
---
