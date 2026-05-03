---
categories: []
consumed_apis:
- rapidapi-platform
description: 'Workflow capability for Enterprise Hub administrators to manage their API marketplace: publishing and updating API listings, managing organizations, controlling subscriptions, and monitoring API usage. Uses the RapidAPI REST Platform API to automate hub administration tasks normally performed through the Enterprise Hub Admin Panel.'
layout: capability
name: RapidAPI Hub Management
operations:
- description: List all APIs in the hub.
  method: GET
  name: list-apis
  path: /v1/apis
- description: Create a new API listing.
  method: POST
  name: create-api
  path: /v1/apis
- description: Get API details.
  method: GET
  name: get-api
  path: /v1/apis/{apiId}
- description: Update an API listing.
  method: PUT
  name: update-api
  path: /v1/apis/{apiId}
- description: Delete an API listing.
  method: DELETE
  name: delete-api
  path: /v1/apis/{apiId}
- description: List all organizations.
  method: GET
  name: list-organizations
  path: /v1/organizations
- description: List all subscriptions.
  method: GET
  name: list-subscriptions
  path: /v1/subscriptions
- description: List all users.
  method: GET
  name: list-users
  path: /v1/users
personas: []
provider_name: RapidAPI
provider_slug: rapidapi
search_terms:
- api subscriptions.
- list all subscriptions.
- api testing
- delete an api listing.
- get api
- update api
- list all organizations.
- list subscriptions
- administration
- marketplace
- remove an api listing from the enterprise hub. this action is irreversible.
- retrieve details for a specific api listing including versions, endpoints, and pricing plans.
- api marketplace
- api management
- list apis
- api design
- single api listing.
- list all users.
- list all organizations in the enterprise hub.
- hub users.
- rapidapi
- api gateway
- list users
- enterprise
- create api
- publish a new api listing to the enterprise hub marketplace.
- list organizations
- update an existing api listing configuration, description, or settings.
- hub organizations.
- api listings in the enterprise hub.
- list all apis in the hub.
- delete api
- platform
- list all users in the enterprise hub to manage access and roles.
- create a new api listing.
- update an api listing.
- list all api subscriptions to monitor adoption and revenue.
- get api details.
- list all api listings in the rapidapi enterprise hub. use to audit, discover, or report on available apis.
slug: hub-management
source_filename: hub-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"RapidAPI Hub Management\"\n  description: >-\n    Workflow capability for Enterprise Hub administrators to manage their API\n    marketplace: publishing and updating API listings, managing organizations,\n    controlling subscriptions, and monitoring API usage. Uses the RapidAPI\n    REST Platform API to automate hub administration tasks normally performed\n    through the Enterprise Hub Admin Panel.\n  tags:\n    - API Management\n    - Platform\n    - Administration\n    - Marketplace\n    - Enterprise\n    - RapidAPI\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      RAPIDAPI_PLATFORM_KEY: RAPIDAPI_PLATFORM_KEY\n\ncapability:\n  consumes:\n    - import: rapidapi-platform\n      location: ./shared/rest-platform-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: rapidapi-hub-management-api\n      description: \"Unified REST API for RapidAPI Enterprise\
  \ Hub management.\"\n      resources:\n        - path: /v1/apis\n          name: apis\n          description: \"API listings in the Enterprise Hub.\"\n          operations:\n            - method: GET\n              name: list-apis\n              description: \"List all APIs in the hub.\"\n              call: \"rapidapi-platform.list-apis\"\n              with:\n                offset: \"rest.offset\"\n                limit: \"rest.limit\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-api\n              description: \"Create a new API listing.\"\n              call: \"rapidapi-platform.create-api\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/apis/{apiId}\n          name: api\n          description: \"Single API listing.\"\n          operations:\n            - method: GET\n              name: get-api\n\
  \              description: \"Get API details.\"\n              call: \"rapidapi-platform.get-api\"\n              with:\n                apiId: \"rest.apiId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: update-api\n              description: \"Update an API listing.\"\n              call: \"rapidapi-platform.update-api\"\n              with:\n                apiId: \"rest.apiId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-api\n              description: \"Delete an API listing.\"\n              call: \"rapidapi-platform.delete-api\"\n              with:\n                apiId: \"rest.apiId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/organizations\n          name: organizations\n          description:\
  \ \"Hub organizations.\"\n          operations:\n            - method: GET\n              name: list-organizations\n              description: \"List all organizations.\"\n              call: \"rapidapi-platform.list-organizations\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/subscriptions\n          name: subscriptions\n          description: \"API subscriptions.\"\n          operations:\n            - method: GET\n              name: list-subscriptions\n              description: \"List all subscriptions.\"\n              call: \"rapidapi-platform.list-subscriptions\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/users\n          name: users\n          description: \"Hub users.\"\n          operations:\n            - method: GET\n              name: list-users\n              description: \"List all users.\"\n              call: \"\
  rapidapi-platform.list-users\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9080\n      namespace: rapidapi-hub-management-mcp\n      transport: http\n      description: \"MCP server for AI-assisted RapidAPI Enterprise Hub management.\"\n      tools:\n        - name: list-apis\n          description: \"List all API listings in the RapidAPI Enterprise Hub. Use to audit, discover, or report on available APIs.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"rapidapi-platform.list-apis\"\n          with:\n            offset: \"tools.offset\"\n            limit: \"tools.limit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-api\n          description: \"Retrieve details for a specific API listing including versions, endpoints, and pricing plans.\"\n          hints:\n            readOnly: true\n\
  \            idempotent: true\n          call: \"rapidapi-platform.get-api\"\n          with:\n            apiId: \"tools.apiId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-api\n          description: \"Publish a new API listing to the Enterprise Hub marketplace.\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"rapidapi-platform.create-api\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: update-api\n          description: \"Update an existing API listing configuration, description, or settings.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"rapidapi-platform.update-api\"\n          with:\n            apiId: \"tools.apiId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name:\
  \ delete-api\n          description: \"Remove an API listing from the Enterprise Hub. This action is irreversible.\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"rapidapi-platform.delete-api\"\n          with:\n            apiId: \"tools.apiId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-organizations\n          description: \"List all organizations in the Enterprise Hub.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"rapidapi-platform.list-organizations\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-subscriptions\n          description: \"List all API subscriptions to monitor adoption and revenue.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"rapidapi-platform.list-subscriptions\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-users\n          description: \"List all users in the Enterprise Hub to manage access and roles.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"rapidapi-platform.list-users\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/rapidapi/refs/heads/main/capabilities/hub-management.yaml
tags:
- API Management
- Platform
- Administration
- Marketplace
- Enterprise
- RapidAPI
tools:
- description: List all API listings in the RapidAPI Enterprise Hub. Use to audit, discover, or report on available APIs.
  hints:
    openWorld: true
    readOnly: true
  name: list-apis
- description: Retrieve details for a specific API listing including versions, endpoints, and pricing plans.
  hints:
    idempotent: true
    readOnly: true
  name: get-api
- description: Publish a new API listing to the Enterprise Hub marketplace.
  hints:
    destructive: false
    readOnly: false
  name: create-api
- description: Update an existing API listing configuration, description, or settings.
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: update-api
- description: Remove an API listing from the Enterprise Hub. This action is irreversible.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-api
- description: List all organizations in the Enterprise Hub.
  hints:
    openWorld: true
    readOnly: true
  name: list-organizations
- description: List all API subscriptions to monitor adoption and revenue.
  hints:
    openWorld: true
    readOnly: true
  name: list-subscriptions
- description: List all users in the Enterprise Hub to manage access and roles.
  hints:
    openWorld: true
    readOnly: true
  name: list-users
---
