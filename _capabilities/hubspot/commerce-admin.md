---
categories:
- content-management
consumed_apis: []
description: Unified workflow for admins to manage commerce payments, subscriptions, HubDB data tables, CMS pages, and domains. Combines commerce operations with CMS data management for platform administration.
layout: capability
name: HubSpot Commerce Admin
operations:
- description: List payments
  method: GET
  name: list-payments
  path: /v1/payments
- description: Create payment
  method: POST
  name: create-payment
  path: /v1/payments
- description: Get payment
  method: GET
  name: get-payment
  path: /v1/payments/{commercePaymentId}
- description: List subscriptions
  method: GET
  name: list-subscriptions
  path: /v1/subscriptions
- description: Get subscription
  method: GET
  name: get-subscription
  path: /v1/subscriptions/{subscriptionId}
personas: []
provider_name: HubSpot
provider_slug: hubspot
search_terms:
- sales
- hubdb
- commerce subscriptions
- hubspot
- create a commerce payment
- analytics
- content
- search payments
- marketing
- create subscription
- get a payment by id
- update payment
- create a commerce subscription
- individual subscription
- operations
- list payments
- commerce
- list subscriptions
- marketing automation
- crm
- commerce payments
- individual payment
- email marketing
- get payment
- update a commerce payment
- list all commerce subscriptions
- get a subscription by id
- admin
- cms
- search commerce payments
- search commerce subscriptions
- get subscription
- customer service
- create payment
- list all commerce payments
- search subscriptions
slug: commerce-admin
source_filename: commerce-admin.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: HubSpot Commerce Admin\n  description: Unified workflow for admins to manage commerce payments, subscriptions, HubDB data tables, CMS pages, and domains.\n    Combines commerce operations with CMS data management for platform administration.\n  tags:\n  - HubSpot\n  - Commerce\n  - Admin\n  - CMS\n  - HubDB\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    HUBSPOT_ACCESS_TOKEN: HUBSPOT_ACCESS_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: commerce-payments\n    baseUri: https://api.hubapi.com\n    description: HubSpot Commerce Payments API.\n    authentication:\n      type: bearer\n      token: '{{HUBSPOT_ACCESS_TOKEN}}'\n    resources:\n    - name: payments\n      path: /crm/v3/objects/commerce_payments\n      description: Commerce payment records\n      operations:\n      - name: list-payments\n        method: GET\n        description: List all commerce payments\n        inputParameters:\n\
  \        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Max results\n        - name: after\n          in: query\n          type: string\n          required: false\n          description: Cursor\n        - name: properties\n          in: query\n          type: string\n          required: false\n          description: Properties\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-payment\n        method: POST\n        description: Create a payment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            properties: '{{tools.properties}}'\n    - name: payment-by-id\n      path: /crm/v3/objects/commerce_payments/{commercePaymentId}\n      description: Individual payment\n      operations:\n      -\
  \ name: get-payment\n        method: GET\n        description: Get a payment\n        inputParameters:\n        - name: commercePaymentId\n          in: path\n          type: string\n          required: true\n          description: Payment ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-payment\n        method: PATCH\n        description: Update a payment\n        inputParameters:\n        - name: commercePaymentId\n          in: path\n          type: string\n          required: true\n          description: Payment ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            properties: '{{tools.properties}}'\n      - name: archive-payment\n        method: DELETE\n        description: Archive a payment\n        inputParameters:\n        - name: commercePaymentId\n\
  \          in: path\n          type: string\n          required: true\n          description: Payment ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: search\n      path: /crm/v3/objects/commerce_payments/search\n      description: Search payments\n      operations:\n      - name: search-payments\n        method: POST\n        description: Search payments\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            filterGroups: '{{tools.filterGroups}}'\n            query: '{{tools.query}}'\n  - type: http\n    namespace: commerce-subscriptions\n    baseUri: https://api.hubapi.com\n    description: HubSpot Commerce Subscriptions API.\n    authentication:\n      type: bearer\n      token: '{{HUBSPOT_ACCESS_TOKEN}}'\n    resources:\n    - name: subscriptions\n    \
  \  path: /crm/v3/objects/subscriptions\n      description: Subscription records\n      operations:\n      - name: list-subscriptions\n        method: GET\n        description: List all subscriptions\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Max results\n        - name: after\n          in: query\n          type: string\n          required: false\n          description: Cursor\n        - name: properties\n          in: query\n          type: string\n          required: false\n          description: Properties\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-subscription\n        method: POST\n        description: Create a subscription\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type:\
  \ json\n          data:\n            properties: '{{tools.properties}}'\n    - name: subscription-by-id\n      path: /crm/v3/objects/subscriptions/{subscriptionId}\n      description: Individual subscription\n      operations:\n      - name: get-subscription\n        method: GET\n        description: Get a subscription\n        inputParameters:\n        - name: subscriptionId\n          in: path\n          type: string\n          required: true\n          description: Subscription ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-subscription\n        method: PATCH\n        description: Update a subscription\n        inputParameters:\n        - name: subscriptionId\n          in: path\n          type: string\n          required: true\n          description: Subscription ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n      \
  \    value: $.\n        body:\n          type: json\n          data:\n            properties: '{{tools.properties}}'\n      - name: archive-subscription\n        method: DELETE\n        description: Archive a subscription\n        inputParameters:\n        - name: subscriptionId\n          in: path\n          type: string\n          required: true\n          description: Subscription ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: search\n      path: /crm/v3/objects/subscriptions/search\n      description: Search subscriptions\n      operations:\n      - name: search-subscriptions\n        method: POST\n        description: Search subscriptions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            filterGroups: '{{tools.filterGroups}}'\n            query:\
  \ '{{tools.query}}'\n  - type: http\n    namespace: cms-hubdb-api\n    baseUri: https://api.hubapi.com\n    description: The HubDB API allows you to create, update, and delete HubDB data tables and their rows. HubDB tables can\n      be used as data sources for dynamic CMS pages and are available in both draft and published ve\n    authentication:\n      type: bearer\n      token: '{{HUBSPOT_ACCESS_TOKEN}}'\n    resources:\n    - name: tables\n      path: /tables\n      description: tables operations\n      operations:\n      - name: listhubdbtables\n        method: GET\n        description: HubSpot List HubDB Tables\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createhubdbtable\n        method: POST\n        description: HubSpot Create a HubDB Table\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: gethubdbtable\n\
  \        method: GET\n        description: HubSpot Get a HubDB Table\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatehubdbtable\n        method: PUT\n        description: HubSpot Update a HubDB Table\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletehubdbtable\n        method: DELETE\n        description: HubSpot Delete a HubDB Table\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: rows\n      path: /rows\n      description: rows operations\n      operations:\n      - name: listhubdbtablerows\n        method: GET\n        description: HubSpot List HubDB Table Rows\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name:\
  \ addhubdbtablerow\n        method: POST\n        description: HubSpot Add a Row to a HubDB Table\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: gethubdbtablerow\n        method: GET\n        description: HubSpot Get a HubDB Table Row\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatehubdbtablerow\n        method: PATCH\n        description: HubSpot Update a HubDB Table Row\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletehubdbtablerow\n        method: DELETE\n        description: HubSpot Delete a HubDB Table Row\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: push-live\n      path: /push-live\n      description:\
  \ push-live operations\n      operations:\n      - name: publishhubdbtabledraft\n        method: POST\n        description: HubSpot Publish HubDB Table Draft\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: cms-pages-api\n    baseUri: https://api.hubapi.com\n    description: The CMS Pages API provides endpoints for creating and managing site pages and landing pages hosted on HubSpot.\n      You can create, retrieve, update, publish, and delete both site pages and landing pages p\n    authentication:\n      type: bearer\n      token: '{{HUBSPOT_ACCESS_TOKEN}}'\n    resources:\n    - name: site-pages\n      path: /site-pages\n      description: site-pages operations\n      operations:\n      - name: listsitepages\n        method: GET\n        description: HubSpot List Site Pages\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n      - name: createsitepage\n        method: POST\n        description: HubSpot Create a Site Page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getsitepage\n        method: GET\n        description: HubSpot Get a Site Page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatesitepage\n        method: PATCH\n        description: HubSpot Update a Site Page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletesitepage\n        method: DELETE\n        description: HubSpot Delete a Site Page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: push-live\n      path: /push-live\n      description: push-live\
  \ operations\n      operations:\n      - name: publishsitepage\n        method: POST\n        description: HubSpot Publish a Site Page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: landing-pages\n      path: /landing-pages\n      description: landing-pages operations\n      operations:\n      - name: listlandingpages\n        method: GET\n        description: HubSpot List Landing Pages\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createlandingpage\n        method: POST\n        description: HubSpot Create a Landing Page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getlandingpage\n        method: GET\n        description: HubSpot Get a Landing Page\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: deletelandingpage\n        method: DELETE\n        description: HubSpot Delete a Landing Page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: domains-api\n    baseUri: https://api.hubapi.com\n    description: 'The HubSpot CMS Domains API allows you to retrieve information about domains connected to a HubSpot CMS\n      site.\n\n\n      Use this API to:\n\n      - List all domains connected to your HubSpot account\n\n      - Get detailed info'\n    authentication:\n      type: bearer\n      token: '{{HUBSPOT_ACCESS_TOKEN}}'\n    resources:\n    - name: domains\n      path: /domains\n      description: domains operations\n      operations:\n      - name: listdomains\n        method: GET\n        description: HubSpot List All Domains\n        outputRawFormat: json\n        outputParameters:\n    \
  \    - name: result\n          type: object\n          value: $.\n      - name: getdomainbyid\n        method: GET\n        description: HubSpot Get a Domain by ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8084\n    namespace: commerce-admin-api\n    description: Unified REST API for commerce operations, data table management, and CMS administration.\n    resources:\n    - path: /v1/payments\n      name: payments\n      description: Commerce payments\n      operations:\n      - method: GET\n        name: list-payments\n        description: List payments\n        call: commerce-payments.list-payments\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-payment\n        description: Create payment\n        call: commerce-payments.create-payment\n        outputParameters:\n        - type: object\n     \
  \     mapping: $.\n    - path: /v1/payments/{commercePaymentId}\n      name: payment-by-id\n      description: Individual payment\n      operations:\n      - method: GET\n        name: get-payment\n        description: Get payment\n        call: commerce-payments.get-payment\n        with:\n          commercePaymentId: rest.commercePaymentId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/subscriptions\n      name: subscriptions\n      description: Commerce subscriptions\n      operations:\n      - method: GET\n        name: list-subscriptions\n        description: List subscriptions\n        call: commerce-subscriptions.list-subscriptions\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/subscriptions/{subscriptionId}\n      name: subscription-by-id\n      description: Individual subscription\n      operations:\n      - method: GET\n        name: get-subscription\n        description: Get subscription\n\
  \        call: commerce-subscriptions.get-subscription\n        with:\n          subscriptionId: rest.subscriptionId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9094\n    namespace: commerce-admin-mcp\n    transport: http\n    description: MCP server for AI-assisted commerce administration, payment tracking, and data management.\n    tools:\n    - name: list-payments\n      description: List all commerce payments\n      hints:\n        readOnly: true\n        idempotent: true\n      call: commerce-payments.list-payments\n      with:\n        limit: tools.limit\n        after: tools.after\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-payment\n      description: Get a payment by ID\n      hints:\n        readOnly: true\n        idempotent: true\n      call: commerce-payments.get-payment\n      with:\n        commercePaymentId: tools.commercePaymentId\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n    - name: create-payment\n      description: Create a commerce payment\n      hints:\n        readOnly: false\n      call: commerce-payments.create-payment\n      with:\n        properties: tools.properties\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-payment\n      description: Update a commerce payment\n      hints:\n        readOnly: false\n        idempotent: true\n      call: commerce-payments.update-payment\n      with:\n        commercePaymentId: tools.commercePaymentId\n        properties: tools.properties\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-payments\n      description: Search commerce payments\n      hints:\n        readOnly: true\n        idempotent: true\n      call: commerce-payments.search-payments\n      with:\n        filterGroups: tools.filterGroups\n        query: tools.query\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name:\
  \ list-subscriptions\n      description: List all commerce subscriptions\n      hints:\n        readOnly: true\n        idempotent: true\n      call: commerce-subscriptions.list-subscriptions\n      with:\n        limit: tools.limit\n        after: tools.after\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-subscription\n      description: Get a subscription by ID\n      hints:\n        readOnly: true\n        idempotent: true\n      call: commerce-subscriptions.get-subscription\n      with:\n        subscriptionId: tools.subscriptionId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-subscription\n      description: Create a commerce subscription\n      hints:\n        readOnly: false\n      call: commerce-subscriptions.create-subscription\n      with:\n        properties: tools.properties\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-subscriptions\n      description:\
  \ Search commerce subscriptions\n      hints:\n        readOnly: true\n        idempotent: true\n      call: commerce-subscriptions.search-subscriptions\n      with:\n        filterGroups: tools.filterGroups\n        query: tools.query\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/hubspot/refs/heads/main/capabilities/commerce-admin.yaml
tags:
- HubSpot
- Commerce
- Admin
- CMS
- HubDB
tools:
- description: List all commerce payments
  hints:
    idempotent: true
    readOnly: true
  name: list-payments
- description: Get a payment by ID
  hints:
    idempotent: true
    readOnly: true
  name: get-payment
- description: Create a commerce payment
  hints:
    readOnly: false
  name: create-payment
- description: Update a commerce payment
  hints:
    idempotent: true
    readOnly: false
  name: update-payment
- description: Search commerce payments
  hints:
    idempotent: true
    readOnly: true
  name: search-payments
- description: List all commerce subscriptions
  hints:
    idempotent: true
    readOnly: true
  name: list-subscriptions
- description: Get a subscription by ID
  hints:
    idempotent: true
    readOnly: true
  name: get-subscription
- description: Create a commerce subscription
  hints:
    readOnly: false
  name: create-subscription
- description: Search commerce subscriptions
  hints:
    idempotent: true
    readOnly: true
  name: search-subscriptions
---
