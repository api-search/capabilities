---
categories:
- payments
consumed_apis:
- commerce-payments-api
- commerce-subscriptions-api
description: Commerce workflow for managing payments and subscriptions.
layout: capability
name: HubSpot Commerce Operations
operations: []
personas: []
provider_name: HubSpot
provider_slug: hubspot
search_terms:
- subscriptions
- operations
- marketing automation
- listsubscriptions
- hubspot create a commerce payment
- searchsubscriptions
- deletesubscription
- hubspot update a batch of commerce payments
- listcommercepayments
- hubspot
- hubspot retrieve a commerce payment
- hubspot list subscriptions
- content
- crm
- hubspot update a commerce payment
- hubspot update a subscription
- batchupdatesubscriptions
- batchcreatesubscriptions
- listsubscriptionassociations
- batchcreatecommercepayments
- archivecommercepaymentbyid
- createcommercepayment
- hubspot create a subscription
- hubspot get a subscription
- hubspot create a batch of commerce payments
- batchupdatecommercepayments
- batchreadcommercepayments
- hubspot batch read subscriptions
- updatecommercepaymentbyid
- hubspot batch update subscriptions
- sales
- hubspot batch create subscriptions
- batcharchivecommercepayments
- hubspot list subscription associations
- hubspot search subscriptions
- hubspot archive a batch of commerce payments
- createsubscription
- hubspot archive a subscription
- batchreadsubscriptions
- getcommercepaymentbyid
- email marketing
- analytics
- commerce
- searchcommercepayments
- hubspot read a batch of commerce payments
- hubspot list commerce payments
- customer service
- hubspot archive a commerce payment
- updatesubscription
- marketing
- getsubscription
- hubspot search commerce payments
- payments
slug: commerce-operations
source_filename: commerce-operations.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha1\ninfo:\n  label: HubSpot Commerce Operations\n  description: Commerce workflow for managing payments and subscriptions.\n  tags:\n  - HubSpot\n  - Commerce\n  - Payments\n  - Subscriptions\n  created: '2026-04-18'\n  modified: '2026-04-18'\nbinds:\n- namespace: env\n  keys:\n    HUBSPOT_ACCESS_TOKEN: HUBSPOT_ACCESS_TOKEN\ncapability:\n  consumes:\n  - import: commerce-payments-api\n    location: ./shared/commerce-payments-api.yaml\n  - import: commerce-subscriptions-api\n    location: ./shared/commerce-subscriptions-api.yaml\n  exposes:\n  - type: mcp\n    port: 9094\n    namespace: commerce-operations-mcp\n    transport: http\n    description: MCP server for AI-assisted HubSpot Commerce Operations.\n    tools:\n    - name: batchreadcommercepayments\n      description: HubSpot Read a Batch of Commerce Payments\n      hints:\n        readOnly: false\n      call: commerce-payments-api.batchreadcommercepayments\n    - name: batcharchivecommercepayments\n\
  \      description: HubSpot Archive a Batch of Commerce Payments\n      hints:\n        readOnly: false\n      call: commerce-payments-api.batcharchivecommercepayments\n    - name: batchcreatecommercepayments\n      description: HubSpot Create a Batch of Commerce Payments\n      hints:\n        readOnly: false\n      call: commerce-payments-api.batchcreatecommercepayments\n    - name: batchupdatecommercepayments\n      description: HubSpot Update a Batch of Commerce Payments\n      hints:\n        readOnly: false\n      call: commerce-payments-api.batchupdatecommercepayments\n    - name: listcommercepayments\n      description: HubSpot List Commerce Payments\n      hints:\n        readOnly: true\n      call: commerce-payments-api.listcommercepayments\n    - name: createcommercepayment\n      description: HubSpot Create a Commerce Payment\n      hints:\n        readOnly: false\n      call: commerce-payments-api.createcommercepayment\n    - name: getcommercepaymentbyid\n      description:\
  \ HubSpot Retrieve a Commerce Payment\n      hints:\n        readOnly: true\n      call: commerce-payments-api.getcommercepaymentbyid\n    - name: updatecommercepaymentbyid\n      description: HubSpot Update a Commerce Payment\n      hints:\n        readOnly: false\n      call: commerce-payments-api.updatecommercepaymentbyid\n    - name: archivecommercepaymentbyid\n      description: HubSpot Archive a Commerce Payment\n      hints:\n        destructive: true\n      call: commerce-payments-api.archivecommercepaymentbyid\n    - name: searchcommercepayments\n      description: HubSpot Search Commerce Payments\n      hints:\n        readOnly: false\n      call: commerce-payments-api.searchcommercepayments\n    - name: listsubscriptions\n      description: HubSpot List Subscriptions\n      hints:\n        readOnly: true\n      call: commerce-subscriptions-api.listsubscriptions\n    - name: createsubscription\n      description: HubSpot Create a Subscription\n      hints:\n        readOnly:\
  \ false\n      call: commerce-subscriptions-api.createsubscription\n    - name: getsubscription\n      description: HubSpot Get a Subscription\n      hints:\n        readOnly: true\n      call: commerce-subscriptions-api.getsubscription\n    - name: updatesubscription\n      description: HubSpot Update a Subscription\n      hints:\n        readOnly: false\n      call: commerce-subscriptions-api.updatesubscription\n    - name: deletesubscription\n      description: HubSpot Archive a Subscription\n      hints:\n        destructive: true\n      call: commerce-subscriptions-api.deletesubscription\n    - name: batchreadsubscriptions\n      description: HubSpot Batch Read Subscriptions\n      hints:\n        readOnly: false\n      call: commerce-subscriptions-api.batchreadsubscriptions\n    - name: batchcreatesubscriptions\n      description: HubSpot Batch Create Subscriptions\n      hints:\n        readOnly: false\n      call: commerce-subscriptions-api.batchcreatesubscriptions\n    - name:\
  \ batchupdatesubscriptions\n      description: HubSpot Batch Update Subscriptions\n      hints:\n        readOnly: false\n      call: commerce-subscriptions-api.batchupdatesubscriptions\n    - name: searchsubscriptions\n      description: HubSpot Search Subscriptions\n      hints:\n        readOnly: false\n      call: commerce-subscriptions-api.searchsubscriptions\n    - name: listsubscriptionassociations\n      description: HubSpot List Subscription Associations\n      hints:\n        readOnly: true\n      call: commerce-subscriptions-api.listsubscriptionassociations\n"
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
