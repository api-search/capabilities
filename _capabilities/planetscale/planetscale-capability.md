---
categories: []
consumed_apis: []
description: The PlanetScale Platform API provides programmatic access to manage PlanetScale serverless MySQL-compatible databases. It allows developers to create and manage databases, branches, deploy requests, passwords, backups, service tokens, organization members, teams, bouncers, and billing data. The API supports authentication via service tokens and OAuth, enabling integration into CI/CD pipelines and infrastructure-as-code workflows.
layout: capability
name: PlanetScale Platform API
operations:
- description: List organizations
  method: GET
  name: listorganizations
  path: /organizations
- description: Get an organization
  method: GET
  name: getorganization
  path: /organizations/{organization}
- description: List organization members
  method: GET
  name: listorganizationmembers
  path: /organizations/{organization}/members
- description: Get an organization member
  method: GET
  name: getorganizationmember
  path: /organizations/{organization}/members/{member_id}
- description: Update an organization member
  method: PATCH
  name: updateorganizationmember
  path: /organizations/{organization}/members/{member_id}
- description: Remove an organization member
  method: DELETE
  name: deleteorganizationmember
  path: /organizations/{organization}/members/{member_id}
- description: List teams
  method: GET
  name: listteams
  path: /organizations/{organization}/teams
- description: Create a team
  method: POST
  name: createteam
  path: /organizations/{organization}/teams
- description: Get a team
  method: GET
  name: getteam
  path: /organizations/{organization}/teams/{team_slug}
- description: Update a team
  method: PATCH
  name: updateteam
  path: /organizations/{organization}/teams/{team_slug}
- description: Delete a team
  method: DELETE
  name: deleteteam
  path: /organizations/{organization}/teams/{team_slug}
- description: List databases
  method: GET
  name: listdatabases
  path: /organizations/{organization}/databases
- description: Create a database
  method: POST
  name: createdatabase
  path: /organizations/{organization}/databases
- description: Get a database
  method: GET
  name: getdatabase
  path: /organizations/{organization}/databases/{database}
- description: Update database settings
  method: PATCH
  name: updatedatabasesettings
  path: /organizations/{organization}/databases/{database}
- description: Delete a database
  method: DELETE
  name: deletedatabase
  path: /organizations/{organization}/databases/{database}
- description: List branches
  method: GET
  name: listbranches
  path: /organizations/{organization}/databases/{database}/branches
- description: Create a branch
  method: POST
  name: createbranch
  path: /organizations/{organization}/databases/{database}/branches
- description: Get a branch
  method: GET
  name: getbranch
  path: /organizations/{organization}/databases/{database}/branches/{branch}
- description: Update a branch
  method: PATCH
  name: updatebranch
  path: /organizations/{organization}/databases/{database}/branches/{branch}
- description: Delete a branch
  method: DELETE
  name: deletebranch
  path: /organizations/{organization}/databases/{database}/branches/{branch}
- description: Lint a branch schema
  method: GET
  name: lintbranchschema
  path: /organizations/{organization}/databases/{database}/branches/{branch}/schema-lint
- description: List deploy requests
  method: GET
  name: listdeployrequests
  path: /organizations/{organization}/databases/{database}/deploy-requests
- description: Create a deploy request
  method: POST
  name: createdeployrequest
  path: /organizations/{organization}/databases/{database}/deploy-requests
- description: Get a deploy request
  method: GET
  name: getdeployrequest
  path: /organizations/{organization}/databases/{database}/deploy-requests/{deploy_request_number}
- description: Close a deploy request
  method: PATCH
  name: closedeployrequest
  path: /organizations/{organization}/databases/{database}/deploy-requests/{deploy_request_number}
- description: Queue a deploy request
  method: POST
  name: queuedeployrequest
  path: /organizations/{organization}/databases/{database}/deploy-requests/{deploy_request_number}/deploy
- description: List deploy request reviews
  method: GET
  name: listdeployrequestreviews
  path: /organizations/{organization}/databases/{database}/deploy-requests/{deploy_request_number}/reviews
- description: Review a deploy request
  method: POST
  name: reviewdeployrequest
  path: /organizations/{organization}/databases/{database}/deploy-requests/{deploy_request_number}/reviews
- description: Skip revert period
  method: POST
  name: skipdeployrequestrevert
  path: /organizations/{organization}/databases/{database}/deploy-requests/{deploy_request_number}/skip-revert
- description: Complete a revert
  method: POST
  name: completedeployrequestrevert
  path: /organizations/{organization}/databases/{database}/deploy-requests/{deploy_request_number}/complete-revert
- description: Get the deploy queue
  method: GET
  name: getdeployqueue
  path: /organizations/{organization}/databases/{database}/deploy-queue
- description: List passwords
  method: GET
  name: listpasswords
  path: /organizations/{organization}/databases/{database}/branches/{branch}/passwords
- description: Create a password
  method: POST
  name: createpassword
  path: /organizations/{organization}/databases/{database}/branches/{branch}/passwords
- description: Get a password
  method: GET
  name: getpassword
  path: /organizations/{organization}/databases/{database}/branches/{branch}/passwords/{password_id}
- description: Delete a password
  method: DELETE
  name: deletepassword
  path: /organizations/{organization}/databases/{database}/branches/{branch}/passwords/{password_id}
- description: Renew a password
  method: POST
  name: renewpassword
  path: /organizations/{organization}/databases/{database}/branches/{branch}/passwords/{password_id}/renew
- description: List backups
  method: GET
  name: listbackups
  path: /organizations/{organization}/databases/{database}/branches/{branch}/backups
- description: Create a backup
  method: POST
  name: createbackup
  path: /organizations/{organization}/databases/{database}/branches/{branch}/backups
- description: Get a backup
  method: GET
  name: getbackup
  path: /organizations/{organization}/databases/{database}/branches/{branch}/backups/{backup_id}
- description: Delete a backup
  method: DELETE
  name: deletebackup
  path: /organizations/{organization}/databases/{database}/branches/{branch}/backups/{backup_id}
- description: List service tokens
  method: GET
  name: listservicetokens
  path: /organizations/{organization}/service-tokens
- description: Create a service token
  method: POST
  name: createservicetoken
  path: /organizations/{organization}/service-tokens
- description: Get a service token
  method: GET
  name: getservicetoken
  path: /organizations/{organization}/service-tokens/{service_token_id}
- description: Delete a service token
  method: DELETE
  name: deleteservicetoken
  path: /organizations/{organization}/service-tokens/{service_token_id}
- description: List service token accesses
  method: GET
  name: listservicetokenaccesses
  path: /organizations/{organization}/service-tokens/{service_token_id}/accesses
- description: Grant service token access
  method: POST
  name: createservicetokenaccess
  path: /organizations/{organization}/service-tokens/{service_token_id}/accesses
- description: List bouncers
  method: GET
  name: listbouncers
  path: /organizations/{organization}/databases/{database}/branches/{branch}/bouncers
- description: Create a bouncer
  method: POST
  name: createbouncer
  path: /organizations/{organization}/databases/{database}/branches/{branch}/bouncers
- description: Get a bouncer
  method: GET
  name: getbouncer
  path: /organizations/{organization}/databases/{database}/branches/{branch}/bouncers/{bouncer_name}
- description: Delete a bouncer
  method: DELETE
  name: deletebouncer
  path: /organizations/{organization}/databases/{database}/branches/{branch}/bouncers/{bouncer_name}
- description: List cluster sizes
  method: GET
  name: listclustersizes
  path: /organizations/{organization}/cluster-size-skus
- description: Create role credentials
  method: POST
  name: createrole
  path: /organizations/{organization}/databases/{database}/branches/{branch}/roles
- description: List IP restrictions
  method: GET
  name: listiprestrictions
  path: /organizations/{organization}/databases/{database}/postgres-cidrs
- description: Create an IP restriction entry
  method: POST
  name: createiprestriction
  path: /organizations/{organization}/databases/{database}/postgres-cidrs
- description: Show the status of a query patterns report
  method: GET
  name: getquerypatternsreportstatus
  path: /organizations/{organization}/databases/{database}/branches/{branch}/query-patterns-report
- description: List webhooks
  method: GET
  name: listwebhooks
  path: /organizations/{organization}/databases/{database}/webhooks
- description: Create a webhook
  method: POST
  name: createwebhook
  path: /organizations/{organization}/databases/{database}/webhooks
- description: List invoices
  method: GET
  name: listinvoices
  path: /organizations/{organization}/invoices
- description: List schema recommendations
  method: GET
  name: listschemarecommendations
  path: /organizations/{organization}/databases/{database}/schema-recommendations
personas: []
provider_name: planetscale
provider_slug: planetscale
search_terms:
- listschemarecommendations
- update a branch
- deletepassword
- getdeployrequest
- close a deploy request
- listiprestrictions
- list organizations
- update an organization member
- list ip restrictions
- renewpassword
- delete a bouncer
- show the status of a query patterns report
- list organization members
- list teams
- complete a revert
- createservicetokenaccess
- remove an organization member
- delete a branch
- get a deploy request
- getdatabase
- delete a backup
- completedeployrequestrevert
- listwebhooks
- api
- deletebranch
- get an organization
- listteams
- createwebhook
- listinvoices
- listbouncers
- listdatabases
- list invoices
- listdeployrequestreviews
- get a service token
- renew a password
- get an organization member
- list bouncers
- deletebouncer
- create a deploy request
- createrole
- update database settings
- get a bouncer
- delete a password
- createbackup
- lint a branch schema
- getbouncer
- getorganization
- create a webhook
- listorganizationmembers
- deletedatabase
- create a backup
- list service tokens
- updateteam
- list service token accesses
- queue a deploy request
- delete a team
- list databases
- getbackup
- list deploy request reviews
- delete a database
- list deploy requests
- listbranches
- get a branch
- review a deploy request
- listdeployrequests
- get a database
- getbranch
- planetscale
- createbranch
- grant service token access
- create an ip restriction entry
- getservicetoken
- createdatabase
- createservicetoken
- list cluster sizes
- createiprestriction
- create a database
- updatedatabasesettings
- skip revert period
- get the deploy queue
- list passwords
- getpassword
- list branches
- list schema recommendations
- reviewdeployrequest
- create a branch
- get a backup
- delete a service token
- createpassword
- create a password
- listservicetokenaccesses
- get a team
- deleteorganizationmember
- create a bouncer
- listservicetokens
- create a service token
- listbackups
- getteam
- list backups
- deleteservicetoken
- deleteteam
- listorganizations
- closedeployrequest
- getquerypatternsreportstatus
- get a password
- getdeployqueue
- getorganizationmember
- update a team
- listclustersizes
- createbouncer
- createteam
- createdeployrequest
- updatebranch
- listpasswords
- create a team
- queuedeployrequest
- skipdeployrequestrevert
- lintbranchschema
- list webhooks
- updateorganizationmember
- deletebackup
- create role credentials
slug: planetscale-capability
source_filename: planetscale-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: PlanetScale Platform API\n  description: The PlanetScale Platform API provides programmatic access to manage PlanetScale serverless MySQL-compatible\n    databases. It allows developers to create and manage databases, branches, deploy requests, passwords, backups, service\n    tokens, organization members, teams, bouncers, and billing data. The API supports authentication via service tokens and\n    OAuth, enabling integration into CI/CD pipelines and infrastructure-as-code workflows.\n  tags:\n  - Planetscale\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: planetscale\n    baseUri: https://api.planetscale.com/v1\n    description: PlanetScale Platform API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: Authorization\n      value: '{{PLANETSCALE_TOKEN}}'\n    resources:\n    - name: organizations\n      path: /organizations\n      operations:\n\
  \      - name: listorganizations\n        method: GET\n        description: List organizations\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organizations-organization\n      path: /organizations/{organization}\n      operations:\n      - name: getorganization\n        method: GET\n        description: Get an organization\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organizations-organization-members\n      path: /organizations/{organization}/members\n      operations:\n      - name: listorganizationmembers\n        method: GET\n        description: List organization members\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organizations-organization-members-member-id\n      path: /organizations/{organization}/members/{member_id}\n\
  \      operations:\n      - name: getorganizationmember\n        method: GET\n        description: Get an organization member\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateorganizationmember\n        method: PATCH\n        description: Update an organization member\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteorganizationmember\n        method: DELETE\n        description: Remove an organization member\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organizations-organization-teams\n      path: /organizations/{organization}/teams\n      operations:\n      - name: listteams\n        method: GET\n        description: List teams\n        outputRawFormat: json\n        outputParameters:\n        -\
  \ name: result\n          type: object\n          value: $.\n      - name: createteam\n        method: POST\n        description: Create a team\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organizations-organization-teams-team-slug\n      path: /organizations/{organization}/teams/{team_slug}\n      operations:\n      - name: getteam\n        method: GET\n        description: Get a team\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateteam\n        method: PATCH\n        description: Update a team\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteteam\n        method: DELETE\n        description: Delete a team\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n       \
  \   type: object\n          value: $.\n    - name: organizations-organization-databases\n      path: /organizations/{organization}/databases\n      operations:\n      - name: listdatabases\n        method: GET\n        description: List databases\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createdatabase\n        method: POST\n        description: Create a database\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organizations-organization-databases-database\n      path: /organizations/{organization}/databases/{database}\n      operations:\n      - name: getdatabase\n        method: GET\n        description: Get a database\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatedatabasesettings\n        method:\
  \ PATCH\n        description: Update database settings\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletedatabase\n        method: DELETE\n        description: Delete a database\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organizations-organization-databases-database-br\n      path: /organizations/{organization}/databases/{database}/branches\n      operations:\n      - name: listbranches\n        method: GET\n        description: List branches\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createbranch\n        method: POST\n        description: Create a branch\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organizations-organization-databases-database-br\n\
  \      path: /organizations/{organization}/databases/{database}/branches/{branch}\n      operations:\n      - name: getbranch\n        method: GET\n        description: Get a branch\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatebranch\n        method: PATCH\n        description: Update a branch\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletebranch\n        method: DELETE\n        description: Delete a branch\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organizations-organization-databases-database-br\n      path: /organizations/{organization}/databases/{database}/branches/{branch}/schema-lint\n      operations:\n      - name: lintbranchschema\n        method: GET\n        description: Lint a branch\
  \ schema\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organizations-organization-databases-database-de\n      path: /organizations/{organization}/databases/{database}/deploy-requests\n      operations:\n      - name: listdeployrequests\n        method: GET\n        description: List deploy requests\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createdeployrequest\n        method: POST\n        description: Create a deploy request\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organizations-organization-databases-database-de\n      path: /organizations/{organization}/databases/{database}/deploy-requests/{deploy_request_number}\n      operations:\n      - name: getdeployrequest\n        method: GET\n        description:\
  \ Get a deploy request\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: closedeployrequest\n        method: PATCH\n        description: Close a deploy request\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organizations-organization-databases-database-de\n      path: /organizations/{organization}/databases/{database}/deploy-requests/{deploy_request_number}/deploy\n      operations:\n      - name: queuedeployrequest\n        method: POST\n        description: Queue a deploy request\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organizations-organization-databases-database-de\n      path: /organizations/{organization}/databases/{database}/deploy-requests/{deploy_request_number}/reviews\n      operations:\n      -\
  \ name: listdeployrequestreviews\n        method: GET\n        description: List deploy request reviews\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: reviewdeployrequest\n        method: POST\n        description: Review a deploy request\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organizations-organization-databases-database-de\n      path: /organizations/{organization}/databases/{database}/deploy-requests/{deploy_request_number}/skip-revert\n      operations:\n      - name: skipdeployrequestrevert\n        method: POST\n        description: Skip revert period\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organizations-organization-databases-database-de\n      path: /organizations/{organization}/databases/{database}/deploy-requests/{deploy_request_number}/complete-revert\n\
  \      operations:\n      - name: completedeployrequestrevert\n        method: POST\n        description: Complete a revert\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organizations-organization-databases-database-de\n      path: /organizations/{organization}/databases/{database}/deploy-queue\n      operations:\n      - name: getdeployqueue\n        method: GET\n        description: Get the deploy queue\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organizations-organization-databases-database-br\n      path: /organizations/{organization}/databases/{database}/branches/{branch}/passwords\n      operations:\n      - name: listpasswords\n        method: GET\n        description: List passwords\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n  \
  \        value: $.\n      - name: createpassword\n        method: POST\n        description: Create a password\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organizations-organization-databases-database-br\n      path: /organizations/{organization}/databases/{database}/branches/{branch}/passwords/{password_id}\n      operations:\n      - name: getpassword\n        method: GET\n        description: Get a password\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletepassword\n        method: DELETE\n        description: Delete a password\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organizations-organization-databases-database-br\n      path: /organizations/{organization}/databases/{database}/branches/{branch}/passwords/{password_id}/renew\n\
  \      operations:\n      - name: renewpassword\n        method: POST\n        description: Renew a password\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organizations-organization-databases-database-br\n      path: /organizations/{organization}/databases/{database}/branches/{branch}/backups\n      operations:\n      - name: listbackups\n        method: GET\n        description: List backups\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createbackup\n        method: POST\n        description: Create a backup\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organizations-organization-databases-database-br\n      path: /organizations/{organization}/databases/{database}/branches/{branch}/backups/{backup_id}\n  \
  \    operations:\n      - name: getbackup\n        method: GET\n        description: Get a backup\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletebackup\n        method: DELETE\n        description: Delete a backup\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organizations-organization-service-tokens\n      path: /organizations/{organization}/service-tokens\n      operations:\n      - name: listservicetokens\n        method: GET\n        description: List service tokens\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createservicetoken\n        method: POST\n        description: Create a service token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n    - name: organizations-organization-service-tokens-servic\n      path: /organizations/{organization}/service-tokens/{service_token_id}\n      operations:\n      - name: getservicetoken\n        method: GET\n        description: Get a service token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteservicetoken\n        method: DELETE\n        description: Delete a service token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organizations-organization-service-tokens-servic\n      path: /organizations/{organization}/service-tokens/{service_token_id}/accesses\n      operations:\n      - name: listservicetokenaccesses\n        method: GET\n        description: List service token accesses\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n        \
  \  type: object\n          value: $.\n      - name: createservicetokenaccess\n        method: POST\n        description: Grant service token access\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organizations-organization-databases-database-br\n      path: /organizations/{organization}/databases/{database}/branches/{branch}/bouncers\n      operations:\n      - name: listbouncers\n        method: GET\n        description: List bouncers\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createbouncer\n        method: POST\n        description: Create a bouncer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organizations-organization-databases-database-br\n      path: /organizations/{organization}/databases/{database}/branches/{branch}/bouncers/{bouncer_name}\n\
  \      operations:\n      - name: getbouncer\n        method: GET\n        description: Get a bouncer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletebouncer\n        method: DELETE\n        description: Delete a bouncer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organizations-organization-cluster-size-skus\n      path: /organizations/{organization}/cluster-size-skus\n      operations:\n      - name: listclustersizes\n        method: GET\n        description: List cluster sizes\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organizations-organization-databases-database-br\n      path: /organizations/{organization}/databases/{database}/branches/{branch}/roles\n      operations:\n      - name: createrole\n\
  \        method: POST\n        description: Create role credentials\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organizations-organization-databases-database-po\n      path: /organizations/{organization}/databases/{database}/postgres-cidrs\n      operations:\n      - name: listiprestrictions\n        method: GET\n        description: List IP restrictions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createiprestriction\n        method: POST\n        description: Create an IP restriction entry\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organizations-organization-databases-database-br\n      path: /organizations/{organization}/databases/{database}/branches/{branch}/query-patterns-report\n      operations:\n\
  \      - name: getquerypatternsreportstatus\n        method: GET\n        description: Show the status of a query patterns report\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organizations-organization-databases-database-we\n      path: /organizations/{organization}/databases/{database}/webhooks\n      operations:\n      - name: listwebhooks\n        method: GET\n        description: List webhooks\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createwebhook\n        method: POST\n        description: Create a webhook\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organizations-organization-invoices\n      path: /organizations/{organization}/invoices\n      operations:\n      - name: listinvoices\n        method:\
  \ GET\n        description: List invoices\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organizations-organization-databases-database-sc\n      path: /organizations/{organization}/databases/{database}/schema-recommendations\n      operations:\n      - name: listschemarecommendations\n        method: GET\n        description: List schema recommendations\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: planetscale-rest\n    description: REST adapter for PlanetScale Platform API.\n    resources:\n    - path: /organizations\n      name: listorganizations\n      operations:\n      - method: GET\n        name: listorganizations\n        description: List organizations\n        call: planetscale.listorganizations\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n    - path: /organizations/{organization}\n      name: getorganization\n      operations:\n      - method: GET\n        name: getorganization\n        description: Get an organization\n        call: planetscale.getorganization\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organizations/{organization}/members\n      name: listorganizationmembers\n      operations:\n      - method: GET\n        name: listorganizationmembers\n        description: List organization members\n        call: planetscale.listorganizationmembers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organizations/{organization}/members/{member_id}\n      name: getorganizationmember\n      operations:\n      - method: GET\n        name: getorganizationmember\n        description: Get an organization member\n        call: planetscale.getorganizationmember\n        outputParameters:\n        - type: object\n         \
  \ mapping: $.\n    - path: /organizations/{organization}/members/{member_id}\n      name: updateorganizationmember\n      operations:\n      - method: PATCH\n        name: updateorganizationmember\n        description: Update an organization member\n        call: planetscale.updateorganizationmember\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organizations/{organization}/members/{member_id}\n      name: deleteorganizationmember\n      operations:\n      - method: DELETE\n        name: deleteorganizationmember\n        description: Remove an organization member\n        call: planetscale.deleteorganizationmember\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organizations/{organization}/teams\n      name: listteams\n      operations:\n      - method: GET\n        name: listteams\n        description: List teams\n        call: planetscale.listteams\n        outputParameters:\n        - type: object\n   \
  \       mapping: $.\n    - path: /organizations/{organization}/teams\n      name: createteam\n      operations:\n      - method: POST\n        name: createteam\n        description: Create a team\n        call: planetscale.createteam\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organizations/{organization}/teams/{team_slug}\n      name: getteam\n      operations:\n      - method: GET\n        name: getteam\n        description: Get a team\n        call: planetscale.getteam\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organizations/{organization}/teams/{team_slug}\n      name: updateteam\n      operations:\n      - method: PATCH\n        name: updateteam\n        description: Update a team\n        call: planetscale.updateteam\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organizations/{organization}/teams/{team_slug}\n      name: deleteteam\n      operations:\n\
  \      - method: DELETE\n        name: deleteteam\n        description: Delete a team\n        call: planetscale.deleteteam\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organizations/{organization}/databases\n      name: listdatabases\n      operations:\n      - method: GET\n        name: listdatabases\n        description: List databases\n        call: planetscale.listdatabases\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organizations/{organization}/databases\n      name: createdatabase\n      operations:\n      - method: POST\n        name: createdatabase\n        description: Create a database\n        call: planetscale.createdatabase\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organizations/{organization}/databases/{database}\n      name: getdatabase\n      operations:\n      - method: GET\n        name: getdatabase\n        description: Get a database\n\
  \        call: planetscale.getdatabase\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organizations/{organization}/databases/{database}\n      name: updatedatabasesettings\n      operations:\n      - method: PATCH\n        name: updatedatabasesettings\n        description: Update database settings\n        call: planetscale.updatedatabasesettings\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organizations/{organization}/databases/{database}\n      name: deletedatabase\n      operations:\n      - method: DELETE\n        name: deletedatabase\n        description: Delete a database\n        call: planetscale.deletedatabase\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organizations/{organization}/databases/{database}/branches\n      name: listbranches\n      operations:\n      - method: GET\n        name: listbranches\n        description: List branches\n        call:\
  \ planetscale.listbranches\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organizations/{organization}/databases/{database}/branches\n      name: createbranch\n      operations:\n      - method: POST\n        name: createbranch\n        description: Create a branch\n        call: planetscale.createbranch\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organizations/{organization}/databases/{database}/branches/{branch}\n      name: getbranch\n      operations:\n      - method: GET\n        name: getbranch\n        description: Get a branch\n        call: planetscale.getbranch\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organizations/{organization}/databases/{database}/branches/{branch}\n      name: updatebranch\n      operations:\n      - method: PATCH\n        name: updatebranch\n        description: Update a branch\n        call: planetscale.updatebranch\n     \
  \   outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organizations/{organization}/databases/{database}/branches/{branch}\n      name: deletebranch\n      operations:\n      - method: DELETE\n        name: deletebranch\n        description: Delete a branch\n        call: planetscale.deletebranch\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organizations/{organization}/databases/{database}/branches/{branch}/schema-lint\n      name: lintbranchschema\n      operations:\n      - method: GET\n        name: lintbranchschema\n        description: Lint a branch schema\n        call: planetscale.lintbranchschema\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organizations/{organization}/databases/{database}/deploy-requests\n      name: listdeployrequests\n      operations:\n      - method: GET\n        name: listdeployrequests\n        description: List deploy requests\n        call:\
  \ planetscale.listdeployrequests\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organizations/{organization}/databases/{database}/deploy-requests\n      name: createdeployrequest\n      operations:\n      - method: POST\n        name: createdeployrequest\n        description: Create a deploy request\n        call: planetscale.createdeployrequest\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organizations/{organization}/databases/{database}/deploy-requests/{deploy_request_number}\n      name: getdeployrequest\n      operations:\n      - method: GET\n        name: getdeployrequest\n        description: Get a deploy request\n        call: planetscale.getdeployrequest\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organizations/{organization}/databases/{database}/deploy-requests/{deploy_request_number}\n      name: closedeployrequest\n      operations:\n      - method:\
  \ PATCH\n        name: closedeployrequest\n        description: Close a deploy request\n        call: planetscale.closedeployrequest\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organizations/{organization}/databases/{database}/deploy-requests/{deploy_request_number}/deploy\n      name: queuedeployrequest\n      operations:\n      - method: POST\n        name: queuedeployrequest\n        description: Queue a deploy request\n        call: planetscale.queuedeployrequest\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organizations/{organization}/databases/{database}/deploy-requests/{deploy_request_number}/reviews\n      name: listdeployrequestreviews\n      operations:\n      - method: GET\n        name: listdeployrequestreviews\n        description: List deploy request reviews\n        call: planetscale.listdeployrequestreviews\n        outputParameters:\n        - type: object\n          mapping: $.\n  \
  \  - path: /organizations/{organization}/databases/{database}/deploy-requests/{deploy_request_number}/reviews\n      name: reviewdeployrequest\n      operations:\n      - method: POST\n        name: reviewdeployrequest\n        description: Review a deploy request\n        call: planetscale.reviewdeployrequest\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organizations/{organization}/databases/{database}/deploy-requests/{deploy_request_number}/skip-revert\n      name: skipdeployrequestrevert\n      operations:\n      - method: POST\n        name: skipdeployrequestrevert\n        description: Skip revert period\n        call: planetscale.skipdeployrequestrevert\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organizations/{organization}/databases/{database}/deploy-requests/{deploy_request_number}/complete-revert\n      name: completedeployrequestrevert\n      operations:\n      - method: POST\n        name:\
  \ completedeployrequestrevert\n        description: Complete a revert\n        call: planetscale.completedeployrequestrevert\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organizations/{organization}/databases/{database}/deploy-queue\n      name: getdeployqueue\n      operations:\n      - method: GET\n        name: getdeployqueue\n        description: Get the deploy queue\n        call: planetscale.getdeployqueue\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organizations/{organization}/databases/{database}/branches/{branch}/passwords\n      name: listpasswords\n      operations:\n      - method: GET\n        name: listpasswords\n        description: List passwords\n        call: planetscale.listpasswords\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organizations/{organization}/databases/{database}/branches/{branch}/passwords\n      name: createpassword\n     \
  \ operations:\n      - method: POST\n        name: createpassword\n        description: Create a password\n        call: planetscale.createpassword\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organizations/{organization}/databases/{database}/branches/{branch}/passwords/{password_id}\n      name: getpassword\n      operations:\n      - method: GET\n        name: getpassword\n        description: Get a password\n        call: planetscale.getpassword\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organizations/{organization}/databases/{database}/branches/{branch}/passwords/{password_id}\n      name: deletepassword\n      operations:\n      - method: DELETE\n        name: deletepassword\n        description: Delete a password\n        call: planetscale.deletepassword\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organizations/{organization}/databases/{database}/branches/{branch}/passwords/{password_id}/renew\n\
  \      name: renewpassword\n      operations:\n      - method: POST\n        name: renewpassword\n        description: Renew a password\n        call: planetscale.renewpassword\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organizations/{organization}/databases/{database}/branches/{branch}/backups\n      name: listbackups\n      operations:\n      - method: GET\n        name: listbackups\n        description: List backups\n        call: planetscale.listbackups\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organizations/{organization}/databases/{database}/branches/{branch}/backups\n      name: createbackup\n      operations:\n      - method: POST\n        name: createbackup\n        description: Create a backup\n        call: planetscale.createbackup\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organizations/{organization}/databases/{database}/branches/{branch}/backups/{backup_id}\n\
  \      name: getbackup\n      operations:\n      - method: GET\n        name: getbackup\n        description: Get a backup\n        call: planetscale.getbackup\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organizations/{organization}/databases/{database}/branches/{branch}/backups/{backup_id}\n      name: deletebackup\n      operations:\n      - method: DELETE\n        name: deletebackup\n        description: Delete a backup\n        call: planetscale.deletebackup\n   \n\n# --- truncated at 32 KB (53 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/planetscale/refs/heads/main/capabilities/planetscale-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/planetscale/refs/heads/main/capabilities/planetscale-capability.yaml
tags:
- Planetscale
- API
tools:
- description: List organizations
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listorganizations
- description: Get an organization
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getorganization
- description: List organization members
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listorganizationmembers
- description: Get an organization member
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getorganizationmember
- description: Update an organization member
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateorganizationmember
- description: Remove an organization member
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteorganizationmember
- description: List teams
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listteams
- description: Create a team
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createteam
- description: Get a team
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getteam
- description: Update a team
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateteam
- description: Delete a team
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteteam
- description: List databases
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listdatabases
- description: Create a database
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createdatabase
- description: Get a database
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdatabase
- description: Update database settings
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatedatabasesettings
- description: Delete a database
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletedatabase
- description: List branches
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listbranches
- description: Create a branch
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createbranch
- description: Get a branch
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getbranch
- description: Update a branch
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatebranch
- description: Delete a branch
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletebranch
- description: Lint a branch schema
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: lintbranchschema
- description: List deploy requests
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listdeployrequests
- description: Create a deploy request
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createdeployrequest
- description: Get a deploy request
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdeployrequest
- description: Close a deploy request
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: closedeployrequest
- description: Queue a deploy request
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: queuedeployrequest
- description: List deploy request reviews
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listdeployrequestreviews
- description: Review a deploy request
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: reviewdeployrequest
- description: Skip revert period
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: skipdeployrequestrevert
- description: Complete a revert
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: completedeployrequestrevert
- description: Get the deploy queue
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdeployqueue
- description: List passwords
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listpasswords
- description: Create a password
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createpassword
- description: Get a password
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getpassword
- description: Delete a password
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletepassword
- description: Renew a password
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: renewpassword
- description: List backups
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listbackups
- description: Create a backup
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createbackup
- description: Get a backup
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getbackup
- description: Delete a backup
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletebackup
- description: List service tokens
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listservicetokens
- description: Create a service token
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createservicetoken
- description: Get a service token
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getservicetoken
- description: Delete a service token
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteservicetoken
- description: List service token accesses
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listservicetokenaccesses
- description: Grant service token access
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createservicetokenaccess
- description: List bouncers
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listbouncers
- description: Create a bouncer
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createbouncer
- description: Get a bouncer
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getbouncer
- description: Delete a bouncer
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletebouncer
- description: List cluster sizes
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listclustersizes
- description: Create role credentials
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createrole
- description: List IP restrictions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listiprestrictions
- description: Create an IP restriction entry
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createiprestriction
- description: Show the status of a query patterns report
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getquerypatternsreportstatus
- description: List webhooks
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listwebhooks
- description: Create a webhook
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createwebhook
- description: List invoices
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listinvoices
- description: List schema recommendations
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listschemarecommendations
---
