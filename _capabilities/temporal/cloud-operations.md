---
categories: []
consumed_apis: []
description: Unified workflow for platform administrators to manage Temporal Cloud infrastructure including namespaces, users, service accounts, API keys, and regions.
layout: capability
name: Temporal Cloud Operations
operations:
- description: List all namespaces
  method: GET
  name: list-namespaces
  path: /v1/namespaces
- description: Create a namespace
  method: POST
  name: create-namespace
  path: /v1/namespaces
- description: Get namespace details
  method: GET
  name: get-namespace
  path: /v1/namespaces/{namespace}
- description: Delete a namespace
  method: DELETE
  name: delete-namespace
  path: /v1/namespaces/{namespace}
- description: List all users
  method: GET
  name: list-users
  path: /v1/users
- description: Create a user
  method: POST
  name: create-user
  path: /v1/users
- description: List all service accounts
  method: GET
  name: list-service-accounts
  path: /v1/service-accounts
- description: Create a service account
  method: POST
  name: create-service-account
  path: /v1/service-accounts
- description: List all API keys
  method: GET
  name: list-api-keys
  path: /v1/api-keys
- description: Create an API key
  method: POST
  name: create-api-key
  path: /v1/api-keys
- description: List available regions
  method: GET
  name: list-regions
  path: /v1/regions
personas: []
provider_name: Temporal
provider_slug: temporal
search_terms:
- create service account
- list all temporal cloud namespaces
- delete api key
- service account management
- delete service account
- get async operation
- api key management
- create a new temporal cloud namespace
- workflow infrastructure
- get namespace
- list regions
- list all api keys
- single namespace operations
- delete a user
- cloud operations
- create a namespace
- create namespace
- get namespace details
- list all users
- update namespace configuration
- list all service accounts
- namespace management
- delete a namespace
- list all users in the account
- get user details
- list available regions
- get details for a specific namespace
- delete user
- get service account details
- get api key
- list users
- delete an api key
- procode_api_composition
- list all available temporal cloud regions
- temporal
- create an api key
- region information
- delete a temporal cloud namespace
- list api keys
- list namespaces
- delete a service account
- delete namespace
- user management
- get user
- check the status of an asynchronous operation
- list all api keys in the account
- create a user
- create user
- list all namespaces
- update namespace
- create a new user
- get service account
- create a service account
- create a new api key for authentication
- create a service account for api access
- workflows
- get api key details
- platform administration
- create api key
- list service accounts
slug: cloud-operations
source_filename: cloud-operations.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Temporal Cloud Operations\n  description: Unified workflow for platform administrators to manage Temporal Cloud infrastructure including namespaces,\n    users, service accounts, API keys, and regions.\n  tags:\n  - Temporal\n  - Cloud Operations\n  - Platform Administration\n  - Workflow Infrastructure\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    TEMPORAL_API_KEY: TEMPORAL_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: cloud-ops\n    baseUri: https://saas-api.tmprl.cloud\n    description: Temporal Cloud Operations API for managing cloud resources.\n    authentication:\n      type: bearer\n      token: '{{TEMPORAL_API_KEY}}'\n    resources:\n    - name: namespaces\n      path: /api/v1\n      description: Namespace management\n      operations:\n      - name: list-namespaces\n        method: GET\n        description: List all namespaces\n        inputParameters:\n        -\
  \ name: pageSize\n          in: query\n          type: integer\n          required: false\n          description: Page size\n        - name: pageToken\n          in: query\n          type: string\n          required: false\n          description: Page token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-namespace\n        method: POST\n        description: Create a new namespace\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            spec: '{{tools.spec}}'\n      - name: get-namespace\n        method: GET\n        description: Get namespace details\n        inputParameters:\n        - name: namespace\n          in: path\n          type: string\n          required: true\n          description: Namespace name\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: delete-namespace\n        method: DELETE\n        description: Delete a namespace\n        inputParameters:\n        - name: namespace\n          in: path\n          type: string\n          required: true\n          description: Namespace name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-namespace\n        method: POST\n        description: Update namespace configuration\n        inputParameters:\n        - name: namespace\n          in: path\n          type: string\n          required: true\n          description: Namespace name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            resourceVersion: '{{tools.resourceVersion}}'\n            spec: '{{tools.spec}}'\n\
  \    - name: users\n      path: /api/v1\n      description: User management\n      operations:\n      - name: list-users\n        method: GET\n        description: List all users\n        inputParameters:\n        - name: pageSize\n          in: query\n          type: integer\n          required: false\n          description: Page size\n        - name: pageToken\n          in: query\n          type: string\n          required: false\n          description: Page token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-user\n        method: POST\n        description: Create a new user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            spec: '{{tools.spec}}'\n      - name: get-user\n        method: GET\n        description: Get user details\n        inputParameters:\n\
  \        - name: userId\n          in: path\n          type: string\n          required: true\n          description: User ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-user\n        method: DELETE\n        description: Delete a user\n        inputParameters:\n        - name: userId\n          in: path\n          type: string\n          required: true\n          description: User ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: service-accounts\n      path: /api/v1\n      description: Service account management\n      operations:\n      - name: list-service-accounts\n        method: GET\n        description: List all service accounts\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-service-account\n\
  \        method: POST\n        description: Create a service account\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            spec: '{{tools.spec}}'\n      - name: get-service-account\n        method: GET\n        description: Get service account details\n        inputParameters:\n        - name: serviceAccountId\n          in: path\n          type: string\n          required: true\n          description: Service account ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-service-account\n        method: DELETE\n        description: Delete a service account\n        inputParameters:\n        - name: serviceAccountId\n          in: path\n          type: string\n          required: true\n          description: Service account ID\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-keys\n      path: /api/v1\n      description: API key management\n      operations:\n      - name: list-api-keys\n        method: GET\n        description: List all API keys\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-api-key\n        method: POST\n        description: Create an API key\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            spec: '{{tools.spec}}'\n      - name: get-api-key\n        method: GET\n        description: Get API key details\n        inputParameters:\n        - name: keyId\n          in: path\n          type: string\n          required: true\n          description: API key ID\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-api-key\n        method: DELETE\n        description: Delete an API key\n        inputParameters:\n        - name: keyId\n          in: path\n          type: string\n          required: true\n          description: API key ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: regions\n      path: /api/v1\n      description: Region information\n      operations:\n      - name: list-regions\n        method: GET\n        description: List all available regions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: async-operations\n      path: /api/v1\n      description: Async operation tracking\n      operations:\n      - name: get-async-operation\n        method: GET\n        description: Get\
  \ async operation status\n        inputParameters:\n        - name: asyncOperationId\n          in: path\n          type: string\n          required: true\n          description: Async operation ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: cloud-operations-api\n    description: Unified REST API for Temporal Cloud operations management.\n    resources:\n    - path: /v1/namespaces\n      name: namespaces\n      description: Namespace management\n      operations:\n      - method: GET\n        name: list-namespaces\n        description: List all namespaces\n        call: cloud-ops.list-namespaces\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-namespace\n        description: Create a namespace\n        call: cloud-ops.create-namespace\n        outputParameters:\n        - type:\
  \ object\n          mapping: $.\n    - path: /v1/namespaces/{namespace}\n      name: namespace-detail\n      description: Single namespace operations\n      operations:\n      - method: GET\n        name: get-namespace\n        description: Get namespace details\n        call: cloud-ops.get-namespace\n        with:\n          namespace: rest.namespace\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-namespace\n        description: Delete a namespace\n        call: cloud-ops.delete-namespace\n        with:\n          namespace: rest.namespace\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/users\n      name: users\n      description: User management\n      operations:\n      - method: GET\n        name: list-users\n        description: List all users\n        call: cloud-ops.list-users\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method:\
  \ POST\n        name: create-user\n        description: Create a user\n        call: cloud-ops.create-user\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/service-accounts\n      name: service-accounts\n      description: Service account management\n      operations:\n      - method: GET\n        name: list-service-accounts\n        description: List all service accounts\n        call: cloud-ops.list-service-accounts\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-service-account\n        description: Create a service account\n        call: cloud-ops.create-service-account\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/api-keys\n      name: api-keys\n      description: API key management\n      operations:\n      - method: GET\n        name: list-api-keys\n        description: List all API keys\n        call: cloud-ops.list-api-keys\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-api-key\n        description: Create an API key\n        call: cloud-ops.create-api-key\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/regions\n      name: regions\n      description: Region information\n      operations:\n      - method: GET\n        name: list-regions\n        description: List available regions\n        call: cloud-ops.list-regions\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: cloud-operations-mcp\n    transport: http\n    description: MCP server for AI-assisted Temporal Cloud operations management.\n    tools:\n    - name: list-namespaces\n      description: List all Temporal Cloud namespaces\n      hints:\n        readOnly: true\n        openWorld: true\n      call: cloud-ops.list-namespaces\n      outputParameters:\n      - type:\
  \ object\n        mapping: $.\n    - name: create-namespace\n      description: Create a new Temporal Cloud namespace\n      hints:\n        readOnly: false\n      call: cloud-ops.create-namespace\n      with:\n        spec: tools.spec\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-namespace\n      description: Get details for a specific namespace\n      hints:\n        readOnly: true\n      call: cloud-ops.get-namespace\n      with:\n        namespace: tools.namespace\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-namespace\n      description: Update namespace configuration\n      hints:\n        readOnly: false\n        idempotent: true\n      call: cloud-ops.update-namespace\n      with:\n        namespace: tools.namespace\n        resourceVersion: tools.resourceVersion\n        spec: tools.spec\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-namespace\n      description:\
  \ Delete a Temporal Cloud namespace\n      hints:\n        destructive: true\n      call: cloud-ops.delete-namespace\n      with:\n        namespace: tools.namespace\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-users\n      description: List all users in the account\n      hints:\n        readOnly: true\n      call: cloud-ops.list-users\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-user\n      description: Create a new user\n      hints:\n        readOnly: false\n      call: cloud-ops.create-user\n      with:\n        spec: tools.spec\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-user\n      description: Get user details\n      hints:\n        readOnly: true\n      call: cloud-ops.get-user\n      with:\n        userId: tools.userId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-user\n      description: Delete a user\n      hints:\n\
  \        destructive: true\n      call: cloud-ops.delete-user\n      with:\n        userId: tools.userId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-service-accounts\n      description: List all service accounts\n      hints:\n        readOnly: true\n      call: cloud-ops.list-service-accounts\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-service-account\n      description: Create a service account for API access\n      hints:\n        readOnly: false\n      call: cloud-ops.create-service-account\n      with:\n        spec: tools.spec\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-service-account\n      description: Get service account details\n      hints:\n        readOnly: true\n      call: cloud-ops.get-service-account\n      with:\n        serviceAccountId: tools.serviceAccountId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-service-account\n\
  \      description: Delete a service account\n      hints:\n        destructive: true\n      call: cloud-ops.delete-service-account\n      with:\n        serviceAccountId: tools.serviceAccountId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-api-keys\n      description: List all API keys in the account\n      hints:\n        readOnly: true\n      call: cloud-ops.list-api-keys\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-api-key\n      description: Create a new API key for authentication\n      hints:\n        readOnly: false\n      call: cloud-ops.create-api-key\n      with:\n        spec: tools.spec\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-api-key\n      description: Get API key details\n      hints:\n        readOnly: true\n      call: cloud-ops.get-api-key\n      with:\n        keyId: tools.keyId\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: delete-api-key\n      description: Delete an API key\n      hints:\n        destructive: true\n      call: cloud-ops.delete-api-key\n      with:\n        keyId: tools.keyId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-regions\n      description: List all available Temporal Cloud regions\n      hints:\n        readOnly: true\n      call: cloud-ops.list-regions\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-async-operation\n      description: Check the status of an asynchronous operation\n      hints:\n        readOnly: true\n      call: cloud-ops.get-async-operation\n      with:\n        asyncOperationId: tools.asyncOperationId\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/temporal/refs/heads/main/capabilities/cloud-operations.yaml
tags:
- Temporal
- Cloud Operations
- Platform Administration
- Workflow Infrastructure
tools:
- description: List all Temporal Cloud namespaces
  hints:
    openWorld: true
    readOnly: true
  name: list-namespaces
- description: Create a new Temporal Cloud namespace
  hints:
    readOnly: false
  name: create-namespace
- description: Get details for a specific namespace
  hints:
    readOnly: true
  name: get-namespace
- description: Update namespace configuration
  hints:
    idempotent: true
    readOnly: false
  name: update-namespace
- description: Delete a Temporal Cloud namespace
  hints:
    destructive: true
  name: delete-namespace
- description: List all users in the account
  hints:
    readOnly: true
  name: list-users
- description: Create a new user
  hints:
    readOnly: false
  name: create-user
- description: Get user details
  hints:
    readOnly: true
  name: get-user
- description: Delete a user
  hints:
    destructive: true
  name: delete-user
- description: List all service accounts
  hints:
    readOnly: true
  name: list-service-accounts
- description: Create a service account for API access
  hints:
    readOnly: false
  name: create-service-account
- description: Get service account details
  hints:
    readOnly: true
  name: get-service-account
- description: Delete a service account
  hints:
    destructive: true
  name: delete-service-account
- description: List all API keys in the account
  hints:
    readOnly: true
  name: list-api-keys
- description: Create a new API key for authentication
  hints:
    readOnly: false
  name: create-api-key
- description: Get API key details
  hints:
    readOnly: true
  name: get-api-key
- description: Delete an API key
  hints:
    destructive: true
  name: delete-api-key
- description: List all available Temporal Cloud regions
  hints:
    readOnly: true
  name: list-regions
- description: Check the status of an asynchronous operation
  hints:
    readOnly: true
  name: get-async-operation
---
