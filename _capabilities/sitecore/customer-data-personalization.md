---
categories: []
consumed_apis:
- cdp-rest
- personalize-rest
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
- update a guest profile
- experiments
- manage personalize decision models
- manage cdp guest profiles
- create a new guest profile in sitecore cdp
- decisioning
- manage a specific guest profile
- list guest orders
- get guest
- list connections
- cdp update guest
- personalize list decision models
- list orders for a specific guest
- create guest
- list personalize connections
- manage personalize flow definitions
- update an existing guest profile in sitecore cdp
- list personalization connections to external systems
- create a new guest profile in cdp
- guest data
- manage orders for a guest profile
- cdp get guest
- list sitecore personalize flow definitions (experiments and experiences)
- get a specific guest profile by reference
- cdp create guest
- personalize create connection
- personalize list connections
- list decision models
- customer data platform
- list orders for a specific guest in sitecore cdp
- list flows
- cdp list guest orders
- personalization
- list guests
- get a guest profile by reference
- personalize list flows
- list sitecore personalize decision models
- update guest
- manage personalize external connections
- sitecore
- cdp list guests
- list guest profiles in sitecore cdp
- create a new external system connection in sitecore personalize
- list personalization flow definitions
slug: customer-data-personalization
source_filename: customer-data-personalization.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Sitecore Customer Data and Personalization\"\n  description: >-\n    Unified capability combining Sitecore CDP guest data management with Sitecore\n    Personalize decisioning and experimentation. Enables marketing technologists and\n    developers to manage customer profiles, build audience segments, configure\n    personalization flows, and orchestrate decision models from a single interface.\n  tags:\n    - Sitecore\n    - Customer Data Platform\n    - Personalization\n    - Guest Data\n    - Decisioning\n    - Experiments\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      CDP_CLIENT_KEY: CDP_CLIENT_KEY\n      CDP_API_TOKEN: CDP_API_TOKEN\n      PERSONALIZE_API_KEY: PERSONALIZE_API_KEY\n\ncapability:\n  consumes:\n    - import: cdp-rest\n      location: ./shared/cdp-rest.yaml\n    - import: personalize-rest\n      location: ./shared/personalize-rest.yaml\n\n  exposes:\n   \
  \ - type: rest\n      port: 8081\n      namespace: customer-data-personalization-api\n      description: \"Unified REST API for Sitecore CDP and Personalize.\"\n      resources:\n        - path: /v1/guests\n          name: guests\n          description: \"Manage CDP guest profiles\"\n          operations:\n            - method: GET\n              name: list-guests\n              description: \"List guest profiles in Sitecore CDP\"\n              call: \"cdp-rest.list-guests\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-guest\n              description: \"Create a new guest profile in CDP\"\n              call: \"cdp-rest.create-guest\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/guests/{ref}\n          name: guest\n          description: \"Manage a specific guest profile\"\n          operations:\n\
  \            - method: GET\n              name: get-guest\n              description: \"Get a guest profile by reference\"\n              call: \"cdp-rest.get-guest\"\n              with:\n                guestRef: \"rest.ref\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: update-guest\n              description: \"Update a guest profile\"\n              call: \"cdp-rest.update-guest\"\n              with:\n                guestRef: \"rest.ref\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/guests/{ref}/orders\n          name: guest-orders\n          description: \"Manage orders for a guest profile\"\n          operations:\n            - method: GET\n              name: list-guest-orders\n              description: \"List orders for a specific guest\"\n              call: \"cdp-rest.list-guest-orders\"\n     \
  \         with:\n                guestRef: \"rest.ref\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/connections\n          name: connections\n          description: \"Manage Personalize external connections\"\n          operations:\n            - method: GET\n              name: list-connections\n              description: \"List Personalize connections\"\n              call: \"personalize-rest.list-connections\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/flows\n          name: flows\n          description: \"Manage Personalize flow definitions\"\n          operations:\n            - method: GET\n              name: list-flows\n              description: \"List personalization flow definitions\"\n              call: \"personalize-rest.list-flow-definitions\"\n              outputParameters:\n                - type: object\n     \
  \             mapping: \"$.\"\n\n        - path: /v1/decision-models\n          name: decision-models\n          description: \"Manage Personalize decision models\"\n          operations:\n            - method: GET\n              name: list-decision-models\n              description: \"List decision models\"\n              call: \"personalize-rest.list-decision-models\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9091\n      namespace: customer-data-personalization-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Sitecore CDP and Personalize management.\"\n      tools:\n        - name: cdp-list-guests\n          description: \"List guest profiles in Sitecore CDP\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"cdp-rest.list-guests\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n  \
  \      - name: cdp-get-guest\n          description: \"Get a specific guest profile by reference\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"cdp-rest.get-guest\"\n          with:\n            guestRef: \"tools.guestRef\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: cdp-create-guest\n          description: \"Create a new guest profile in Sitecore CDP\"\n          call: \"cdp-rest.create-guest\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: cdp-update-guest\n          description: \"Update an existing guest profile in Sitecore CDP\"\n          call: \"cdp-rest.update-guest\"\n          with:\n            guestRef: \"tools.guestRef\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: cdp-list-guest-orders\n          description: \"List orders for a specific guest\
  \ in Sitecore CDP\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"cdp-rest.list-guest-orders\"\n          with:\n            guestRef: \"tools.guestRef\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: personalize-list-connections\n          description: \"List personalization connections to external systems\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"personalize-rest.list-connections\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: personalize-list-flows\n          description: \"List Sitecore Personalize flow definitions (experiments and experiences)\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"personalize-rest.list-flow-definitions\"\n          outputParameters:\n            - type: object\n              mapping: \"\
  $.\"\n\n        - name: personalize-list-decision-models\n          description: \"List Sitecore Personalize decision models\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"personalize-rest.list-decision-models\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: personalize-create-connection\n          description: \"Create a new external system connection in Sitecore Personalize\"\n          call: \"personalize-rest.create-connection\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
