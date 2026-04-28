---
categories:
- api-management
consumed_apis: []
description: Workflow capability for building and managing GraphQL APIs with AppSync including data sources, resolvers, and schema management.
layout: capability
name: GraphQL Api Management Workflow
operations:
- description: List all GraphQL APIs
  method: GET
  name: list-graphql-apis
  path: /v1/apis
- description: Create a GraphQL API
  method: POST
  name: create-graphql-api
  path: /v1/apis
- description: Upload a new GraphQL schema
  method: POST
  name: start-schema-creation
  path: /v1/schema
personas: []
provider_name: Amazon AppSync
provider_slug: amazon-appsync
search_terms:
- list reusable pipeline functions available for composing complex resolvers.
- list resolvers
- create a new graphql api with the specified authentication type and configuration.
- serverless
- list all appsync graphql apis to understand available apis and their configurations.
- list all graphql apis
- amazon appsync
- aws
- create a graphql api
- create a reusable pipeline function for use in pipeline resolvers.
- connect a data source (dynamodb, lambda, opensearch, http) to a graphql api.
- get complete details of a graphql api including authentication configuration and endpoints.
- upload a new graphql schema definition to an appsync api.
- get graphql api
- list data sources
- create graphql api
- graphql schema management
- list all resolvers for a specific graphql type to understand field-to-data-source mappings.
- upload a new graphql schema
- create data source
- list graphql apis
- create resolver
- create function
- start schema creation
- list all data sources connected to a graphql api.
- graphql
- create a resolver that maps a graphql field to a data source operation.
- api management
- list functions
- graphql api management
slug: graphql-api-management
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: GraphQL Api Management Workflow\n  description: Workflow capability for building and managing GraphQL APIs with AppSync including data sources, resolvers, and schema management.\n  tags:\n    - Amazon AppSync\n    - GraphQL\n    - API Management\n    - Serverless\n    - AWS\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nimports:\n  - namespace: appsync\n    from: shared/appsync-api.yaml\n\ncapability:\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: graphql-mgmt-rest\n      resources:\n        - path: /v1/apis\n          name: graphql-apis\n          description: GraphQL API management\n          operations:\n            - method: GET\n              name: list-graphql-apis\n              description: List all GraphQL APIs\n              call: \"appsync.list-graphql-apis\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n  \
  \            name: create-graphql-api\n              description: Create a GraphQL API\n              call: \"appsync.create-graphql-api\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/schema\n          name: schema\n          description: GraphQL schema management\n          operations:\n            - method: POST\n              name: start-schema-creation\n              description: Upload a new GraphQL schema\n              call: \"appsync.start-schema-creation\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: graphql-mgmt-mcp\n      transport: http\n      tools:\n        - name: list-graphql-apis\n          description: List all AppSync GraphQL APIs to understand available APIs and their configurations.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"appsync.list-graphql-apis\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-graphql-api\n          description: Get complete details of a GraphQL API including authentication configuration and endpoints.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"appsync.get-graphql-api\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-graphql-api\n          description: Create a new GraphQL API with the specified authentication type and configuration.\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"appsync.create-graphql-api\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-data-sources\n          description: List all data sources connected to a GraphQL API.\n          hints:\n            readOnly: true\n            openWorld: true\n      \
  \    call: \"appsync.list-data-sources\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-data-source\n          description: Connect a data source (DynamoDB, Lambda, OpenSearch, HTTP) to a GraphQL API.\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"appsync.create-data-source\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-resolvers\n          description: List all resolvers for a specific GraphQL type to understand field-to-data-source mappings.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"appsync.list-resolvers\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-resolver\n          description: Create a resolver that maps a GraphQL field to a data source operation.\n          hints:\n           \
  \ readOnly: false\n            openWorld: false\n          call: \"appsync.create-resolver\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-functions\n          description: List reusable pipeline functions available for composing complex resolvers.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"appsync.list-functions\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-function\n          description: Create a reusable pipeline function for use in pipeline resolvers.\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"appsync.create-function\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: start-schema-creation\n          description: Upload a new GraphQL schema definition to an AppSync API.\n          hints:\n\
  \            readOnly: false\n            openWorld: false\n          call: \"appsync.start-schema-creation\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\npersonas:\n  - name: GraphQL Api Developer\n    description: Builds GraphQL APIs with data sources, resolvers, and schema definitions.\n    tools:\n      - list-graphql-apis\n      - get-graphql-api\n      - create-graphql-api\n      - list-data-sources\n      - create-data-source\n      - list-resolvers\n      - create-resolver\n      - list-functions\n      - create-function\n      - start-schema-creation\n\n  - name: Api Operations Engineer\n    description: Monitors and maintains AppSync APIs in production.\n    tools:\n      - list-graphql-apis\n      - get-graphql-api\n      - list-data-sources\n      - list-resolvers\n      - list-functions\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-appsync/refs/heads/main/capabilities/graphql-api-management.yaml
tags:
- Amazon AppSync
- GraphQL
- API Management
- Serverless
- AWS
tools:
- description: List all AppSync GraphQL APIs to understand available APIs and their configurations.
  hints:
    openWorld: true
    readOnly: true
  name: list-graphql-apis
- description: Get complete details of a GraphQL API including authentication configuration and endpoints.
  hints:
    openWorld: true
    readOnly: true
  name: get-graphql-api
- description: Create a new GraphQL API with the specified authentication type and configuration.
  hints:
    openWorld: false
    readOnly: false
  name: create-graphql-api
- description: List all data sources connected to a GraphQL API.
  hints:
    openWorld: true
    readOnly: true
  name: list-data-sources
- description: Connect a data source (DynamoDB, Lambda, OpenSearch, HTTP) to a GraphQL API.
  hints:
    openWorld: false
    readOnly: false
  name: create-data-source
- description: List all resolvers for a specific GraphQL type to understand field-to-data-source mappings.
  hints:
    openWorld: true
    readOnly: true
  name: list-resolvers
- description: Create a resolver that maps a GraphQL field to a data source operation.
  hints:
    openWorld: false
    readOnly: false
  name: create-resolver
- description: List reusable pipeline functions available for composing complex resolvers.
  hints:
    openWorld: true
    readOnly: true
  name: list-functions
- description: Create a reusable pipeline function for use in pipeline resolvers.
  hints:
    openWorld: false
    readOnly: false
  name: create-function
- description: Upload a new GraphQL schema definition to an AppSync API.
  hints:
    openWorld: false
    readOnly: false
  name: start-schema-creation
---
