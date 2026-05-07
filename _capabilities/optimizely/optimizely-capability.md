---
categories: []
consumed_apis: []
description: The Optimizely Campaign REST API provides programmatic access to Optimizely's email and omnichannel campaign management capabilities. Developers can use the API to manage campaigns, recipients, mailing lists, smart campaigns, transactional mails, and messaging workflows. The API is hosted at api.campaign.episerver.net and supports automation of marketing campaign operations, enabling integration with external systems and custom marketing workflows. The base URL includes the client ID for multi-tenant access.
layout: capability
name: Optimizely Campaign REST API
operations:
- description: List recipients
  method: GET
  name: listrecipients
  path: /{clientId}/recipients/{recipientListId}
- description: Add a recipient
  method: POST
  name: addrecipient
  path: /{clientId}/recipients/{recipientListId}
- description: Get a recipient
  method: GET
  name: getrecipient
  path: /{clientId}/recipients/{recipientListId}/{recipientId}
- description: Update a recipient
  method: PUT
  name: updaterecipient
  path: /{clientId}/recipients/{recipientListId}/{recipientId}
- description: Delete a recipient
  method: DELETE
  name: deleterecipient
  path: /{clientId}/recipients/{recipientListId}/{recipientId}
- description: List smart campaigns
  method: GET
  name: listsmartcampaigns
  path: /{clientId}/smartcampaigns
- description: Get a smart campaign
  method: GET
  name: getsmartcampaign
  path: /{clientId}/smartcampaigns/{campaignId}
- description: Start a smart campaign
  method: POST
  name: startsmartcampaign
  path: /{clientId}/smartcampaigns/{campaignId}/start
- description: Pause a smart campaign
  method: POST
  name: pausesmartcampaign
  path: /{clientId}/smartcampaigns/{campaignId}/pause
- description: Send a transactional mail
  method: POST
  name: sendtransactionalmail
  path: /{clientId}/transactionalmail
- description: List mailing lists
  method: GET
  name: listmailinglists
  path: /{clientId}/mailinglists
- description: Get a mailing list
  method: GET
  name: getmailinglist
  path: /{clientId}/mailinglists/{mailingListId}
- description: List unsubscribes
  method: GET
  name: listunsubscribes
  path: /{clientId}/unsubscribes
- description: Add an unsubscribe
  method: POST
  name: addunsubscribe
  path: /{clientId}/unsubscribes
- description: List assets
  method: GET
  name: listassets
  path: /{clientId}/assets
- description: Upload an asset
  method: POST
  name: uploadasset
  path: /{clientId}/assets
personas: []
provider_name: Optimizely
provider_slug: optimizely
search_terms:
- startsmartcampaign
- feature flags
- get a recipient
- start a smart campaign
- experimentation
- sendtransactionalmail
- list recipients
- addunsubscribe
- api
- pausesmartcampaign
- deleterecipient
- uploadasset
- list mailing lists
- upload an asset
- send a transactional mail
- update a recipient
- listunsubscribes
- getrecipient
- get a mailing list
- add a recipient
- listrecipients
- e-commerce
- listmailinglists
- delete a recipient
- listassets
- addrecipient
- a/b testing
- content management
- marketing
- add an unsubscribe
- pause a smart campaign
- updaterecipient
- optimizely
- list smart campaigns
- list unsubscribes
- getmailinglist
- listsmartcampaigns
- customer data
- getsmartcampaign
- list assets
- get a smart campaign
slug: optimizely-capability
source_filename: optimizely-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Optimizely Campaign REST API\n  description: The Optimizely Campaign REST API provides programmatic access to Optimizely's email and omnichannel campaign\n    management capabilities. Developers can use the API to manage campaigns, recipients, mailing lists, smart campaigns, transactional\n    mails, and messaging workflows. The API is hosted at api.campaign.episerver.net and supports automation of marketing campaign\n    operations, enabling integration with external systems and custom marketing workflows. The base URL includes the client\n    ID for multi-tenant access.\n  tags:\n  - Optimizely\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: optimizely\n    baseUri: https://api.campaign.episerver.net/rest\n    description: Optimizely Campaign REST API HTTP API.\n    authentication:\n      type: basic\n      username: '{{OPTIMIZELY_USERNAME}}'\n      password: '{{OPTIMIZELY_PASSWORD}}'\n\
  \    resources:\n    - name: clientid-recipients-recipientlistid\n      path: /{clientId}/recipients/{recipientListId}\n      operations:\n      - name: listrecipients\n        method: GET\n        description: List recipients\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: addrecipient\n        method: POST\n        description: Add a recipient\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: clientid-recipients-recipientlistid-recipientid\n      path: /{clientId}/recipients/{recipientListId}/{recipientId}\n      operations:\n      - name: getrecipient\n        method: GET\n        description: Get a recipient\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updaterecipient\n        method: PUT\n        description:\
  \ Update a recipient\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleterecipient\n        method: DELETE\n        description: Delete a recipient\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: clientid-smartcampaigns\n      path: /{clientId}/smartcampaigns\n      operations:\n      - name: listsmartcampaigns\n        method: GET\n        description: List smart campaigns\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: clientid-smartcampaigns-campaignid\n      path: /{clientId}/smartcampaigns/{campaignId}\n      operations:\n      - name: getsmartcampaign\n        method: GET\n        description: Get a smart campaign\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n        \
  \  type: object\n          value: $.\n    - name: clientid-smartcampaigns-campaignid-start\n      path: /{clientId}/smartcampaigns/{campaignId}/start\n      operations:\n      - name: startsmartcampaign\n        method: POST\n        description: Start a smart campaign\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: clientid-smartcampaigns-campaignid-pause\n      path: /{clientId}/smartcampaigns/{campaignId}/pause\n      operations:\n      - name: pausesmartcampaign\n        method: POST\n        description: Pause a smart campaign\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: clientid-transactionalmail\n      path: /{clientId}/transactionalmail\n      operations:\n      - name: sendtransactionalmail\n        method: POST\n        description: Send a transactional mail\n        outputRawFormat: json\n \
  \       outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: clientid-mailinglists\n      path: /{clientId}/mailinglists\n      operations:\n      - name: listmailinglists\n        method: GET\n        description: List mailing lists\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: clientid-mailinglists-mailinglistid\n      path: /{clientId}/mailinglists/{mailingListId}\n      operations:\n      - name: getmailinglist\n        method: GET\n        description: Get a mailing list\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: clientid-unsubscribes\n      path: /{clientId}/unsubscribes\n      operations:\n      - name: listunsubscribes\n        method: GET\n        description: List unsubscribes\n        outputRawFormat: json\n        outputParameters:\n      \
  \  - name: result\n          type: object\n          value: $.\n      - name: addunsubscribe\n        method: POST\n        description: Add an unsubscribe\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: clientid-assets\n      path: /{clientId}/assets\n      operations:\n      - name: listassets\n        method: GET\n        description: List assets\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: uploadasset\n        method: POST\n        description: Upload an asset\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: optimizely-rest\n    description: REST adapter for Optimizely Campaign REST API.\n    resources:\n    - path: /{clientId}/recipients/{recipientListId}\n  \
  \    name: listrecipients\n      operations:\n      - method: GET\n        name: listrecipients\n        description: List recipients\n        call: optimizely.listrecipients\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /{clientId}/recipients/{recipientListId}\n      name: addrecipient\n      operations:\n      - method: POST\n        name: addrecipient\n        description: Add a recipient\n        call: optimizely.addrecipient\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /{clientId}/recipients/{recipientListId}/{recipientId}\n      name: getrecipient\n      operations:\n      - method: GET\n        name: getrecipient\n        description: Get a recipient\n        call: optimizely.getrecipient\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /{clientId}/recipients/{recipientListId}/{recipientId}\n      name: updaterecipient\n      operations:\n      - method: PUT\n\
  \        name: updaterecipient\n        description: Update a recipient\n        call: optimizely.updaterecipient\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /{clientId}/recipients/{recipientListId}/{recipientId}\n      name: deleterecipient\n      operations:\n      - method: DELETE\n        name: deleterecipient\n        description: Delete a recipient\n        call: optimizely.deleterecipient\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /{clientId}/smartcampaigns\n      name: listsmartcampaigns\n      operations:\n      - method: GET\n        name: listsmartcampaigns\n        description: List smart campaigns\n        call: optimizely.listsmartcampaigns\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /{clientId}/smartcampaigns/{campaignId}\n      name: getsmartcampaign\n      operations:\n      - method: GET\n        name: getsmartcampaign\n        description:\
  \ Get a smart campaign\n        call: optimizely.getsmartcampaign\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /{clientId}/smartcampaigns/{campaignId}/start\n      name: startsmartcampaign\n      operations:\n      - method: POST\n        name: startsmartcampaign\n        description: Start a smart campaign\n        call: optimizely.startsmartcampaign\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /{clientId}/smartcampaigns/{campaignId}/pause\n      name: pausesmartcampaign\n      operations:\n      - method: POST\n        name: pausesmartcampaign\n        description: Pause a smart campaign\n        call: optimizely.pausesmartcampaign\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /{clientId}/transactionalmail\n      name: sendtransactionalmail\n      operations:\n      - method: POST\n        name: sendtransactionalmail\n        description: Send a transactional mail\n\
  \        call: optimizely.sendtransactionalmail\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /{clientId}/mailinglists\n      name: listmailinglists\n      operations:\n      - method: GET\n        name: listmailinglists\n        description: List mailing lists\n        call: optimizely.listmailinglists\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /{clientId}/mailinglists/{mailingListId}\n      name: getmailinglist\n      operations:\n      - method: GET\n        name: getmailinglist\n        description: Get a mailing list\n        call: optimizely.getmailinglist\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /{clientId}/unsubscribes\n      name: listunsubscribes\n      operations:\n      - method: GET\n        name: listunsubscribes\n        description: List unsubscribes\n        call: optimizely.listunsubscribes\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n    - path: /{clientId}/unsubscribes\n      name: addunsubscribe\n      operations:\n      - method: POST\n        name: addunsubscribe\n        description: Add an unsubscribe\n        call: optimizely.addunsubscribe\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /{clientId}/assets\n      name: listassets\n      operations:\n      - method: GET\n        name: listassets\n        description: List assets\n        call: optimizely.listassets\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /{clientId}/assets\n      name: uploadasset\n      operations:\n      - method: POST\n        name: uploadasset\n        description: Upload an asset\n        call: optimizely.uploadasset\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: optimizely-mcp\n    transport: http\n    description: MCP adapter for Optimizely Campaign REST\
  \ API for AI agent use.\n    tools:\n    - name: listrecipients\n      description: List recipients\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: optimizely.listrecipients\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: addrecipient\n      description: Add a recipient\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: optimizely.addrecipient\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getrecipient\n      description: Get a recipient\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: optimizely.getrecipient\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updaterecipient\n      description: Update a recipient\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: optimizely.updaterecipient\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleterecipient\n      description: Delete a recipient\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: optimizely.deleterecipient\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listsmartcampaigns\n      description: List smart campaigns\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: optimizely.listsmartcampaigns\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getsmartcampaign\n      description: Get a smart campaign\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: optimizely.getsmartcampaign\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: startsmartcampaign\n      description: Start a smart campaign\n      hints:\n        readOnly: false\n\
  \        destructive: false\n        idempotent: false\n      call: optimizely.startsmartcampaign\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: pausesmartcampaign\n      description: Pause a smart campaign\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: optimizely.pausesmartcampaign\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: sendtransactionalmail\n      description: Send a transactional mail\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: optimizely.sendtransactionalmail\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listmailinglists\n      description: List mailing lists\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: optimizely.listmailinglists\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: getmailinglist\n      description: Get a mailing list\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: optimizely.getmailinglist\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listunsubscribes\n      description: List unsubscribes\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: optimizely.listunsubscribes\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: addunsubscribe\n      description: Add an unsubscribe\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: optimizely.addunsubscribe\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listassets\n      description: List assets\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: optimizely.listassets\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: uploadasset\n      description: Upload an asset\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: optimizely.uploadasset\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    OPTIMIZELY_USERNAME: OPTIMIZELY_USERNAME\n    OPTIMIZELY_PASSWORD: OPTIMIZELY_PASSWORD\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/optimizely/refs/heads/main/capabilities/optimizely-capability.yaml
tags:
- Optimizely
- API
tools:
- description: List recipients
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listrecipients
- description: Add a recipient
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: addrecipient
- description: Get a recipient
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getrecipient
- description: Update a recipient
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updaterecipient
- description: Delete a recipient
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleterecipient
- description: List smart campaigns
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listsmartcampaigns
- description: Get a smart campaign
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getsmartcampaign
- description: Start a smart campaign
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: startsmartcampaign
- description: Pause a smart campaign
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: pausesmartcampaign
- description: Send a transactional mail
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: sendtransactionalmail
- description: List mailing lists
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listmailinglists
- description: Get a mailing list
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getmailinglist
- description: List unsubscribes
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listunsubscribes
- description: Add an unsubscribe
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: addunsubscribe
- description: List assets
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listassets
- description: Upload an asset
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: uploadasset
---
