---
categories: []
consumed_apis: []
description: Unified capability combining Sitecore CDP guest data management with Sitecore Personalize decisioning and experimentation. Enables marketing technologists and developers to manage customer profiles, build audience segments, configure personalization flows, and orchestrate decision models from a single interface.
layout: capability
name: Sitecore Customer Data and Personalization
operations:
- description: List guest profiles in Sitecore CDP
  method: GET
  name: list-guests
  path: /v1/guests
- description: Create a new guest profile in CDP
  method: POST
  name: create-guest
  path: /v1/guests
- description: Get a guest profile by reference
  method: GET
  name: get-guest
  path: /v1/guests/{ref}
- description: Update a guest profile
  method: PUT
  name: update-guest
  path: /v1/guests/{ref}
- description: List orders for a specific guest
  method: GET
  name: list-guest-orders
  path: /v1/guests/{ref}/orders
- description: List Personalize connections
  method: GET
  name: list-connections
  path: /v1/connections
- description: List personalization flow definitions
  method: GET
  name: list-flows
  path: /v1/flows
- description: List decision models
  method: GET
  name: list-decision-models
  path: /v1/decision-models
personas: []
provider_name: sitecore
provider_slug: sitecore
search_terms:
- update guest
- list flows
- get guest
- get a specific guest profile by reference
- manage a specific guest profile
- manage cdp guest profiles
- list connections
- manage personalize external connections
- list sitecore personalize decision models
- list personalization flow definitions
- list guest orders
- list orders for a specific guest
- list guest profiles in sitecore cdp
- cdp list guests
- create a new external system connection in sitecore personalize
- list personalize connections
- manage personalize decision models
- cdp get guest
- update an existing guest profile in sitecore cdp
- personalize list connections
- personalization
- manage orders for a guest profile
- list orders for a specific guest in sitecore cdp
- list personalization connections to external systems
- list sitecore personalize flow definitions (experiments and experiences)
- personalize list flows
- get a guest profile by reference
- personalize list decision models
- create a new guest profile in sitecore cdp
- create a new guest profile in cdp
- update a guest profile
- create guest
- cdp update guest
- cdp list guest orders
- manage personalize flow definitions
- personalize create connection
- customer data platform
- experiments
- list guests
- decisioning
- list decision models
- cdp create guest
- sitecore
- guest data
slug: customer-data-personalization
source_filename: customer-data-personalization.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Sitecore Customer Data and Personalization\n  description: Unified capability combining Sitecore CDP guest data management with Sitecore Personalize decisioning and experimentation.\n    Enables marketing technologists and developers to manage customer profiles, build audience segments, configure personalization\n    flows, and orchestrate decision models from a single interface.\n  tags:\n  - Sitecore\n  - Customer Data Platform\n  - Personalization\n  - Guest Data\n  - Decisioning\n  - Experiments\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    CDP_CLIENT_KEY: CDP_CLIENT_KEY\n    CDP_API_TOKEN: CDP_API_TOKEN\n    PERSONALIZE_API_KEY: PERSONALIZE_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: cdp-rest\n    baseUri: https://api-engage-us.sitecorecloud.io\n    description: Sitecore CDP REST API for guest and order data management\n    authentication:\n      type: basic\n    \
  \  username: '{{CDP_CLIENT_KEY}}'\n      password: '{{CDP_API_TOKEN}}'\n    resources:\n    - name: guests\n      path: /v2.1/guests\n      description: Manage guest profiles in Sitecore CDP\n      operations:\n      - name: list-guests\n        method: GET\n        description: List guest profiles with optional email filter\n        inputParameters:\n        - name: email\n          in: query\n          type: string\n          required: false\n          description: Filter by email address\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Max results (max 100)\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-guest\n        method: POST\n        description: Create a new guest profile\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            email: '{{tools.email}}'\n            firstName: '{{tools.firstName}}'\n            lastName: '{{tools.lastName}}'\n    - name: guest\n      path: /v2.1/guests/{guestRef}\n      description: Manage a specific guest profile\n      operations:\n      - name: get-guest\n        method: GET\n        description: Get a guest profile by reference\n        inputParameters:\n        - name: guestRef\n          in: path\n          type: string\n          required: true\n          description: The guest reference identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-guest\n        method: PUT\n        description: Update a guest profile\n        inputParameters:\n        - name: guestRef\n          in:\
  \ path\n          type: string\n          required: true\n          description: The guest reference identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            email: '{{tools.email}}'\n            firstName: '{{tools.firstName}}'\n      - name: delete-guest\n        method: DELETE\n        description: Delete a guest profile\n        inputParameters:\n        - name: guestRef\n          in: path\n          type: string\n          required: true\n          description: The guest reference identifier\n    - name: guest-orders\n      path: /v2.1/guests/{guestRef}/orders\n      description: Manage orders for a guest\n      operations:\n      - name: list-guest-orders\n        method: GET\n        description: List orders for a specific guest\n        inputParameters:\n        - name: guestRef\n          in: path\n          type: string\n       \
  \   required: true\n          description: The guest reference identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-guest-order\n        method: POST\n        description: Create an order for a guest\n        inputParameters:\n        - name: guestRef\n          in: path\n          type: string\n          required: true\n          description: The guest reference identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            referenceId: '{{tools.referenceId}}'\n            status: '{{tools.status}}'\n            currencyCode: '{{tools.currencyCode}}'\n  - type: http\n    namespace: personalize-rest\n    baseUri: https://api.boxever.com\n    description: Sitecore Personalize REST API for decisioning and experiment management\n    authentication:\n\
  \      type: apikey\n      key: api_key\n      value: '{{PERSONALIZE_API_KEY}}'\n      placement: query\n    resources:\n    - name: connections\n      path: /v1/connections\n      description: Manage connections to external systems\n      operations:\n      - name: list-connections\n        method: GET\n        description: List all configured connections\n        inputParameters:\n        - name: pageSize\n          in: query\n          type: integer\n          required: false\n          description: Results per page\n        - name: pageOffset\n          in: query\n          type: integer\n          required: false\n          description: Page offset\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-connection\n        method: POST\n        description: Create a new external system connection\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            type: '{{tools.type}}'\n    - name: flow-definitions\n      path: /v1/flowDefinitions\n      description: Manage personalization flow definitions\n      operations:\n      - name: list-flow-definitions\n        method: GET\n        description: List all flow definitions\n        inputParameters:\n        - name: pageSize\n          in: query\n          type: integer\n          required: false\n          description: Results per page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-flow-definition\n        method: POST\n        description: Create a new flow definition\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n         \
  \   name: '{{tools.name}}'\n            type: '{{tools.type}}'\n    - name: decision-models\n      path: /v1/decisionModels\n      description: Manage decision models for targeting\n      operations:\n      - name: list-decision-models\n        method: GET\n        description: List all decision models\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-decision-model\n        method: POST\n        description: Create a new decision model\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n  exposes:\n  - type: rest\n    port: 8081\n    namespace: customer-data-personalization-api\n    description: Unified REST API for Sitecore CDP and Personalize.\n    resources:\n    - path: /v1/guests\n      name: guests\n      description:\
  \ Manage CDP guest profiles\n      operations:\n      - method: GET\n        name: list-guests\n        description: List guest profiles in Sitecore CDP\n        call: cdp-rest.list-guests\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-guest\n        description: Create a new guest profile in CDP\n        call: cdp-rest.create-guest\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/guests/{ref}\n      name: guest\n      description: Manage a specific guest profile\n      operations:\n      - method: GET\n        name: get-guest\n        description: Get a guest profile by reference\n        call: cdp-rest.get-guest\n        with:\n          guestRef: rest.ref\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PUT\n        name: update-guest\n        description: Update a guest profile\n        call: cdp-rest.update-guest\n        with:\n\
  \          guestRef: rest.ref\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/guests/{ref}/orders\n      name: guest-orders\n      description: Manage orders for a guest profile\n      operations:\n      - method: GET\n        name: list-guest-orders\n        description: List orders for a specific guest\n        call: cdp-rest.list-guest-orders\n        with:\n          guestRef: rest.ref\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/connections\n      name: connections\n      description: Manage Personalize external connections\n      operations:\n      - method: GET\n        name: list-connections\n        description: List Personalize connections\n        call: personalize-rest.list-connections\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/flows\n      name: flows\n      description: Manage Personalize flow definitions\n      operations:\n      - method:\
  \ GET\n        name: list-flows\n        description: List personalization flow definitions\n        call: personalize-rest.list-flow-definitions\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/decision-models\n      name: decision-models\n      description: Manage Personalize decision models\n      operations:\n      - method: GET\n        name: list-decision-models\n        description: List decision models\n        call: personalize-rest.list-decision-models\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9091\n    namespace: customer-data-personalization-mcp\n    transport: http\n    description: MCP server for AI-assisted Sitecore CDP and Personalize management.\n    tools:\n    - name: cdp-list-guests\n      description: List guest profiles in Sitecore CDP\n      hints:\n        readOnly: true\n        idempotent: true\n      call: cdp-rest.list-guests\n      outputParameters:\n      -\
  \ type: object\n        mapping: $.\n    - name: cdp-get-guest\n      description: Get a specific guest profile by reference\n      hints:\n        readOnly: true\n        idempotent: true\n      call: cdp-rest.get-guest\n      with:\n        guestRef: tools.guestRef\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: cdp-create-guest\n      description: Create a new guest profile in Sitecore CDP\n      call: cdp-rest.create-guest\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: cdp-update-guest\n      description: Update an existing guest profile in Sitecore CDP\n      call: cdp-rest.update-guest\n      with:\n        guestRef: tools.guestRef\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: cdp-list-guest-orders\n      description: List orders for a specific guest in Sitecore CDP\n      hints:\n        readOnly: true\n        idempotent: true\n      call: cdp-rest.list-guest-orders\n      with:\n\
  \        guestRef: tools.guestRef\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: personalize-list-connections\n      description: List personalization connections to external systems\n      hints:\n        readOnly: true\n        idempotent: true\n      call: personalize-rest.list-connections\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: personalize-list-flows\n      description: List Sitecore Personalize flow definitions (experiments and experiences)\n      hints:\n        readOnly: true\n        idempotent: true\n      call: personalize-rest.list-flow-definitions\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: personalize-list-decision-models\n      description: List Sitecore Personalize decision models\n      hints:\n        readOnly: true\n        idempotent: true\n      call: personalize-rest.list-decision-models\n      outputParameters:\n      - type: object\n        mapping: $.\n\
  \    - name: personalize-create-connection\n      description: Create a new external system connection in Sitecore Personalize\n      call: personalize-rest.create-connection\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/sitecore/refs/heads/main/capabilities/customer-data-personalization.yaml
tags:
- Sitecore
- Customer Data Platform
- Personalization
- Guest Data
- Decisioning
- Experiments
tools:
- description: List guest profiles in Sitecore CDP
  hints:
    idempotent: true
    readOnly: true
  name: cdp-list-guests
- description: Get a specific guest profile by reference
  hints:
    idempotent: true
    readOnly: true
  name: cdp-get-guest
- description: Create a new guest profile in Sitecore CDP
  hints: {}
  name: cdp-create-guest
- description: Update an existing guest profile in Sitecore CDP
  hints: {}
  name: cdp-update-guest
- description: List orders for a specific guest in Sitecore CDP
  hints:
    idempotent: true
    readOnly: true
  name: cdp-list-guest-orders
- description: List personalization connections to external systems
  hints:
    idempotent: true
    readOnly: true
  name: personalize-list-connections
- description: List Sitecore Personalize flow definitions (experiments and experiences)
  hints:
    idempotent: true
    readOnly: true
  name: personalize-list-flows
- description: List Sitecore Personalize decision models
  hints:
    idempotent: true
    readOnly: true
  name: personalize-list-decision-models
- description: Create a new external system connection in Sitecore Personalize
  hints: {}
  name: personalize-create-connection
---
