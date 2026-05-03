---
api_specs:
- filename: stepzen-admin-openapi.yml
  format: yaml
  label: stepzen-admin
  slug: stepzen-admin
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/stepzen/refs/heads/main/openapi/stepzen-admin-openapi.yml
categories: []
consumed_apis:
- stepzen-admin
description: GraphQL API lifecycle management workflow for StepZen/IBM API Connect. Covers deploying GraphQL APIs from REST, database, and GraphQL backends, managing endpoints, rotating API keys, and monitoring account usage. Designed for platform engineers and API developers building data federation layers.
layout: capability
name: StepZen GraphQL API Management
operations:
- description: List all deployed GraphQL API endpoints
  method: GET
  name: list-endpoints
  path: /v1/endpoints
- description: Deploy a new GraphQL API endpoint
  method: POST
  name: create-endpoint
  path: /v1/endpoints
- description: Get details of a specific endpoint
  method: GET
  name: get-endpoint
  path: /v1/endpoints/{id}
- description: Delete a deployed GraphQL endpoint
  method: DELETE
  name: delete-endpoint
  path: /v1/endpoints/{id}
- description: List all API keys
  method: GET
  name: list-api-keys
  path: /v1/api-keys
- description: Create a new API key for endpoint access
  method: POST
  name: create-api-key
  path: /v1/api-keys
- description: Retrieve account details and monthly usage statistics
  method: GET
  name: get-account
  path: /v1/account
personas: []
provider_name: StepZen
provider_slug: stepzen
search_terms:
- deploy a new graphql api endpoint
- list api keys
- graphql endpoint deployment and management
- ibm
- delete a deployed stepzen graphql endpoint. this removes the endpoint and makes it inaccessible to clients.
- account information and usage
- individual endpoint operations
- stepzen
- api management
- graphql
- retrieve stepzen account details including plan, endpoint count, and api request usage statistics for the current month.
- get account
- create a new api key for accessing stepzen graphql endpoints. specify a descriptive name and key type (admin or user).
- data federation
- api gateway
- api key management
- create api key
- retrieve account details and monthly usage statistics
- backend integration
- get details of a specific endpoint
- get details of a specific stepzen graphql endpoint including url, status, and configuration.
- list all api keys in the stepzen account. keys are used to authenticate requests to deployed graphql endpoints.
- create a new api key for endpoint access
- list all deployed stepzen graphql api endpoints in the account. use to see what apis are currently deployed and their status.
- list endpoints
- list all deployed graphql api endpoints
- get endpoint
- delete endpoint
- rest to graphql
- create endpoint
- deploy a new stepzen graphql endpoint from a schema folder. use to publish a new graphql api making it accessible to clients.
- list all api keys
- delete a deployed graphql endpoint
slug: graphql-api-management
source_filename: graphql-api-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"StepZen GraphQL API Management\"\n  description: >-\n    GraphQL API lifecycle management workflow for StepZen/IBM API Connect.\n    Covers deploying GraphQL APIs from REST, database, and GraphQL backends,\n    managing endpoints, rotating API keys, and monitoring account usage.\n    Designed for platform engineers and API developers building data federation\n    layers.\n  tags:\n    - StepZen\n    - GraphQL\n    - API Management\n    - IBM\n    - Data Federation\n    - REST to GraphQL\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      STEPZEN_ADMIN_KEY: STEPZEN_ADMIN_KEY\n\ncapability:\n  consumes:\n    - import: stepzen-admin\n      location: ./shared/stepzen-admin.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: graphql-api-management-api\n      description: \"Unified REST API for StepZen GraphQL endpoint lifecycle management.\"\n      resources:\n\
  \        - path: /v1/endpoints\n          name: endpoints\n          description: GraphQL endpoint deployment and management\n          operations:\n            - method: GET\n              name: list-endpoints\n              description: List all deployed GraphQL API endpoints\n              call: \"stepzen-admin.list-endpoints\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-endpoint\n              description: Deploy a new GraphQL API endpoint\n              call: \"stepzen-admin.create-endpoint\"\n              with:\n                name: \"rest.name\"\n                folder: \"rest.folder\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/endpoints/{id}\n          name: endpoint\n          description: Individual endpoint operations\n          operations:\n            - method: GET\n              name:\
  \ get-endpoint\n              description: Get details of a specific endpoint\n              call: \"stepzen-admin.get-endpoint\"\n              with:\n                endpointId: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-endpoint\n              description: Delete a deployed GraphQL endpoint\n              call: \"stepzen-admin.delete-endpoint\"\n              with:\n                endpointId: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/api-keys\n          name: api-keys\n          description: API key management\n          operations:\n            - method: GET\n              name: list-api-keys\n              description: List all API keys\n              call: \"stepzen-admin.list-api-keys\"\n              outputParameters:\n                - type: object\n           \
  \       mapping: \"$.\"\n            - method: POST\n              name: create-api-key\n              description: Create a new API key for endpoint access\n              call: \"stepzen-admin.create-api-key\"\n              with:\n                name: \"rest.name\"\n                type: \"rest.type\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/account\n          name: account\n          description: Account information and usage\n          operations:\n            - method: GET\n              name: get-account\n              description: Retrieve account details and monthly usage statistics\n              call: \"stepzen-admin.get-account\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: graphql-api-management-mcp\n      transport: http\n      description: \"MCP server for AI-assisted StepZen GraphQL\
  \ API lifecycle management.\"\n      tools:\n        - name: list-endpoints\n          description: >-\n            List all deployed StepZen GraphQL API endpoints in the account.\n            Use to see what APIs are currently deployed and their status.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"stepzen-admin.list-endpoints\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-endpoint\n          description: >-\n            Get details of a specific StepZen GraphQL endpoint including URL,\n            status, and configuration.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"stepzen-admin.get-endpoint\"\n          with:\n            endpointId: \"tools.endpointId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-endpoint\n          description: >-\n            Deploy a\
  \ new StepZen GraphQL endpoint from a schema folder.\n            Use to publish a new GraphQL API making it accessible to clients.\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"stepzen-admin.create-endpoint\"\n          with:\n            name: \"tools.name\"\n            folder: \"tools.folder\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-endpoint\n          description: >-\n            Delete a deployed StepZen GraphQL endpoint. This removes the\n            endpoint and makes it inaccessible to clients.\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"stepzen-admin.delete-endpoint\"\n          with:\n            endpointId: \"tools.endpointId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-api-keys\n          description: >-\n\
  \            List all API keys in the StepZen account. Keys are used to\n            authenticate requests to deployed GraphQL endpoints.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"stepzen-admin.list-api-keys\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-api-key\n          description: >-\n            Create a new API key for accessing StepZen GraphQL endpoints.\n            Specify a descriptive name and key type (admin or user).\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"stepzen-admin.create-api-key\"\n          with:\n            name: \"tools.name\"\n            type: \"tools.type\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-account\n          description: >-\n            Retrieve StepZen account details including plan, endpoint count,\n        \
  \    and API request usage statistics for the current month.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"stepzen-admin.get-account\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/stepzen/refs/heads/main/capabilities/graphql-api-management.yaml
tags:
- StepZen
- GraphQL
- API Management
- IBM
- Data Federation
- REST to GraphQL
tools:
- description: List all deployed StepZen GraphQL API endpoints in the account. Use to see what APIs are currently deployed and their status.
  hints:
    openWorld: true
    readOnly: true
  name: list-endpoints
- description: Get details of a specific StepZen GraphQL endpoint including URL, status, and configuration.
  hints:
    openWorld: true
    readOnly: true
  name: get-endpoint
- description: Deploy a new StepZen GraphQL endpoint from a schema folder. Use to publish a new GraphQL API making it accessible to clients.
  hints:
    destructive: false
    readOnly: false
  name: create-endpoint
- description: Delete a deployed StepZen GraphQL endpoint. This removes the endpoint and makes it inaccessible to clients.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-endpoint
- description: List all API keys in the StepZen account. Keys are used to authenticate requests to deployed GraphQL endpoints.
  hints:
    openWorld: true
    readOnly: true
  name: list-api-keys
- description: Create a new API key for accessing StepZen GraphQL endpoints. Specify a descriptive name and key type (admin or user).
  hints:
    destructive: false
    readOnly: false
  name: create-api-key
- description: Retrieve StepZen account details including plan, endpoint count, and API request usage statistics for the current month.
  hints:
    openWorld: true
    readOnly: true
  name: get-account
---
