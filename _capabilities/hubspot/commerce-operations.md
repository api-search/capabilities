---
categories:
- payments
consumed_apis: []
description: Commerce workflow for managing payments and subscriptions.
layout: capability
name: HubSpot Commerce Operations
operations: []
personas: []
provider_name: HubSpot
provider_slug: hubspot
search_terms:
- hubspot get a subscription
- hubspot search commerce payments
- deletesubscription
- sales
- batchreadsubscriptions
- hubspot archive a batch of commerce payments
- hubspot
- createcommercepayment
- analytics
- hubspot archive a commerce payment
- content
- searchsubscriptions
- hubspot create a commerce payment
- batchreadcommercepayments
- batchcreatecommercepayments
- hubspot list subscriptions
- hubspot update a batch of commerce payments
- hubspot create a batch of commerce payments
- marketing
- updatecommercepaymentbyid
- updatesubscription
- getsubscription
- getcommercepaymentbyid
- listsubscriptionassociations
- createsubscription
- hubspot update a commerce payment
- operations
- commerce
- hubspot archive a subscription
- marketing automation
- hubspot update a subscription
- crm
- email marketing
- batchupdatecommercepayments
- hubspot search subscriptions
- hubspot create a subscription
- hubspot batch create subscriptions
- batchcreatesubscriptions
- hubspot batch read subscriptions
- listcommercepayments
- hubspot batch update subscriptions
- payments
- listsubscriptions
- subscriptions
- hubspot retrieve a commerce payment
- searchcommercepayments
- batcharchivecommercepayments
- batchupdatesubscriptions
- hubspot read a batch of commerce payments
- archivecommercepaymentbyid
- customer service
- hubspot list subscription associations
- hubspot list commerce payments
slug: commerce-operations
source_filename: commerce-operations.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: HubSpot Commerce Operations\n  description: Commerce workflow for managing payments and subscriptions.\n  tags:\n  - HubSpot\n  - Commerce\n  - Payments\n  - Subscriptions\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    HUBSPOT_ACCESS_TOKEN: HUBSPOT_ACCESS_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: commerce-payments-api\n    baseUri: https://api.hubapi.com\n    description: \"The HubSpot Commerce Payments API enables developers to manage commerce payment objects within \\nthe HubSpot\\\n      \\ CRM. This API provides comprehensive functionality for creating, reading, updating, \\narchivi\"\n    authentication:\n      type: bearer\n      token: '{{HUBSPOT_ACCESS_TOKEN}}'\n    resources:\n    - name: read\n      path: /read\n      description: read operations\n      operations:\n      - name: batchreadcommercepayments\n        method: POST\n        description: HubSpot Read\
  \ a Batch of Commerce Payments\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: archive\n      path: /archive\n      description: archive operations\n      operations:\n      - name: batcharchivecommercepayments\n        method: POST\n        description: HubSpot Archive a Batch of Commerce Payments\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: create\n      path: /create\n      description: create operations\n      operations:\n      - name: batchcreatecommercepayments\n        method: POST\n        description: HubSpot Create a Batch of Commerce Payments\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: update\n      path: /update\n      description: update operations\n      operations:\n      - name: batchupdatecommercepayments\n\
  \        method: POST\n        description: HubSpot Update a Batch of Commerce Payments\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: commerce_payments\n      path: /commerce_payments\n      description: commerce_payments operations\n      operations:\n      - name: listcommercepayments\n        method: GET\n        description: HubSpot List Commerce Payments\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createcommercepayment\n        method: POST\n        description: HubSpot Create a Commerce Payment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getcommercepaymentbyid\n        method: GET\n        description: HubSpot Retrieve a Commerce Payment\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: updatecommercepaymentbyid\n        method: PATCH\n        description: HubSpot Update a Commerce Payment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: archivecommercepaymentbyid\n        method: DELETE\n        description: HubSpot Archive a Commerce Payment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: search\n      path: /search\n      description: search operations\n      operations:\n      - name: searchcommercepayments\n        method: POST\n        description: HubSpot Search Commerce Payments\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: commerce-subscriptions-api\n    baseUri: https://api.hubapi.com\n\
  \    description: The subscriptions API allows you to retrieve data about recurring subscription records in HubSpot Commerce.\n      Subscriptions are created when a customer purchases a recurring product through HubSpot paym\n    authentication:\n      type: bearer\n      token: '{{HUBSPOT_ACCESS_TOKEN}}'\n    resources:\n    - name: subscriptions\n      path: /subscriptions\n      description: subscriptions operations\n      operations:\n      - name: listsubscriptions\n        method: GET\n        description: HubSpot List Subscriptions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createsubscription\n        method: POST\n        description: HubSpot Create a Subscription\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getsubscription\n        method: GET\n        description: HubSpot Get a Subscription\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatesubscription\n        method: PATCH\n        description: HubSpot Update a Subscription\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletesubscription\n        method: DELETE\n        description: HubSpot Archive a Subscription\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: read\n      path: /read\n      description: read operations\n      operations:\n      - name: batchreadsubscriptions\n        method: POST\n        description: HubSpot Batch Read Subscriptions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: create\n      path: /create\n      description: create\
  \ operations\n      operations:\n      - name: batchcreatesubscriptions\n        method: POST\n        description: HubSpot Batch Create Subscriptions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: update\n      path: /update\n      description: update operations\n      operations:\n      - name: batchupdatesubscriptions\n        method: POST\n        description: HubSpot Batch Update Subscriptions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: search\n      path: /search\n      description: search operations\n      operations:\n      - name: searchsubscriptions\n        method: POST\n        description: HubSpot Search Subscriptions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: associations\n      path: /associations\n\
  \      description: associations operations\n      operations:\n      - name: listsubscriptionassociations\n        method: GET\n        description: HubSpot List Subscription Associations\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: mcp\n    port: 9094\n    namespace: commerce-operations-mcp\n    transport: http\n    description: MCP server for AI-assisted HubSpot Commerce Operations.\n    tools:\n    - name: batchreadcommercepayments\n      description: HubSpot Read a Batch of Commerce Payments\n      hints:\n        readOnly: false\n      call: commerce-payments-api.batchreadcommercepayments\n    - name: batcharchivecommercepayments\n      description: HubSpot Archive a Batch of Commerce Payments\n      hints:\n        readOnly: false\n      call: commerce-payments-api.batcharchivecommercepayments\n    - name: batchcreatecommercepayments\n      description: HubSpot Create a Batch\
  \ of Commerce Payments\n      hints:\n        readOnly: false\n      call: commerce-payments-api.batchcreatecommercepayments\n    - name: batchupdatecommercepayments\n      description: HubSpot Update a Batch of Commerce Payments\n      hints:\n        readOnly: false\n      call: commerce-payments-api.batchupdatecommercepayments\n    - name: listcommercepayments\n      description: HubSpot List Commerce Payments\n      hints:\n        readOnly: true\n      call: commerce-payments-api.listcommercepayments\n    - name: createcommercepayment\n      description: HubSpot Create a Commerce Payment\n      hints:\n        readOnly: false\n      call: commerce-payments-api.createcommercepayment\n    - name: getcommercepaymentbyid\n      description: HubSpot Retrieve a Commerce Payment\n      hints:\n        readOnly: true\n      call: commerce-payments-api.getcommercepaymentbyid\n    - name: updatecommercepaymentbyid\n      description: HubSpot Update a Commerce Payment\n      hints:\n       \
  \ readOnly: false\n      call: commerce-payments-api.updatecommercepaymentbyid\n    - name: archivecommercepaymentbyid\n      description: HubSpot Archive a Commerce Payment\n      hints:\n        destructive: true\n      call: commerce-payments-api.archivecommercepaymentbyid\n    - name: searchcommercepayments\n      description: HubSpot Search Commerce Payments\n      hints:\n        readOnly: false\n      call: commerce-payments-api.searchcommercepayments\n    - name: listsubscriptions\n      description: HubSpot List Subscriptions\n      hints:\n        readOnly: true\n      call: commerce-subscriptions-api.listsubscriptions\n    - name: createsubscription\n      description: HubSpot Create a Subscription\n      hints:\n        readOnly: false\n      call: commerce-subscriptions-api.createsubscription\n    - name: getsubscription\n      description: HubSpot Get a Subscription\n      hints:\n        readOnly: true\n      call: commerce-subscriptions-api.getsubscription\n    - name:\
  \ updatesubscription\n      description: HubSpot Update a Subscription\n      hints:\n        readOnly: false\n      call: commerce-subscriptions-api.updatesubscription\n    - name: deletesubscription\n      description: HubSpot Archive a Subscription\n      hints:\n        destructive: true\n      call: commerce-subscriptions-api.deletesubscription\n    - name: batchreadsubscriptions\n      description: HubSpot Batch Read Subscriptions\n      hints:\n        readOnly: false\n      call: commerce-subscriptions-api.batchreadsubscriptions\n    - name: batchcreatesubscriptions\n      description: HubSpot Batch Create Subscriptions\n      hints:\n        readOnly: false\n      call: commerce-subscriptions-api.batchcreatesubscriptions\n    - name: batchupdatesubscriptions\n      description: HubSpot Batch Update Subscriptions\n      hints:\n        readOnly: false\n      call: commerce-subscriptions-api.batchupdatesubscriptions\n    - name: searchsubscriptions\n      description: HubSpot Search\
  \ Subscriptions\n      hints:\n        readOnly: false\n      call: commerce-subscriptions-api.searchsubscriptions\n    - name: listsubscriptionassociations\n      description: HubSpot List Subscription Associations\n      hints:\n        readOnly: true\n      call: commerce-subscriptions-api.listsubscriptionassociations\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/hubspot/refs/heads/main/capabilities/commerce-operations.yaml
tags:
- HubSpot
- Commerce
- Payments
- Subscriptions
tools:
- description: HubSpot Read a Batch of Commerce Payments
  hints:
    readOnly: false
  name: batchreadcommercepayments
- description: HubSpot Archive a Batch of Commerce Payments
  hints:
    readOnly: false
  name: batcharchivecommercepayments
- description: HubSpot Create a Batch of Commerce Payments
  hints:
    readOnly: false
  name: batchcreatecommercepayments
- description: HubSpot Update a Batch of Commerce Payments
  hints:
    readOnly: false
  name: batchupdatecommercepayments
- description: HubSpot List Commerce Payments
  hints:
    readOnly: true
  name: listcommercepayments
- description: HubSpot Create a Commerce Payment
  hints:
    readOnly: false
  name: createcommercepayment
- description: HubSpot Retrieve a Commerce Payment
  hints:
    readOnly: true
  name: getcommercepaymentbyid
- description: HubSpot Update a Commerce Payment
  hints:
    readOnly: false
  name: updatecommercepaymentbyid
- description: HubSpot Archive a Commerce Payment
  hints:
    destructive: true
  name: archivecommercepaymentbyid
- description: HubSpot Search Commerce Payments
  hints:
    readOnly: false
  name: searchcommercepayments
- description: HubSpot List Subscriptions
  hints:
    readOnly: true
  name: listsubscriptions
- description: HubSpot Create a Subscription
  hints:
    readOnly: false
  name: createsubscription
- description: HubSpot Get a Subscription
  hints:
    readOnly: true
  name: getsubscription
- description: HubSpot Update a Subscription
  hints:
    readOnly: false
  name: updatesubscription
- description: HubSpot Archive a Subscription
  hints:
    destructive: true
  name: deletesubscription
- description: HubSpot Batch Read Subscriptions
  hints:
    readOnly: false
  name: batchreadsubscriptions
- description: HubSpot Batch Create Subscriptions
  hints:
    readOnly: false
  name: batchcreatesubscriptions
- description: HubSpot Batch Update Subscriptions
  hints:
    readOnly: false
  name: batchupdatesubscriptions
- description: HubSpot Search Subscriptions
  hints:
    readOnly: false
  name: searchsubscriptions
- description: HubSpot List Subscription Associations
  hints:
    readOnly: true
  name: listsubscriptionassociations
---
