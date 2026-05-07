---
categories: []
consumed_apis: []
description: The Zesty.io Accounts API is used to manage users, roles, instances, teams, tokens, ecosystems, webhooks, and apps. It provides administrative control over the organizational structure of a Zesty.io account. All endpoints require authentication via a session token obtained from the Auth API.
layout: capability
name: Zesty Accounts API
operations:
- description: Zesty List all instances
  method: GET
  name: getinstances
  path: /instances
- description: Zesty Create a new instance
  method: POST
  name: createinstance
  path: /instances
- description: Zesty Get an instance
  method: GET
  name: getinstance
  path: /instances/{instanceZUID}
- description: Zesty Update an instance
  method: PUT
  name: updateinstance
  path: /instances/{instanceZUID}
- description: Zesty Delete an instance
  method: DELETE
  name: deleteinstance
  path: /instances/{instanceZUID}
- description: Zesty List all users
  method: GET
  name: getusers
  path: /users
- description: Zesty Get a user
  method: GET
  name: getuser
  path: /users/{userZUID}
- description: Zesty Update a user
  method: PUT
  name: updateuser
  path: /users/{userZUID}
- description: Zesty Delete a user
  method: DELETE
  name: deleteuser
  path: /users/{userZUID}
- description: Zesty List all roles
  method: GET
  name: getroles
  path: /roles
- description: Zesty Create a new role
  method: POST
  name: createrole
  path: /roles
- description: Zesty Get a role
  method: GET
  name: getrole
  path: /roles/{roleZUID}
- description: Zesty Update a role
  method: PUT
  name: updaterole
  path: /roles/{roleZUID}
- description: Zesty Delete a role
  method: DELETE
  name: deleterole
  path: /roles/{roleZUID}
- description: Zesty List all teams
  method: GET
  name: getteams
  path: /teams
- description: Zesty Create a new team
  method: POST
  name: createteam
  path: /teams
- description: Zesty Get a team
  method: GET
  name: getteam
  path: /teams/{teamZUID}
- description: Zesty Update a team
  method: PUT
  name: updateteam
  path: /teams/{teamZUID}
- description: Zesty Delete a team
  method: DELETE
  name: deleteteam
  path: /teams/{teamZUID}
- description: Zesty List all access tokens
  method: GET
  name: gettokens
  path: /tokens
- description: Zesty Create an access token
  method: POST
  name: createtoken
  path: /tokens
- description: Zesty Get an access token
  method: GET
  name: gettoken
  path: /tokens/{tokenZUID}
- description: Zesty Delete an access token
  method: DELETE
  name: deletetoken
  path: /tokens/{tokenZUID}
- description: Zesty List all apps
  method: GET
  name: getapps
  path: /apps
- description: Zesty List all webhooks
  method: GET
  name: getwebhooks
  path: /webhooks
- description: Zesty Create a webhook
  method: POST
  name: createwebhook
  path: /webhooks
personas: []
provider_name: Zesty
provider_slug: zesty
search_terms:
- zesty create a new instance
- getteams
- getinstances
- updateinstance
- createinstance
- zesty list all users
- getusers
- api
- zesty create an access token
- zesty update a role
- zesty get an instance
- composable
- createtoken
- zesty update an instance
- gettokens
- zesty delete a user
- deleteinstance
- deleterole
- updaterole
- zesty delete an access token
- zesty delete an instance
- getwebhooks
- zesty delete a team
- graphql
- createwebhook
- getuser
- zesty get a role
- createteam
- getinstance
- deleteuser
- zesty get a user
- cms
- getrole
- zesty delete a role
- zesty get a team
- gettoken
- zesty
- zesty update a team
- zesty list all instances
- updateuser
- zesty list all access tokens
- zesty create a new team
- getapps
- deleteteam
- zesty update a user
- zesty list all apps
- zesty create a webhook
- updateteam
- content management
- deletetoken
- zesty create a new role
- media
- getteam
- zesty get an access token
- zesty list all teams
- zesty list all roles
- headless cms
- getroles
- zesty list all webhooks
- createrole
slug: zesty-capability
source_filename: zesty-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Zesty Accounts API\n  description: The Zesty.io Accounts API is used to manage users, roles, instances, teams, tokens, ecosystems, webhooks, and\n    apps. It provides administrative control over the organizational structure of a Zesty.io account. All endpoints require\n    authentication via a session token obtained from the Auth API.\n  tags:\n  - Zesty\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: zesty\n    baseUri: https://accounts.api.zesty.io/v1\n    description: Zesty Accounts API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: Authorization\n      value: '{{ZESTY_TOKEN}}'\n    resources:\n    - name: instances\n      path: /instances\n      operations:\n      - name: getinstances\n        method: GET\n        description: Zesty List all instances\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n      - name: createinstance\n        method: POST\n        description: Zesty Create a new instance\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: instances-instancezuid\n      path: /instances/{instanceZUID}\n      operations:\n      - name: getinstance\n        method: GET\n        description: Zesty Get an instance\n        inputParameters:\n        - name: instanceZUID\n          in: path\n          type: string\n          required: true\n          description: The ZUID of the instance.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateinstance\n        method: PUT\n        description: Zesty Update an instance\n        inputParameters:\n        - name: instanceZUID\n          in: path\n          type: string\n          required: true\n          description:\
  \ The ZUID of the instance.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteinstance\n        method: DELETE\n        description: Zesty Delete an instance\n        inputParameters:\n        - name: instanceZUID\n          in: path\n          type: string\n          required: true\n          description: The ZUID of the instance.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users\n      path: /users\n      operations:\n      - name: getusers\n        method: GET\n        description: Zesty List all users\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users-userzuid\n      path: /users/{userZUID}\n      operations:\n      - name: getuser\n        method: GET\n        description: Zesty Get a user\n     \
  \   inputParameters:\n        - name: userZUID\n          in: path\n          type: string\n          required: true\n          description: The ZUID of the user.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateuser\n        method: PUT\n        description: Zesty Update a user\n        inputParameters:\n        - name: userZUID\n          in: path\n          type: string\n          required: true\n          description: The ZUID of the user.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteuser\n        method: DELETE\n        description: Zesty Delete a user\n        inputParameters:\n        - name: userZUID\n          in: path\n          type: string\n          required: true\n          description: The ZUID of the user.\n        outputRawFormat: json\n        outputParameters:\n      \
  \  - name: result\n          type: object\n          value: $.\n    - name: roles\n      path: /roles\n      operations:\n      - name: getroles\n        method: GET\n        description: Zesty List all roles\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createrole\n        method: POST\n        description: Zesty Create a new role\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: roles-rolezuid\n      path: /roles/{roleZUID}\n      operations:\n      - name: getrole\n        method: GET\n        description: Zesty Get a role\n        inputParameters:\n        - name: roleZUID\n          in: path\n          type: string\n          required: true\n          description: The ZUID of the role.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n      \
  \    value: $.\n      - name: updaterole\n        method: PUT\n        description: Zesty Update a role\n        inputParameters:\n        - name: roleZUID\n          in: path\n          type: string\n          required: true\n          description: The ZUID of the role.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleterole\n        method: DELETE\n        description: Zesty Delete a role\n        inputParameters:\n        - name: roleZUID\n          in: path\n          type: string\n          required: true\n          description: The ZUID of the role.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: teams\n      path: /teams\n      operations:\n      - name: getteams\n        method: GET\n        description: Zesty List all teams\n        outputRawFormat: json\n        outputParameters:\n        -\
  \ name: result\n          type: object\n          value: $.\n      - name: createteam\n        method: POST\n        description: Zesty Create a new team\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: teams-teamzuid\n      path: /teams/{teamZUID}\n      operations:\n      - name: getteam\n        method: GET\n        description: Zesty Get a team\n        inputParameters:\n        - name: teamZUID\n          in: path\n          type: string\n          required: true\n          description: The ZUID of the team.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateteam\n        method: PUT\n        description: Zesty Update a team\n        inputParameters:\n        - name: teamZUID\n          in: path\n          type: string\n          required: true\n          description: The ZUID of the team.\n    \
  \    outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteteam\n        method: DELETE\n        description: Zesty Delete a team\n        inputParameters:\n        - name: teamZUID\n          in: path\n          type: string\n          required: true\n          description: The ZUID of the team.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tokens\n      path: /tokens\n      operations:\n      - name: gettokens\n        method: GET\n        description: Zesty List all access tokens\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createtoken\n        method: POST\n        description: Zesty Create an access token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n    - name: tokens-tokenzuid\n      path: /tokens/{tokenZUID}\n      operations:\n      - name: gettoken\n        method: GET\n        description: Zesty Get an access token\n        inputParameters:\n        - name: tokenZUID\n          in: path\n          type: string\n          required: true\n          description: The ZUID of the token.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletetoken\n        method: DELETE\n        description: Zesty Delete an access token\n        inputParameters:\n        - name: tokenZUID\n          in: path\n          type: string\n          required: true\n          description: The ZUID of the token.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: apps\n      path: /apps\n      operations:\n      - name: getapps\n        method: GET\n      \
  \  description: Zesty List all apps\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: webhooks\n      path: /webhooks\n      operations:\n      - name: getwebhooks\n        method: GET\n        description: Zesty List all webhooks\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createwebhook\n        method: POST\n        description: Zesty Create a webhook\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: zesty-rest\n    description: REST adapter for Zesty Accounts API.\n    resources:\n    - path: /instances\n      name: getinstances\n      operations:\n      - method: GET\n        name: getinstances\n        description: Zesty List all instances\n        call: zesty.getinstances\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /instances\n      name: createinstance\n      operations:\n      - method: POST\n        name: createinstance\n        description: Zesty Create a new instance\n        call: zesty.createinstance\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /instances/{instanceZUID}\n      name: getinstance\n      operations:\n      - method: GET\n        name: getinstance\n        description: Zesty Get an instance\n        call: zesty.getinstance\n        with:\n          instanceZUID: rest.instanceZUID\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /instances/{instanceZUID}\n      name: updateinstance\n      operations:\n      - method: PUT\n        name: updateinstance\n        description: Zesty Update an instance\n        call: zesty.updateinstance\n        with:\n          instanceZUID: rest.instanceZUID\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /instances/{instanceZUID}\n      name: deleteinstance\n      operations:\n      - method: DELETE\n        name: deleteinstance\n        description: Zesty Delete an instance\n        call: zesty.deleteinstance\n        with:\n          instanceZUID: rest.instanceZUID\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users\n      name: getusers\n      operations:\n      - method: GET\n        name: getusers\n        description: Zesty List all users\n        call: zesty.getusers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users/{userZUID}\n      name: getuser\n      operations:\n      - method: GET\n        name: getuser\n        description: Zesty Get a user\n        call: zesty.getuser\n        with:\n          userZUID: rest.userZUID\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users/{userZUID}\n     \
  \ name: updateuser\n      operations:\n      - method: PUT\n        name: updateuser\n        description: Zesty Update a user\n        call: zesty.updateuser\n        with:\n          userZUID: rest.userZUID\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users/{userZUID}\n      name: deleteuser\n      operations:\n      - method: DELETE\n        name: deleteuser\n        description: Zesty Delete a user\n        call: zesty.deleteuser\n        with:\n          userZUID: rest.userZUID\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /roles\n      name: getroles\n      operations:\n      - method: GET\n        name: getroles\n        description: Zesty List all roles\n        call: zesty.getroles\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /roles\n      name: createrole\n      operations:\n      - method: POST\n        name: createrole\n        description: Zesty Create\
  \ a new role\n        call: zesty.createrole\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /roles/{roleZUID}\n      name: getrole\n      operations:\n      - method: GET\n        name: getrole\n        description: Zesty Get a role\n        call: zesty.getrole\n        with:\n          roleZUID: rest.roleZUID\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /roles/{roleZUID}\n      name: updaterole\n      operations:\n      - method: PUT\n        name: updaterole\n        description: Zesty Update a role\n        call: zesty.updaterole\n        with:\n          roleZUID: rest.roleZUID\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /roles/{roleZUID}\n      name: deleterole\n      operations:\n      - method: DELETE\n        name: deleterole\n        description: Zesty Delete a role\n        call: zesty.deleterole\n        with:\n          roleZUID: rest.roleZUID\n     \
  \   outputParameters:\n        - type: object\n          mapping: $.\n    - path: /teams\n      name: getteams\n      operations:\n      - method: GET\n        name: getteams\n        description: Zesty List all teams\n        call: zesty.getteams\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /teams\n      name: createteam\n      operations:\n      - method: POST\n        name: createteam\n        description: Zesty Create a new team\n        call: zesty.createteam\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /teams/{teamZUID}\n      name: getteam\n      operations:\n      - method: GET\n        name: getteam\n        description: Zesty Get a team\n        call: zesty.getteam\n        with:\n          teamZUID: rest.teamZUID\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /teams/{teamZUID}\n      name: updateteam\n      operations:\n      - method: PUT\n        name:\
  \ updateteam\n        description: Zesty Update a team\n        call: zesty.updateteam\n        with:\n          teamZUID: rest.teamZUID\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /teams/{teamZUID}\n      name: deleteteam\n      operations:\n      - method: DELETE\n        name: deleteteam\n        description: Zesty Delete a team\n        call: zesty.deleteteam\n        with:\n          teamZUID: rest.teamZUID\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /tokens\n      name: gettokens\n      operations:\n      - method: GET\n        name: gettokens\n        description: Zesty List all access tokens\n        call: zesty.gettokens\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /tokens\n      name: createtoken\n      operations:\n      - method: POST\n        name: createtoken\n        description: Zesty Create an access token\n        call: zesty.createtoken\n  \
  \      outputParameters:\n        - type: object\n          mapping: $.\n    - path: /tokens/{tokenZUID}\n      name: gettoken\n      operations:\n      - method: GET\n        name: gettoken\n        description: Zesty Get an access token\n        call: zesty.gettoken\n        with:\n          tokenZUID: rest.tokenZUID\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /tokens/{tokenZUID}\n      name: deletetoken\n      operations:\n      - method: DELETE\n        name: deletetoken\n        description: Zesty Delete an access token\n        call: zesty.deletetoken\n        with:\n          tokenZUID: rest.tokenZUID\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apps\n      name: getapps\n      operations:\n      - method: GET\n        name: getapps\n        description: Zesty List all apps\n        call: zesty.getapps\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /webhooks\n\
  \      name: getwebhooks\n      operations:\n      - method: GET\n        name: getwebhooks\n        description: Zesty List all webhooks\n        call: zesty.getwebhooks\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /webhooks\n      name: createwebhook\n      operations:\n      - method: POST\n        name: createwebhook\n        description: Zesty Create a webhook\n        call: zesty.createwebhook\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: zesty-mcp\n    transport: http\n    description: MCP adapter for Zesty Accounts API for AI agent use.\n    tools:\n    - name: getinstances\n      description: Zesty List all instances\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: zesty.getinstances\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createinstance\n      description: Zesty Create\
  \ a new instance\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: zesty.createinstance\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getinstance\n      description: Zesty Get an instance\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: zesty.getinstance\n      with:\n        instanceZUID: tools.instanceZUID\n      inputParameters:\n      - name: instanceZUID\n        type: string\n        description: The ZUID of the instance.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateinstance\n      description: Zesty Update an instance\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: zesty.updateinstance\n      with:\n        instanceZUID: tools.instanceZUID\n      inputParameters:\n      - name: instanceZUID\n        type: string\n\
  \        description: The ZUID of the instance.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteinstance\n      description: Zesty Delete an instance\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: zesty.deleteinstance\n      with:\n        instanceZUID: tools.instanceZUID\n      inputParameters:\n      - name: instanceZUID\n        type: string\n        description: The ZUID of the instance.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getusers\n      description: Zesty List all users\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: zesty.getusers\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getuser\n      description: Zesty Get a user\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent:\
  \ true\n      call: zesty.getuser\n      with:\n        userZUID: tools.userZUID\n      inputParameters:\n      - name: userZUID\n        type: string\n        description: The ZUID of the user.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateuser\n      description: Zesty Update a user\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: zesty.updateuser\n      with:\n        userZUID: tools.userZUID\n      inputParameters:\n      - name: userZUID\n        type: string\n        description: The ZUID of the user.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteuser\n      description: Zesty Delete a user\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: zesty.deleteuser\n      with:\n        userZUID: tools.userZUID\n      inputParameters:\n      - name: userZUID\n\
  \        type: string\n        description: The ZUID of the user.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getroles\n      description: Zesty List all roles\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: zesty.getroles\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createrole\n      description: Zesty Create a new role\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: zesty.createrole\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getrole\n      description: Zesty Get a role\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: zesty.getrole\n      with:\n        roleZUID: tools.roleZUID\n      inputParameters:\n      - name: roleZUID\n        type: string\n        description: The ZUID of the\
  \ role.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updaterole\n      description: Zesty Update a role\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: zesty.updaterole\n      with:\n        roleZUID: tools.roleZUID\n      inputParameters:\n      - name: roleZUID\n        type: string\n        description: The ZUID of the role.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleterole\n      description: Zesty Delete a role\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: zesty.deleterole\n      with:\n        roleZUID: tools.roleZUID\n      inputParameters:\n      - name: roleZUID\n        type: string\n        description: The ZUID of the role.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getteams\n\
  \      description: Zesty List all teams\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: zesty.getteams\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createteam\n      description: Zesty Create a new team\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: zesty.createteam\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getteam\n      description: Zesty Get a team\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: zesty.getteam\n      with:\n        teamZUID: tools.teamZUID\n      inputParameters:\n      - name: teamZUID\n        type: string\n        description: The ZUID of the team.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateteam\n      description: Zesty Update a team\n      hints:\n \
  \       readOnly: false\n        destructive: false\n        idempotent: true\n      call: zesty.updateteam\n      with:\n        teamZUID: tools.teamZUID\n      inputParameters:\n      - name: teamZUID\n        type: string\n        description: The ZUID of the team.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteteam\n      description: Zesty Delete a team\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: zesty.deleteteam\n      with:\n        teamZUID: tools.teamZUID\n      inputParameters:\n      - name: teamZUID\n        type: string\n        description: The ZUID of the team.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: gettokens\n      description: Zesty List all access tokens\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: zesty.gettokens\n     \
  \ outputParameters:\n      - type: object\n        mapping: $.\n    - name: createtoken\n      description: Zesty Create an access token\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: zesty.createtoken\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: gettoken\n      description: Zesty Get an access token\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: zesty.gettoken\n      with:\n        tokenZUID: tools.tokenZUID\n      inputParameters:\n      - name: tokenZUID\n        type: string\n        description: The ZUID of the token.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletetoken\n      description: Zesty Delete an access token\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: zesty.deletetoken\n      with:\n        tokenZUID:\
  \ tools.tokenZUID\n      inputParameters:\n      - name: tokenZUID\n        type: string\n        description: The ZUID of the token.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getapps\n      description: Zesty List all apps\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: zesty.getapps\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getwebhooks\n      description: Zesty List all webhooks\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: zesty.getwebhooks\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createwebhook\n      description: Zesty Create a webhook\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: zesty.createwebhook\n      outputParameters:\n      - type: object\n        mapping: $.\n\
  binds:\n- namespace: env\n  keys:\n    ZESTY_TOKEN: ZESTY_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/zesty/refs/heads/main/capabilities/zesty-capability.yaml
tags:
- Zesty
- API
tools:
- description: Zesty List all instances
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getinstances
- description: Zesty Create a new instance
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createinstance
- description: Zesty Get an instance
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getinstance
- description: Zesty Update an instance
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateinstance
- description: Zesty Delete an instance
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteinstance
- description: Zesty List all users
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getusers
- description: Zesty Get a user
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getuser
- description: Zesty Update a user
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateuser
- description: Zesty Delete a user
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteuser
- description: Zesty List all roles
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getroles
- description: Zesty Create a new role
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createrole
- description: Zesty Get a role
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getrole
- description: Zesty Update a role
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updaterole
- description: Zesty Delete a role
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleterole
- description: Zesty List all teams
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getteams
- description: Zesty Create a new team
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createteam
- description: Zesty Get a team
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getteam
- description: Zesty Update a team
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateteam
- description: Zesty Delete a team
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteteam
- description: Zesty List all access tokens
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettokens
- description: Zesty Create an access token
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createtoken
- description: Zesty Get an access token
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettoken
- description: Zesty Delete an access token
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletetoken
- description: Zesty List all apps
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getapps
- description: Zesty List all webhooks
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getwebhooks
- description: Zesty Create a webhook
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createwebhook
---
