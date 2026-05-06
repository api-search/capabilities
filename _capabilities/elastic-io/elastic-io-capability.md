---
categories: []
consumed_apis: []
description: The elastic.io Platform REST API v2 provides programmatic access to the elastic.io iPaaS platform. It allows you to manage integration flows, workspaces, contracts, credentials, components, recipes, users, and other platform resources. The API follows the JSON:API specification and uses Bearer token authentication.
layout: capability
name: elastic.io Platform REST API
operations:
- description: Elastic.io List flows
  method: GET
  name: listflows
  path: /flows
- description: Elastic.io Create a flow
  method: POST
  name: createflow
  path: /flows
- description: Elastic.io Get a flow
  method: GET
  name: getflow
  path: /flows/{flow_id}
- description: Elastic.io Update a flow
  method: PATCH
  name: updateflow
  path: /flows/{flow_id}
- description: Elastic.io Delete a flow
  method: DELETE
  name: deleteflow
  path: /flows/{flow_id}
- description: Elastic.io Start a flow
  method: POST
  name: startflow
  path: /flows/{flow_id}/start
- description: Elastic.io Stop a flow
  method: POST
  name: stopflow
  path: /flows/{flow_id}/stop
- description: Elastic.io Run a flow on demand
  method: POST
  name: runflownow
  path: /flows/{flow_id}/run-now
- description: Elastic.io List flow drafts
  method: GET
  name: listflowdrafts
  path: /flow-drafts
- description: Elastic.io Create a flow draft
  method: POST
  name: createflowdraft
  path: /flow-drafts
- description: Elastic.io Get a flow draft
  method: GET
  name: getflowdraft
  path: /flow-drafts/{flow_draft_id}
- description: Elastic.io Update a flow draft
  method: PATCH
  name: updateflowdraft
  path: /flow-drafts/{flow_draft_id}
- description: Elastic.io Delete a flow draft
  method: DELETE
  name: deleteflowdraft
  path: /flow-drafts/{flow_draft_id}
- description: Elastic.io Get a flow version
  method: GET
  name: getflowversion
  path: /flow-versions/{flow_version_id}
- description: Elastic.io List workspaces
  method: GET
  name: listworkspaces
  path: /workspaces
- description: Elastic.io Create a workspace
  method: POST
  name: createworkspace
  path: /workspaces
- description: Elastic.io Get a workspace
  method: GET
  name: getworkspace
  path: /workspaces/{workspace_id}
- description: Elastic.io Update a workspace
  method: PATCH
  name: updateworkspace
  path: /workspaces/{workspace_id}
- description: Elastic.io Delete a workspace
  method: DELETE
  name: deleteworkspace
  path: /workspaces/{workspace_id}
- description: Elastic.io List workspace members
  method: GET
  name: listworkspacemembers
  path: /workspaces/{workspace_id}/members
- description: Elastic.io Add a workspace member
  method: POST
  name: addworkspacemember
  path: /workspaces/{workspace_id}/members
- description: Elastic.io Remove a workspace member
  method: DELETE
  name: removeworkspacemember
  path: /workspaces/{workspace_id}/members/{user_id}
- description: Elastic.io List contracts
  method: GET
  name: listcontracts
  path: /contracts
- description: Elastic.io Get a contract
  method: GET
  name: getcontract
  path: /contracts/{contract_id}
- description: Elastic.io Update a contract
  method: PATCH
  name: updatecontract
  path: /contracts/{contract_id}
- description: Elastic.io List contract members
  method: GET
  name: listcontractmembers
  path: /contracts/{contract_id}/members
- description: Elastic.io Add a contract member
  method: POST
  name: addcontractmember
  path: /contracts/{contract_id}/members
- description: Elastic.io List credentials
  method: GET
  name: listcredentials
  path: /credentials
- description: Elastic.io Create a credential
  method: POST
  name: createcredential
  path: /credentials
- description: Elastic.io Get a credential
  method: GET
  name: getcredential
  path: /credentials/{credential_id}
- description: Elastic.io Update a credential
  method: PATCH
  name: updatecredential
  path: /credentials/{credential_id}
- description: Elastic.io Delete a credential
  method: DELETE
  name: deletecredential
  path: /credentials/{credential_id}
- description: Elastic.io List components
  method: GET
  name: listcomponents
  path: /components
- description: Elastic.io Get a component
  method: GET
  name: getcomponent
  path: /components/{component_id}
- description: Elastic.io Update a component
  method: PATCH
  name: updatecomponent
  path: /components/{component_id}
- description: Elastic.io Delete a component
  method: DELETE
  name: deletecomponent
  path: /components/{component_id}
- description: Elastic.io List recipes
  method: GET
  name: listrecipes
  path: /recipes
- description: Elastic.io Create a recipe
  method: POST
  name: createrecipe
  path: /recipes
- description: Elastic.io Get a recipe
  method: GET
  name: getrecipe
  path: /recipes/{recipe_id}
- description: Elastic.io Update a recipe
  method: PATCH
  name: updaterecipe
  path: /recipes/{recipe_id}
- description: Elastic.io Delete a recipe
  method: DELETE
  name: deleterecipe
  path: /recipes/{recipe_id}
- description: Elastic.io Update recipe visibility
  method: PATCH
  name: updaterecipevisibility
  path: /recipes/{recipe_id}/visibility
- description: Elastic.io Get current user
  method: GET
  name: getcurrentuser
  path: /users/me
- description: Elastic.io Update current user
  method: PATCH
  name: updatecurrentuser
  path: /users/me
- description: Elastic.io Get a user
  method: GET
  name: getuser
  path: /users/{user_id}
- description: Elastic.io List auth clients
  method: GET
  name: listauthclients
  path: /auth-clients
- description: Elastic.io Create an auth client
  method: POST
  name: createauthclient
  path: /auth-clients
- description: Elastic.io Get an auth client
  method: GET
  name: getauthclient
  path: /auth-clients/{auth_client_id}
- description: Elastic.io Update an auth client
  method: PATCH
  name: updateauthclient
  path: /auth-clients/{auth_client_id}
- description: Elastic.io Delete an auth client
  method: DELETE
  name: deleteauthclient
  path: /auth-clients/{auth_client_id}
- description: Elastic.io List auth secrets
  method: GET
  name: listauthsecrets
  path: /auth-secrets
- description: Elastic.io Create an auth secret
  method: POST
  name: createauthsecret
  path: /auth-secrets
- description: Elastic.io Get an auth secret
  method: GET
  name: getauthsecret
  path: /auth-secrets/{auth_secret_id}
- description: Elastic.io Update an auth secret
  method: PATCH
  name: updateauthsecret
  path: /auth-secrets/{auth_secret_id}
- description: Elastic.io Delete an auth secret
  method: DELETE
  name: deleteauthsecret
  path: /auth-secrets/{auth_secret_id}
- description: Elastic.io List teams
  method: GET
  name: listteams
  path: /teams
- description: Elastic.io Create a team
  method: POST
  name: createteam
  path: /teams
- description: Elastic.io Get a team
  method: GET
  name: getteam
  path: /teams/{team_id}
- description: Elastic.io Delete a team
  method: DELETE
  name: deleteteam
  path: /teams/{team_id}
- description: Elastic.io List agents
  method: GET
  name: listagents
  path: /agents
personas: []
provider_name: Elastic.io
provider_slug: elastic-io
search_terms:
- deletecomponent
- elastic.io get a flow draft
- updateflow
- elastic.io update a workspace
- addworkspacemember
- elastic.io delete an auth secret
- elastic.io list components
- getcredential
- elastic.io create a workspace
- elastic.io list credentials
- deleteworkspace
- elastic.io list auth clients
- io
- elastic.io update a credential
- updatecurrentuser
- elastic.io update a flow
- elastic.io get a component
- startflow
- elastic.io list recipes
- stopflow
- deleteauthsecret
- elastic.io list workspace members
- listagents
- elastic.io update a component
- createauthsecret
- api
- getcontract
- listteams
- elastic.io get current user
- getuser
- listcontracts
- deletecredential
- elastic.io run a flow on demand
- deleteflow
- elastic.io update current user
- getcomponent
- elastic.io update a recipe
- getflow
- deleteauthclient
- getworkspace
- elastic.io list auth secrets
- listworkspacemembers
- updatecomponent
- createflow
- addcontractmember
- listcredentials
- elastic.io list teams
- elastic.io list contracts
- elastic.io start a flow
- elastic.io get an auth secret
- elastic.io remove a workspace member
- getauthsecret
- createauthclient
- elastic
- elastic.io get a user
- elastic.io create a flow draft
- elastic.io delete an auth client
- updaterecipevisibility
- createflowdraft
- updatecredential
- elastic.io create a credential
- updateauthsecret
- elastic.io list agents
- elastic.io get an auth client
- elastic.io update a contract
- runflownow
- listworkspaces
- listcontractmembers
- listflows
- elastic.io list contract members
- elastic.io create an auth secret
- elastic.io list flow drafts
- elastic.io delete a team
- elastic.io add a contract member
- elastic.io add a workspace member
- listrecipes
- getflowversion
- elastic.io list workspaces
- integrations
- elastic.io delete a workspace
- elastic.io get a credential
- elastic.io get a workspace
- getflowdraft
- ipaas
- elastic.io create a flow
- listauthclients
- deleterecipe
- listcomponents
- createrecipe
- elastic.io create a team
- updatecontract
- getrecipe
- saas integration
- elastic.io update an auth secret
- updateworkspace
- createcredential
- elastic.io delete a recipe
- elastic.io stop a flow
- updateauthclient
- getauthclient
- elastic.io get a recipe
- elastic.io get a team
- getcurrentuser
- updaterecipe
- elastic.io create a recipe
- removeworkspacemember
- elastic.io update recipe visibility
- createworkspace
- elastic.io update a flow draft
- listflowdrafts
- elastic.io get a flow version
- elastic.io delete a component
- getteam
- elastic.io delete a credential
- elastic.io update an auth client
- elastic.io get a contract
- deleteteam
- deleteflowdraft
- elastic.io list flows
- updateflowdraft
- elastic.io delete a flow draft
- createteam
- elastic.io get a flow
- elastic.io delete a flow
- listauthsecrets
- elastic.io create an auth client
slug: elastic-io-capability
source_filename: elastic-io-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: elastic.io Platform REST API\n  description: The elastic.io Platform REST API v2 provides programmatic access to the elastic.io iPaaS platform. It allows\n    you to manage integration flows, workspaces, contracts, credentials, components, recipes, users, and other platform resources.\n    The API follows the JSON:API specification and uses Bearer token authentication.\n  tags:\n  - Elastic\n  - Io\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: elastic-io\n    baseUri: https://api.elastic.io/v2\n    description: elastic.io Platform REST API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{ELASTIC_IO_TOKEN}}'\n    resources:\n    - name: flows\n      path: /flows\n      operations:\n      - name: listflows\n        method: GET\n        description: Elastic.io List flows\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n      - name: createflow\n        method: POST\n        description: Elastic.io Create a flow\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: flows-flow-id\n      path: /flows/{flow_id}\n      operations:\n      - name: getflow\n        method: GET\n        description: Elastic.io Get a flow\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateflow\n        method: PATCH\n        description: Elastic.io Update a flow\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteflow\n        method: DELETE\n        description: Elastic.io Delete a flow\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n    - name: flows-flow-id-start\n      path: /flows/{flow_id}/start\n      operations:\n      - name: startflow\n        method: POST\n        description: Elastic.io Start a flow\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: flows-flow-id-stop\n      path: /flows/{flow_id}/stop\n      operations:\n      - name: stopflow\n        method: POST\n        description: Elastic.io Stop a flow\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: flows-flow-id-run-now\n      path: /flows/{flow_id}/run-now\n      operations:\n      - name: runflownow\n        method: POST\n        description: Elastic.io Run a flow on demand\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: flow-drafts\n      path: /flow-drafts\n      operations:\n\
  \      - name: listflowdrafts\n        method: GET\n        description: Elastic.io List flow drafts\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createflowdraft\n        method: POST\n        description: Elastic.io Create a flow draft\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: flow-drafts-flow-draft-id\n      path: /flow-drafts/{flow_draft_id}\n      operations:\n      - name: getflowdraft\n        method: GET\n        description: Elastic.io Get a flow draft\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateflowdraft\n        method: PATCH\n        description: Elastic.io Update a flow draft\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n      - name: deleteflowdraft\n        method: DELETE\n        description: Elastic.io Delete a flow draft\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: flow-versions-flow-version-id\n      path: /flow-versions/{flow_version_id}\n      operations:\n      - name: getflowversion\n        method: GET\n        description: Elastic.io Get a flow version\n        inputParameters:\n        - name: flow_version_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: workspaces\n      path: /workspaces\n      operations:\n      - name: listworkspaces\n        method: GET\n        description: Elastic.io List workspaces\n        inputParameters:\n        - name: filter[contract_id]\n          in: query\n          type: string\n\
  \          description: Filter by contract ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createworkspace\n        method: POST\n        description: Elastic.io Create a workspace\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: workspaces-workspace-id\n      path: /workspaces/{workspace_id}\n      operations:\n      - name: getworkspace\n        method: GET\n        description: Elastic.io Get a workspace\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateworkspace\n        method: PATCH\n        description: Elastic.io Update a workspace\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteworkspace\n        method:\
  \ DELETE\n        description: Elastic.io Delete a workspace\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: workspaces-workspace-id-members\n      path: /workspaces/{workspace_id}/members\n      operations:\n      - name: listworkspacemembers\n        method: GET\n        description: Elastic.io List workspace members\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: addworkspacemember\n        method: POST\n        description: Elastic.io Add a workspace member\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: workspaces-workspace-id-members-user-id\n      path: /workspaces/{workspace_id}/members/{user_id}\n      operations:\n      - name: removeworkspacemember\n        method: DELETE\n        description: Elastic.io\
  \ Remove a workspace member\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: contracts\n      path: /contracts\n      operations:\n      - name: listcontracts\n        method: GET\n        description: Elastic.io List contracts\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: contracts-contract-id\n      path: /contracts/{contract_id}\n      operations:\n      - name: getcontract\n        method: GET\n        description: Elastic.io Get a contract\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatecontract\n        method: PATCH\n        description: Elastic.io Update a contract\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name:\
  \ contracts-contract-id-members\n      path: /contracts/{contract_id}/members\n      operations:\n      - name: listcontractmembers\n        method: GET\n        description: Elastic.io List contract members\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: addcontractmember\n        method: POST\n        description: Elastic.io Add a contract member\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: credentials\n      path: /credentials\n      operations:\n      - name: listcredentials\n        method: GET\n        description: Elastic.io List credentials\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createcredential\n        method: POST\n        description: Elastic.io Create a credential\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: credentials-credential-id\n      path: /credentials/{credential_id}\n      operations:\n      - name: getcredential\n        method: GET\n        description: Elastic.io Get a credential\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatecredential\n        method: PATCH\n        description: Elastic.io Update a credential\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletecredential\n        method: DELETE\n        description: Elastic.io Delete a credential\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: components\n      path: /components\n      operations:\n      - name: listcomponents\n\
  \        method: GET\n        description: Elastic.io List components\n        inputParameters:\n        - name: filter[contract_id]\n          in: query\n          type: string\n          description: Filter by contract ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: components-component-id\n      path: /components/{component_id}\n      operations:\n      - name: getcomponent\n        method: GET\n        description: Elastic.io Get a component\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatecomponent\n        method: PATCH\n        description: Elastic.io Update a component\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletecomponent\n        method: DELETE\n        description: Elastic.io Delete\
  \ a component\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: recipes\n      path: /recipes\n      operations:\n      - name: listrecipes\n        method: GET\n        description: Elastic.io List recipes\n        inputParameters:\n        - name: filter[contract_id]\n          in: query\n          type: string\n          description: Filter by contract ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createrecipe\n        method: POST\n        description: Elastic.io Create a recipe\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: recipes-recipe-id\n      path: /recipes/{recipe_id}\n      operations:\n      - name: getrecipe\n        method: GET\n        description: Elastic.io Get a recipe\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updaterecipe\n        method: PATCH\n        description: Elastic.io Update a recipe\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleterecipe\n        method: DELETE\n        description: Elastic.io Delete a recipe\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: recipes-recipe-id-visibility\n      path: /recipes/{recipe_id}/visibility\n      operations:\n      - name: updaterecipevisibility\n        method: PATCH\n        description: Elastic.io Update recipe visibility\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users-me\n      path: /users/me\n      operations:\n      - name: getcurrentuser\n\
  \        method: GET\n        description: Elastic.io Get current user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatecurrentuser\n        method: PATCH\n        description: Elastic.io Update current user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users-user-id\n      path: /users/{user_id}\n      operations:\n      - name: getuser\n        method: GET\n        description: Elastic.io Get a user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: auth-clients\n      path: /auth-clients\n      operations:\n      - name: listauthclients\n        method: GET\n        description: Elastic.io List auth clients\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n      - name: createauthclient\n        method: POST\n        description: Elastic.io Create an auth client\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: auth-clients-auth-client-id\n      path: /auth-clients/{auth_client_id}\n      operations:\n      - name: getauthclient\n        method: GET\n        description: Elastic.io Get an auth client\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateauthclient\n        method: PATCH\n        description: Elastic.io Update an auth client\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteauthclient\n        method: DELETE\n        description: Elastic.io Delete an auth client\n        outputRawFormat: json\n        outputParameters:\n  \
  \      - name: result\n          type: object\n          value: $.\n    - name: auth-secrets\n      path: /auth-secrets\n      operations:\n      - name: listauthsecrets\n        method: GET\n        description: Elastic.io List auth secrets\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createauthsecret\n        method: POST\n        description: Elastic.io Create an auth secret\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: auth-secrets-auth-secret-id\n      path: /auth-secrets/{auth_secret_id}\n      operations:\n      - name: getauthsecret\n        method: GET\n        description: Elastic.io Get an auth secret\n        inputParameters:\n        - name: auth_secret_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n \
  \       - name: result\n          type: object\n          value: $.\n      - name: updateauthsecret\n        method: PATCH\n        description: Elastic.io Update an auth secret\n        inputParameters:\n        - name: auth_secret_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteauthsecret\n        method: DELETE\n        description: Elastic.io Delete an auth secret\n        inputParameters:\n        - name: auth_secret_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: teams\n      path: /teams\n      operations:\n      - name: listteams\n        method: GET\n        description: Elastic.io List teams\n        inputParameters:\n        - name: filter[contract_id]\n\
  \          in: query\n          type: string\n          description: Filter by contract ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createteam\n        method: POST\n        description: Elastic.io Create a team\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: teams-team-id\n      path: /teams/{team_id}\n      operations:\n      - name: getteam\n        method: GET\n        description: Elastic.io Get a team\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteteam\n        method: DELETE\n        description: Elastic.io Delete a team\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: agents\n      path: /agents\n  \
  \    operations:\n      - name: listagents\n        method: GET\n        description: Elastic.io List agents\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: elastic-io-rest\n    description: REST adapter for elastic.io Platform REST API.\n    resources:\n    - path: /flows\n      name: listflows\n      operations:\n      - method: GET\n        name: listflows\n        description: Elastic.io List flows\n        call: elastic-io.listflows\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /flows\n      name: createflow\n      operations:\n      - method: POST\n        name: createflow\n        description: Elastic.io Create a flow\n        call: elastic-io.createflow\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /flows/{flow_id}\n      name: getflow\n      operations:\n    \
  \  - method: GET\n        name: getflow\n        description: Elastic.io Get a flow\n        call: elastic-io.getflow\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /flows/{flow_id}\n      name: updateflow\n      operations:\n      - method: PATCH\n        name: updateflow\n        description: Elastic.io Update a flow\n        call: elastic-io.updateflow\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /flows/{flow_id}\n      name: deleteflow\n      operations:\n      - method: DELETE\n        name: deleteflow\n        description: Elastic.io Delete a flow\n        call: elastic-io.deleteflow\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /flows/{flow_id}/start\n      name: startflow\n      operations:\n      - method: POST\n        name: startflow\n        description: Elastic.io Start a flow\n        call: elastic-io.startflow\n        outputParameters:\n        - type:\
  \ object\n          mapping: $.\n    - path: /flows/{flow_id}/stop\n      name: stopflow\n      operations:\n      - method: POST\n        name: stopflow\n        description: Elastic.io Stop a flow\n        call: elastic-io.stopflow\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /flows/{flow_id}/run-now\n      name: runflownow\n      operations:\n      - method: POST\n        name: runflownow\n        description: Elastic.io Run a flow on demand\n        call: elastic-io.runflownow\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /flow-drafts\n      name: listflowdrafts\n      operations:\n      - method: GET\n        name: listflowdrafts\n        description: Elastic.io List flow drafts\n        call: elastic-io.listflowdrafts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /flow-drafts\n      name: createflowdraft\n      operations:\n      - method: POST\n        name:\
  \ createflowdraft\n        description: Elastic.io Create a flow draft\n        call: elastic-io.createflowdraft\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /flow-drafts/{flow_draft_id}\n      name: getflowdraft\n      operations:\n      - method: GET\n        name: getflowdraft\n        description: Elastic.io Get a flow draft\n        call: elastic-io.getflowdraft\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /flow-drafts/{flow_draft_id}\n      name: updateflowdraft\n      operations:\n      - method: PATCH\n        name: updateflowdraft\n        description: Elastic.io Update a flow draft\n        call: elastic-io.updateflowdraft\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /flow-drafts/{flow_draft_id}\n      name: deleteflowdraft\n      operations:\n      - method: DELETE\n        name: deleteflowdraft\n        description: Elastic.io Delete a flow draft\n \
  \       call: elastic-io.deleteflowdraft\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /flow-versions/{flow_version_id}\n      name: getflowversion\n      operations:\n      - method: GET\n        name: getflowversion\n        description: Elastic.io Get a flow version\n        call: elastic-io.getflowversion\n        with:\n          flow_version_id: rest.flow_version_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /workspaces\n      name: listworkspaces\n      operations:\n      - method: GET\n        name: listworkspaces\n        description: Elastic.io List workspaces\n        call: elastic-io.listworkspaces\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /workspaces\n      name: createworkspace\n      operations:\n      - method: POST\n        name: createworkspace\n        description: Elastic.io Create a workspace\n        call: elastic-io.createworkspace\n \
  \       outputParameters:\n        - type: object\n          mapping: $.\n    - path: /workspaces/{workspace_id}\n      name: getworkspace\n      operations:\n      - method: GET\n        name: getworkspace\n        description: Elastic.io Get a workspace\n        call: elastic-io.getworkspace\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /workspaces/{workspace_id}\n      name: updateworkspace\n      operations:\n      - method: PATCH\n        name: updateworkspace\n        description: Elastic.io Update a workspace\n        call: elastic-io.updateworkspace\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /workspaces/{workspace_id}\n      name: deleteworkspace\n      operations:\n      - method: DELETE\n        name: deleteworkspace\n        description: Elastic.io Delete a workspace\n        call: elastic-io.deleteworkspace\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path:\
  \ /workspaces/{workspace_id}/members\n      name: listworkspacemembers\n      operations:\n      - method: GET\n        name: listworkspacemembers\n        description: Elastic.io List workspace members\n        call: elastic-io.listworkspacemembers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /workspaces/{workspace_id}/members\n      name: addworkspacemember\n      operations:\n      - method: POST\n        name: addworkspacemember\n        description: Elastic.io Add a workspace member\n        call: elastic-io.addworkspacemember\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /workspaces/{workspace_id}/members/{user_id}\n      name: removeworkspacemember\n      operations:\n      - method: DELETE\n        name: removeworkspacemember\n        description: Elastic.io Remove a workspace member\n        call: elastic-io.removeworkspacemember\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /contracts\n      name: listcontracts\n      operations:\n      - method: GET\n        name: listcontracts\n        description: Elastic.io List contracts\n        call: elastic-io.listcontracts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /contracts/{contract_id}\n      name: getcontract\n      operations:\n      - method: GET\n        name: getcontract\n        description: Elastic.io Get a contract\n        call: elastic-io.getcontract\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /contracts/{contract_id}\n      name: updatecontract\n      operations:\n      - method: PATCH\n        name: updatecontract\n        description: Elastic.io Update a contract\n        call: elastic-io.updatecontract\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /contracts/{contract_id}/members\n      name: listcontractmembers\n      operations:\n      - method: GET\n\
  \        name: listcontractmembers\n        description: Elastic.io List contract members\n        call: elastic-io.listcontractmembers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /contracts/{contract_id}/members\n      name: addcontractmember\n      operations:\n      - method: POST\n        name: addcontractmember\n        description: Elastic.io Add a contract member\n        call: elastic-io.addcontractmember\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /credentials\n      name: listcredentials\n      operations:\n      - method: GET\n        name: listcredentials\n        description: Elastic.io List credentials\n        call: elastic-io.listcredentials\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /credentials\n      name: createcredential\n      operations:\n      - method: POST\n        name: createcredential\n        description: Elastic.io Create a credential\n\
  \        call: elastic-io.createcredential\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /credentials/{credential_id}\n      name: getcredential\n      operations:\n      - method: GET\n        name: getcredential\n        description: Elastic.io Get a credential\n        call: elastic-io.getcredential\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /credentials/{credential_id}\n      name: updatecredential\n      operations:\n      - method: PATCH\n        name: updatecredential\n        description: Elastic.io Update a credential\n        call: elastic-io.updatecredential\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /credentials/{credential_id}\n      name: deletecredential\n      operations:\n      - method: DELETE\n        name: deletecredential\n        description: Elastic.io Delete a credential\n        call: elastic-io.deletecredential\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /components\n      name: listcomponents\n      operations:\n      - method: GET\n        name: listcomponents\n        description: Elastic.io List components\n        call: elastic-io.listcomponents\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /components/{component_id}\n      name: getcomponent\n      operations:\n      - method: GET\n        name: getcomponent\n        description: Elastic.io Get a component\n        call: elastic-io.getcomponent\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /components/{component_id}\n      name: updatecomponent\n      operations:\n      - method: PATCH\n        name: updatecomponent\n        description: Elastic.io Update a component\n        call: elastic-io.updatecomponent\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /components/{component_id}\n      name: deletecomponent\n\
  \      operations:\n      - method: DELETE\n        name: deletecomponent\n        description: Elastic.io Delete a component\n        call: elastic-io.deletecomponent\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /recipes\n      name: listrecipes\n      operations:\n      - method: GET\n        name: listrecipes\n        description: Elastic.io List recipes\n        call: elastic-io.listrecipes\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /recipes\n      name: createrecipe\n      operations:\n      - method: POST\n        name: createrecipe\n        description: Elastic.io Create a recipe\n        call: elastic-io.createrecipe\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /recipes/{recipe_id}\n      name: getrecipe\n      operations:\n      - method: GET\n        name: getrecipe\n        description: Elastic.io Get a recipe\n        call: elastic-io.getrecipe\n \
  \       outputParameters:\n        - type: object\n          mapping: $.\n    - path: /recipes/{recipe_id}\n      name: updaterecipe\n      operations:\n      - method: PATCH\n        name: updaterecipe\n        description: Elastic.io Update a recipe\n        call: elastic-io.updaterecipe\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /recipes/{recipe_id}\n      name: deleterecipe\n      operations:\n      - method: DELETE\n        name: deleterecipe\n        description: Elastic.io Delete a recipe\n        call: elastic-io.deleterecipe\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /recipes/{recipe_id}/visibility\n      name: updaterecipevisibility\n      operations:\n      - method: PATCH\n        name: updaterecipevisibility\n        description: Elastic.io Update recipe visibility\n        call: elastic-io.updaterecipevisibility\n        outputParameters:\n        - type: object\n          mapping: $.\n\
  \    - path: /users/me\n      name: getcurrentuser\n      operations:\n      - method: GET\n        name: getcurrentuser\n        description: Elastic.io Get current user\n        call: elastic-io.getcurrentuser\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users/me\n      name: updatecurrentuser\n      operations:\n      - method: PATCH\n        name: updatecurrentuser\n        description: Elastic.io Update current user\n        call: elastic-io.updatecurrentuser\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users/{user_id}\n      name: getuser\n      operations:\n      - method: GET\n        name: getuser\n        description: Elastic.io Get a user\n        call: elastic-io.getuser\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth-clients\n      name: listauthclients\n      operations:\n      - method: GET\n        name: listauthclients\n        description:\
  \ Elastic.io List auth clients\n        call: elastic-io.listauthclients\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth-clients\n      name: createauthclient\n      operations:\n      - method: POST\n        name: createauthclient\n        description: Elastic.io Create an auth client\n        call: elastic-io.createauthclient\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth-clients/{auth_client_id}\n      name: getauthclient\n      operations:\n      - method: GET\n        name: getauthclient\n        description: Elastic.io Get an auth client\n        call: elastic-io.getauthclient\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth-clients/{auth_client_id}\n      name: updateauthclient\n      operations:\n      - method: PATCH\n        name: updateauthclient\n        description: Elastic.io Update an auth client\n        call: elastic-io.updateauthclient\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth-clients/{auth_client_id}\n      name: deleteauthclient\n      operations:\n      - method: DELETE\n        name: deleteauthclient\n        description: Elastic.io Delete an auth client\n        call: elastic-io.deleteauthclient\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth-secrets\n      name: listauthsecrets\n      operations:\n      - method: GET\n        name: listauthsecrets\n        description: Elastic.io List auth secrets\n        call: elastic-io.listauthsecrets\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth-secrets\n      name: createauthsecret\n      operations:\n      - method: POST\n        name: createauthsecret\n        description: Elastic.io Create an auth secret\n        \n\n# --- truncated at 32 KB (51 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/elastic-io/refs/heads/main/capabilities/elastic-io-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/elastic-io/refs/heads/main/capabilities/elastic-io-capability.yaml
tags:
- Elastic
- Io
- API
tools:
- description: Elastic.io List flows
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listflows
- description: Elastic.io Create a flow
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createflow
- description: Elastic.io Get a flow
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getflow
- description: Elastic.io Update a flow
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateflow
- description: Elastic.io Delete a flow
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteflow
- description: Elastic.io Start a flow
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: startflow
- description: Elastic.io Stop a flow
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: stopflow
- description: Elastic.io Run a flow on demand
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: runflownow
- description: Elastic.io List flow drafts
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listflowdrafts
- description: Elastic.io Create a flow draft
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createflowdraft
- description: Elastic.io Get a flow draft
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getflowdraft
- description: Elastic.io Update a flow draft
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateflowdraft
- description: Elastic.io Delete a flow draft
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteflowdraft
- description: Elastic.io Get a flow version
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getflowversion
- description: Elastic.io List workspaces
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listworkspaces
- description: Elastic.io Create a workspace
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createworkspace
- description: Elastic.io Get a workspace
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getworkspace
- description: Elastic.io Update a workspace
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateworkspace
- description: Elastic.io Delete a workspace
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteworkspace
- description: Elastic.io List workspace members
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listworkspacemembers
- description: Elastic.io Add a workspace member
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: addworkspacemember
- description: Elastic.io Remove a workspace member
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: removeworkspacemember
- description: Elastic.io List contracts
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcontracts
- description: Elastic.io Get a contract
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcontract
- description: Elastic.io Update a contract
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatecontract
- description: Elastic.io List contract members
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcontractmembers
- description: Elastic.io Add a contract member
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: addcontractmember
- description: Elastic.io List credentials
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcredentials
- description: Elastic.io Create a credential
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createcredential
- description: Elastic.io Get a credential
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcredential
- description: Elastic.io Update a credential
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatecredential
- description: Elastic.io Delete a credential
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletecredential
- description: Elastic.io List components
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcomponents
- description: Elastic.io Get a component
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcomponent
- description: Elastic.io Update a component
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatecomponent
- description: Elastic.io Delete a component
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletecomponent
- description: Elastic.io List recipes
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listrecipes
- description: Elastic.io Create a recipe
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createrecipe
- description: Elastic.io Get a recipe
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getrecipe
- description: Elastic.io Update a recipe
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updaterecipe
- description: Elastic.io Delete a recipe
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleterecipe
- description: Elastic.io Update recipe visibility
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updaterecipevisibility
- description: Elastic.io Get current user
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcurrentuser
- description: Elastic.io Update current user
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatecurrentuser
- description: Elastic.io Get a user
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getuser
- description: Elastic.io List auth clients
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listauthclients
- description: Elastic.io Create an auth client
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createauthclient
- description: Elastic.io Get an auth client
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getauthclient
- description: Elastic.io Update an auth client
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateauthclient
- description: Elastic.io Delete an auth client
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteauthclient
- description: Elastic.io List auth secrets
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listauthsecrets
- description: Elastic.io Create an auth secret
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createauthsecret
- description: Elastic.io Get an auth secret
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getauthsecret
- description: Elastic.io Update an auth secret
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateauthsecret
- description: Elastic.io Delete an auth secret
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteauthsecret
- description: Elastic.io List teams
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listteams
- description: Elastic.io Create a team
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createteam
- description: Elastic.io Get a team
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getteam
- description: Elastic.io Delete a team
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteteam
- description: Elastic.io List agents
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listagents
---
