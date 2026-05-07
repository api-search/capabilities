---
categories: []
consumed_apis: []
description: The Keycloak Admin REST API provides endpoints for managing all aspects of a Keycloak deployment, including realms, users, clients, roles, groups, and identity providers. All endpoints require authentication via a bearer token obtained from the Keycloak token endpoint.
layout: capability
name: Keycloak Admin REST API
operations:
- description: Keycloak List all realms
  method: GET
  name: getrealms
  path: /
- description: Keycloak Get a realm
  method: GET
  name: getrealm
  path: /{realm}
- description: Keycloak Update a realm
  method: PUT
  name: updaterealm
  path: /{realm}
- description: Keycloak Delete a realm
  method: DELETE
  name: deleterealm
  path: /{realm}
- description: Keycloak List users
  method: GET
  name: getusers
  path: /{realm}/users
- description: Keycloak Create a new user
  method: POST
  name: createuser
  path: /{realm}/users
- description: Keycloak Get a user
  method: GET
  name: getuser
  path: /{realm}/users/{userId}
- description: Keycloak Update a user
  method: PUT
  name: updateuser
  path: /{realm}/users/{userId}
- description: Keycloak Delete a user
  method: DELETE
  name: deleteuser
  path: /{realm}/users/{userId}
- description: Keycloak Get realm-level role mappings for a user
  method: GET
  name: getuserrealmrolemappings
  path: /{realm}/users/{userId}/role-mappings/realm
- description: Keycloak Add realm-level role mappings to a user
  method: POST
  name: adduserrealmrolemappings
  path: /{realm}/users/{userId}/role-mappings/realm
- description: Keycloak Remove realm-level role mappings from a user
  method: DELETE
  name: deleteuserrealmrolemappings
  path: /{realm}/users/{userId}/role-mappings/realm
- description: Keycloak Get groups for a user
  method: GET
  name: getusergroups
  path: /{realm}/users/{userId}/groups
- description: Keycloak Add a user to a group
  method: PUT
  name: addusertogroup
  path: /{realm}/users/{userId}/groups/{groupId}
- description: Keycloak Remove a user from a group
  method: DELETE
  name: removeuserfromgroup
  path: /{realm}/users/{userId}/groups/{groupId}
- description: Keycloak Reset a user's password
  method: PUT
  name: resetuserpassword
  path: /{realm}/users/{userId}/reset-password
- description: Keycloak List clients
  method: GET
  name: getclients
  path: /{realm}/clients
- description: Keycloak Create a new client
  method: POST
  name: createclient
  path: /{realm}/clients
- description: Keycloak Get a client
  method: GET
  name: getclient
  path: /{realm}/clients/{clientUuid}
- description: Keycloak Update a client
  method: PUT
  name: updateclient
  path: /{realm}/clients/{clientUuid}
- description: Keycloak Delete a client
  method: DELETE
  name: deleteclient
  path: /{realm}/clients/{clientUuid}
- description: Keycloak Get the client secret
  method: GET
  name: getclientsecret
  path: /{realm}/clients/{clientUuid}/client-secret
- description: Keycloak Regenerate the client secret
  method: POST
  name: regenerateclientsecret
  path: /{realm}/clients/{clientUuid}/client-secret
- description: Keycloak List realm-level roles
  method: GET
  name: getroles
  path: /{realm}/roles
- description: Keycloak Create a realm-level role
  method: POST
  name: createrole
  path: /{realm}/roles
- description: Keycloak Get a realm-level role by name
  method: GET
  name: getrole
  path: /{realm}/roles/{roleName}
- description: Keycloak Update a realm-level role
  method: PUT
  name: updaterole
  path: /{realm}/roles/{roleName}
- description: Keycloak Delete a realm-level role
  method: DELETE
  name: deleterole
  path: /{realm}/roles/{roleName}
- description: Keycloak List groups
  method: GET
  name: getgroups
  path: /{realm}/groups
- description: Keycloak Create a top-level group
  method: POST
  name: creategroup
  path: /{realm}/groups
- description: Keycloak Get a group
  method: GET
  name: getgroup
  path: /{realm}/groups/{groupId}
- description: Keycloak Update a group
  method: PUT
  name: updategroup
  path: /{realm}/groups/{groupId}
- description: Keycloak Delete a group
  method: DELETE
  name: deletegroup
  path: /{realm}/groups/{groupId}
- description: Keycloak Create a child group
  method: POST
  name: createchildgroup
  path: /{realm}/groups/{groupId}/children
- description: Keycloak Get members of a group
  method: GET
  name: getgroupmembers
  path: /{realm}/groups/{groupId}/members
- description: Keycloak List identity providers
  method: GET
  name: getidentityproviders
  path: /{realm}/identity-provider/instances
- description: Keycloak Create an identity provider
  method: POST
  name: createidentityprovider
  path: /{realm}/identity-provider/instances
- description: Keycloak Get an identity provider
  method: GET
  name: getidentityprovider
  path: /{realm}/identity-provider/instances/{alias}
- description: Keycloak Update an identity provider
  method: PUT
  name: updateidentityprovider
  path: /{realm}/identity-provider/instances/{alias}
- description: Keycloak Delete an identity provider
  method: DELETE
  name: deleteidentityprovider
  path: /{realm}/identity-provider/instances/{alias}
personas: []
provider_name: Keycloak
provider_slug: keycloak
search_terms:
- keycloak delete a realm
- getidentityproviders
- keycloak
- api
- keycloak add a user to a group
- identity management
- keycloak get the client secret
- keycloak get a realm
- updaterole
- removeuserfromgroup
- keycloak create an identity provider
- getgroup
- deleteuser
- keycloak delete a client
- adduserrealmrolemappings
- getrole
- keycloak list identity providers
- authorization
- deleterealm
- keycloak update a realm
- getusergroups
- getidentityprovider
- keycloak list realm-level roles
- getroles
- deletegroup
- deleteclient
- createrole
- keycloak remove realm-level role mappings from a user
- keycloak create a new client
- keycloak update an identity provider
- resetuserpassword
- creategroup
- getgroups
- updaterealm
- getgroupmembers
- keycloak get a client
- authentication
- keycloak add realm-level role mappings to a user
- updateclient
- keycloak update a client
- keycloak update a realm-level role
- keycloak reset a user's password
- keycloak list groups
- keycloak get members of a group
- getclientsecret
- regenerateclientsecret
- keycloak remove a user from a group
- getclients
- createuser
- keycloak list all realms
- keycloak delete a user
- deleteidentityprovider
- keycloak delete a realm-level role
- security
- getclient
- keycloak get an identity provider
- updateidentityprovider
- createclient
- openid connect
- keycloak get groups for a user
- keycloak delete a group
- keycloak get a realm-level role by name
- deleteuserrealmrolemappings
- updateuser
- keycloak regenerate the client secret
- createchildgroup
- oauth
- keycloak list users
- keycloak get a user
- getuserrealmrolemappings
- keycloak list clients
- keycloak update a user
- createidentityprovider
- getusers
- addusertogroup
- keycloak update a group
- sso
- deleterole
- getrealms
- keycloak create a realm-level role
- keycloak get realm-level role mappings for a user
- getuser
- keycloak create a top-level group
- keycloak create a new user
- updategroup
- keycloak delete an identity provider
- keycloak create a child group
- getrealm
- keycloak get a group
slug: keycloak-capability
source_filename: keycloak-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Keycloak Admin REST API\n  description: The Keycloak Admin REST API provides endpoints for managing all aspects of a Keycloak deployment, including\n    realms, users, clients, roles, groups, and identity providers. All endpoints require authentication via a bearer token\n    obtained from the Keycloak token endpoint.\n  tags:\n  - Keycloak\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: keycloak\n    baseUri: https://localhost:8080/admin/realms\n    description: Keycloak Admin REST API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{KEYCLOAK_TOKEN}}'\n    resources:\n    - name: resource\n      path: /\n      operations:\n      - name: getrealms\n        method: GET\n        description: Keycloak List all realms\n        inputParameters:\n        - name: briefRepresentation\n          in: query\n          type: boolean\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: realm\n      path: /{realm}\n      operations:\n      - name: getrealm\n        method: GET\n        description: Keycloak Get a realm\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updaterealm\n        method: PUT\n        description: Keycloak Update a realm\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleterealm\n        method: DELETE\n        description: Keycloak Delete a realm\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: realm-users\n      path: /{realm}/users\n      operations:\n      - name: getusers\n        method: GET\n        description: Keycloak List users\n        inputParameters:\n\
  \        - name: search\n          in: query\n          type: string\n          description: Search string for username, first name, last name, or email\n        - name: username\n          in: query\n          type: string\n        - name: email\n          in: query\n          type: string\n        - name: firstName\n          in: query\n          type: string\n        - name: lastName\n          in: query\n          type: string\n        - name: enabled\n          in: query\n          type: boolean\n        - name: first\n          in: query\n          type: integer\n          description: Pagination offset\n        - name: max\n          in: query\n          type: integer\n          description: Maximum results size\n        - name: briefRepresentation\n          in: query\n          type: boolean\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createuser\n        method: POST\n        description:\
  \ Keycloak Create a new user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: realm-users-userid\n      path: /{realm}/users/{userId}\n      operations:\n      - name: getuser\n        method: GET\n        description: Keycloak Get a user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateuser\n        method: PUT\n        description: Keycloak Update a user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteuser\n        method: DELETE\n        description: Keycloak Delete a user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: realm-users-userid-role-mappings-realm\n      path: /{realm}/users/{userId}/role-mappings/realm\n\
  \      operations:\n      - name: getuserrealmrolemappings\n        method: GET\n        description: Keycloak Get realm-level role mappings for a user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: adduserrealmrolemappings\n        method: POST\n        description: Keycloak Add realm-level role mappings to a user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteuserrealmrolemappings\n        method: DELETE\n        description: Keycloak Remove realm-level role mappings from a user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: realm-users-userid-groups\n      path: /{realm}/users/{userId}/groups\n      operations:\n      - name: getusergroups\n        method: GET\n        description: Keycloak Get groups\
  \ for a user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: realm-users-userid-groups-groupid\n      path: /{realm}/users/{userId}/groups/{groupId}\n      operations:\n      - name: addusertogroup\n        method: PUT\n        description: Keycloak Add a user to a group\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: removeuserfromgroup\n        method: DELETE\n        description: Keycloak Remove a user from a group\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: realm-users-userid-reset-password\n      path: /{realm}/users/{userId}/reset-password\n      operations:\n      - name: resetuserpassword\n        method: PUT\n        description: Keycloak Reset a user's password\n        outputRawFormat: json\n     \
  \   outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: realm-clients\n      path: /{realm}/clients\n      operations:\n      - name: getclients\n        method: GET\n        description: Keycloak List clients\n        inputParameters:\n        - name: clientId\n          in: query\n          type: string\n          description: Filter by clientId\n        - name: search\n          in: query\n          type: boolean\n        - name: first\n          in: query\n          type: integer\n        - name: max\n          in: query\n          type: integer\n        - name: viewableOnly\n          in: query\n          type: boolean\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createclient\n        method: POST\n        description: Keycloak Create a new client\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n        \
  \  type: object\n          value: $.\n    - name: realm-clients-clientuuid\n      path: /{realm}/clients/{clientUuid}\n      operations:\n      - name: getclient\n        method: GET\n        description: Keycloak Get a client\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateclient\n        method: PUT\n        description: Keycloak Update a client\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteclient\n        method: DELETE\n        description: Keycloak Delete a client\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: realm-clients-clientuuid-client-secret\n      path: /{realm}/clients/{clientUuid}/client-secret\n      operations:\n      - name: getclientsecret\n        method: GET\n        description:\
  \ Keycloak Get the client secret\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: regenerateclientsecret\n        method: POST\n        description: Keycloak Regenerate the client secret\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: realm-roles\n      path: /{realm}/roles\n      operations:\n      - name: getroles\n        method: GET\n        description: Keycloak List realm-level roles\n        inputParameters:\n        - name: search\n          in: query\n          type: string\n        - name: first\n          in: query\n          type: integer\n        - name: max\n          in: query\n          type: integer\n        - name: briefRepresentation\n          in: query\n          type: boolean\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n      - name: createrole\n        method: POST\n        description: Keycloak Create a realm-level role\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: realm-roles-rolename\n      path: /{realm}/roles/{roleName}\n      operations:\n      - name: getrole\n        method: GET\n        description: Keycloak Get a realm-level role by name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updaterole\n        method: PUT\n        description: Keycloak Update a realm-level role\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleterole\n        method: DELETE\n        description: Keycloak Delete a realm-level role\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n    - name: realm-groups\n      path: /{realm}/groups\n      operations:\n      - name: getgroups\n        method: GET\n        description: Keycloak List groups\n        inputParameters:\n        - name: search\n          in: query\n          type: string\n        - name: first\n          in: query\n          type: integer\n        - name: max\n          in: query\n          type: integer\n        - name: briefRepresentation\n          in: query\n          type: boolean\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: creategroup\n        method: POST\n        description: Keycloak Create a top-level group\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: realm-groups-groupid\n      path: /{realm}/groups/{groupId}\n      operations:\n      - name: getgroup\n \
  \       method: GET\n        description: Keycloak Get a group\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updategroup\n        method: PUT\n        description: Keycloak Update a group\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletegroup\n        method: DELETE\n        description: Keycloak Delete a group\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: realm-groups-groupid-children\n      path: /{realm}/groups/{groupId}/children\n      operations:\n      - name: createchildgroup\n        method: POST\n        description: Keycloak Create a child group\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: realm-groups-groupid-members\n\
  \      path: /{realm}/groups/{groupId}/members\n      operations:\n      - name: getgroupmembers\n        method: GET\n        description: Keycloak Get members of a group\n        inputParameters:\n        - name: first\n          in: query\n          type: integer\n        - name: max\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: realm-identity-provider-instances\n      path: /{realm}/identity-provider/instances\n      operations:\n      - name: getidentityproviders\n        method: GET\n        description: Keycloak List identity providers\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createidentityprovider\n        method: POST\n        description: Keycloak Create an identity provider\n        outputRawFormat: json\n        outputParameters:\n     \
  \   - name: result\n          type: object\n          value: $.\n    - name: realm-identity-provider-instances-alias\n      path: /{realm}/identity-provider/instances/{alias}\n      operations:\n      - name: getidentityprovider\n        method: GET\n        description: Keycloak Get an identity provider\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateidentityprovider\n        method: PUT\n        description: Keycloak Update an identity provider\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteidentityprovider\n        method: DELETE\n        description: Keycloak Delete an identity provider\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: keycloak-rest\n\
  \    description: REST adapter for Keycloak Admin REST API.\n    resources:\n    - path: /\n      name: getrealms\n      operations:\n      - method: GET\n        name: getrealms\n        description: Keycloak List all realms\n        call: keycloak.getrealms\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /{realm}\n      name: getrealm\n      operations:\n      - method: GET\n        name: getrealm\n        description: Keycloak Get a realm\n        call: keycloak.getrealm\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /{realm}\n      name: updaterealm\n      operations:\n      - method: PUT\n        name: updaterealm\n        description: Keycloak Update a realm\n        call: keycloak.updaterealm\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /{realm}\n      name: deleterealm\n      operations:\n      - method: DELETE\n        name: deleterealm\n        description:\
  \ Keycloak Delete a realm\n        call: keycloak.deleterealm\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /{realm}/users\n      name: getusers\n      operations:\n      - method: GET\n        name: getusers\n        description: Keycloak List users\n        call: keycloak.getusers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /{realm}/users\n      name: createuser\n      operations:\n      - method: POST\n        name: createuser\n        description: Keycloak Create a new user\n        call: keycloak.createuser\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /{realm}/users/{userId}\n      name: getuser\n      operations:\n      - method: GET\n        name: getuser\n        description: Keycloak Get a user\n        call: keycloak.getuser\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /{realm}/users/{userId}\n      name: updateuser\n\
  \      operations:\n      - method: PUT\n        name: updateuser\n        description: Keycloak Update a user\n        call: keycloak.updateuser\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /{realm}/users/{userId}\n      name: deleteuser\n      operations:\n      - method: DELETE\n        name: deleteuser\n        description: Keycloak Delete a user\n        call: keycloak.deleteuser\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /{realm}/users/{userId}/role-mappings/realm\n      name: getuserrealmrolemappings\n      operations:\n      - method: GET\n        name: getuserrealmrolemappings\n        description: Keycloak Get realm-level role mappings for a user\n        call: keycloak.getuserrealmrolemappings\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /{realm}/users/{userId}/role-mappings/realm\n      name: adduserrealmrolemappings\n      operations:\n      - method:\
  \ POST\n        name: adduserrealmrolemappings\n        description: Keycloak Add realm-level role mappings to a user\n        call: keycloak.adduserrealmrolemappings\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /{realm}/users/{userId}/role-mappings/realm\n      name: deleteuserrealmrolemappings\n      operations:\n      - method: DELETE\n        name: deleteuserrealmrolemappings\n        description: Keycloak Remove realm-level role mappings from a user\n        call: keycloak.deleteuserrealmrolemappings\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /{realm}/users/{userId}/groups\n      name: getusergroups\n      operations:\n      - method: GET\n        name: getusergroups\n        description: Keycloak Get groups for a user\n        call: keycloak.getusergroups\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /{realm}/users/{userId}/groups/{groupId}\n      name: addusertogroup\n\
  \      operations:\n      - method: PUT\n        name: addusertogroup\n        description: Keycloak Add a user to a group\n        call: keycloak.addusertogroup\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /{realm}/users/{userId}/groups/{groupId}\n      name: removeuserfromgroup\n      operations:\n      - method: DELETE\n        name: removeuserfromgroup\n        description: Keycloak Remove a user from a group\n        call: keycloak.removeuserfromgroup\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /{realm}/users/{userId}/reset-password\n      name: resetuserpassword\n      operations:\n      - method: PUT\n        name: resetuserpassword\n        description: Keycloak Reset a user's password\n        call: keycloak.resetuserpassword\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /{realm}/clients\n      name: getclients\n      operations:\n      - method: GET\n\
  \        name: getclients\n        description: Keycloak List clients\n        call: keycloak.getclients\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /{realm}/clients\n      name: createclient\n      operations:\n      - method: POST\n        name: createclient\n        description: Keycloak Create a new client\n        call: keycloak.createclient\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /{realm}/clients/{clientUuid}\n      name: getclient\n      operations:\n      - method: GET\n        name: getclient\n        description: Keycloak Get a client\n        call: keycloak.getclient\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /{realm}/clients/{clientUuid}\n      name: updateclient\n      operations:\n      - method: PUT\n        name: updateclient\n        description: Keycloak Update a client\n        call: keycloak.updateclient\n        outputParameters:\n \
  \       - type: object\n          mapping: $.\n    - path: /{realm}/clients/{clientUuid}\n      name: deleteclient\n      operations:\n      - method: DELETE\n        name: deleteclient\n        description: Keycloak Delete a client\n        call: keycloak.deleteclient\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /{realm}/clients/{clientUuid}/client-secret\n      name: getclientsecret\n      operations:\n      - method: GET\n        name: getclientsecret\n        description: Keycloak Get the client secret\n        call: keycloak.getclientsecret\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /{realm}/clients/{clientUuid}/client-secret\n      name: regenerateclientsecret\n      operations:\n      - method: POST\n        name: regenerateclientsecret\n        description: Keycloak Regenerate the client secret\n        call: keycloak.regenerateclientsecret\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n    - path: /{realm}/roles\n      name: getroles\n      operations:\n      - method: GET\n        name: getroles\n        description: Keycloak List realm-level roles\n        call: keycloak.getroles\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /{realm}/roles\n      name: createrole\n      operations:\n      - method: POST\n        name: createrole\n        description: Keycloak Create a realm-level role\n        call: keycloak.createrole\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /{realm}/roles/{roleName}\n      name: getrole\n      operations:\n      - method: GET\n        name: getrole\n        description: Keycloak Get a realm-level role by name\n        call: keycloak.getrole\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /{realm}/roles/{roleName}\n      name: updaterole\n      operations:\n      - method: PUT\n        name: updaterole\n\
  \        description: Keycloak Update a realm-level role\n        call: keycloak.updaterole\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /{realm}/roles/{roleName}\n      name: deleterole\n      operations:\n      - method: DELETE\n        name: deleterole\n        description: Keycloak Delete a realm-level role\n        call: keycloak.deleterole\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /{realm}/groups\n      name: getgroups\n      operations:\n      - method: GET\n        name: getgroups\n        description: Keycloak List groups\n        call: keycloak.getgroups\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /{realm}/groups\n      name: creategroup\n      operations:\n      - method: POST\n        name: creategroup\n        description: Keycloak Create a top-level group\n        call: keycloak.creategroup\n        outputParameters:\n        - type: object\n \
  \         mapping: $.\n    - path: /{realm}/groups/{groupId}\n      name: getgroup\n      operations:\n      - method: GET\n        name: getgroup\n        description: Keycloak Get a group\n        call: keycloak.getgroup\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /{realm}/groups/{groupId}\n      name: updategroup\n      operations:\n      - method: PUT\n        name: updategroup\n        description: Keycloak Update a group\n        call: keycloak.updategroup\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /{realm}/groups/{groupId}\n      name: deletegroup\n      operations:\n      - method: DELETE\n        name: deletegroup\n        description: Keycloak Delete a group\n        call: keycloak.deletegroup\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /{realm}/groups/{groupId}/children\n      name: createchildgroup\n      operations:\n      - method: POST\n     \
  \   name: createchildgroup\n        description: Keycloak Create a child group\n        call: keycloak.createchildgroup\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /{realm}/groups/{groupId}/members\n      name: getgroupmembers\n      operations:\n      - method: GET\n        name: getgroupmembers\n        description: Keycloak Get members of a group\n        call: keycloak.getgroupmembers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /{realm}/identity-provider/instances\n      name: getidentityproviders\n      operations:\n      - method: GET\n        name: getidentityproviders\n        description: Keycloak List identity providers\n        call: keycloak.getidentityproviders\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /{realm}/identity-provider/instances\n      name: createidentityprovider\n      operations:\n      - method: POST\n        name: createidentityprovider\n\
  \        description: Keycloak Create an identity provider\n        call: keycloak.createidentityprovider\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /{realm}/identity-provider/instances/{alias}\n      name: getidentityprovider\n      operations:\n      - method: GET\n        name: getidentityprovider\n        description: Keycloak Get an identity provider\n        call: keycloak.getidentityprovider\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /{realm}/identity-provider/instances/{alias}\n      name: updateidentityprovider\n      operations:\n      - method: PUT\n        name: updateidentityprovider\n        description: Keycloak Update an identity provider\n        call: keycloak.updateidentityprovider\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /{realm}/identity-provider/instances/{alias}\n      name: deleteidentityprovider\n      operations:\n      - method:\
  \ DELETE\n        name: deleteidentityprovider\n        description: Keycloak Delete an identity provider\n        call: keycloak.deleteidentityprovider\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: keycloak-mcp\n    transport: http\n    description: MCP adapter for Keycloak Admin REST API for AI agent use.\n    tools:\n    - name: getrealms\n      description: Keycloak List all realms\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: keycloak.getrealms\n      with:\n        briefRepresentation: tools.briefRepresentation\n      inputParameters:\n      - name: briefRepresentation\n        type: boolean\n        description: briefRepresentation\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getrealm\n      description: Keycloak Get a realm\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n\
  \      call: keycloak.getrealm\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updaterealm\n      description: Keycloak Update a realm\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: keycloak.updaterealm\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleterealm\n      description: Keycloak Delete a realm\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: keycloak.deleterealm\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getusers\n      description: Keycloak List users\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: keycloak.getusers\n      with:\n        search: tools.search\n        username: tools.username\n        email: tools.email\n        firstName: tools.firstName\n        lastName: tools.lastName\n        enabled:\
  \ tools.enabled\n        first: tools.first\n        max: tools.max\n        briefRepresentation: tools.briefRepresentation\n      inputParameters:\n      - name: search\n        type: string\n        description: Search string for username, first name, last name, or email\n      - name: username\n        type: string\n        description: username\n      - name: email\n        type: string\n        description: email\n      - name: firstName\n        type: string\n        description: firstName\n      - name: lastName\n        type: string\n        description: lastName\n      - name: enabled\n        type: boolean\n        description: enabled\n      - name: first\n        type: integer\n        description: Pagination offset\n      - name: max\n        type: integer\n        description: Maximum results size\n      - name: briefRepresentation\n        type: boolean\n        description: briefRepresentation\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name:\
  \ createuser\n      description: Keycloak Create a new user\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: keycloak.createuser\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getuser\n      description: Keycloak Get a user\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: keycloak.getuser\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateuser\n      description: Keycloak Update a user\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: keycloak.updateuser\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteuser\n      description: Keycloak Delete a user\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: keycloak.deleteuser\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n    - name: getuserrealmrolemappings\n      description: Keycloak Get realm-level role mappings for a user\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: keycloak.getuserrealmrolemappings\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: adduserrealmrolemappings\n      description: Keycloak Add realm-level role mappings to a user\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: keycloak.adduserrealmrolemappings\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteuserrealmrolemappings\n      description: Keycloak Remove realm-level role mappings from a user\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: keycloak.deleteuserrealmrolemappings\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getusergroups\n\
  \      description: Keycloak Get groups for a user\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: keycloak.getusergroups\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: addusertogroup\n      description: Keycloak Add a user to a group\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: keycloak.addusertogroup\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: removeuserfromgroup\n      description: Keycloak Remove a user from a group\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: keycloak.removeuserfromgroup\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: resetuserpassword\n      description: Keycloak Reset a user's password\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call:\
  \ keycloak.resetuserpassword\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getclients\n      description: Keycloak List clients\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: keycloak.getclients\n      with:\n        clientId: tools.clientId\n        search: tools.search\n        first: tools.first\n        max: tools.max\n        viewableOnly: tools.viewableOnly\n      inputParameters:\n      - name: clientId\n        type: string\n        description: Filter by clientId\n      - name: search\n        type: boolean\n        description: search\n      - name: first\n        type: integer\n        description: first\n      - name: max\n        type: integer\n        description: max\n      - name: viewableOnly\n        type: boolean\n        description: viewableOnly\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createclient\n      description: Keycloak Create\
  \ a new client\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: keycloak.createclient\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getclient\n      description: Keycloak Get a client\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: keycloak.getclient\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateclient\n      description: Keycloak Update a client\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: keycloak.updateclient\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteclient\n      description: Keycloak Delete a client\n      hints:\n        readOnly: false\n        destructive: true\n\n# --- truncated at 32 KB (38 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/keycloak/refs/heads/main/capabilities/keycloak-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/keycloak/refs/heads/main/capabilities/keycloak-capability.yaml
tags:
- Keycloak
- API
tools:
- description: Keycloak List all realms
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getrealms
- description: Keycloak Get a realm
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getrealm
- description: Keycloak Update a realm
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updaterealm
- description: Keycloak Delete a realm
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleterealm
- description: Keycloak List users
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getusers
- description: Keycloak Create a new user
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createuser
- description: Keycloak Get a user
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getuser
- description: Keycloak Update a user
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateuser
- description: Keycloak Delete a user
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteuser
- description: Keycloak Get realm-level role mappings for a user
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getuserrealmrolemappings
- description: Keycloak Add realm-level role mappings to a user
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: adduserrealmrolemappings
- description: Keycloak Remove realm-level role mappings from a user
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteuserrealmrolemappings
- description: Keycloak Get groups for a user
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getusergroups
- description: Keycloak Add a user to a group
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: addusertogroup
- description: Keycloak Remove a user from a group
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: removeuserfromgroup
- description: Keycloak Reset a user's password
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: resetuserpassword
- description: Keycloak List clients
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getclients
- description: Keycloak Create a new client
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createclient
- description: Keycloak Get a client
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getclient
- description: Keycloak Update a client
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateclient
- description: Keycloak Delete a client
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteclient
- description: Keycloak Get the client secret
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getclientsecret
- description: Keycloak Regenerate the client secret
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: regenerateclientsecret
- description: Keycloak List realm-level roles
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getroles
- description: Keycloak Create a realm-level role
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createrole
- description: Keycloak Get a realm-level role by name
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getrole
- description: Keycloak Update a realm-level role
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updaterole
- description: Keycloak Delete a realm-level role
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleterole
- description: Keycloak List groups
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getgroups
- description: Keycloak Create a top-level group
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: creategroup
- description: Keycloak Get a group
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getgroup
- description: Keycloak Update a group
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updategroup
- description: Keycloak Delete a group
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletegroup
- description: Keycloak Create a child group
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createchildgroup
- description: Keycloak Get members of a group
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getgroupmembers
- description: Keycloak List identity providers
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getidentityproviders
- description: Keycloak Create an identity provider
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createidentityprovider
- description: Keycloak Get an identity provider
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getidentityprovider
- description: Keycloak Update an identity provider
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateidentityprovider
- description: Keycloak Delete an identity provider
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteidentityprovider
---
