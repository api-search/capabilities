---
categories: []
consumed_apis: []
description: OneLogin REST API for identity and access management. Provides programmatic access to users, roles, apps, MFA, branding, connectors, reports, SAML assertions, smart hooks, and Vigilance AI. Authentication is handled via OAuth 2.0 bearer tokens.
layout: capability
name: OneLogin API
operations:
- description: Generate access token
  method: POST
  name: generatetoken
  path: /auth/oauth2/v2/token
- description: Revoke access token
  method: POST
  name: revoketoken
  path: /auth/oauth2/revoke
- description: List users
  method: GET
  name: listusers
  path: /api/1/users
- description: Create user
  method: POST
  name: createuser
  path: /api/1/users
- description: Get user by ID
  method: GET
  name: getuser
  path: /api/1/users/{id}
- description: Update user by ID
  method: PUT
  name: updateuser
  path: /api/1/users/{id}
- description: Delete user by ID
  method: DELETE
  name: deleteuser
  path: /api/1/users/{id}
- description: Get apps for a user
  method: GET
  name: getuserapps
  path: /api/1/users/{id}/apps
- description: Get roles for a user
  method: GET
  name: getuserroles
  path: /api/1/users/{id}/roles
- description: Assign role to user
  method: POST
  name: assignuserrole
  path: /api/1/users/{id}/roles
- description: Remove role from user
  method: DELETE
  name: removeuserrole
  path: /api/1/users/{id}/roles/{role_id}
- description: Set user password
  method: PUT
  name: setuserpassword
  path: /api/1/users/{id}/password
- description: Set custom attribute
  method: PUT
  name: setusercustomattribute
  path: /api/1/users/{id}/custom_attributes
- description: Set user state
  method: PUT
  name: setuserstate
  path: /api/1/users/{id}/state
- description: Log user out
  method: POST
  name: logoutuser
  path: /api/1/users/{id}/logout
- description: Lock user account
  method: POST
  name: lockuser
  path: /api/1/users/{id}/lock
- description: Get roles
  method: GET
  name: getroles
  path: /api/1/roles
- description: List roles (v2)
  method: GET
  name: listrolesv2
  path: /api/2/roles
- description: Create role
  method: POST
  name: createrole
  path: /api/2/roles
- description: Get role by ID
  method: GET
  name: getrole
  path: /api/2/roles/{id}
- description: Update role
  method: PUT
  name: updaterole
  path: /api/2/roles/{id}
- description: Delete role
  method: DELETE
  name: deleterole
  path: /api/2/roles/{id}
- description: List apps
  method: GET
  name: listapps
  path: /api/2/apps
- description: Create app
  method: POST
  name: createapp
  path: /api/2/apps
- description: Get app by ID
  method: GET
  name: getapp
  path: /api/2/apps/{id}
- description: Update app
  method: PUT
  name: updateapp
  path: /api/2/apps/{id}
- description: Delete app
  method: DELETE
  name: deleteapp
  path: /api/2/apps/{id}
- description: Generate SAML assertion
  method: POST
  name: generatesamlassertion
  path: /api/1/saml_assertion
- description: Verify factor for SAML
  method: POST
  name: verifysamlfactor
  path: /api/1/saml_assertion/verify_factor
- description: Get available auth factors
  method: GET
  name: getotpdevices
  path: /api/1/users/{id}/otp_devices
- description: Enroll auth factor
  method: POST
  name: enrollfactor
  path: /api/1/users/{id}/otp_devices
personas: []
provider_name: OneLogin
provider_slug: onelogin
search_terms:
- list roles (v2)
- setuserpassword
- lockuser
- list apps
- create app
- createuser
- update user by id
- update app
- deleteapp
- identity
- createrole
- get roles
- deleterole
- onelogin
- getrole
- assign role to user
- assignuserrole
- enroll auth factor
- getapp
- getroles
- verifysamlfactor
- listapps
- logoutuser
- lock user account
- get apps for a user
- create user
- get available auth factors
- get user by id
- generate saml assertion
- oauth
- updaterole
- set user state
- getuserroles
- getuserapps
- delete app
- get role by id
- generatesamlassertion
- saml
- set user password
- enrollfactor
- revoke access token
- setuserstate
- listrolesv2
- updateapp
- log user out
- api
- remove role from user
- revoketoken
- single sign-on
- setusercustomattribute
- update role
- delete user by id
- get roles for a user
- access management
- removeuserrole
- getotpdevices
- getuser
- create role
- list users
- multi-factor authentication
- delete role
- generate access token
- listusers
- set custom attribute
- generatetoken
- get app by id
- updateuser
- createapp
- verify factor for saml
- deleteuser
slug: onelogin-capability
source_filename: onelogin-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: OneLogin API\n  description: OneLogin REST API for identity and access management. Provides programmatic access to users, roles, apps, MFA,\n    branding, connectors, reports, SAML assertions, smart hooks, and Vigilance AI. Authentication is handled via OAuth 2.0\n    bearer tokens.\n  tags:\n  - Onelogin\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: onelogin\n    baseUri: https://api.onelogin.com\n    description: OneLogin API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{ONELOGIN_TOKEN}}'\n    resources:\n    - name: auth-oauth2-v2-token\n      path: /auth/oauth2/v2/token\n      operations:\n      - name: generatetoken\n        method: POST\n        description: Generate access token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: auth-oauth2-revoke\n\
  \      path: /auth/oauth2/revoke\n      operations:\n      - name: revoketoken\n        method: POST\n        description: Revoke access token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-1-users\n      path: /api/1/users\n      operations:\n      - name: listusers\n        method: GET\n        description: List users\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n        - name: page\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createuser\n        method: POST\n        description: Create user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-1-users-id\n      path: /api/1/users/{id}\n      operations:\n  \
  \    - name: getuser\n        method: GET\n        description: Get user by ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateuser\n        method: PUT\n        description: Update user by ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteuser\n        method: DELETE\n        description: Delete user by ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-1-users-id-apps\n      path: /api/1/users/{id}/apps\n      operations:\n      - name: getuserapps\n        method: GET\n        description: Get apps for a user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-1-users-id-roles\n      path: /api/1/users/{id}/roles\n\
  \      operations:\n      - name: getuserroles\n        method: GET\n        description: Get roles for a user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: assignuserrole\n        method: POST\n        description: Assign role to user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-1-users-id-roles-role-id\n      path: /api/1/users/{id}/roles/{role_id}\n      operations:\n      - name: removeuserrole\n        method: DELETE\n        description: Remove role from user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-1-users-id-password\n      path: /api/1/users/{id}/password\n      operations:\n      - name: setuserpassword\n        method: PUT\n        description: Set user password\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-1-users-id-custom-attributes\n      path: /api/1/users/{id}/custom_attributes\n      operations:\n      - name: setusercustomattribute\n        method: PUT\n        description: Set custom attribute\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-1-users-id-state\n      path: /api/1/users/{id}/state\n      operations:\n      - name: setuserstate\n        method: PUT\n        description: Set user state\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-1-users-id-logout\n      path: /api/1/users/{id}/logout\n      operations:\n      - name: logoutuser\n        method: POST\n        description: Log user out\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n    - name: api-1-users-id-lock\n      path: /api/1/users/{id}/lock\n      operations:\n      - name: lockuser\n        method: POST\n        description: Lock user account\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-1-roles\n      path: /api/1/roles\n      operations:\n      - name: getroles\n        method: GET\n        description: Get roles\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-2-roles\n      path: /api/2/roles\n      operations:\n      - name: listrolesv2\n        method: GET\n        description: List roles (v2)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createrole\n        method: POST\n        description: Create role\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-2-roles-id\n      path: /api/2/roles/{id}\n      operations:\n      - name: getrole\n        method: GET\n        description: Get role by ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updaterole\n        method: PUT\n        description: Update role\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleterole\n        method: DELETE\n        description: Delete role\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-2-apps\n      path: /api/2/apps\n      operations:\n      - name: listapps\n        method: GET\n        description: List apps\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: createapp\n        method: POST\n        description: Create app\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-2-apps-id\n      path: /api/2/apps/{id}\n      operations:\n      - name: getapp\n        method: GET\n        description: Get app by ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateapp\n        method: PUT\n        description: Update app\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteapp\n        method: DELETE\n        description: Delete app\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-1-saml-assertion\n\
  \      path: /api/1/saml_assertion\n      operations:\n      - name: generatesamlassertion\n        method: POST\n        description: Generate SAML assertion\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-1-saml-assertion-verify-factor\n      path: /api/1/saml_assertion/verify_factor\n      operations:\n      - name: verifysamlfactor\n        method: POST\n        description: Verify factor for SAML\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-1-users-id-otp-devices\n      path: /api/1/users/{id}/otp_devices\n      operations:\n      - name: getotpdevices\n        method: GET\n        description: Get available auth factors\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: enrollfactor\n        method:\
  \ POST\n        description: Enroll auth factor\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: onelogin-rest\n    description: REST adapter for OneLogin API.\n    resources:\n    - path: /auth/oauth2/v2/token\n      name: generatetoken\n      operations:\n      - method: POST\n        name: generatetoken\n        description: Generate access token\n        call: onelogin.generatetoken\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth/oauth2/revoke\n      name: revoketoken\n      operations:\n      - method: POST\n        name: revoketoken\n        description: Revoke access token\n        call: onelogin.revoketoken\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/1/users\n      name: listusers\n      operations:\n      - method: GET\n        name: listusers\n    \
  \    description: List users\n        call: onelogin.listusers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/1/users\n      name: createuser\n      operations:\n      - method: POST\n        name: createuser\n        description: Create user\n        call: onelogin.createuser\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/1/users/{id}\n      name: getuser\n      operations:\n      - method: GET\n        name: getuser\n        description: Get user by ID\n        call: onelogin.getuser\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/1/users/{id}\n      name: updateuser\n      operations:\n      - method: PUT\n        name: updateuser\n        description: Update user by ID\n        call: onelogin.updateuser\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/1/users/{id}\n      name: deleteuser\n      operations:\n\
  \      - method: DELETE\n        name: deleteuser\n        description: Delete user by ID\n        call: onelogin.deleteuser\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/1/users/{id}/apps\n      name: getuserapps\n      operations:\n      - method: GET\n        name: getuserapps\n        description: Get apps for a user\n        call: onelogin.getuserapps\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/1/users/{id}/roles\n      name: getuserroles\n      operations:\n      - method: GET\n        name: getuserroles\n        description: Get roles for a user\n        call: onelogin.getuserroles\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/1/users/{id}/roles\n      name: assignuserrole\n      operations:\n      - method: POST\n        name: assignuserrole\n        description: Assign role to user\n        call: onelogin.assignuserrole\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /api/1/users/{id}/roles/{role_id}\n      name: removeuserrole\n      operations:\n      - method: DELETE\n        name: removeuserrole\n        description: Remove role from user\n        call: onelogin.removeuserrole\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/1/users/{id}/password\n      name: setuserpassword\n      operations:\n      - method: PUT\n        name: setuserpassword\n        description: Set user password\n        call: onelogin.setuserpassword\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/1/users/{id}/custom_attributes\n      name: setusercustomattribute\n      operations:\n      - method: PUT\n        name: setusercustomattribute\n        description: Set custom attribute\n        call: onelogin.setusercustomattribute\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/1/users/{id}/state\n\
  \      name: setuserstate\n      operations:\n      - method: PUT\n        name: setuserstate\n        description: Set user state\n        call: onelogin.setuserstate\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/1/users/{id}/logout\n      name: logoutuser\n      operations:\n      - method: POST\n        name: logoutuser\n        description: Log user out\n        call: onelogin.logoutuser\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/1/users/{id}/lock\n      name: lockuser\n      operations:\n      - method: POST\n        name: lockuser\n        description: Lock user account\n        call: onelogin.lockuser\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/1/roles\n      name: getroles\n      operations:\n      - method: GET\n        name: getroles\n        description: Get roles\n        call: onelogin.getroles\n        outputParameters:\n        -\
  \ type: object\n          mapping: $.\n    - path: /api/2/roles\n      name: listrolesv2\n      operations:\n      - method: GET\n        name: listrolesv2\n        description: List roles (v2)\n        call: onelogin.listrolesv2\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/2/roles\n      name: createrole\n      operations:\n      - method: POST\n        name: createrole\n        description: Create role\n        call: onelogin.createrole\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/2/roles/{id}\n      name: getrole\n      operations:\n      - method: GET\n        name: getrole\n        description: Get role by ID\n        call: onelogin.getrole\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/2/roles/{id}\n      name: updaterole\n      operations:\n      - method: PUT\n        name: updaterole\n        description: Update role\n        call: onelogin.updaterole\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/2/roles/{id}\n      name: deleterole\n      operations:\n      - method: DELETE\n        name: deleterole\n        description: Delete role\n        call: onelogin.deleterole\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/2/apps\n      name: listapps\n      operations:\n      - method: GET\n        name: listapps\n        description: List apps\n        call: onelogin.listapps\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/2/apps\n      name: createapp\n      operations:\n      - method: POST\n        name: createapp\n        description: Create app\n        call: onelogin.createapp\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/2/apps/{id}\n      name: getapp\n      operations:\n      - method: GET\n        name: getapp\n        description: Get app by ID\n    \
  \    call: onelogin.getapp\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/2/apps/{id}\n      name: updateapp\n      operations:\n      - method: PUT\n        name: updateapp\n        description: Update app\n        call: onelogin.updateapp\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/2/apps/{id}\n      name: deleteapp\n      operations:\n      - method: DELETE\n        name: deleteapp\n        description: Delete app\n        call: onelogin.deleteapp\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/1/saml_assertion\n      name: generatesamlassertion\n      operations:\n      - method: POST\n        name: generatesamlassertion\n        description: Generate SAML assertion\n        call: onelogin.generatesamlassertion\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/1/saml_assertion/verify_factor\n      name: verifysamlfactor\n\
  \      operations:\n      - method: POST\n        name: verifysamlfactor\n        description: Verify factor for SAML\n        call: onelogin.verifysamlfactor\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/1/users/{id}/otp_devices\n      name: getotpdevices\n      operations:\n      - method: GET\n        name: getotpdevices\n        description: Get available auth factors\n        call: onelogin.getotpdevices\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/1/users/{id}/otp_devices\n      name: enrollfactor\n      operations:\n      - method: POST\n        name: enrollfactor\n        description: Enroll auth factor\n        call: onelogin.enrollfactor\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: onelogin-mcp\n    transport: http\n    description: MCP adapter for OneLogin API for AI agent use.\n    tools:\n    - name: generatetoken\n\
  \      description: Generate access token\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: onelogin.generatetoken\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: revoketoken\n      description: Revoke access token\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: onelogin.revoketoken\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listusers\n      description: List users\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: onelogin.listusers\n      with:\n        limit: tools.limit\n        page: tools.page\n      inputParameters:\n      - name: limit\n        type: integer\n        description: limit\n      - name: page\n        type: integer\n        description: page\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createuser\n\
  \      description: Create user\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: onelogin.createuser\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getuser\n      description: Get user by ID\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: onelogin.getuser\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateuser\n      description: Update user by ID\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: onelogin.updateuser\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteuser\n      description: Delete user by ID\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: onelogin.deleteuser\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getuserapps\n\
  \      description: Get apps for a user\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: onelogin.getuserapps\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getuserroles\n      description: Get roles for a user\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: onelogin.getuserroles\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: assignuserrole\n      description: Assign role to user\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: onelogin.assignuserrole\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: removeuserrole\n      description: Remove role from user\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: onelogin.removeuserrole\n      outputParameters:\n      - type:\
  \ object\n        mapping: $.\n    - name: setuserpassword\n      description: Set user password\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: onelogin.setuserpassword\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: setusercustomattribute\n      description: Set custom attribute\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: onelogin.setusercustomattribute\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: setuserstate\n      description: Set user state\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: onelogin.setuserstate\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: logoutuser\n      description: Log user out\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call:\
  \ onelogin.logoutuser\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: lockuser\n      description: Lock user account\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: onelogin.lockuser\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getroles\n      description: Get roles\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: onelogin.getroles\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listrolesv2\n      description: List roles (v2)\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: onelogin.listrolesv2\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createrole\n      description: Create role\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call:\
  \ onelogin.createrole\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getrole\n      description: Get role by ID\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: onelogin.getrole\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updaterole\n      description: Update role\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: onelogin.updaterole\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleterole\n      description: Delete role\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: onelogin.deleterole\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listapps\n      description: List apps\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: onelogin.listapps\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createapp\n      description: Create app\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: onelogin.createapp\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getapp\n      description: Get app by ID\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: onelogin.getapp\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateapp\n      description: Update app\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: onelogin.updateapp\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteapp\n      description: Delete app\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: onelogin.deleteapp\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: generatesamlassertion\n      description: Generate SAML assertion\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: onelogin.generatesamlassertion\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: verifysamlfactor\n      description: Verify factor for SAML\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: onelogin.verifysamlfactor\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getotpdevices\n      description: Get available auth factors\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: onelogin.getotpdevices\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: enrollfactor\n      description: Enroll auth factor\n      hints:\n        readOnly: false\n        destructive: false\n\
  \        idempotent: false\n      call: onelogin.enrollfactor\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    ONELOGIN_TOKEN: ONELOGIN_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/onelogin/refs/heads/main/capabilities/onelogin-capability.yaml
tags:
- Onelogin
- API
tools:
- description: Generate access token
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: generatetoken
- description: Revoke access token
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: revoketoken
- description: List users
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listusers
- description: Create user
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createuser
- description: Get user by ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getuser
- description: Update user by ID
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateuser
- description: Delete user by ID
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteuser
- description: Get apps for a user
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getuserapps
- description: Get roles for a user
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getuserroles
- description: Assign role to user
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: assignuserrole
- description: Remove role from user
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: removeuserrole
- description: Set user password
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: setuserpassword
- description: Set custom attribute
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: setusercustomattribute
- description: Set user state
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: setuserstate
- description: Log user out
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: logoutuser
- description: Lock user account
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: lockuser
- description: Get roles
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getroles
- description: List roles (v2)
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listrolesv2
- description: Create role
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createrole
- description: Get role by ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getrole
- description: Update role
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updaterole
- description: Delete role
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleterole
- description: List apps
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listapps
- description: Create app
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createapp
- description: Get app by ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getapp
- description: Update app
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateapp
- description: Delete app
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteapp
- description: Generate SAML assertion
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: generatesamlassertion
- description: Verify factor for SAML
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: verifysamlfactor
- description: Get available auth factors
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getotpdevices
- description: Enroll auth factor
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: enrollfactor
---
