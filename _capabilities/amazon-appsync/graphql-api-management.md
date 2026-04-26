---
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
- create a resolver that maps a graphql field to a data source operation.
- create a reusable pipeline function for use in pipeline resolvers.
- create a new graphql api with the specified authentication type and configuration.
- graphql schema management
- get graphql api
- serverless
- list all resolvers for a specific graphql type to understand field-to-data-source mappings.
- list graphql apis
- start schema creation
- create function
- aws
- upload a new graphql schema definition to an appsync api.
- api management
- get complete details of a graphql api including authentication configuration and endpoints.
- create a graphql api
- upload a new graphql schema
- list all appsync graphql apis to understand available apis and their configurations.
- list all data sources connected to a graphql api.
- list resolvers
- amazon appsync
- connect a data source (dynamodb, lambda, opensearch, http) to a graphql api.
- graphql
- list data sources
- list all graphql apis
- create data source
- graphql api management
- create graphql api
- list functions
- create resolver
- list reusable pipeline functions available for composing complex resolvers.
slug: graphql-api-management
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
