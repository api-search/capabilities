---
categories: []
consumed_apis: []
description: The Neon Management API is a RESTful interface for programmatically managing Neon serverless Postgres resources. It allows developers to create and manage projects, branches, databases, roles, compute endpoints, and operations. The API supports everything available through the Neon Console, enabling automation of database infrastructure workflows. An OpenAPI 3.0 specification is available along with TypeScript, Python, and Go SDKs.
layout: capability
name: Neon Management API
operations:
- description: List projects
  method: GET
  name: listprojects
  path: /projects
- description: Create a project
  method: POST
  name: createproject
  path: /projects
- description: Retrieve project details
  method: GET
  name: getproject
  path: /projects/{project_id}
- description: Update a project
  method: PATCH
  name: updateproject
  path: /projects/{project_id}
- description: Delete a project
  method: DELETE
  name: deleteproject
  path: /projects/{project_id}
- description: List branches
  method: GET
  name: listprojectbranches
  path: /projects/{project_id}/branches
- description: Create a branch
  method: POST
  name: createprojectbranch
  path: /projects/{project_id}/branches
- description: Retrieve branch details
  method: GET
  name: getprojectbranch
  path: /projects/{project_id}/branches/{branch_id}
- description: Update a branch
  method: PATCH
  name: updateprojectbranch
  path: /projects/{project_id}/branches/{branch_id}
- description: Delete a branch
  method: DELETE
  name: deleteprojectbranch
  path: /projects/{project_id}/branches/{branch_id}
- description: Restore a branch
  method: POST
  name: restoreprojectbranch
  path: /projects/{project_id}/branches/{branch_id}/restore
- description: List databases
  method: GET
  name: listprojectbranchdatabases
  path: /projects/{project_id}/branches/{branch_id}/databases
- description: Create a database
  method: POST
  name: createprojectbranchdatabase
  path: /projects/{project_id}/branches/{branch_id}/databases
- description: Retrieve database details
  method: GET
  name: getprojectbranchdatabase
  path: /projects/{project_id}/branches/{branch_id}/databases/{database_name}
- description: Update a database
  method: PATCH
  name: updateprojectbranchdatabase
  path: /projects/{project_id}/branches/{branch_id}/databases/{database_name}
- description: Delete a database
  method: DELETE
  name: deleteprojectbranchdatabase
  path: /projects/{project_id}/branches/{branch_id}/databases/{database_name}
- description: List roles
  method: GET
  name: listprojectbranchroles
  path: /projects/{project_id}/branches/{branch_id}/roles
- description: Create a role
  method: POST
  name: createprojectbranchrole
  path: /projects/{project_id}/branches/{branch_id}/roles
- description: Retrieve role details
  method: GET
  name: getprojectbranchrole
  path: /projects/{project_id}/branches/{branch_id}/roles/{role_name}
- description: Delete a role
  method: DELETE
  name: deleteprojectbranchrole
  path: /projects/{project_id}/branches/{branch_id}/roles/{role_name}
- description: Reset role password
  method: POST
  name: resetprojectbranchrolepassword
  path: /projects/{project_id}/branches/{branch_id}/roles/{role_name}/reset_password
- description: List compute endpoints
  method: GET
  name: listprojectendpoints
  path: /projects/{project_id}/endpoints
- description: Create a compute endpoint
  method: POST
  name: createprojectendpoint
  path: /projects/{project_id}/endpoints
- description: Retrieve compute endpoint details
  method: GET
  name: getprojectendpoint
  path: /projects/{project_id}/endpoints/{endpoint_id}
- description: Update a compute endpoint
  method: PATCH
  name: updateprojectendpoint
  path: /projects/{project_id}/endpoints/{endpoint_id}
- description: Delete a compute endpoint
  method: DELETE
  name: deleteprojectendpoint
  path: /projects/{project_id}/endpoints/{endpoint_id}
- description: Start a compute endpoint
  method: POST
  name: startprojectendpoint
  path: /projects/{project_id}/endpoints/{endpoint_id}/start
- description: Suspend a compute endpoint
  method: POST
  name: suspendprojectendpoint
  path: /projects/{project_id}/endpoints/{endpoint_id}/suspend
- description: Restart a compute endpoint
  method: POST
  name: restartprojectendpoint
  path: /projects/{project_id}/endpoints/{endpoint_id}/restart
- description: List branch endpoints
  method: GET
  name: listprojectbranchendpoints
  path: /projects/{project_id}/branches/{branch_id}/endpoints
- description: List project operations
  method: GET
  name: listprojectoperations
  path: /projects/{project_id}/operations
- description: Retrieve operation details
  method: GET
  name: getprojectoperation
  path: /projects/{project_id}/operations/{operation_id}
- description: Get account consumption metrics
  method: GET
  name: getconsumptionhistoryperaccount
  path: /consumption_history/account
- description: Get project consumption metrics
  method: GET
  name: getconsumptionhistoryperproject
  path: /consumption_history/projects
- description: List API keys
  method: GET
  name: listapikeys
  path: /api_keys
- description: Create an API key
  method: POST
  name: createapikey
  path: /api_keys
- description: Revoke an API key
  method: DELETE
  name: revokeapikey
  path: /api_keys/{key_id}
- description: Get Data API configuration
  method: GET
  name: getprojectbranchdataapi
  path: /projects/{project_id}/branches/{branch_id}/data-api
- description: Update Data API configuration
  method: PUT
  name: updateprojectbranchdataapi
  path: /projects/{project_id}/branches/{branch_id}/data-api
- description: Get Auth configuration
  method: GET
  name: getprojectbranchauth
  path: /projects/{project_id}/branches/{branch_id}/auth
- description: Update Auth configuration
  method: PUT
  name: updateprojectbranchauth
  path: /projects/{project_id}/branches/{branch_id}/auth
- description: List OAuth providers
  method: GET
  name: listneonauthoauthproviders
  path: /projects/{project_id}/branches/{branch_id}/auth/providers
- description: Create an OAuth provider
  method: POST
  name: createneonauthoauthprovider
  path: /projects/{project_id}/branches/{branch_id}/auth/providers
- description: Update an OAuth provider
  method: PATCH
  name: updateneonauthoauthprovider
  path: /projects/{project_id}/branches/{branch_id}/auth/providers/{provider_id}
- description: Delete an OAuth provider
  method: DELETE
  name: deleteneonauthoauthprovider
  path: /projects/{project_id}/branches/{branch_id}/auth/providers/{provider_id}
- description: Retrieve connection URI
  method: GET
  name: getconnectionuri
  path: /projects/{project_id}/connection_uri
personas: []
provider_name: Neon
provider_slug: neon
search_terms:
- updateprojectbranchauth
- api
- listprojectendpoints
- list databases
- getconnectionuri
- list project operations
- list compute endpoints
- deleteproject
- create a branch
- get auth configuration
- getprojectbranch
- suspendprojectendpoint
- listprojectoperations
- getprojectbranchauth
- delete a branch
- databases
- update a branch
- updateprojectbranchdataapi
- createprojectendpoint
- deleteprojectbranchdatabase
- create a role
- authentication
- create a project
- update an oauth provider
- getprojectendpoint
- updateprojectendpoint
- updateprojectbranchdatabase
- updateproject
- serverless
- listapikeys
- list projects
- startprojectendpoint
- deleteprojectbranchrole
- retrieve role details
- update a project
- retrieve project details
- updateprojectbranch
- retrieve database details
- list roles
- listneonauthoauthproviders
- createprojectbranchdatabase
- delete an oauth provider
- retrieve operation details
- getproject
- retrieve compute endpoint details
- getprojectbranchdataapi
- getprojectbranchrole
- get project consumption metrics
- retrieve connection uri
- infrastructure
- listprojectbranchdatabases
- restoreprojectbranch
- listprojectbranchroles
- update auth configuration
- getprojectbranchdatabase
- suspend a compute endpoint
- listprojectbranchendpoints
- getconsumptionhistoryperaccount
- deleteprojectbranch
- revoke an api key
- get account consumption metrics
- get data api configuration
- list branch endpoints
- deleteneonauthoauthprovider
- start a compute endpoint
- createapikey
- delete a role
- update a compute endpoint
- delete a project
- listprojectbranches
- createproject
- delete a database
- revokeapikey
- list oauth providers
- neon
- create a database
- updateneonauthoauthprovider
- createneonauthoauthprovider
- create a compute endpoint
- createprojectbranch
- restart a compute endpoint
- getconsumptionhistoryperproject
- edge
- delete a compute endpoint
- update data api configuration
- createprojectbranchrole
- getprojectoperation
- create an oauth provider
- create an api key
- list branches
- retrieve branch details
- list api keys
- postgres
- restore a branch
- reset role password
- listprojects
- deleteprojectendpoint
- update a database
- restartprojectendpoint
- resetprojectbranchrolepassword
slug: neon-capability
source_filename: neon-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Neon Management API\n  description: The Neon Management API is a RESTful interface for programmatically managing Neon serverless Postgres resources.\n    It allows developers to create and manage projects, branches, databases, roles, compute endpoints, and operations. The\n    API supports everything available through the Neon Console, enabling automation of database infrastructure workflows.\n    An OpenAPI 3.0 specification is available along with TypeScript, Python, and Go SDKs.\n  tags:\n  - Neon\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: neon\n    baseUri: https://console.neon.tech/api/v2\n    description: Neon Management API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{NEON_TOKEN}}'\n    resources:\n    - name: projects\n      path: /projects\n      operations:\n      - name: listprojects\n        method: GET\n        description: List\
  \ projects\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createproject\n        method: POST\n        description: Create a project\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-project-id\n      path: /projects/{project_id}\n      operations:\n      - name: getproject\n        method: GET\n        description: Retrieve project details\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateproject\n        method: PATCH\n        description: Update a project\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteproject\n        method: DELETE\n        description: Delete a project\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-project-id-branches\n      path: /projects/{project_id}/branches\n      operations:\n      - name: listprojectbranches\n        method: GET\n        description: List branches\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createprojectbranch\n        method: POST\n        description: Create a branch\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-project-id-branches-branch-id\n      path: /projects/{project_id}/branches/{branch_id}\n      operations:\n      - name: getprojectbranch\n        method: GET\n        description: Retrieve branch details\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n      - name: updateprojectbranch\n        method: PATCH\n        description: Update a branch\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteprojectbranch\n        method: DELETE\n        description: Delete a branch\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-project-id-branches-branch-id-restore\n      path: /projects/{project_id}/branches/{branch_id}/restore\n      operations:\n      - name: restoreprojectbranch\n        method: POST\n        description: Restore a branch\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-project-id-branches-branch-id-databases\n      path: /projects/{project_id}/branches/{branch_id}/databases\n      operations:\n      - name: listprojectbranchdatabases\n\
  \        method: GET\n        description: List databases\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createprojectbranchdatabase\n        method: POST\n        description: Create a database\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-project-id-branches-branch-id-databases\n      path: /projects/{project_id}/branches/{branch_id}/databases/{database_name}\n      operations:\n      - name: getprojectbranchdatabase\n        method: GET\n        description: Retrieve database details\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateprojectbranchdatabase\n        method: PATCH\n        description: Update a database\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n      - name: deleteprojectbranchdatabase\n        method: DELETE\n        description: Delete a database\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-project-id-branches-branch-id-roles\n      path: /projects/{project_id}/branches/{branch_id}/roles\n      operations:\n      - name: listprojectbranchroles\n        method: GET\n        description: List roles\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createprojectbranchrole\n        method: POST\n        description: Create a role\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-project-id-branches-branch-id-roles-rol\n      path: /projects/{project_id}/branches/{branch_id}/roles/{role_name}\n\
  \      operations:\n      - name: getprojectbranchrole\n        method: GET\n        description: Retrieve role details\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteprojectbranchrole\n        method: DELETE\n        description: Delete a role\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-project-id-branches-branch-id-roles-rol\n      path: /projects/{project_id}/branches/{branch_id}/roles/{role_name}/reset_password\n      operations:\n      - name: resetprojectbranchrolepassword\n        method: POST\n        description: Reset role password\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-project-id-endpoints\n      path: /projects/{project_id}/endpoints\n      operations:\n      - name:\
  \ listprojectendpoints\n        method: GET\n        description: List compute endpoints\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createprojectendpoint\n        method: POST\n        description: Create a compute endpoint\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-project-id-endpoints-endpoint-id\n      path: /projects/{project_id}/endpoints/{endpoint_id}\n      operations:\n      - name: getprojectendpoint\n        method: GET\n        description: Retrieve compute endpoint details\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateprojectendpoint\n        method: PATCH\n        description: Update a compute endpoint\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n      - name: deleteprojectendpoint\n        method: DELETE\n        description: Delete a compute endpoint\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-project-id-endpoints-endpoint-id-start\n      path: /projects/{project_id}/endpoints/{endpoint_id}/start\n      operations:\n      - name: startprojectendpoint\n        method: POST\n        description: Start a compute endpoint\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-project-id-endpoints-endpoint-id-suspen\n      path: /projects/{project_id}/endpoints/{endpoint_id}/suspend\n      operations:\n      - name: suspendprojectendpoint\n        method: POST\n        description: Suspend a compute endpoint\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n    - name: projects-project-id-endpoints-endpoint-id-restar\n      path: /projects/{project_id}/endpoints/{endpoint_id}/restart\n      operations:\n      - name: restartprojectendpoint\n        method: POST\n        description: Restart a compute endpoint\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-project-id-branches-branch-id-endpoints\n      path: /projects/{project_id}/branches/{branch_id}/endpoints\n      operations:\n      - name: listprojectbranchendpoints\n        method: GET\n        description: List branch endpoints\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-project-id-operations\n      path: /projects/{project_id}/operations\n      operations:\n      - name: listprojectoperations\n        method: GET\n        description:\
  \ List project operations\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-project-id-operations-operation-id\n      path: /projects/{project_id}/operations/{operation_id}\n      operations:\n      - name: getprojectoperation\n        method: GET\n        description: Retrieve operation details\n        inputParameters:\n        - name: operation_id\n          in: path\n          type: string\n          required: true\n          description: The operation ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: consumption-history-account\n      path: /consumption_history/account\n      operations:\n      - name: getconsumptionhistoryperaccount\n        method: GET\n        description: Get account consumption metrics\n        inputParameters:\n        - name: from\n          in: query\n          type:\
  \ string\n          required: true\n          description: Start date for the consumption period\n        - name: to\n          in: query\n          type: string\n          required: true\n          description: End date for the consumption period\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: consumption-history-projects\n      path: /consumption_history/projects\n      operations:\n      - name: getconsumptionhistoryperproject\n        method: GET\n        description: Get project consumption metrics\n        inputParameters:\n        - name: from\n          in: query\n          type: string\n          required: true\n          description: Start date for the consumption period\n        - name: to\n          in: query\n          type: string\n          required: true\n          description: End date for the consumption period\n        outputRawFormat: json\n        outputParameters:\n       \
  \ - name: result\n          type: object\n          value: $.\n    - name: api-keys\n      path: /api_keys\n      operations:\n      - name: listapikeys\n        method: GET\n        description: List API keys\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createapikey\n        method: POST\n        description: Create an API key\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-keys-key-id\n      path: /api_keys/{key_id}\n      operations:\n      - name: revokeapikey\n        method: DELETE\n        description: Revoke an API key\n        inputParameters:\n        - name: key_id\n          in: path\n          type: integer\n          required: true\n          description: The API key ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n      \
  \    value: $.\n    - name: projects-project-id-branches-branch-id-data-api\n      path: /projects/{project_id}/branches/{branch_id}/data-api\n      operations:\n      - name: getprojectbranchdataapi\n        method: GET\n        description: Get Data API configuration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateprojectbranchdataapi\n        method: PUT\n        description: Update Data API configuration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-project-id-branches-branch-id-auth\n      path: /projects/{project_id}/branches/{branch_id}/auth\n      operations:\n      - name: getprojectbranchauth\n        method: GET\n        description: Get Auth configuration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n      - name: updateprojectbranchauth\n        method: PUT\n        description: Update Auth configuration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-project-id-branches-branch-id-auth-prov\n      path: /projects/{project_id}/branches/{branch_id}/auth/providers\n      operations:\n      - name: listneonauthoauthproviders\n        method: GET\n        description: List OAuth providers\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createneonauthoauthprovider\n        method: POST\n        description: Create an OAuth provider\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-project-id-branches-branch-id-auth-prov\n      path: /projects/{project_id}/branches/{branch_id}/auth/providers/{provider_id}\n\
  \      operations:\n      - name: updateneonauthoauthprovider\n        method: PATCH\n        description: Update an OAuth provider\n        inputParameters:\n        - name: provider_id\n          in: path\n          type: string\n          required: true\n          description: The OAuth provider ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteneonauthoauthprovider\n        method: DELETE\n        description: Delete an OAuth provider\n        inputParameters:\n        - name: provider_id\n          in: path\n          type: string\n          required: true\n          description: The OAuth provider ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-project-id-connection-uri\n      path: /projects/{project_id}/connection_uri\n      operations:\n      - name: getconnectionuri\n      \
  \  method: GET\n        description: Retrieve connection URI\n        inputParameters:\n        - name: branch_id\n          in: query\n          type: string\n          description: The branch ID\n        - name: endpoint_id\n          in: query\n          type: string\n          description: The endpoint ID\n        - name: database_name\n          in: query\n          type: string\n          required: true\n          description: The database name\n        - name: role_name\n          in: query\n          type: string\n          required: true\n          description: The role name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: neon-rest\n    description: REST adapter for Neon Management API.\n    resources:\n    - path: /projects\n      name: listprojects\n      operations:\n      - method: GET\n        name: listprojects\n        description: List\
  \ projects\n        call: neon.listprojects\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects\n      name: createproject\n      operations:\n      - method: POST\n        name: createproject\n        description: Create a project\n        call: neon.createproject\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project_id}\n      name: getproject\n      operations:\n      - method: GET\n        name: getproject\n        description: Retrieve project details\n        call: neon.getproject\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project_id}\n      name: updateproject\n      operations:\n      - method: PATCH\n        name: updateproject\n        description: Update a project\n        call: neon.updateproject\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project_id}\n      name: deleteproject\n\
  \      operations:\n      - method: DELETE\n        name: deleteproject\n        description: Delete a project\n        call: neon.deleteproject\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project_id}/branches\n      name: listprojectbranches\n      operations:\n      - method: GET\n        name: listprojectbranches\n        description: List branches\n        call: neon.listprojectbranches\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project_id}/branches\n      name: createprojectbranch\n      operations:\n      - method: POST\n        name: createprojectbranch\n        description: Create a branch\n        call: neon.createprojectbranch\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project_id}/branches/{branch_id}\n      name: getprojectbranch\n      operations:\n      - method: GET\n        name: getprojectbranch\n        description:\
  \ Retrieve branch details\n        call: neon.getprojectbranch\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project_id}/branches/{branch_id}\n      name: updateprojectbranch\n      operations:\n      - method: PATCH\n        name: updateprojectbranch\n        description: Update a branch\n        call: neon.updateprojectbranch\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project_id}/branches/{branch_id}\n      name: deleteprojectbranch\n      operations:\n      - method: DELETE\n        name: deleteprojectbranch\n        description: Delete a branch\n        call: neon.deleteprojectbranch\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project_id}/branches/{branch_id}/restore\n      name: restoreprojectbranch\n      operations:\n      - method: POST\n        name: restoreprojectbranch\n        description: Restore a branch\n       \
  \ call: neon.restoreprojectbranch\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project_id}/branches/{branch_id}/databases\n      name: listprojectbranchdatabases\n      operations:\n      - method: GET\n        name: listprojectbranchdatabases\n        description: List databases\n        call: neon.listprojectbranchdatabases\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project_id}/branches/{branch_id}/databases\n      name: createprojectbranchdatabase\n      operations:\n      - method: POST\n        name: createprojectbranchdatabase\n        description: Create a database\n        call: neon.createprojectbranchdatabase\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project_id}/branches/{branch_id}/databases/{database_name}\n      name: getprojectbranchdatabase\n      operations:\n      - method: GET\n        name: getprojectbranchdatabase\n\
  \        description: Retrieve database details\n        call: neon.getprojectbranchdatabase\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project_id}/branches/{branch_id}/databases/{database_name}\n      name: updateprojectbranchdatabase\n      operations:\n      - method: PATCH\n        name: updateprojectbranchdatabase\n        description: Update a database\n        call: neon.updateprojectbranchdatabase\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project_id}/branches/{branch_id}/databases/{database_name}\n      name: deleteprojectbranchdatabase\n      operations:\n      - method: DELETE\n        name: deleteprojectbranchdatabase\n        description: Delete a database\n        call: neon.deleteprojectbranchdatabase\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project_id}/branches/{branch_id}/roles\n      name: listprojectbranchroles\n\
  \      operations:\n      - method: GET\n        name: listprojectbranchroles\n        description: List roles\n        call: neon.listprojectbranchroles\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project_id}/branches/{branch_id}/roles\n      name: createprojectbranchrole\n      operations:\n      - method: POST\n        name: createprojectbranchrole\n        description: Create a role\n        call: neon.createprojectbranchrole\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project_id}/branches/{branch_id}/roles/{role_name}\n      name: getprojectbranchrole\n      operations:\n      - method: GET\n        name: getprojectbranchrole\n        description: Retrieve role details\n        call: neon.getprojectbranchrole\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project_id}/branches/{branch_id}/roles/{role_name}\n      name: deleteprojectbranchrole\n\
  \      operations:\n      - method: DELETE\n        name: deleteprojectbranchrole\n        description: Delete a role\n        call: neon.deleteprojectbranchrole\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project_id}/branches/{branch_id}/roles/{role_name}/reset_password\n      name: resetprojectbranchrolepassword\n      operations:\n      - method: POST\n        name: resetprojectbranchrolepassword\n        description: Reset role password\n        call: neon.resetprojectbranchrolepassword\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project_id}/endpoints\n      name: listprojectendpoints\n      operations:\n      - method: GET\n        name: listprojectendpoints\n        description: List compute endpoints\n        call: neon.listprojectendpoints\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project_id}/endpoints\n      name: createprojectendpoint\n\
  \      operations:\n      - method: POST\n        name: createprojectendpoint\n        description: Create a compute endpoint\n        call: neon.createprojectendpoint\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project_id}/endpoints/{endpoint_id}\n      name: getprojectendpoint\n      operations:\n      - method: GET\n        name: getprojectendpoint\n        description: Retrieve compute endpoint details\n        call: neon.getprojectendpoint\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project_id}/endpoints/{endpoint_id}\n      name: updateprojectendpoint\n      operations:\n      - method: PATCH\n        name: updateprojectendpoint\n        description: Update a compute endpoint\n        call: neon.updateprojectendpoint\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project_id}/endpoints/{endpoint_id}\n      name: deleteprojectendpoint\n\
  \      operations:\n      - method: DELETE\n        name: deleteprojectendpoint\n        description: Delete a compute endpoint\n        call: neon.deleteprojectendpoint\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project_id}/endpoints/{endpoint_id}/start\n      name: startprojectendpoint\n      operations:\n      - method: POST\n        name: startprojectendpoint\n        description: Start a compute endpoint\n        call: neon.startprojectendpoint\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project_id}/endpoints/{endpoint_id}/suspend\n      name: suspendprojectendpoint\n      operations:\n      - method: POST\n        name: suspendprojectendpoint\n        description: Suspend a compute endpoint\n        call: neon.suspendprojectendpoint\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project_id}/endpoints/{endpoint_id}/restart\n\
  \      name: restartprojectendpoint\n      operations:\n      - method: POST\n        name: restartprojectendpoint\n        description: Restart a compute endpoint\n        call: neon.restartprojectendpoint\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project_id}/branches/{branch_id}/endpoints\n      name: listprojectbranchendpoints\n      operations:\n      - method: GET\n        name: listprojectbranchendpoints\n        description: List branch endpoints\n        call: neon.listprojectbranchendpoints\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project_id}/operations\n      name: listprojectoperations\n      operations:\n      - method: GET\n        name: listprojectoperations\n        description: List project operations\n        call: neon.listprojectoperations\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project_id}/operations/{operation_id}\n\
  \      name: getprojectoperation\n      operations:\n      - method: GET\n        name: getprojectoperation\n        description: Retrieve operation details\n        call: neon.getprojectoperation\n        with:\n          operation_id: rest.operation_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /consumption_history/account\n      name: getconsumptionhistoryperaccount\n      operations:\n      - method: GET\n        name: getconsumptionhistoryperaccount\n        description: Get account consumption metrics\n        call: neon.getconsumptionhistoryperaccount\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /consumption_history/projects\n      name: getconsumptionhistoryperproject\n      operations:\n      - method: GET\n        name: getconsumptionhistoryperproject\n        description: Get project consumption metrics\n        call: neon.getconsumptionhistoryperproject\n        outputParameters:\n       \
  \ - type: object\n          mapping: $.\n    - path: /api_keys\n      name: listapikeys\n      operations:\n      - method: GET\n        name: listapikeys\n        description: List API keys\n        call: neon.listapikeys\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api_keys\n      name: createapikey\n      operations:\n      - method: POST\n        name: createapikey\n        description: Create an API key\n        call: neon.createapikey\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api_keys/{key_id}\n      name: revokeapikey\n      operations:\n      - method: DELETE\n        name: revokeapikey\n        description: Revoke an API key\n        call: neon.revokeapikey\n        with:\n          key_id: rest.key_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project_id}/branches/{branch_id}/data-api\n      name: getprojectbranchdataapi\n      operations:\n\
  \      - method: GET\n        name: getprojectbranchdataapi\n        description: Get Data API configuration\n        call: neon.getprojectbranchdataapi\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project_id}/branches/{branch_id}/data-api\n      name: updateprojectbranchdataapi\n      operations:\n      - method: PUT\n        name: updateprojectbranchdataapi\n        description: Update Data API configuration\n        call: neon.updateprojectbranchdataapi\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project_id}/branches/{branch_id}/auth\n      name: getprojectbranchauth\n      operations:\n      - method: GET\n        name: getprojectbranchauth\n        description: Get Auth configuration\n        call: neon.getprojectbranchauth\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project_id}/branches/{branch_id}/auth\n      name: updateprojectbranchauth\n\
  \      operations:\n      - method: PUT\n        name: updateprojectbranchauth\n        description: Update Auth configuration\n        call: neon.updateprojectbranchauth\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project_id}/branches/{branch_id}/auth/providers\n      name: listneonauthoauthproviders\n      operations:\n      - method: GET\n        name: listneonauthoauthproviders\n        description: List OAuth providers\n        call: neon.listneonauthoauthproviders\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project_id}/branches/{branch_id}/auth/providers\n      name: createneonauthoauthprovider\n      operations:\n      - method: POST\n        name: createneonauthoauthprovider\n        description: Create an OAuth provider\n        call: neon.createneonauthoauthprovider\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project_id}/branches/{branch_id}/auth/providers/{provider_id}\n\
  \      name: updateneonauthoauthprovider\n      operations:\n      - method: PATCH\n        name: updateneonauthoauthprovider\n        description: Update an OAuth provider\n        call: neon.updateneonauthoauthprovider\n        with:\n          provider_id: rest.provider_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project_id}/branches/{branch_id}/auth/providers/{provider_id}\n      name: deleteneonauthoauthprovider\n      operations:\n      - method: DELETE\n        name: deleteneonauthoauthprovider\n        description: Delete an OAuth provider\n        call: neon.deleteneonauthoauthprovider\n        with:\n          provider_id: rest.provider_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project_id}/connection_uri\n      name: getconnectionuri\n      operations:\n      - method: GET\n        name: getconnectionuri\n        description: Retrieve connection URI\n        call:\
  \ neon.getconnectionuri\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: neon-mcp\n    transport: http\n    description: MCP adapter for Neon Management API for AI agent use.\n    tools:\n    - name: listprojects\n      description: List projects\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: neon.listprojects\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createproject\n      description: Create a project\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: neon.createproject\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getproject\n      description: Retrieve project details\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: neon.getproject\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n    - name: updateproject\n      description: Update a project\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: neon.updateproject\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteproject\n      description: Delete a project\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: neon.deleteproject\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listprojectbranches\n      description: List branches\n      hints:\n        readOnly:\n\n# --- truncated at 32 KB (44 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/neon/refs/heads/main/capabilities/neon-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/neon/refs/heads/main/capabilities/neon-capability.yaml
tags:
- Neon
- API
tools:
- description: List projects
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listprojects
- description: Create a project
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createproject
- description: Retrieve project details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getproject
- description: Update a project
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateproject
- description: Delete a project
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteproject
- description: List branches
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listprojectbranches
- description: Create a branch
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createprojectbranch
- description: Retrieve branch details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getprojectbranch
- description: Update a branch
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateprojectbranch
- description: Delete a branch
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteprojectbranch
- description: Restore a branch
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: restoreprojectbranch
- description: List databases
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listprojectbranchdatabases
- description: Create a database
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createprojectbranchdatabase
- description: Retrieve database details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getprojectbranchdatabase
- description: Update a database
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateprojectbranchdatabase
- description: Delete a database
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteprojectbranchdatabase
- description: List roles
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listprojectbranchroles
- description: Create a role
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createprojectbranchrole
- description: Retrieve role details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getprojectbranchrole
- description: Delete a role
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteprojectbranchrole
- description: Reset role password
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: resetprojectbranchrolepassword
- description: List compute endpoints
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listprojectendpoints
- description: Create a compute endpoint
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createprojectendpoint
- description: Retrieve compute endpoint details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getprojectendpoint
- description: Update a compute endpoint
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateprojectendpoint
- description: Delete a compute endpoint
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteprojectendpoint
- description: Start a compute endpoint
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: startprojectendpoint
- description: Suspend a compute endpoint
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: suspendprojectendpoint
- description: Restart a compute endpoint
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: restartprojectendpoint
- description: List branch endpoints
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listprojectbranchendpoints
- description: List project operations
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listprojectoperations
- description: Retrieve operation details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getprojectoperation
- description: Get account consumption metrics
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getconsumptionhistoryperaccount
- description: Get project consumption metrics
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getconsumptionhistoryperproject
- description: List API keys
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listapikeys
- description: Create an API key
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createapikey
- description: Revoke an API key
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: revokeapikey
- description: Get Data API configuration
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getprojectbranchdataapi
- description: Update Data API configuration
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateprojectbranchdataapi
- description: Get Auth configuration
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getprojectbranchauth
- description: Update Auth configuration
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateprojectbranchauth
- description: List OAuth providers
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listneonauthoauthproviders
- description: Create an OAuth provider
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createneonauthoauthprovider
- description: Update an OAuth provider
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateneonauthoauthprovider
- description: Delete an OAuth provider
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteneonauthoauthprovider
- description: Retrieve connection URI
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getconnectionuri
---
