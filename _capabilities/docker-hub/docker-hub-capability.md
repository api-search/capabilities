---
categories: []
consumed_apis: []
description: Docker Hub is a service provided by Docker for finding and sharing container images with your team. It is the world's largest library and community for container images. In addition to the [Docker Hub UI](https://docs.docker.com/docker-hub/) and [Docker Hub CLI tool](https://github.com/docker/hub-tool#readme) (currently experimental), Docker provides an API that allows you to interact with Docker Hub. Browse through the Docker Hub API documentation to explore the supported endpoints.
layout: capability
name: Docker HUB API
operations:
- description: Create an authentication token
  method: POST
  name: postuserslogin
  path: /v2/users/login
- description: Second factor authentication
  method: POST
  name: postusers2falogin
  path: /v2/users/2fa-login
- description: Create access token
  method: POST
  name: authcreateaccesstoken
  path: /v2/auth/token
- description: Create personal access token
  method: POST
  name: post-v2-access-tokens
  path: /v2/access-tokens
- description: List personal access tokens
  method: GET
  name: get-v2-access-tokens
  path: /v2/access-tokens
- description: Update personal access token
  method: PATCH
  name: patch-v2-access-tokens-uuid
  path: /v2/access-tokens/{uuid}
- description: Get personal access token
  method: GET
  name: get-v2-access-tokens-uuid
  path: /v2/access-tokens/{uuid}
- description: Delete personal access token
  method: DELETE
  name: delete-v2-access-tokens-uuid
  path: /v2/access-tokens/{uuid}
- description: List audit log actions
  method: GET
  name: auditlogs-listauditactions
  path: /v2/auditlogs/{account}/actions
- description: List audit log events
  method: GET
  name: auditlogs-listauditlogs
  path: /v2/auditlogs/{account}
- description: Get organization settings
  method: GET
  name: get-v2-orgs-name-settings
  path: /v2/orgs/{name}/settings
- description: Update organization settings
  method: PUT
  name: put-v2-orgs-name-settings
  path: /v2/orgs/{name}/settings
- description: Create access token
  method: POST
  name: post-v2-orgs-name-access-tokens
  path: /v2/orgs/{name}/access-tokens
- description: List access tokens
  method: GET
  name: get-v2-orgs-name-access-tokens
  path: /v2/orgs/{name}/access-tokens
- description: Get access token
  method: GET
  name: get-v2-orgs-org-name-access-tokens-access-token-
  path: /v2/orgs/{org_name}/access-tokens/{access_token_id}
- description: Update access token
  method: PATCH
  name: patch-v2-orgs-org-name-access-tokens-access-toke
  path: /v2/orgs/{org_name}/access-tokens/{access_token_id}
- description: Delete access token
  method: DELETE
  name: delete-v2-orgs-org-name-access-tokens-access-tok
  path: /v2/orgs/{org_name}/access-tokens/{access_token_id}
- description: List repository tags
  method: GET
  name: listrepositorytags
  path: /v2/namespaces/{namespace}/repositories/{repository}/tags
- description: Read repository tag
  method: GET
  name: getrepositorytag
  path: /v2/namespaces/{namespace}/repositories/{repository}/tags/{tag}
- description: Update repository immutable tags
  method: PATCH
  name: updaterepositoryimmutabletags
  path: /v2/namespaces/{namespace}/repositories/{repository}/immutabletags
- description: Verify repository immutable tags
  method: POST
  name: verifyrepositoryimmutabletags
  path: /v2/namespaces/{namespace}/repositories/{repository}/immutabletags/verify
- description: Assign a group (Team) to a repository for access
  method: POST
  name: createrepositorygroup
  path: /v2/repositories/{namespace}/{repository}/groups
- description: List repositories in a namespace
  method: GET
  name: listnamespacerepositories
  path: /v2/namespaces/{namespace}/repositories
- description: Create a new repository
  method: POST
  name: createrepository
  path: /v2/namespaces/{namespace}/repositories
- description: Get repository in a namespace
  method: GET
  name: getrepository
  path: /v2/namespaces/{namespace}/repositories/{repository}
- description: List org members
  method: GET
  name: get-v2-orgs-org-name-members
  path: /v2/orgs/{org_name}/members
- description: Export org members CSV
  method: GET
  name: get-v2-orgs-org-name-members-export
  path: /v2/orgs/{org_name}/members/export
- description: Update org member (role)
  method: PUT
  name: put-v2-orgs-org-name-members-username
  path: /v2/orgs/{org_name}/members/{username}
- description: Remove member from org
  method: DELETE
  name: delete-v2-orgs-org-name-members-username
  path: /v2/orgs/{org_name}/members/{username}
- description: List org invites
  method: GET
  name: get-v2-orgs-org-name-invites
  path: /v2/orgs/{org_name}/invites
- description: Get groups of an organization
  method: GET
  name: get-v2-orgs-org-name-groups
  path: /v2/orgs/{org_name}/groups
- description: Create a new group
  method: POST
  name: post-v2-orgs-org-name-groups
  path: /v2/orgs/{org_name}/groups
- description: Get a group of an organization
  method: GET
  name: get-v2-orgs-org-name-groups-group-name
  path: /v2/orgs/{org_name}/groups/{group_name}
- description: Update the details for an organization group
  method: PUT
  name: put-v2-orgs-org-name-groups-group-name
  path: /v2/orgs/{org_name}/groups/{group_name}
- description: Update some details for an organization group
  method: PATCH
  name: patch-v2-orgs-org-name-groups-group-name
  path: /v2/orgs/{org_name}/groups/{group_name}
- description: Delete an organization group
  method: DELETE
  name: delete-v2-orgs-org-name-groups-group-name
  path: /v2/orgs/{org_name}/groups/{group_name}
- description: List members of a group
  method: GET
  name: get-v2-orgs-org-name-groups-group-name-members
  path: /v2/orgs/{org_name}/groups/{group_name}/members
- description: Add a member to a group
  method: POST
  name: post-v2-orgs-org-name-groups-group-name-members
  path: /v2/orgs/{org_name}/groups/{group_name}/members
- description: Remove a user from a group
  method: DELETE
  name: delete-v2-orgs-org-name-groups-group-name-member
  path: /v2/orgs/{org_name}/groups/{group_name}/members/{username}
- description: Cancel an invite
  method: DELETE
  name: delete-v2-invites-id
  path: /v2/invites/{id}
- description: Resend an invite
  method: PATCH
  name: patch-v2-invites-id-resend
  path: /v2/invites/{id}/resend
- description: Bulk create invites
  method: POST
  name: post-v2-invites-bulk
  path: /v2/invites/bulk
- description: Get service provider config
  method: GET
  name: get-v2-scim-2-0-serviceproviderconfig
  path: /v2/scim/2.0/ServiceProviderConfig
- description: List resource types
  method: GET
  name: get-v2-scim-2-0-resourcetypes
  path: /v2/scim/2.0/ResourceTypes
- description: Get a resource type
  method: GET
  name: get-v2-scim-2-0-resourcetypes-name
  path: /v2/scim/2.0/ResourceTypes/{name}
- description: List schemas
  method: GET
  name: get-v2-scim-2-0-schemas
  path: /v2/scim/2.0/Schemas
- description: Get a schema
  method: GET
  name: get-v2-scim-2-0-schemas-id
  path: /v2/scim/2.0/Schemas/{id}
- description: List users
  method: GET
  name: get-v2-scim-2-0-users
  path: /v2/scim/2.0/Users
- description: Create user
  method: POST
  name: post-v2-scim-2-0-users
  path: /v2/scim/2.0/Users
- description: Get a user
  method: GET
  name: get-v2-scim-2-0-users-id
  path: /v2/scim/2.0/Users/{id}
- description: Update a user
  method: PUT
  name: put-v2-scim-2-0-users-id
  path: /v2/scim/2.0/Users/{id}
personas: []
provider_name: Docker Hub
provider_slug: docker-hub
search_terms:
- auditlogs listauditlogs
- list personal access tokens
- list org members
- read repository tag
- get v2 scim 2 0 resourcetypes
- verify repository immutable tags
- post v2 invites bulk
- list audit log actions
- list repositories in a namespace
- delete v2 orgs org name groups group name
- getrepository
- get v2 orgs org name members export
- get groups of an organization
- update personal access token
- verifyrepositoryimmutabletags
- resend an invite
- export org members csv
- updaterepositoryimmutabletags
- list resource types
- auditlogs listauditactions
- put v2 orgs org name members username
- api
- post v2 orgs name access tokens
- get v2 orgs name access tokens
- delete an organization group
- hub
- list schemas
- patch v2 access tokens uuid
- get v2 access tokens uuid
- get v2 scim 2 0 schemas id
- create access token
- post v2 orgs org name groups
- update repository immutable tags
- get v2 orgs org name groups
- patch v2 orgs org name access tokens access toke
- createrepository
- assign a group (team) to a repository for access
- getrepositorytag
- create user
- listrepositorytags
- postusers2falogin
- create a new repository
- delete v2 orgs org name members username
- post v2 scim 2 0 users
- get v2 orgs org name members
- add a member to a group
- authcreateaccesstoken
- get personal access token
- create personal access token
- get v2 orgs org name groups group name members
- delete v2 invites id
- createrepositorygroup
- get v2 orgs org name invites
- get organization settings
- delete access token
- delete v2 orgs org name groups group name member
- get service provider config
- get v2 scim 2 0 resourcetypes name
- devops
- update some details for an organization group
- create an authentication token
- list members of a group
- get v2 orgs name settings
- registry
- patch v2 invites id resend
- list audit log events
- put v2 orgs name settings
- get a group of an organization
- remove a user from a group
- listnamespacerepositories
- get v2 orgs org name access tokens access token
- update organization settings
- list access tokens
- get v2 access tokens
- get v2 scim 2 0 users
- delete personal access token
- delete v2 access tokens uuid
- postuserslogin
- list repository tags
- delete v2 orgs org name access tokens access tok
- update org member (role)
- post v2 orgs org name groups group name members
- bulk create invites
- get access token
- get a schema
- patch v2 orgs org name groups group name
- get a resource type
- containers
- put v2 scim 2 0 users id
- second factor authentication
- docker
- get repository in a namespace
- list org invites
- create a new group
- put v2 orgs org name groups group name
- get v2 scim 2 0 users id
- post v2 access tokens
- update access token
- get v2 orgs org name groups group name
- list users
- get a user
- update a user
- cancel an invite
- get v2 scim 2 0 schemas
- remove member from org
- get v2 scim 2 0 serviceproviderconfig
- update the details for an organization group
slug: docker-hub-capability
source_filename: docker-hub-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Docker HUB API\n  description: Docker Hub is a service provided by Docker for finding and sharing container images with your team. It is the\n    world's largest library and community for container images. In addition to the [Docker Hub UI](https://docs.docker.com/docker-hub/)\n    and [Docker Hub CLI tool](https://github.com/docker/hub-tool#readme) (currently experimental), Docker provides an API\n    that allows you to interact with Docker Hub. Browse through the Docker Hub API documentation to explore the supported\n    endpoints.\n  tags:\n  - Docker\n  - Hub\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: docker-hub\n    baseUri: https://hub.docker.com\n    description: Docker HUB API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{DOCKER_HUB_TOKEN}}'\n    resources:\n    - name: v2-users-login\n      path: /v2/users/login\n      operations:\n\
  \      - name: postuserslogin\n        method: POST\n        description: Create an authentication token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v2-users-2fa-login\n      path: /v2/users/2fa-login\n      operations:\n      - name: postusers2falogin\n        method: POST\n        description: Second factor authentication\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v2-auth-token\n      path: /v2/auth/token\n      operations:\n      - name: authcreateaccesstoken\n        method: POST\n        description: Create access token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v2-access-tokens\n      path: /v2/access-tokens\n      operations:\n      - name: post-v2-access-tokens\n        method: POST\n        description:\
  \ Create personal access token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-v2-access-tokens\n        method: GET\n        description: List personal access tokens\n        inputParameters:\n        - name: page\n          in: query\n          type: number\n        - name: page_size\n          in: query\n          type: number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v2-access-tokens-uuid\n      path: /v2/access-tokens/{uuid}\n      operations:\n      - name: patch-v2-access-tokens-uuid\n        method: PATCH\n        description: Update personal access token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-v2-access-tokens-uuid\n        method: GET\n        description: Get personal access token\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-v2-access-tokens-uuid\n        method: DELETE\n        description: Delete personal access token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v2-auditlogs-account-actions\n      path: /v2/auditlogs/{account}/actions\n      operations:\n      - name: auditlogs-listauditactions\n        method: GET\n        description: List audit log actions\n        inputParameters:\n        - name: account\n          in: path\n          type: string\n          required: true\n          description: Namespace to query audit log actions for.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v2-auditlogs-account\n      path: /v2/auditlogs/{account}\n      operations:\n      -\
  \ name: auditlogs-listauditlogs\n        method: GET\n        description: List audit log events\n        inputParameters:\n        - name: account\n          in: path\n          type: string\n          required: true\n          description: Namespace to query audit logs for.\n        - name: action\n          in: query\n          type: string\n          description: action name one of [\"repo.tag.push\", ...]. Optional parameter to filter specific audit log actions.\n        - name: name\n          in: query\n          type: string\n          description: name. Optional parameter to filter audit log events to a specific name. For repository events, this\n            is the name of the repository. For organization events, this\n        - name: actor\n          in: query\n          type: string\n          description: actor name. Optional parameter to filter audit log events to the specific user who triggered the event.\n        - name: from\n          in: query\n          type: string\n\
  \          description: Start of the time window you wish to query audit events for.\n        - name: to\n          in: query\n          type: string\n          description: End of the time window you wish to query audit events for.\n        - name: page\n          in: query\n          type: integer\n          description: page - specify page number. Page number to get.\n        - name: page_size\n          in: query\n          type: integer\n          description: page_size - specify page size. Number of events to return per page.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v2-orgs-name-settings\n      path: /v2/orgs/{name}/settings\n      operations:\n      - name: get-v2-orgs-name-settings\n        method: GET\n        description: Get organization settings\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    \
  \  - name: put-v2-orgs-name-settings\n        method: PUT\n        description: Update organization settings\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v2-orgs-name-access-tokens\n      path: /v2/orgs/{name}/access-tokens\n      operations:\n      - name: post-v2-orgs-name-access-tokens\n        method: POST\n        description: Create access token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-v2-orgs-name-access-tokens\n        method: GET\n        description: List access tokens\n        inputParameters:\n        - name: page\n          in: query\n          type: number\n        - name: page_size\n          in: query\n          type: number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v2-orgs-org-name-access-tokens-access-token-id\n\
  \      path: /v2/orgs/{org_name}/access-tokens/{access_token_id}\n      operations:\n      - name: get-v2-orgs-org-name-access-tokens-access-token-\n        method: GET\n        description: Get access token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: patch-v2-orgs-org-name-access-tokens-access-toke\n        method: PATCH\n        description: Update access token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-v2-orgs-org-name-access-tokens-access-tok\n        method: DELETE\n        description: Delete access token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v2-namespaces-namespace-repositories-repository-\n      path: /v2/namespaces/{namespace}/repositories/{repository}/tags\n      operations:\n\
  \      - name: listrepositorytags\n        method: GET\n        description: List repository tags\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n          description: Page number to get. Defaults to 1.\n        - name: page_size\n          in: query\n          type: integer\n          description: Number of items to get per page. Defaults to 10. Max of 100.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v2-namespaces-namespace-repositories-repository-\n      path: /v2/namespaces/{namespace}/repositories/{repository}/tags/{tag}\n      operations:\n      - name: getrepositorytag\n        method: GET\n        description: Read repository tag\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v2-namespaces-namespace-repositories-repository-\n      path: /v2/namespaces/{namespace}/repositories/{repository}/immutabletags\n\
  \      operations:\n      - name: updaterepositoryimmutabletags\n        method: PATCH\n        description: Update repository immutable tags\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v2-namespaces-namespace-repositories-repository-\n      path: /v2/namespaces/{namespace}/repositories/{repository}/immutabletags/verify\n      operations:\n      - name: verifyrepositoryimmutabletags\n        method: POST\n        description: Verify repository immutable tags\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v2-repositories-namespace-repository-groups\n      path: /v2/repositories/{namespace}/{repository}/groups\n      operations:\n      - name: createrepositorygroup\n        method: POST\n        description: Assign a group (Team) to a repository for access\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: v2-namespaces-namespace-repositories\n      path: /v2/namespaces/{namespace}/repositories\n      operations:\n      - name: listnamespacerepositories\n        method: GET\n        description: List repositories in a namespace\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n          description: Page number to get. Defaults to 1.\n        - name: page_size\n          in: query\n          type: integer\n          description: Number of repositories to get per page. Defaults to 10. Max of 100.\n        - name: name\n          in: query\n          type: string\n          description: Filter repositories by name (partial match).\n        - name: ordering\n          in: query\n          type: string\n          description: 'Order repositories by the specified field. Prefix with ''-'' for descending order. Available options:\n            - `name` / `-name`: Repository\
  \ name (ascending/descending) -'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createrepository\n        method: POST\n        description: Create a new repository\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v2-namespaces-namespace-repositories-repository\n      path: /v2/namespaces/{namespace}/repositories/{repository}\n      operations:\n      - name: getrepository\n        method: GET\n        description: Get repository in a namespace\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v2-orgs-org-name-members\n      path: /v2/orgs/{org_name}/members\n      operations:\n      - name: get-v2-orgs-org-name-members\n        method: GET\n        description: List org members\n        outputRawFormat: json\n   \
  \     outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v2-orgs-org-name-members-export\n      path: /v2/orgs/{org_name}/members/export\n      operations:\n      - name: get-v2-orgs-org-name-members-export\n        method: GET\n        description: Export org members CSV\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v2-orgs-org-name-members-username\n      path: /v2/orgs/{org_name}/members/{username}\n      operations:\n      - name: put-v2-orgs-org-name-members-username\n        method: PUT\n        description: Update org member (role)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-v2-orgs-org-name-members-username\n        method: DELETE\n        description: Remove member from org\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: v2-orgs-org-name-invites\n      path: /v2/orgs/{org_name}/invites\n      operations:\n      - name: get-v2-orgs-org-name-invites\n        method: GET\n        description: List org invites\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v2-orgs-org-name-groups\n      path: /v2/orgs/{org_name}/groups\n      operations:\n      - name: get-v2-orgs-org-name-groups\n        method: GET\n        description: Get groups of an organization\n        inputParameters:\n        - name: username\n          in: query\n          type: string\n          description: Get groups for the specified username in the organization.\n        - name: search\n          in: query\n          type: string\n          description: Get groups for the specified group in the organization.\n        outputRawFormat: json\n        outputParameters:\n \
  \       - name: result\n          type: object\n          value: $.\n      - name: post-v2-orgs-org-name-groups\n        method: POST\n        description: Create a new group\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v2-orgs-org-name-groups-group-name\n      path: /v2/orgs/{org_name}/groups/{group_name}\n      operations:\n      - name: get-v2-orgs-org-name-groups-group-name\n        method: GET\n        description: Get a group of an organization\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: put-v2-orgs-org-name-groups-group-name\n        method: PUT\n        description: Update the details for an organization group\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: patch-v2-orgs-org-name-groups-group-name\n\
  \        method: PATCH\n        description: Update some details for an organization group\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-v2-orgs-org-name-groups-group-name\n        method: DELETE\n        description: Delete an organization group\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v2-orgs-org-name-groups-group-name-members\n      path: /v2/orgs/{org_name}/groups/{group_name}/members\n      operations:\n      - name: get-v2-orgs-org-name-groups-group-name-members\n        method: GET\n        description: List members of a group\n        inputParameters:\n        - name: search\n          in: query\n          type: string\n          description: Search members by username, full_name or email.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n       \
  \   type: object\n          value: $.\n      - name: post-v2-orgs-org-name-groups-group-name-members\n        method: POST\n        description: Add a member to a group\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v2-orgs-org-name-groups-group-name-members-usern\n      path: /v2/orgs/{org_name}/groups/{group_name}/members/{username}\n      operations:\n      - name: delete-v2-orgs-org-name-groups-group-name-member\n        method: DELETE\n        description: Remove a user from a group\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v2-invites-id\n      path: /v2/invites/{id}\n      operations:\n      - name: delete-v2-invites-id\n        method: DELETE\n        description: Cancel an invite\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n    \
  \      value: $.\n    - name: v2-invites-id-resend\n      path: /v2/invites/{id}/resend\n      operations:\n      - name: patch-v2-invites-id-resend\n        method: PATCH\n        description: Resend an invite\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v2-invites-bulk\n      path: /v2/invites/bulk\n      operations:\n      - name: post-v2-invites-bulk\n        method: POST\n        description: Bulk create invites\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v2-scim-2-0-serviceproviderconfig\n      path: /v2/scim/2.0/ServiceProviderConfig\n      operations:\n      - name: get-v2-scim-2-0-serviceproviderconfig\n        method: GET\n        description: Get service provider config\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n    - name: v2-scim-2-0-resourcetypes\n      path: /v2/scim/2.0/ResourceTypes\n      operations:\n      - name: get-v2-scim-2-0-resourcetypes\n        method: GET\n        description: List resource types\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v2-scim-2-0-resourcetypes-name\n      path: /v2/scim/2.0/ResourceTypes/{name}\n      operations:\n      - name: get-v2-scim-2-0-resourcetypes-name\n        method: GET\n        description: Get a resource type\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v2-scim-2-0-schemas\n      path: /v2/scim/2.0/Schemas\n      operations:\n      - name: get-v2-scim-2-0-schemas\n        method: GET\n        description: List schemas\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v2-scim-2-0-schemas-id\n      path: /v2/scim/2.0/Schemas/{id}\n      operations:\n      - name: get-v2-scim-2-0-schemas-id\n        method: GET\n        description: Get a schema\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v2-scim-2-0-users\n      path: /v2/scim/2.0/Users\n      operations:\n      - name: get-v2-scim-2-0-users\n        method: GET\n        description: List users\n        inputParameters:\n        - name: startIndex\n          in: query\n          type: integer\n        - name: count\n          in: query\n          type: integer\n        - name: filter\n          in: query\n          type: string\n        - name: sortOrder\n          in: query\n \
  \         type: string\n        - name: sortBy\n          in: query\n          type: string\n          description: User attribute to sort by.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: post-v2-scim-2-0-users\n        method: POST\n        description: Create user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v2-scim-2-0-users-id\n      path: /v2/scim/2.0/Users/{id}\n      operations:\n      - name: get-v2-scim-2-0-users-id\n        method: GET\n        description: Get a user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: put-v2-scim-2-0-users-id\n        method: PUT\n        description: Update a user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: docker-hub-rest\n    description: REST adapter for Docker HUB API.\n    resources:\n    - path: /v2/users/login\n      name: postuserslogin\n      operations:\n      - method: POST\n        name: postuserslogin\n        description: Create an authentication token\n        call: docker-hub.postuserslogin\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/users/2fa-login\n      name: postusers2falogin\n      operations:\n      - method: POST\n        name: postusers2falogin\n        description: Second factor authentication\n        call: docker-hub.postusers2falogin\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/auth/token\n      name: authcreateaccesstoken\n      operations:\n      - method: POST\n        name: authcreateaccesstoken\n        description: Create access token\n        call: docker-hub.authcreateaccesstoken\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/access-tokens\n      name: post-v2-access-tokens\n      operations:\n      - method: POST\n        name: post-v2-access-tokens\n        description: Create personal access token\n        call: docker-hub.post-v2-access-tokens\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/access-tokens\n      name: get-v2-access-tokens\n      operations:\n      - method: GET\n        name: get-v2-access-tokens\n        description: List personal access tokens\n        call: docker-hub.get-v2-access-tokens\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/access-tokens/{uuid}\n      name: patch-v2-access-tokens-uuid\n      operations:\n      - method: PATCH\n        name: patch-v2-access-tokens-uuid\n        description: Update personal access token\n        call: docker-hub.patch-v2-access-tokens-uuid\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /v2/access-tokens/{uuid}\n      name: get-v2-access-tokens-uuid\n      operations:\n      - method: GET\n        name: get-v2-access-tokens-uuid\n        description: Get personal access token\n        call: docker-hub.get-v2-access-tokens-uuid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/access-tokens/{uuid}\n      name: delete-v2-access-tokens-uuid\n      operations:\n      - method: DELETE\n        name: delete-v2-access-tokens-uuid\n        description: Delete personal access token\n        call: docker-hub.delete-v2-access-tokens-uuid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/auditlogs/{account}/actions\n      name: auditlogs-listauditactions\n      operations:\n      - method: GET\n        name: auditlogs-listauditactions\n        description: List audit log actions\n        call: docker-hub.auditlogs-listauditactions\n       \
  \ with:\n          account: rest.account\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/auditlogs/{account}\n      name: auditlogs-listauditlogs\n      operations:\n      - method: GET\n        name: auditlogs-listauditlogs\n        description: List audit log events\n        call: docker-hub.auditlogs-listauditlogs\n        with:\n          account: rest.account\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/orgs/{name}/settings\n      name: get-v2-orgs-name-settings\n      operations:\n      - method: GET\n        name: get-v2-orgs-name-settings\n        description: Get organization settings\n        call: docker-hub.get-v2-orgs-name-settings\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/orgs/{name}/settings\n      name: put-v2-orgs-name-settings\n      operations:\n      - method: PUT\n        name: put-v2-orgs-name-settings\n        description: Update\
  \ organization settings\n        call: docker-hub.put-v2-orgs-name-settings\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/orgs/{name}/access-tokens\n      name: post-v2-orgs-name-access-tokens\n      operations:\n      - method: POST\n        name: post-v2-orgs-name-access-tokens\n        description: Create access token\n        call: docker-hub.post-v2-orgs-name-access-tokens\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/orgs/{name}/access-tokens\n      name: get-v2-orgs-name-access-tokens\n      operations:\n      - method: GET\n        name: get-v2-orgs-name-access-tokens\n        description: List access tokens\n        call: docker-hub.get-v2-orgs-name-access-tokens\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/orgs/{org_name}/access-tokens/{access_token_id}\n      name: get-v2-orgs-org-name-access-tokens-access-token\n      operations:\n      - method:\
  \ GET\n        name: get-v2-orgs-org-name-access-tokens-access-token-\n        description: Get access token\n        call: docker-hub.get-v2-orgs-org-name-access-tokens-access-token-\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/orgs/{org_name}/access-tokens/{access_token_id}\n      name: patch-v2-orgs-org-name-access-tokens-access-toke\n      operations:\n      - method: PATCH\n        name: patch-v2-orgs-org-name-access-tokens-access-toke\n        description: Update access token\n        call: docker-hub.patch-v2-orgs-org-name-access-tokens-access-toke\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/orgs/{org_name}/access-tokens/{access_token_id}\n      name: delete-v2-orgs-org-name-access-tokens-access-tok\n      operations:\n      - method: DELETE\n        name: delete-v2-orgs-org-name-access-tokens-access-tok\n        description: Delete access token\n        call: docker-hub.delete-v2-orgs-org-name-access-tokens-access-tok\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/namespaces/{namespace}/repositories/{repository}/tags\n      name: listrepositorytags\n      operations:\n      - method: GET\n        name: listrepositorytags\n        description: List repository tags\n        call: docker-hub.listrepositorytags\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/namespaces/{namespace}/repositories/{repository}/tags/{tag}\n      name: getrepositorytag\n      operations:\n      - method: GET\n        name: getrepositorytag\n        description: Read repository tag\n        call: docker-hub.getrepositorytag\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/namespaces/{namespace}/repositories/{repository}/immutabletags\n      name: updaterepositoryimmutabletags\n      operations:\n      - method: PATCH\n        name: updaterepositoryimmutabletags\n        description: Update repository\
  \ immutable tags\n        call: docker-hub.updaterepositoryimmutabletags\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/namespaces/{namespace}/repositories/{repository}/immutabletags/verify\n      name: verifyrepositoryimmutabletags\n      operations:\n      - method: POST\n        name: verifyrepositoryimmutabletags\n        description: Verify repository immutable tags\n        call: docker-hub.verifyrepositoryimmutabletags\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/repositories/{namespace}/{repository}/groups\n      name: createrepositorygroup\n      operations:\n      - method: POST\n        name: createrepositorygroup\n        description: Assign a group (Team) to a repository for access\n        call: docker-hub.createrepositorygroup\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/namespaces/{namespace}/repositories\n      name: listnamespacerepositories\n\
  \      operations:\n      - method: GET\n        name: listnamespacerepositories\n        description: List repositories in a namespace\n        call: docker-hub.listnamespacerepositories\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/namespaces/{namespace}/repositories\n      name: createrepository\n      operations:\n      - method: POST\n        name: createrepository\n        description: Create a new repository\n        call: docker-hub.createrepository\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/namespaces/{namespace}/repositories/{repository}\n      name: getrepository\n      operations:\n      - method: GET\n        name: getrepository\n        description: Get repository in a namespace\n        call: docker-hub.getrepository\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/orgs/{org_name}/members\n      name: get-v2-orgs-org-name-members\n      operations:\n\
  \      - method: GET\n        name: get-v2-orgs-org-name-members\n        description: List org members\n        call: docker-hub.get-v2-orgs-org-name-members\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/orgs/{org_name}/members/export\n      name: get-v2-orgs-org-name-members-export\n      operations:\n      - method: GET\n        name: get-v2-orgs-org-name-members-export\n        description: Export org members CSV\n        call: docker-hub.get-v2-orgs-org-name-members-export\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/orgs/{org_name}/members/{username}\n      name: put-v2-orgs-org-name-members-username\n      operations:\n      - method: PUT\n        name: put-v2-orgs-org-name-members-username\n        description: Update org member (role)\n        call: docker-hub.put-v2-orgs-org-name-members-username\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/orgs/{org_name}/members/{username}\n\
  \      name: delete-v2-orgs-org-name-members-username\n      operations:\n      - method: DELETE\n        name: delete-v2-orgs-org-name-members-username\n        description: Remove member from org\n        call: docker-hub.delete-v2-orgs-org-name-members-username\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/orgs/{org_name}/invites\n      name: get-v2-orgs-org-name-invites\n      operations:\n      - method: GET\n        name: get-v2-orgs-org-name-invites\n        description: List org invites\n        call: docker-hub.get-v2-orgs-org-name-invites\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/orgs/{org_name}/groups\n      name: get-v2-orgs-org-name-groups\n      operations:\n      - method: GET\n        name: get-v2-orgs-org-name-groups\n        description: Get groups of an organization\n        call: docker-hub.get-v2-orgs-org-name-groups\n        outputParameters:\n        - type: object\n   \
  \       mapping: $.\n    - path: /v2/orgs/{org_name}/groups\n      name: post-v2-orgs-org-name-groups\n      operations:\n      - method: POST\n        name: post-v2-orgs-org-name-groups\n        description: Create a new group\n        call: docker-hub.post-v2-orgs-org-name-groups\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/orgs/{org_name}/groups/{group_name}\n      name: get-v2-orgs-org-name-groups-group-name\n      operations:\n      - method: GET\n        name: get-v2-orgs-org-name-groups-group-name\n        description: Get a group of an organization\n        call: docker-hub.get-v2-orgs-org-name-groups-group-name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/orgs/{org_name}/groups/{group_name}\n      name: put-v2-orgs-org-name-groups-group-name\n      operations:\n      - method: PUT\n        name: put-v2-orgs-org-name-groups-group-name\n        description: Update the details for an organization\
  \ group\n        call: docker-hub.put-v2-orgs-org-name-groups-group-name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/orgs/{org_name}/groups/{group_name}\n      name: patch-v2-orgs-org-name-groups-group-name\n      operations:\n      - method: PATCH\n        name: patch-v2-orgs-org-name-groups-group-name\n        description: Update some details for an organization group\n        call: docker-hub.patch-v2-orgs-org-name-groups-group-name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/orgs/{o\n\n# --- truncated at 32 KB (56 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/docker-hub/refs/heads/main/capabilities/docker-hub-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/docker-hub/refs/heads/main/capabilities/docker-hub-capability.yaml
tags:
- Docker
- Hub
- API
tools:
- description: Create an authentication token
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: postuserslogin
- description: Second factor authentication
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: postusers2falogin
- description: Create access token
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: authcreateaccesstoken
- description: Create personal access token
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-v2-access-tokens
- description: List personal access tokens
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-v2-access-tokens
- description: Update personal access token
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: patch-v2-access-tokens-uuid
- description: Get personal access token
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-v2-access-tokens-uuid
- description: Delete personal access token
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-v2-access-tokens-uuid
- description: List audit log actions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: auditlogs-listauditactions
- description: List audit log events
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: auditlogs-listauditlogs
- description: Get organization settings
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-v2-orgs-name-settings
- description: Update organization settings
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: put-v2-orgs-name-settings
- description: Create access token
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-v2-orgs-name-access-tokens
- description: List access tokens
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-v2-orgs-name-access-tokens
- description: Get access token
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-v2-orgs-org-name-access-tokens-access-token-
- description: Update access token
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: patch-v2-orgs-org-name-access-tokens-access-toke
- description: Delete access token
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-v2-orgs-org-name-access-tokens-access-tok
- description: List repository tags
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listrepositorytags
- description: Read repository tag
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getrepositorytag
- description: Update repository immutable tags
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updaterepositoryimmutabletags
- description: Verify repository immutable tags
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: verifyrepositoryimmutabletags
- description: Assign a group (Team) to a repository for access
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createrepositorygroup
- description: List repositories in a namespace
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listnamespacerepositories
- description: Create a new repository
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createrepository
- description: Get repository in a namespace
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getrepository
- description: List org members
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-v2-orgs-org-name-members
- description: Export org members CSV
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-v2-orgs-org-name-members-export
- description: Update org member (role)
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: put-v2-orgs-org-name-members-username
- description: Remove member from org
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-v2-orgs-org-name-members-username
- description: List org invites
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-v2-orgs-org-name-invites
- description: Get groups of an organization
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-v2-orgs-org-name-groups
- description: Create a new group
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-v2-orgs-org-name-groups
- description: Get a group of an organization
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-v2-orgs-org-name-groups-group-name
- description: Update the details for an organization group
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: put-v2-orgs-org-name-groups-group-name
- description: Update some details for an organization group
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: patch-v2-orgs-org-name-groups-group-name
- description: Delete an organization group
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-v2-orgs-org-name-groups-group-name
- description: List members of a group
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-v2-orgs-org-name-groups-group-name-members
- description: Add a member to a group
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-v2-orgs-org-name-groups-group-name-members
- description: Remove a user from a group
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-v2-orgs-org-name-groups-group-name-member
- description: Cancel an invite
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-v2-invites-id
- description: Resend an invite
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: patch-v2-invites-id-resend
- description: Bulk create invites
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-v2-invites-bulk
- description: Get service provider config
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-v2-scim-2-0-serviceproviderconfig
- description: List resource types
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-v2-scim-2-0-resourcetypes
- description: Get a resource type
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-v2-scim-2-0-resourcetypes-name
- description: List schemas
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-v2-scim-2-0-schemas
- description: Get a schema
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-v2-scim-2-0-schemas-id
- description: List users
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-v2-scim-2-0-users
- description: Create user
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-v2-scim-2-0-users
- description: Get a user
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-v2-scim-2-0-users-id
- description: Update a user
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: put-v2-scim-2-0-users-id
---
