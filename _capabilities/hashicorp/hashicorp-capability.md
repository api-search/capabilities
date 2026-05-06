---
categories: []
consumed_apis: []
description: HTTP API that gives you full access to Vault. All API routes are prefixed with `/v1/`.
layout: capability
name: HashiCorp Vault API
operations:
- description: HashiCorp List token accessors, which can then be be used to iterate and discover their properties or revoke them. Because this can be used to cause a denial of service, this endpoint requires 'sudo' capability in addition to 'list'.
  method: GET
  name: getauthtokenaccessors
  path: /auth/token/accessors/
- description: HashiCorp The token create path is used to create new tokens.
  method: POST
  name: postauthtokencreate
  path: /auth/token/create
- description: HashiCorp The token create path is used to create new orphan tokens.
  method: POST
  name: postauthtokencreateorphan
  path: /auth/token/create-orphan
- description: HashiCorp This token create path is used to create new tokens adhering to the given role.
  method: POST
  name: postauthtokencreaterole-name
  path: /auth/token/create/{role_name}
- description: HashiCorp This endpoint will lookup a token and its properties.
  method: GET
  name: getauthtokenlookup
  path: /auth/token/lookup
- description: HashiCorp This endpoint will lookup a token and its properties.
  method: POST
  name: postauthtokenlookup
  path: /auth/token/lookup
- description: HashiCorp This endpoint will lookup a token associated with the given accessor and its properties. Response will not contain the token ID.
  method: POST
  name: postauthtokenlookupaccessor
  path: /auth/token/lookup-accessor
- description: HashiCorp This endpoint will lookup a token and its properties.
  method: GET
  name: getauthtokenlookupself
  path: /auth/token/lookup-self
- description: HashiCorp This endpoint will lookup a token and its properties.
  method: POST
  name: postauthtokenlookupself
  path: /auth/token/lookup-self
- description: HashiCorp This endpoint will renew the given token and prevent expiration.
  method: POST
  name: postauthtokenrenew
  path: /auth/token/renew
- description: HashiCorp This endpoint will renew a token associated with the given accessor and its properties. Response will not contain the token ID.
  method: POST
  name: postauthtokenrenewaccessor
  path: /auth/token/renew-accessor
- description: HashiCorp This endpoint will renew the token used to call it and prevent expiration.
  method: POST
  name: postauthtokenrenewself
  path: /auth/token/renew-self
- description: HashiCorp This endpoint will delete the given token and all of its child tokens.
  method: POST
  name: postauthtokenrevoke
  path: /auth/token/revoke
- description: HashiCorp This endpoint will delete the token associated with the accessor and all of its child tokens.
  method: POST
  name: postauthtokenrevokeaccessor
  path: /auth/token/revoke-accessor
- description: HashiCorp This endpoint will delete the token and orphan its child tokens.
  method: POST
  name: postauthtokenrevokeorphan
  path: /auth/token/revoke-orphan
- description: HashiCorp This endpoint will delete the token used to call it and all of its child tokens.
  method: POST
  name: postauthtokenrevokeself
  path: /auth/token/revoke-self
- description: HashiCorp This endpoint lists configured roles.
  method: GET
  name: getauthtokenroles
  path: /auth/token/roles
- description: GET /auth/token/roles/{role_name}
  method: GET
  name: getauthtokenrolesrole-name
  path: /auth/token/roles/{role_name}
- description: POST /auth/token/roles/{role_name}
  method: POST
  name: postauthtokenrolesrole-name
  path: /auth/token/roles/{role_name}
- description: DELETE /auth/token/roles/{role_name}
  method: DELETE
  name: deleteauthtokenrolesrole-name
  path: /auth/token/roles/{role_name}
- description: HashiCorp This endpoint performs cleanup tasks that can be run if certain error conditions have occurred.
  method: POST
  name: postauthtokentidy
  path: /auth/token/tidy
- description: HashiCorp Retrieve the secret at the specified location.
  method: GET
  name: getcubbyholepath
  path: /cubbyhole/{path}
- description: HashiCorp Store a secret at the specified location.
  method: POST
  name: postcubbyholepath
  path: /cubbyhole/{path}
- description: HashiCorp Deletes the secret at the specified location.
  method: DELETE
  name: deletecubbyholepath
  path: /cubbyhole/{path}
- description: HashiCorp Create a new alias.
  method: POST
  name: postidentityalias
  path: /identity/alias
- description: HashiCorp List all the alias IDs.
  method: GET
  name: getidentityaliasid
  path: /identity/alias/id
- description: HashiCorp Update, read or delete an alias ID.
  method: GET
  name: getidentityaliasidid
  path: /identity/alias/id/{id}
- description: HashiCorp Update, read or delete an alias ID.
  method: POST
  name: postidentityaliasidid
  path: /identity/alias/id/{id}
- description: HashiCorp Update, read or delete an alias ID.
  method: DELETE
  name: deleteidentityaliasidid
  path: /identity/alias/id/{id}
- description: HashiCorp Create a new entity
  method: POST
  name: postidentityentity
  path: /identity/entity
- description: HashiCorp Create a new alias.
  method: POST
  name: postidentityentityalias
  path: /identity/entity-alias
- description: HashiCorp List all the alias IDs.
  method: GET
  name: getidentityentityaliasid
  path: /identity/entity-alias/id
- description: HashiCorp Update, read or delete an alias ID.
  method: GET
  name: getidentityentityaliasidid
  path: /identity/entity-alias/id/{id}
- description: HashiCorp Update, read or delete an alias ID.
  method: POST
  name: postidentityentityaliasidid
  path: /identity/entity-alias/id/{id}
- description: HashiCorp Update, read or delete an alias ID.
  method: DELETE
  name: deleteidentityentityaliasidid
  path: /identity/entity-alias/id/{id}
- description: HashiCorp Delete all of the entities provided
  method: POST
  name: postidentityentitybatchdelete
  path: /identity/entity/batch-delete
- description: HashiCorp List all the entity IDs
  method: GET
  name: getidentityentityid
  path: /identity/entity/id
- description: HashiCorp Update, read or delete an entity using entity ID
  method: GET
  name: getidentityentityidid
  path: /identity/entity/id/{id}
- description: HashiCorp Update, read or delete an entity using entity ID
  method: POST
  name: postidentityentityidid
  path: /identity/entity/id/{id}
- description: HashiCorp Update, read or delete an entity using entity ID
  method: DELETE
  name: deleteidentityentityidid
  path: /identity/entity/id/{id}
- description: HashiCorp Merge two or more entities together
  method: POST
  name: postidentityentitymerge
  path: /identity/entity/merge
- description: HashiCorp List all the entity names
  method: GET
  name: getidentityentityname
  path: /identity/entity/name
- description: HashiCorp Update, read or delete an entity using entity name
  method: GET
  name: getidentityentitynamename
  path: /identity/entity/name/{name}
- description: HashiCorp Update, read or delete an entity using entity name
  method: POST
  name: postidentityentitynamename
  path: /identity/entity/name/{name}
- description: HashiCorp Update, read or delete an entity using entity name
  method: DELETE
  name: deleteidentityentitynamename
  path: /identity/entity/name/{name}
- description: HashiCorp Create a new group.
  method: POST
  name: postidentitygroup
  path: /identity/group
- description: HashiCorp Creates a new group alias, or updates an existing one.
  method: POST
  name: postidentitygroupalias
  path: /identity/group-alias
- description: HashiCorp List all the group alias IDs.
  method: GET
  name: getidentitygroupaliasid
  path: /identity/group-alias/id
- description: GET /identity/group-alias/id/{id}
  method: GET
  name: getidentitygroupaliasidid
  path: /identity/group-alias/id/{id}
- description: POST /identity/group-alias/id/{id}
  method: POST
  name: postidentitygroupaliasidid
  path: /identity/group-alias/id/{id}
- description: DELETE /identity/group-alias/id/{id}
  method: DELETE
  name: deleteidentitygroupaliasidid
  path: /identity/group-alias/id/{id}
- description: HashiCorp List all the group IDs.
  method: GET
  name: getidentitygroupid
  path: /identity/group/id
- description: HashiCorp Update or delete an existing group using its ID.
  method: GET
  name: getidentitygroupidid
  path: /identity/group/id/{id}
- description: HashiCorp Update or delete an existing group using its ID.
  method: POST
  name: postidentitygroupidid
  path: /identity/group/id/{id}
- description: HashiCorp Update or delete an existing group using its ID.
  method: DELETE
  name: deleteidentitygroupidid
  path: /identity/group/id/{id}
- description: GET /identity/group/name
  method: GET
  name: getidentitygroupname
  path: /identity/group/name
- description: GET /identity/group/name/{name}
  method: GET
  name: getidentitygroupnamename
  path: /identity/group/name/{name}
- description: POST /identity/group/name/{name}
  method: POST
  name: postidentitygroupnamename
  path: /identity/group/name/{name}
- description: DELETE /identity/group/name/{name}
  method: DELETE
  name: deleteidentitygroupnamename
  path: /identity/group/name/{name}
- description: HashiCorp Query entities based on various properties.
  method: POST
  name: postidentitylookupentity
  path: /identity/lookup/entity
personas: []
provider_name: HashiCorp
provider_slug: hashicorp
search_terms:
- postauthtokenlookupaccessor
- getauthtokenlookupself
- hashicorp this token create path is used to create new tokens adhering to the given role.
- postauthtokenrevoke
- postauthtokencreaterole name
- hashicorp this endpoint will delete the token associated with the accessor and all of its child tokens.
- delete /auth/token/roles/{role_name}
- postidentitygroup
- postauthtokenlookupself
- hashicorp the token create path is used to create new orphan tokens.
- postauthtokenrenew
- cloud
- delete /identity/group/name/{name}
- hashicorp this endpoint will delete the token and orphan its child tokens.
- getidentityentityaliasidid
- getidentitygroupname
- deletecubbyholepath
- postauthtokenrevokeself
- api
- postauthtokenlookup
- hashicorp merge two or more entities together
- postauthtokenrenewself
- postcubbyholepath
- post /auth/token/roles/{role_name}
- hashicorp update, read or delete an entity using entity name
- hashicorp list token accessors, which can then be be used to iterate and discover their properties or revoke them. because this can be used to cause a denial of service, this endpoint requires 'sudo' capability in addition to 'list'.
- postauthtokenrevokeorphan
- hashicorp create a new group.
- deleteidentitygroupnamename
- postidentityentitynamename
- get /identity/group/name/{name}
- getidentitygroupaliasidid
- deleteauthtokenrolesrole name
- hashicorp delete all of the entities provided
- infrastructure
- hashicorp list all the group ids.
- getidentitygroupid
- postidentityentitybatchdelete
- getidentitygroupnamename
- postauthtokenrenewaccessor
- hashicorp this endpoint will renew the given token and prevent expiration.
- postidentityentity
- deleteidentitygroupidid
- postauthtokencreateorphan
- postidentitylookupentity
- postidentitygroupnamename
- hashicorp this endpoint will renew the token used to call it and prevent expiration.
- deleteidentityaliasidid
- getidentitygroupaliasid
- deleteidentitygroupaliasidid
- hashicorp create a new entity
- hashicorp this endpoint performs cleanup tasks that can be run if certain error conditions have occurred.
- hashicorp deletes the secret at the specified location.
- postidentitygroupaliasidid
- postidentityentityalias
- postidentityalias
- deleteidentityentityaliasidid
- getauthtokenaccessors
- getidentityentitynamename
- post /identity/group/name/{name}
- hashicorp update, read or delete an entity using entity id
- hashicorp update or delete an existing group using its id.
- devops
- hashicorp this endpoint will delete the given token and all of its child tokens.
- hashicorp
- hashicorp this endpoint lists configured roles.
- getidentityaliasid
- hashicorp this endpoint will renew a token associated with the given accessor and its properties. response will not contain the token id.
- getauthtokenrolesrole name
- post /identity/group-alias/id/{id}
- getidentityentityname
- hashicorp this endpoint will delete the token used to call it and all of its child tokens.
- hashicorp creates a new group alias, or updates an existing one.
- getidentitygroupidid
- deleteidentityentitynamename
- postidentityentityaliasidid
- hashicorp store a secret at the specified location.
- get /identity/group-alias/id/{id}
- hashicorp retrieve the secret at the specified location.
- postidentityentityidid
- delete /identity/group-alias/id/{id}
- get /identity/group/name
- getidentityentityaliasid
- hashicorp query entities based on various properties.
- hashicorp update, read or delete an alias id.
- postauthtokenrolesrole name
- getcubbyholepath
- hashicorp list all the alias ids.
- postauthtokencreate
- getidentityentityid
- deleteidentityentityidid
- hashicorp list all the entity names
- postidentitygroupalias
- postauthtokentidy
- hashicorp the token create path is used to create new tokens.
- hashicorp list all the entity ids
- postidentityentitymerge
- getauthtokenlookup
- getidentityentityidid
- get /auth/token/roles/{role_name}
- hashicorp this endpoint will lookup a token and its properties.
- hashicorp this endpoint will lookup a token associated with the given accessor and its properties. response will not contain the token id.
- getidentityaliasidid
- postauthtokenrevokeaccessor
- hashicorp create a new alias.
- platform
- getauthtokenroles
- postidentityaliasidid
- hashicorp list all the group alias ids.
- postidentitygroupidid
slug: hashicorp-capability
source_filename: hashicorp-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: HashiCorp Vault API\n  description: HTTP API that gives you full access to Vault. All API routes are prefixed with `/v1/`.\n  tags:\n  - Hashicorp\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: hashicorp\n    baseUri: https://api.example.com\n    description: HashiCorp Vault API HTTP API.\n    resources:\n    - name: auth-token-accessors\n      path: /auth/token/accessors/\n      operations:\n      - name: getauthtokenaccessors\n        method: GET\n        description: HashiCorp List token accessors, which can then be be used to iterate and discover their properties or\n          revoke them. Because this can be used to cause a denial of service, this endpoint requires 'sudo' capability in\n          addition to 'list'.\n        inputParameters:\n        - name: list\n          in: query\n          type: string\n          description: Return a list if `true`\n    \
  \    outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: auth-token-create\n      path: /auth/token/create\n      operations:\n      - name: postauthtokencreate\n        method: POST\n        description: HashiCorp The token create path is used to create new tokens.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: auth-token-create-orphan\n      path: /auth/token/create-orphan\n      operations:\n      - name: postauthtokencreateorphan\n        method: POST\n        description: HashiCorp The token create path is used to create new orphan tokens.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: auth-token-create-role-name\n      path: /auth/token/create/{role_name}\n      operations:\n      - name: postauthtokencreaterole-name\n\
  \        method: POST\n        description: HashiCorp This token create path is used to create new tokens adhering to the given role.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: auth-token-lookup\n      path: /auth/token/lookup\n      operations:\n      - name: getauthtokenlookup\n        method: GET\n        description: HashiCorp This endpoint will lookup a token and its properties.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: postauthtokenlookup\n        method: POST\n        description: HashiCorp This endpoint will lookup a token and its properties.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: auth-token-lookup-accessor\n      path: /auth/token/lookup-accessor\n      operations:\n      - name: postauthtokenlookupaccessor\n\
  \        method: POST\n        description: HashiCorp This endpoint will lookup a token associated with the given accessor and its properties. Response\n          will not contain the token ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: auth-token-lookup-self\n      path: /auth/token/lookup-self\n      operations:\n      - name: getauthtokenlookupself\n        method: GET\n        description: HashiCorp This endpoint will lookup a token and its properties.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: postauthtokenlookupself\n        method: POST\n        description: HashiCorp This endpoint will lookup a token and its properties.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: auth-token-renew\n      path:\
  \ /auth/token/renew\n      operations:\n      - name: postauthtokenrenew\n        method: POST\n        description: HashiCorp This endpoint will renew the given token and prevent expiration.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: auth-token-renew-accessor\n      path: /auth/token/renew-accessor\n      operations:\n      - name: postauthtokenrenewaccessor\n        method: POST\n        description: HashiCorp This endpoint will renew a token associated with the given accessor and its properties. Response\n          will not contain the token ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: auth-token-renew-self\n      path: /auth/token/renew-self\n      operations:\n      - name: postauthtokenrenewself\n        method: POST\n        description: HashiCorp This endpoint will renew the token used\
  \ to call it and prevent expiration.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: auth-token-revoke\n      path: /auth/token/revoke\n      operations:\n      - name: postauthtokenrevoke\n        method: POST\n        description: HashiCorp This endpoint will delete the given token and all of its child tokens.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: auth-token-revoke-accessor\n      path: /auth/token/revoke-accessor\n      operations:\n      - name: postauthtokenrevokeaccessor\n        method: POST\n        description: HashiCorp This endpoint will delete the token associated with the accessor and all of its child tokens.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: auth-token-revoke-orphan\n      path:\
  \ /auth/token/revoke-orphan\n      operations:\n      - name: postauthtokenrevokeorphan\n        method: POST\n        description: HashiCorp This endpoint will delete the token and orphan its child tokens.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: auth-token-revoke-self\n      path: /auth/token/revoke-self\n      operations:\n      - name: postauthtokenrevokeself\n        method: POST\n        description: HashiCorp This endpoint will delete the token used to call it and all of its child tokens.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: auth-token-roles\n      path: /auth/token/roles\n      operations:\n      - name: getauthtokenroles\n        method: GET\n        description: HashiCorp This endpoint lists configured roles.\n        inputParameters:\n        - name: list\n          in: query\n\
  \          type: string\n          description: Return a list if `true`\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: auth-token-roles-role-name\n      path: /auth/token/roles/{role_name}\n      operations:\n      - name: getauthtokenrolesrole-name\n        method: GET\n        description: GET /auth/token/roles/{role_name}\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: postauthtokenrolesrole-name\n        method: POST\n        description: POST /auth/token/roles/{role_name}\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteauthtokenrolesrole-name\n        method: DELETE\n        description: DELETE /auth/token/roles/{role_name}\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n    - name: auth-token-tidy\n      path: /auth/token/tidy\n      operations:\n      - name: postauthtokentidy\n        method: POST\n        description: HashiCorp This endpoint performs cleanup tasks that can be run if certain error conditions have occurred.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cubbyhole-path\n      path: /cubbyhole/{path}\n      operations:\n      - name: getcubbyholepath\n        method: GET\n        description: HashiCorp Retrieve the secret at the specified location.\n        inputParameters:\n        - name: list\n          in: query\n          type: string\n          description: Return a list if `true`\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: postcubbyholepath\n        method: POST\n        description: HashiCorp Store\
  \ a secret at the specified location.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletecubbyholepath\n        method: DELETE\n        description: HashiCorp Deletes the secret at the specified location.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: identity-alias\n      path: /identity/alias\n      operations:\n      - name: postidentityalias\n        method: POST\n        description: HashiCorp Create a new alias.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: identity-alias-id\n      path: /identity/alias/id\n      operations:\n      - name: getidentityaliasid\n        method: GET\n        description: HashiCorp List all the alias IDs.\n        inputParameters:\n        - name: list\n          in: query\n\
  \          type: string\n          description: Return a list if `true`\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: identity-alias-id-id\n      path: /identity/alias/id/{id}\n      operations:\n      - name: getidentityaliasidid\n        method: GET\n        description: HashiCorp Update, read or delete an alias ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: postidentityaliasidid\n        method: POST\n        description: HashiCorp Update, read or delete an alias ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteidentityaliasidid\n        method: DELETE\n        description: HashiCorp Update, read or delete an alias ID.\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n    - name: identity-entity\n      path: /identity/entity\n      operations:\n      - name: postidentityentity\n        method: POST\n        description: HashiCorp Create a new entity\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: identity-entity-alias\n      path: /identity/entity-alias\n      operations:\n      - name: postidentityentityalias\n        method: POST\n        description: HashiCorp Create a new alias.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: identity-entity-alias-id\n      path: /identity/entity-alias/id\n      operations:\n      - name: getidentityentityaliasid\n        method: GET\n        description: HashiCorp List all the alias IDs.\n        inputParameters:\n        - name: list\n          in: query\n          type: string\n\
  \          description: Return a list if `true`\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: identity-entity-alias-id-id\n      path: /identity/entity-alias/id/{id}\n      operations:\n      - name: getidentityentityaliasidid\n        method: GET\n        description: HashiCorp Update, read or delete an alias ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: postidentityentityaliasidid\n        method: POST\n        description: HashiCorp Update, read or delete an alias ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteidentityentityaliasidid\n        method: DELETE\n        description: HashiCorp Update, read or delete an alias ID.\n        outputRawFormat: json\n        outputParameters:\n      \
  \  - name: result\n          type: object\n          value: $.\n    - name: identity-entity-batch-delete\n      path: /identity/entity/batch-delete\n      operations:\n      - name: postidentityentitybatchdelete\n        method: POST\n        description: HashiCorp Delete all of the entities provided\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: identity-entity-id\n      path: /identity/entity/id\n      operations:\n      - name: getidentityentityid\n        method: GET\n        description: HashiCorp List all the entity IDs\n        inputParameters:\n        - name: list\n          in: query\n          type: string\n          description: Return a list if `true`\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: identity-entity-id-id\n      path: /identity/entity/id/{id}\n      operations:\n      - name:\
  \ getidentityentityidid\n        method: GET\n        description: HashiCorp Update, read or delete an entity using entity ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: postidentityentityidid\n        method: POST\n        description: HashiCorp Update, read or delete an entity using entity ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteidentityentityidid\n        method: DELETE\n        description: HashiCorp Update, read or delete an entity using entity ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: identity-entity-merge\n      path: /identity/entity/merge\n      operations:\n      - name: postidentityentitymerge\n        method: POST\n        description: HashiCorp Merge two or more entities\
  \ together\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: identity-entity-name\n      path: /identity/entity/name\n      operations:\n      - name: getidentityentityname\n        method: GET\n        description: HashiCorp List all the entity names\n        inputParameters:\n        - name: list\n          in: query\n          type: string\n          description: Return a list if `true`\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: identity-entity-name-name\n      path: /identity/entity/name/{name}\n      operations:\n      - name: getidentityentitynamename\n        method: GET\n        description: HashiCorp Update, read or delete an entity using entity name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: postidentityentitynamename\n\
  \        method: POST\n        description: HashiCorp Update, read or delete an entity using entity name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteidentityentitynamename\n        method: DELETE\n        description: HashiCorp Update, read or delete an entity using entity name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: identity-group\n      path: /identity/group\n      operations:\n      - name: postidentitygroup\n        method: POST\n        description: HashiCorp Create a new group.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: identity-group-alias\n      path: /identity/group-alias\n      operations:\n      - name: postidentitygroupalias\n        method: POST\n        description: HashiCorp\
  \ Creates a new group alias, or updates an existing one.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: identity-group-alias-id\n      path: /identity/group-alias/id\n      operations:\n      - name: getidentitygroupaliasid\n        method: GET\n        description: HashiCorp List all the group alias IDs.\n        inputParameters:\n        - name: list\n          in: query\n          type: string\n          description: Return a list if `true`\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: identity-group-alias-id-id\n      path: /identity/group-alias/id/{id}\n      operations:\n      - name: getidentitygroupaliasidid\n        method: GET\n        description: GET /identity/group-alias/id/{id}\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n    \
  \      value: $.\n      - name: postidentitygroupaliasidid\n        method: POST\n        description: POST /identity/group-alias/id/{id}\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteidentitygroupaliasidid\n        method: DELETE\n        description: DELETE /identity/group-alias/id/{id}\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: identity-group-id\n      path: /identity/group/id\n      operations:\n      - name: getidentitygroupid\n        method: GET\n        description: HashiCorp List all the group IDs.\n        inputParameters:\n        - name: list\n          in: query\n          type: string\n          description: Return a list if `true`\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: identity-group-id-id\n\
  \      path: /identity/group/id/{id}\n      operations:\n      - name: getidentitygroupidid\n        method: GET\n        description: HashiCorp Update or delete an existing group using its ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: postidentitygroupidid\n        method: POST\n        description: HashiCorp Update or delete an existing group using its ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteidentitygroupidid\n        method: DELETE\n        description: HashiCorp Update or delete an existing group using its ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: identity-group-name\n      path: /identity/group/name\n      operations:\n      - name: getidentitygroupname\n        method: GET\n\
  \        description: GET /identity/group/name\n        inputParameters:\n        - name: list\n          in: query\n          type: string\n          description: Return a list if `true`\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: identity-group-name-name\n      path: /identity/group/name/{name}\n      operations:\n      - name: getidentitygroupnamename\n        method: GET\n        description: GET /identity/group/name/{name}\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: postidentitygroupnamename\n        method: POST\n        description: POST /identity/group/name/{name}\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteidentitygroupnamename\n        method: DELETE\n        description: DELETE /identity/group/name/{name}\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: identity-lookup-entity\n      path: /identity/lookup/entity\n      operations:\n      - name: postidentitylookupentity\n        method: POST\n        description: HashiCorp Query entities based on various properties.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: hashicorp-rest\n    description: REST adapter for HashiCorp Vault API.\n    resources:\n    - path: /auth/token/accessors/\n      name: getauthtokenaccessors\n      operations:\n      - method: GET\n        name: getauthtokenaccessors\n        description: HashiCorp List token accessors, which can then be be used to iterate and discover their properties or\n          revoke them. Because this can be used to cause a denial of service, this endpoint requires\
  \ 'sudo' capability in\n          addition to 'list'.\n        call: hashicorp.getauthtokenaccessors\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth/token/create\n      name: postauthtokencreate\n      operations:\n      - method: POST\n        name: postauthtokencreate\n        description: HashiCorp The token create path is used to create new tokens.\n        call: hashicorp.postauthtokencreate\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth/token/create-orphan\n      name: postauthtokencreateorphan\n      operations:\n      - method: POST\n        name: postauthtokencreateorphan\n        description: HashiCorp The token create path is used to create new orphan tokens.\n        call: hashicorp.postauthtokencreateorphan\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth/token/create/{role_name}\n      name: postauthtokencreaterole-name\n      operations:\n\
  \      - method: POST\n        name: postauthtokencreaterole-name\n        description: HashiCorp This token create path is used to create new tokens adhering to the given role.\n        call: hashicorp.postauthtokencreaterole-name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth/token/lookup\n      name: getauthtokenlookup\n      operations:\n      - method: GET\n        name: getauthtokenlookup\n        description: HashiCorp This endpoint will lookup a token and its properties.\n        call: hashicorp.getauthtokenlookup\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth/token/lookup\n      name: postauthtokenlookup\n      operations:\n      - method: POST\n        name: postauthtokenlookup\n        description: HashiCorp This endpoint will lookup a token and its properties.\n        call: hashicorp.postauthtokenlookup\n        outputParameters:\n        - type: object\n          mapping: $.\n    -\
  \ path: /auth/token/lookup-accessor\n      name: postauthtokenlookupaccessor\n      operations:\n      - method: POST\n        name: postauthtokenlookupaccessor\n        description: HashiCorp This endpoint will lookup a token associated with the given accessor and its properties. Response\n          will not contain the token ID.\n        call: hashicorp.postauthtokenlookupaccessor\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth/token/lookup-self\n      name: getauthtokenlookupself\n      operations:\n      - method: GET\n        name: getauthtokenlookupself\n        description: HashiCorp This endpoint will lookup a token and its properties.\n        call: hashicorp.getauthtokenlookupself\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth/token/lookup-self\n      name: postauthtokenlookupself\n      operations:\n      - method: POST\n        name: postauthtokenlookupself\n        description: HashiCorp\
  \ This endpoint will lookup a token and its properties.\n        call: hashicorp.postauthtokenlookupself\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth/token/renew\n      name: postauthtokenrenew\n      operations:\n      - method: POST\n        name: postauthtokenrenew\n        description: HashiCorp This endpoint will renew the given token and prevent expiration.\n        call: hashicorp.postauthtokenrenew\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth/token/renew-accessor\n      name: postauthtokenrenewaccessor\n      operations:\n      - method: POST\n        name: postauthtokenrenewaccessor\n        description: HashiCorp This endpoint will renew a token associated with the given accessor and its properties. Response\n          will not contain the token ID.\n        call: hashicorp.postauthtokenrenewaccessor\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path:\
  \ /auth/token/renew-self\n      name: postauthtokenrenewself\n      operations:\n      - method: POST\n        name: postauthtokenrenewself\n        description: HashiCorp This endpoint will renew the token used to call it and prevent expiration.\n        call: hashicorp.postauthtokenrenewself\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth/token/revoke\n      name: postauthtokenrevoke\n      operations:\n      - method: POST\n        name: postauthtokenrevoke\n        description: HashiCorp This endpoint will delete the given token and all of its child tokens.\n        call: hashicorp.postauthtokenrevoke\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth/token/revoke-accessor\n      name: postauthtokenrevokeaccessor\n      operations:\n      - method: POST\n        name: postauthtokenrevokeaccessor\n        description: HashiCorp This endpoint will delete the token associated with the accessor and all\
  \ of its child tokens.\n        call: hashicorp.postauthtokenrevokeaccessor\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth/token/revoke-orphan\n      name: postauthtokenrevokeorphan\n      operations:\n      - method: POST\n        name: postauthtokenrevokeorphan\n        description: HashiCorp This endpoint will delete the token and orphan its child tokens.\n        call: hashicorp.postauthtokenrevokeorphan\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth/token/revoke-self\n      name: postauthtokenrevokeself\n      operations:\n      - method: POST\n        name: postauthtokenrevokeself\n        description: HashiCorp This endpoint will delete the token used to call it and all of its child tokens.\n        call: hashicorp.postauthtokenrevokeself\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth/token/roles\n      name: getauthtokenroles\n      operations:\n\
  \      - method: GET\n        name: getauthtokenroles\n        description: HashiCorp This endpoint lists configured roles.\n        call: hashicorp.getauthtokenroles\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth/token/roles/{role_name}\n      name: getauthtokenrolesrole-name\n      operations:\n      - method: GET\n        name: getauthtokenrolesrole-name\n        description: GET /auth/token/roles/{role_name}\n        call: hashicorp.getauthtokenrolesrole-name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth/token/roles/{role_name}\n      name: postauthtokenrolesrole-name\n      operations:\n      - method: POST\n        name: postauthtokenrolesrole-name\n        description: POST /auth/token/roles/{role_name}\n        call: hashicorp.postauthtokenrolesrole-name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth/token/roles/{role_name}\n      name: deleteauthtokenrolesrole-name\n\
  \      operations:\n      - method: DELETE\n        name: deleteauthtokenrolesrole-name\n        description: DELETE /auth/token/roles/{role_name}\n        call: hashicorp.deleteauthtokenrolesrole-name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth/token/tidy\n      name: postauthtokentidy\n      operations:\n      - method: POST\n        name: postauthtokentidy\n        description: HashiCorp This endpoint performs cleanup tasks that can be run if certain error conditions have occurred.\n        call: hashicorp.postauthtokentidy\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /cubbyhole/{path}\n      name: getcubbyholepath\n      operations:\n      - method: GET\n        name: getcubbyholepath\n        description: HashiCorp Retrieve the secret at the specified location.\n        call: hashicorp.getcubbyholepath\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /cubbyhole/{path}\n\
  \      name: postcubbyholepath\n      operations:\n      - method: POST\n        name: postcubbyholepath\n        description: HashiCorp Store a secret at the specified location.\n        call: hashicorp.postcubbyholepath\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /cubbyhole/{path}\n      name: deletecubbyholepath\n      operations:\n      - method: DELETE\n        name: deletecubbyholepath\n        description: HashiCorp Deletes the secret at the specified location.\n        call: hashicorp.deletecubbyholepath\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /identity/alias\n      name: postidentityalias\n      operations:\n      - method: POST\n        name: postidentityalias\n        description: HashiCorp Create a new alias.\n        call: hashicorp.postidentityalias\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /identity/alias/id\n      name: getidentityaliasid\n\
  \      operations:\n      - method: GET\n        name: getidentityaliasid\n        description: HashiCorp List all the alias IDs.\n        call: hashicorp.getidentityaliasid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /identity/alias/id/{id}\n      name: getidentityaliasidid\n      operations:\n      - method: GET\n        name: getidentityaliasidid\n        description: HashiCorp Update, read or delete an alias ID.\n        call: hashicorp.getidentityaliasidid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /identity/alias/id/{id}\n      name: postidentityaliasidid\n      operations:\n      - method: POST\n        name: postidentityaliasidid\n        description: HashiCorp Update, read or delete an alias ID.\n        call: hashicorp.postidentityaliasidid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /identity/alias/id/{id}\n      name: deleteidentityaliasidid\n  \
  \    operations:\n      - method: DELETE\n        name: deleteidentityaliasidid\n        description: HashiCorp Update, read or delete an alias ID.\n        call: hashicorp.deleteidentityaliasidid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /identity/entity\n      name: postidentityentity\n      operations:\n      - method: POST\n        name: postidentityentity\n        description: HashiCorp Create a new entity\n        call: hashicorp.postidentityentity\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /identity/entity-alias\n      name: postidentityentityalias\n      operations:\n      - method: POST\n        name: postidentityentityalias\n        description: HashiCorp Create a new alias.\n        call: hashicorp.postidentityentityalias\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /identity/entity-alias/id\n      name: getidentityentityaliasid\n      operations:\n\
  \      - method: GET\n        name: getidentityentityaliasid\n        description: HashiCorp List all the alias IDs.\n        call: hashicorp.getidentityentityaliasid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /identity/entity-alias/id/{id}\n      name: getidentityentityaliasidid\n      operations:\n      - method: GET\n        name: getidentityentityaliasidid\n        description: HashiCorp Update, read or delete an alias ID.\n        call: hashicorp.getidentityentityaliasidid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /identity/entity-alias/id/{id}\n   \n\n# --- truncated at 32 KB (60 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/hashicorp/refs/heads/main/capabilities/hashicorp-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/hashicorp/refs/heads/main/capabilities/hashicorp-capability.yaml
tags:
- Hashicorp
- API
tools:
- description: HashiCorp List token accessors, which can then be be used to iterate and discover their properties or revoke them. Because this can be used to cause a denial of service, this endpoint requires 'sudo' capability in addition to 'list'.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getauthtokenaccessors
- description: HashiCorp The token create path is used to create new tokens.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: postauthtokencreate
- description: HashiCorp The token create path is used to create new orphan tokens.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: postauthtokencreateorphan
- description: HashiCorp This token create path is used to create new tokens adhering to the given role.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: postauthtokencreaterole-name
- description: HashiCorp This endpoint will lookup a token and its properties.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getauthtokenlookup
- description: HashiCorp This endpoint will lookup a token and its properties.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: postauthtokenlookup
- description: HashiCorp This endpoint will lookup a token associated with the given accessor and its properties. Response will not contain the token ID.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: postauthtokenlookupaccessor
- description: HashiCorp This endpoint will lookup a token and its properties.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getauthtokenlookupself
- description: HashiCorp This endpoint will lookup a token and its properties.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: postauthtokenlookupself
- description: HashiCorp This endpoint will renew the given token and prevent expiration.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: postauthtokenrenew
- description: HashiCorp This endpoint will renew a token associated with the given accessor and its properties. Response will not contain the token ID.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: postauthtokenrenewaccessor
- description: HashiCorp This endpoint will renew the token used to call it and prevent expiration.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: postauthtokenrenewself
- description: HashiCorp This endpoint will delete the given token and all of its child tokens.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: postauthtokenrevoke
- description: HashiCorp This endpoint will delete the token associated with the accessor and all of its child tokens.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: postauthtokenrevokeaccessor
- description: HashiCorp This endpoint will delete the token and orphan its child tokens.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: postauthtokenrevokeorphan
- description: HashiCorp This endpoint will delete the token used to call it and all of its child tokens.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: postauthtokenrevokeself
- description: HashiCorp This endpoint lists configured roles.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getauthtokenroles
- description: GET /auth/token/roles/{role_name}
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getauthtokenrolesrole-name
- description: POST /auth/token/roles/{role_name}
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: postauthtokenrolesrole-name
- description: DELETE /auth/token/roles/{role_name}
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteauthtokenrolesrole-name
- description: HashiCorp This endpoint performs cleanup tasks that can be run if certain error conditions have occurred.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: postauthtokentidy
- description: HashiCorp Retrieve the secret at the specified location.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcubbyholepath
- description: HashiCorp Store a secret at the specified location.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: postcubbyholepath
- description: HashiCorp Deletes the secret at the specified location.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletecubbyholepath
- description: HashiCorp Create a new alias.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: postidentityalias
- description: HashiCorp List all the alias IDs.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getidentityaliasid
- description: HashiCorp Update, read or delete an alias ID.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getidentityaliasidid
- description: HashiCorp Update, read or delete an alias ID.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: postidentityaliasidid
- description: HashiCorp Update, read or delete an alias ID.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteidentityaliasidid
- description: HashiCorp Create a new entity
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: postidentityentity
- description: HashiCorp Create a new alias.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: postidentityentityalias
- description: HashiCorp List all the alias IDs.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getidentityentityaliasid
- description: HashiCorp Update, read or delete an alias ID.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getidentityentityaliasidid
- description: HashiCorp Update, read or delete an alias ID.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: postidentityentityaliasidid
- description: HashiCorp Update, read or delete an alias ID.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteidentityentityaliasidid
- description: HashiCorp Delete all of the entities provided
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: postidentityentitybatchdelete
- description: HashiCorp List all the entity IDs
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getidentityentityid
- description: HashiCorp Update, read or delete an entity using entity ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getidentityentityidid
- description: HashiCorp Update, read or delete an entity using entity ID
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: postidentityentityidid
- description: HashiCorp Update, read or delete an entity using entity ID
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteidentityentityidid
- description: HashiCorp Merge two or more entities together
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: postidentityentitymerge
- description: HashiCorp List all the entity names
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getidentityentityname
- description: HashiCorp Update, read or delete an entity using entity name
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getidentityentitynamename
- description: HashiCorp Update, read or delete an entity using entity name
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: postidentityentitynamename
- description: HashiCorp Update, read or delete an entity using entity name
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteidentityentitynamename
- description: HashiCorp Create a new group.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: postidentitygroup
- description: HashiCorp Creates a new group alias, or updates an existing one.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: postidentitygroupalias
- description: HashiCorp List all the group alias IDs.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getidentitygroupaliasid
- description: GET /identity/group-alias/id/{id}
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getidentitygroupaliasidid
- description: POST /identity/group-alias/id/{id}
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: postidentitygroupaliasidid
- description: DELETE /identity/group-alias/id/{id}
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteidentitygroupaliasidid
- description: HashiCorp List all the group IDs.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getidentitygroupid
- description: HashiCorp Update or delete an existing group using its ID.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getidentitygroupidid
- description: HashiCorp Update or delete an existing group using its ID.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: postidentitygroupidid
- description: HashiCorp Update or delete an existing group using its ID.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteidentitygroupidid
- description: GET /identity/group/name
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getidentitygroupname
- description: GET /identity/group/name/{name}
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getidentitygroupnamename
- description: POST /identity/group/name/{name}
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: postidentitygroupnamename
- description: DELETE /identity/group/name/{name}
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteidentitygroupnamename
- description: HashiCorp Query entities based on various properties.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: postidentitylookupentity
---
