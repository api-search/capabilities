---
categories: []
consumed_apis: []
description: The OurPeople API uses common standards to allow easy read and write access to your data. OurPeople is a frontline communications platform that helps organizations communicate with deskless workers. The API is currently in closed beta.
layout: capability
name: OurPeople API
operations:
- description: Exchange client credentials for a token
  method: POST
  name: createtoken
  path: /v1/auth
- description: Refresh an access token
  method: POST
  name: refreshtoken
  path: /v1/auth/refresh
- description: List recent deliveries
  method: GET
  name: listdeliveries
  path: /v1/broadcasts/deliveries
- description: Get broadcast details
  method: GET
  name: getbroadcast
  path: /v1/broadcasts/{broadcastId}
- description: List delivery recipients
  method: GET
  name: listdeliveryrecipients
  path: /v1/broadcasts/deliveries/{deliveryId}/recipients
- description: List content recipients
  method: GET
  name: listcontentrecipients
  path: /v1/broadcasts/deliveries/{deliveryId}/contents/{contentId}/recipients
personas: []
provider_name: OurPeople
provider_slug: ourpeople
search_terms:
- createtoken
- exchange client credentials for a token
- listdeliveryrecipients
- list recent deliveries
- get broadcast details
- refreshtoken
- ourpeople
- listdeliveries
- getbroadcast
- refresh an access token
- api
- frontline
- list content recipients
- listcontentrecipients
- workforce
- list delivery recipients
- communications
slug: ourpeople-capability
source_filename: ourpeople-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: OurPeople API\n  description: The OurPeople API uses common standards to allow easy read and write access to your data. OurPeople is a frontline\n    communications platform that helps organizations communicate with deskless workers. The API is currently in closed beta.\n  tags:\n  - Ourpeople\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: ourpeople\n    baseUri: https://example-api.ourpeople.co\n    description: OurPeople API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{OURPEOPLE_TOKEN}}'\n    resources:\n    - name: v1-auth\n      path: /v1/auth\n      operations:\n      - name: createtoken\n        method: POST\n        description: Exchange client credentials for a token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-auth-refresh\n      path: /v1/auth/refresh\n\
  \      operations:\n      - name: refreshtoken\n        method: POST\n        description: Refresh an access token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-broadcasts-deliveries\n      path: /v1/broadcasts/deliveries\n      operations:\n      - name: listdeliveries\n        method: GET\n        description: List recent deliveries\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-broadcasts-broadcastid\n      path: /v1/broadcasts/{broadcastId}\n      operations:\n      - name: getbroadcast\n        method: GET\n        description: Get broadcast details\n        inputParameters:\n        - name: broadcastId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n    - name: v1-broadcasts-deliveries-deliveryid-recipients\n      path: /v1/broadcasts/deliveries/{deliveryId}/recipients\n      operations:\n      - name: listdeliveryrecipients\n        method: GET\n        description: List delivery recipients\n        inputParameters:\n        - name: deliveryId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-broadcasts-deliveries-deliveryid-contents-con\n      path: /v1/broadcasts/deliveries/{deliveryId}/contents/{contentId}/recipients\n      operations:\n      - name: listcontentrecipients\n        method: GET\n        description: List content recipients\n        inputParameters:\n        - name: deliveryId\n          in: path\n          type: string\n          required: true\n        - name: contentId\n          in: path\n          type: string\n          required: true\n    \
  \    - name: rating\n          in: query\n          type: integer\n          description: Filter by rating value when the content type is a rating.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: ourpeople-rest\n    description: REST adapter for OurPeople API.\n    resources:\n    - path: /v1/auth\n      name: createtoken\n      operations:\n      - method: POST\n        name: createtoken\n        description: Exchange client credentials for a token\n        call: ourpeople.createtoken\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/auth/refresh\n      name: refreshtoken\n      operations:\n      - method: POST\n        name: refreshtoken\n        description: Refresh an access token\n        call: ourpeople.refreshtoken\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path:\
  \ /v1/broadcasts/deliveries\n      name: listdeliveries\n      operations:\n      - method: GET\n        name: listdeliveries\n        description: List recent deliveries\n        call: ourpeople.listdeliveries\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/broadcasts/{broadcastId}\n      name: getbroadcast\n      operations:\n      - method: GET\n        name: getbroadcast\n        description: Get broadcast details\n        call: ourpeople.getbroadcast\n        with:\n          broadcastId: rest.broadcastId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/broadcasts/deliveries/{deliveryId}/recipients\n      name: listdeliveryrecipients\n      operations:\n      - method: GET\n        name: listdeliveryrecipients\n        description: List delivery recipients\n        call: ourpeople.listdeliveryrecipients\n        with:\n          deliveryId: rest.deliveryId\n        outputParameters:\n        - type:\
  \ object\n          mapping: $.\n    - path: /v1/broadcasts/deliveries/{deliveryId}/contents/{contentId}/recipients\n      name: listcontentrecipients\n      operations:\n      - method: GET\n        name: listcontentrecipients\n        description: List content recipients\n        call: ourpeople.listcontentrecipients\n        with:\n          deliveryId: rest.deliveryId\n          contentId: rest.contentId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: ourpeople-mcp\n    transport: http\n    description: MCP adapter for OurPeople API for AI agent use.\n    tools:\n    - name: createtoken\n      description: Exchange client credentials for a token\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: ourpeople.createtoken\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: refreshtoken\n      description: Refresh an access token\n\
  \      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: ourpeople.refreshtoken\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listdeliveries\n      description: List recent deliveries\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: ourpeople.listdeliveries\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getbroadcast\n      description: Get broadcast details\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: ourpeople.getbroadcast\n      with:\n        broadcastId: tools.broadcastId\n      inputParameters:\n      - name: broadcastId\n        type: string\n        description: broadcastId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listdeliveryrecipients\n      description: List delivery recipients\n  \
  \    hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: ourpeople.listdeliveryrecipients\n      with:\n        deliveryId: tools.deliveryId\n      inputParameters:\n      - name: deliveryId\n        type: string\n        description: deliveryId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listcontentrecipients\n      description: List content recipients\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: ourpeople.listcontentrecipients\n      with:\n        deliveryId: tools.deliveryId\n        contentId: tools.contentId\n        rating: tools.rating\n      inputParameters:\n      - name: deliveryId\n        type: string\n        description: deliveryId\n        required: true\n      - name: contentId\n        type: string\n        description: contentId\n        required: true\n      - name: rating\n        type: integer\n    \
  \    description: Filter by rating value when the content type is a rating.\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    OURPEOPLE_TOKEN: OURPEOPLE_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/ourpeople/refs/heads/main/capabilities/ourpeople-capability.yaml
tags:
- Ourpeople
- API
tools:
- description: Exchange client credentials for a token
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createtoken
- description: Refresh an access token
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: refreshtoken
- description: List recent deliveries
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listdeliveries
- description: Get broadcast details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getbroadcast
- description: List delivery recipients
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listdeliveryrecipients
- description: List content recipients
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcontentrecipients
---
