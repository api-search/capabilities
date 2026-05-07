---
categories: []
consumed_apis: []
description: REST API for ForgeRock Access Management (AM) providing authentication, authorization, session management, and policy evaluation. Supports OAuth 2.0 and OpenID Connect flows, authentication trees/journeys, policy-based authorization decisions, and realm management.
layout: capability
name: ForgeRock Access Management API
operations:
- description: ForgeRock Authenticate a user
  method: POST
  name: authenticate
  path: /json/realms/root/realms/{realm}/authenticate
- description: ForgeRock Query sessions
  method: GET
  name: querysessions
  path: /json/realms/root/realms/{realm}/sessions
- description: ForgeRock Perform a session action
  method: POST
  name: sessionaction
  path: /json/realms/root/realms/{realm}/sessions
- description: ForgeRock List authorization policies
  method: GET
  name: listpolicies
  path: /json/realms/root/realms/{realm}/policies
- description: ForgeRock Create a policy or evaluate policies
  method: POST
  name: createpolicyorevaluate
  path: /json/realms/root/realms/{realm}/policies
- description: ForgeRock Get a policy
  method: GET
  name: getpolicy
  path: /json/realms/root/realms/{realm}/policies/{policyName}
- description: ForgeRock Update a policy
  method: PUT
  name: updatepolicy
  path: /json/realms/root/realms/{realm}/policies/{policyName}
- description: ForgeRock Delete a policy
  method: DELETE
  name: deletepolicy
  path: /json/realms/root/realms/{realm}/policies/{policyName}
- description: ForgeRock List resource types
  method: GET
  name: listresourcetypes
  path: /json/realms/root/realms/{realm}/resourcetypes
- description: ForgeRock Create a resource type
  method: POST
  name: createresourcetype
  path: /json/realms/root/realms/{realm}/resourcetypes
- description: ForgeRock Get a resource type
  method: GET
  name: getresourcetype
  path: /json/realms/root/realms/{realm}/resourcetypes/{resourceTypeId}
- description: ForgeRock Update a resource type
  method: PUT
  name: updateresourcetype
  path: /json/realms/root/realms/{realm}/resourcetypes/{resourceTypeId}
- description: ForgeRock Delete a resource type
  method: DELETE
  name: deleteresourcetype
  path: /json/realms/root/realms/{realm}/resourcetypes/{resourceTypeId}
- description: ForgeRock List realms
  method: GET
  name: listrealms
  path: /json/global-config/realms
- description: ForgeRock Create a realm
  method: POST
  name: createrealm
  path: /json/global-config/realms
- description: ForgeRock Get a realm
  method: GET
  name: getrealm
  path: /json/global-config/realms/{realmName}
- description: ForgeRock Update a realm
  method: PUT
  name: updaterealm
  path: /json/global-config/realms/{realmName}
- description: ForgeRock Delete a realm
  method: DELETE
  name: deleterealm
  path: /json/global-config/realms/{realmName}
- description: ForgeRock List scripts
  method: GET
  name: listscripts
  path: /json/realms/root/realms/{realm}/scripts
- description: ForgeRock Get a script
  method: GET
  name: getscript
  path: /json/realms/root/realms/{realm}/scripts/{scriptId}
- description: ForgeRock OAuth 2.0 authorization endpoint
  method: GET
  name: oauth2authorize
  path: /oauth2/realms/root/realms/{realm}/authorize
- description: ForgeRock OAuth 2.0 token endpoint
  method: POST
  name: oauth2token
  path: /oauth2/realms/root/realms/{realm}/access_token
- description: ForgeRock OAuth 2.0 token introspection
  method: GET
  name: oauth2tokeninfo
  path: /oauth2/realms/root/realms/{realm}/tokeninfo
- description: ForgeRock OpenID Connect UserInfo endpoint
  method: GET
  name: oidcuserinfo
  path: /oauth2/realms/root/realms/{realm}/userinfo
- description: ForgeRock OpenID Connect discovery
  method: GET
  name: oidcdiscovery
  path: /.well-known/openid-configuration
personas: []
provider_name: ForgeRock
provider_slug: forgerock
search_terms:
- listpolicies
- oauth2token
- updateresourcetype
- listscripts
- api
- oauth2authorize
- forgerock create a realm
- updaterealm
- identity management
- deleteresourcetype
- authentication
- forgerock get a resource type
- deletepolicy
- oidcuserinfo
- forgerock openid connect discovery
- getpolicy
- updatepolicy
- forgerock create a policy or evaluate policies
- forgerock list resource types
- forgerock create a resource type
- forgerock get a realm
- forgerock update a realm
- forgerock oauth 2.0 token introspection
- identity governance
- openid connect
- createresourcetype
- createpolicyorevaluate
- oidcdiscovery
- authenticate
- forgerock openid connect userinfo endpoint
- forgerock update a resource type
- forgerock delete a resource type
- forgerock delete a realm
- sessionaction
- forgerock oauth 2.0 authorization endpoint
- forgerock
- forgerock list authorization policies
- forgerock get a policy
- listrealms
- forgerock get a script
- authorization
- deleterealm
- getrealm
- getresourcetype
- access management
- createrealm
- forgerock list scripts
- forgerock query sessions
- forgerock oauth 2.0 token endpoint
- forgerock update a policy
- forgerock list realms
- forgerock authenticate a user
- forgerock perform a session action
- querysessions
- getscript
- oauth
- oauth2tokeninfo
- forgerock delete a policy
- listresourcetypes
slug: forgerock-capability
source_filename: forgerock-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: ForgeRock Access Management API\n  description: REST API for ForgeRock Access Management (AM) providing authentication, authorization, session management,\n    and policy evaluation. Supports OAuth 2.0 and OpenID Connect flows, authentication trees/journeys, policy-based authorization\n    decisions, and realm management.\n  tags:\n  - Forgerock\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: forgerock\n    baseUri: https://am.example.com/am\n    description: ForgeRock Access Management API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: iPlanetDirectoryPro\n      value: '{{FORGEROCK_TOKEN}}'\n    resources:\n    - name: json-realms-root-realms-realm-authenticate\n      path: /json/realms/root/realms/{realm}/authenticate\n      operations:\n      - name: authenticate\n        method: POST\n        description: ForgeRock Authenticate\
  \ a user\n        inputParameters:\n        - name: authIndexType\n          in: query\n          type: string\n          description: Type of authentication index\n        - name: authIndexValue\n          in: query\n          type: string\n          description: Name of the authentication tree or module\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: json-realms-root-realms-realm-sessions\n      path: /json/realms/root/realms/{realm}/sessions\n      operations:\n      - name: querysessions\n        method: GET\n        description: ForgeRock Query sessions\n        inputParameters:\n        - name: _queryFilter\n          in: query\n          type: string\n          description: CREST query filter for sessions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: sessionaction\n        method: POST\n      \
  \  description: ForgeRock Perform a session action\n        inputParameters:\n        - name: _action\n          in: query\n          type: string\n          required: true\n          description: The session action to perform\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: json-realms-root-realms-realm-policies\n      path: /json/realms/root/realms/{realm}/policies\n      operations:\n      - name: listpolicies\n        method: GET\n        description: ForgeRock List authorization policies\n        inputParameters:\n        - name: _queryFilter\n          in: query\n          type: string\n          description: CREST query filter expression\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createpolicyorevaluate\n        method: POST\n        description: ForgeRock Create a policy or evaluate policies\n\
  \        inputParameters:\n        - name: _action\n          in: query\n          type: string\n          description: Action to perform (evaluate or evaluateTree)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: json-realms-root-realms-realm-policies-policynam\n      path: /json/realms/root/realms/{realm}/policies/{policyName}\n      operations:\n      - name: getpolicy\n        method: GET\n        description: ForgeRock Get a policy\n        inputParameters:\n        - name: policyName\n          in: path\n          type: string\n          required: true\n          description: The policy name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatepolicy\n        method: PUT\n        description: ForgeRock Update a policy\n        inputParameters:\n        - name: policyName\n          in: path\n    \
  \      type: string\n          required: true\n          description: The policy name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletepolicy\n        method: DELETE\n        description: ForgeRock Delete a policy\n        inputParameters:\n        - name: policyName\n          in: path\n          type: string\n          required: true\n          description: The policy name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: json-realms-root-realms-realm-resourcetypes\n      path: /json/realms/root/realms/{realm}/resourcetypes\n      operations:\n      - name: listresourcetypes\n        method: GET\n        description: ForgeRock List resource types\n        inputParameters:\n        - name: _queryFilter\n          in: query\n          type: string\n          description: CREST query filter\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createresourcetype\n        method: POST\n        description: ForgeRock Create a resource type\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: json-realms-root-realms-realm-resourcetypes-reso\n      path: /json/realms/root/realms/{realm}/resourcetypes/{resourceTypeId}\n      operations:\n      - name: getresourcetype\n        method: GET\n        description: ForgeRock Get a resource type\n        inputParameters:\n        - name: resourceTypeId\n          in: path\n          type: string\n          required: true\n          description: The resource type UUID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateresourcetype\n        method: PUT\n        description: ForgeRock Update a\
  \ resource type\n        inputParameters:\n        - name: resourceTypeId\n          in: path\n          type: string\n          required: true\n          description: The resource type UUID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteresourcetype\n        method: DELETE\n        description: ForgeRock Delete a resource type\n        inputParameters:\n        - name: resourceTypeId\n          in: path\n          type: string\n          required: true\n          description: The resource type UUID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: json-global-config-realms\n      path: /json/global-config/realms\n      operations:\n      - name: listrealms\n        method: GET\n        description: ForgeRock List realms\n        inputParameters:\n        - name: _queryFilter\n          in: query\n\
  \          type: string\n          description: CREST query filter for realms\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createrealm\n        method: POST\n        description: ForgeRock Create a realm\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: json-global-config-realms-realmname\n      path: /json/global-config/realms/{realmName}\n      operations:\n      - name: getrealm\n        method: GET\n        description: ForgeRock Get a realm\n        inputParameters:\n        - name: realmName\n          in: path\n          type: string\n          required: true\n          description: The realm name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updaterealm\n        method: PUT\n        description: ForgeRock\
  \ Update a realm\n        inputParameters:\n        - name: realmName\n          in: path\n          type: string\n          required: true\n          description: The realm name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleterealm\n        method: DELETE\n        description: ForgeRock Delete a realm\n        inputParameters:\n        - name: realmName\n          in: path\n          type: string\n          required: true\n          description: The realm name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: json-realms-root-realms-realm-scripts\n      path: /json/realms/root/realms/{realm}/scripts\n      operations:\n      - name: listscripts\n        method: GET\n        description: ForgeRock List scripts\n        inputParameters:\n        - name: _queryFilter\n          in: query\n          type:\
  \ string\n          description: CREST query filter\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: json-realms-root-realms-realm-scripts-scriptid\n      path: /json/realms/root/realms/{realm}/scripts/{scriptId}\n      operations:\n      - name: getscript\n        method: GET\n        description: ForgeRock Get a script\n        inputParameters:\n        - name: scriptId\n          in: path\n          type: string\n          required: true\n          description: The script UUID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: oauth2-realms-root-realms-realm-authorize\n      path: /oauth2/realms/root/realms/{realm}/authorize\n      operations:\n      - name: oauth2authorize\n        method: GET\n        description: ForgeRock OAuth 2.0 authorization endpoint\n        inputParameters:\n        - name: client_id\n\
  \          in: query\n          type: string\n          required: true\n        - name: response_type\n          in: query\n          type: string\n          required: true\n        - name: redirect_uri\n          in: query\n          type: string\n          required: true\n        - name: scope\n          in: query\n          type: string\n        - name: state\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: oauth2-realms-root-realms-realm-access-token\n      path: /oauth2/realms/root/realms/{realm}/access_token\n      operations:\n      - name: oauth2token\n        method: POST\n        description: ForgeRock OAuth 2.0 token endpoint\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: oauth2-realms-root-realms-realm-tokeninfo\n      path: /oauth2/realms/root/realms/{realm}/tokeninfo\n\
  \      operations:\n      - name: oauth2tokeninfo\n        method: GET\n        description: ForgeRock OAuth 2.0 token introspection\n        inputParameters:\n        - name: access_token\n          in: query\n          type: string\n          required: true\n          description: The access token to introspect\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: oauth2-realms-root-realms-realm-userinfo\n      path: /oauth2/realms/root/realms/{realm}/userinfo\n      operations:\n      - name: oidcuserinfo\n        method: GET\n        description: ForgeRock OpenID Connect UserInfo endpoint\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: well-known-openid-configuration\n      path: /.well-known/openid-configuration\n      operations:\n      - name: oidcdiscovery\n        method: GET\n        description: ForgeRock\
  \ OpenID Connect discovery\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: forgerock-rest\n    description: REST adapter for ForgeRock Access Management API.\n    resources:\n    - path: /json/realms/root/realms/{realm}/authenticate\n      name: authenticate\n      operations:\n      - method: POST\n        name: authenticate\n        description: ForgeRock Authenticate a user\n        call: forgerock.authenticate\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /json/realms/root/realms/{realm}/sessions\n      name: querysessions\n      operations:\n      - method: GET\n        name: querysessions\n        description: ForgeRock Query sessions\n        call: forgerock.querysessions\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /json/realms/root/realms/{realm}/sessions\n \
  \     name: sessionaction\n      operations:\n      - method: POST\n        name: sessionaction\n        description: ForgeRock Perform a session action\n        call: forgerock.sessionaction\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /json/realms/root/realms/{realm}/policies\n      name: listpolicies\n      operations:\n      - method: GET\n        name: listpolicies\n        description: ForgeRock List authorization policies\n        call: forgerock.listpolicies\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /json/realms/root/realms/{realm}/policies\n      name: createpolicyorevaluate\n      operations:\n      - method: POST\n        name: createpolicyorevaluate\n        description: ForgeRock Create a policy or evaluate policies\n        call: forgerock.createpolicyorevaluate\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /json/realms/root/realms/{realm}/policies/{policyName}\n\
  \      name: getpolicy\n      operations:\n      - method: GET\n        name: getpolicy\n        description: ForgeRock Get a policy\n        call: forgerock.getpolicy\n        with:\n          policyName: rest.policyName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /json/realms/root/realms/{realm}/policies/{policyName}\n      name: updatepolicy\n      operations:\n      - method: PUT\n        name: updatepolicy\n        description: ForgeRock Update a policy\n        call: forgerock.updatepolicy\n        with:\n          policyName: rest.policyName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /json/realms/root/realms/{realm}/policies/{policyName}\n      name: deletepolicy\n      operations:\n      - method: DELETE\n        name: deletepolicy\n        description: ForgeRock Delete a policy\n        call: forgerock.deletepolicy\n        with:\n          policyName: rest.policyName\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /json/realms/root/realms/{realm}/resourcetypes\n      name: listresourcetypes\n      operations:\n      - method: GET\n        name: listresourcetypes\n        description: ForgeRock List resource types\n        call: forgerock.listresourcetypes\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /json/realms/root/realms/{realm}/resourcetypes\n      name: createresourcetype\n      operations:\n      - method: POST\n        name: createresourcetype\n        description: ForgeRock Create a resource type\n        call: forgerock.createresourcetype\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /json/realms/root/realms/{realm}/resourcetypes/{resourceTypeId}\n      name: getresourcetype\n      operations:\n      - method: GET\n        name: getresourcetype\n        description: ForgeRock Get a resource type\n        call: forgerock.getresourcetype\n        with:\n\
  \          resourceTypeId: rest.resourceTypeId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /json/realms/root/realms/{realm}/resourcetypes/{resourceTypeId}\n      name: updateresourcetype\n      operations:\n      - method: PUT\n        name: updateresourcetype\n        description: ForgeRock Update a resource type\n        call: forgerock.updateresourcetype\n        with:\n          resourceTypeId: rest.resourceTypeId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /json/realms/root/realms/{realm}/resourcetypes/{resourceTypeId}\n      name: deleteresourcetype\n      operations:\n      - method: DELETE\n        name: deleteresourcetype\n        description: ForgeRock Delete a resource type\n        call: forgerock.deleteresourcetype\n        with:\n          resourceTypeId: rest.resourceTypeId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /json/global-config/realms\n\
  \      name: listrealms\n      operations:\n      - method: GET\n        name: listrealms\n        description: ForgeRock List realms\n        call: forgerock.listrealms\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /json/global-config/realms\n      name: createrealm\n      operations:\n      - method: POST\n        name: createrealm\n        description: ForgeRock Create a realm\n        call: forgerock.createrealm\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /json/global-config/realms/{realmName}\n      name: getrealm\n      operations:\n      - method: GET\n        name: getrealm\n        description: ForgeRock Get a realm\n        call: forgerock.getrealm\n        with:\n          realmName: rest.realmName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /json/global-config/realms/{realmName}\n      name: updaterealm\n      operations:\n      - method: PUT\n    \
  \    name: updaterealm\n        description: ForgeRock Update a realm\n        call: forgerock.updaterealm\n        with:\n          realmName: rest.realmName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /json/global-config/realms/{realmName}\n      name: deleterealm\n      operations:\n      - method: DELETE\n        name: deleterealm\n        description: ForgeRock Delete a realm\n        call: forgerock.deleterealm\n        with:\n          realmName: rest.realmName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /json/realms/root/realms/{realm}/scripts\n      name: listscripts\n      operations:\n      - method: GET\n        name: listscripts\n        description: ForgeRock List scripts\n        call: forgerock.listscripts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /json/realms/root/realms/{realm}/scripts/{scriptId}\n      name: getscript\n      operations:\n\
  \      - method: GET\n        name: getscript\n        description: ForgeRock Get a script\n        call: forgerock.getscript\n        with:\n          scriptId: rest.scriptId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /oauth2/realms/root/realms/{realm}/authorize\n      name: oauth2authorize\n      operations:\n      - method: GET\n        name: oauth2authorize\n        description: ForgeRock OAuth 2.0 authorization endpoint\n        call: forgerock.oauth2authorize\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /oauth2/realms/root/realms/{realm}/access_token\n      name: oauth2token\n      operations:\n      - method: POST\n        name: oauth2token\n        description: ForgeRock OAuth 2.0 token endpoint\n        call: forgerock.oauth2token\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /oauth2/realms/root/realms/{realm}/tokeninfo\n      name: oauth2tokeninfo\n \
  \     operations:\n      - method: GET\n        name: oauth2tokeninfo\n        description: ForgeRock OAuth 2.0 token introspection\n        call: forgerock.oauth2tokeninfo\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /oauth2/realms/root/realms/{realm}/userinfo\n      name: oidcuserinfo\n      operations:\n      - method: GET\n        name: oidcuserinfo\n        description: ForgeRock OpenID Connect UserInfo endpoint\n        call: forgerock.oidcuserinfo\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /.well-known/openid-configuration\n      name: oidcdiscovery\n      operations:\n      - method: GET\n        name: oidcdiscovery\n        description: ForgeRock OpenID Connect discovery\n        call: forgerock.oidcdiscovery\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: forgerock-mcp\n    transport: http\n    description: MCP adapter\
  \ for ForgeRock Access Management API for AI agent use.\n    tools:\n    - name: authenticate\n      description: ForgeRock Authenticate a user\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: forgerock.authenticate\n      with:\n        authIndexType: tools.authIndexType\n        authIndexValue: tools.authIndexValue\n      inputParameters:\n      - name: authIndexType\n        type: string\n        description: Type of authentication index\n      - name: authIndexValue\n        type: string\n        description: Name of the authentication tree or module\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: querysessions\n      description: ForgeRock Query sessions\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: forgerock.querysessions\n      with:\n        _queryFilter: tools._queryFilter\n      inputParameters:\n      - name: _queryFilter\n   \
  \     type: string\n        description: CREST query filter for sessions\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: sessionaction\n      description: ForgeRock Perform a session action\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: forgerock.sessionaction\n      with:\n        _action: tools._action\n      inputParameters:\n      - name: _action\n        type: string\n        description: The session action to perform\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listpolicies\n      description: ForgeRock List authorization policies\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: forgerock.listpolicies\n      with:\n        _queryFilter: tools._queryFilter\n      inputParameters:\n      - name: _queryFilter\n        type: string\n        description: CREST query filter expression\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createpolicyorevaluate\n      description: ForgeRock Create a policy or evaluate policies\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: forgerock.createpolicyorevaluate\n      with:\n        _action: tools._action\n      inputParameters:\n      - name: _action\n        type: string\n        description: Action to perform (evaluate or evaluateTree)\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getpolicy\n      description: ForgeRock Get a policy\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: forgerock.getpolicy\n      with:\n        policyName: tools.policyName\n      inputParameters:\n      - name: policyName\n        type: string\n        description: The policy name\n        required: true\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: updatepolicy\n      description: ForgeRock Update a policy\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: forgerock.updatepolicy\n      with:\n        policyName: tools.policyName\n      inputParameters:\n      - name: policyName\n        type: string\n        description: The policy name\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletepolicy\n      description: ForgeRock Delete a policy\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: forgerock.deletepolicy\n      with:\n        policyName: tools.policyName\n      inputParameters:\n      - name: policyName\n        type: string\n        description: The policy name\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listresourcetypes\n      description: ForgeRock List resource types\n     \
  \ hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: forgerock.listresourcetypes\n      with:\n        _queryFilter: tools._queryFilter\n      inputParameters:\n      - name: _queryFilter\n        type: string\n        description: CREST query filter\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createresourcetype\n      description: ForgeRock Create a resource type\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: forgerock.createresourcetype\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getresourcetype\n      description: ForgeRock Get a resource type\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: forgerock.getresourcetype\n      with:\n        resourceTypeId: tools.resourceTypeId\n      inputParameters:\n      - name: resourceTypeId\n        type: string\n\
  \        description: The resource type UUID\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateresourcetype\n      description: ForgeRock Update a resource type\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: forgerock.updateresourcetype\n      with:\n        resourceTypeId: tools.resourceTypeId\n      inputParameters:\n      - name: resourceTypeId\n        type: string\n        description: The resource type UUID\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteresourcetype\n      description: ForgeRock Delete a resource type\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: forgerock.deleteresourcetype\n      with:\n        resourceTypeId: tools.resourceTypeId\n      inputParameters:\n      - name: resourceTypeId\n        type: string\n        description:\
  \ The resource type UUID\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listrealms\n      description: ForgeRock List realms\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: forgerock.listrealms\n      with:\n        _queryFilter: tools._queryFilter\n      inputParameters:\n      - name: _queryFilter\n        type: string\n        description: CREST query filter for realms\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createrealm\n      description: ForgeRock Create a realm\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: forgerock.createrealm\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getrealm\n      description: ForgeRock Get a realm\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: forgerock.getrealm\n\
  \      with:\n        realmName: tools.realmName\n      inputParameters:\n      - name: realmName\n        type: string\n        description: The realm name\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updaterealm\n      description: ForgeRock Update a realm\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: forgerock.updaterealm\n      with:\n        realmName: tools.realmName\n      inputParameters:\n      - name: realmName\n        type: string\n        description: The realm name\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleterealm\n      description: ForgeRock Delete a realm\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: forgerock.deleterealm\n      with:\n        realmName: tools.realmName\n      inputParameters:\n      - name: realmName\n       \
  \ type: string\n        description: The realm name\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listscripts\n      description: ForgeRock List scripts\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: forgerock.listscripts\n      with:\n        _queryFilter: tools._queryFilter\n      inputParameters:\n      - name: _queryFilter\n        type: string\n        description: CREST query filter\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getscript\n      description: ForgeRock Get a script\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: forgerock.getscript\n      with:\n        scriptId: tools.scriptId\n      inputParameters:\n      - name: scriptId\n        type: string\n        description: The script UUID\n        required: true\n      outputParameters:\n      - type: object\n    \
  \    mapping: $.\n    - name: oauth2authorize\n      description: ForgeRock OAuth 2.0 authorization endpoint\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: forgerock.oauth2authorize\n      with:\n        client_id: tools.client_id\n        response_type: tools.response_type\n        redirect_uri: tools.redirect_uri\n        scope: tools.scope\n        state: tools.state\n      inputParameters:\n      - name: client_id\n        type: string\n        description: client_id\n        required: true\n      - name: response_type\n        type: string\n        description: response_type\n        required: true\n      - name: redirect_uri\n        type: string\n        description: redirect_uri\n        required: true\n      - name: scope\n        type: string\n        description: scope\n      - name: state\n        type: string\n        description: state\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name:\
  \ oauth2token\n      description: ForgeRock OAuth 2.0 token endpoint\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: forgerock.oauth2token\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: oauth2tokeninfo\n      description: ForgeRock OAuth 2.0 token introspection\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: forgerock.oauth2tokeninfo\n      with:\n        access_token: tools.access_token\n      inputParameters:\n      - name: access_token\n        type: string\n        description: The access token to introspect\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: oidcuserinfo\n      description: ForgeRock OpenID Connect UserInfo endpoint\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: forgerock.oidcuserinfo\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: oidcdiscovery\n      description: ForgeRock OpenID Connect discovery\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: forgerock.oidcdiscovery\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    FORGEROCK_TOKEN: FORGEROCK_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/forgerock/refs/heads/main/capabilities/forgerock-capability.yaml
tags:
- Forgerock
- API
tools:
- description: ForgeRock Authenticate a user
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: authenticate
- description: ForgeRock Query sessions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: querysessions
- description: ForgeRock Perform a session action
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: sessionaction
- description: ForgeRock List authorization policies
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listpolicies
- description: ForgeRock Create a policy or evaluate policies
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createpolicyorevaluate
- description: ForgeRock Get a policy
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getpolicy
- description: ForgeRock Update a policy
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatepolicy
- description: ForgeRock Delete a policy
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletepolicy
- description: ForgeRock List resource types
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listresourcetypes
- description: ForgeRock Create a resource type
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createresourcetype
- description: ForgeRock Get a resource type
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getresourcetype
- description: ForgeRock Update a resource type
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateresourcetype
- description: ForgeRock Delete a resource type
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteresourcetype
- description: ForgeRock List realms
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listrealms
- description: ForgeRock Create a realm
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createrealm
- description: ForgeRock Get a realm
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getrealm
- description: ForgeRock Update a realm
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updaterealm
- description: ForgeRock Delete a realm
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleterealm
- description: ForgeRock List scripts
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listscripts
- description: ForgeRock Get a script
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getscript
- description: ForgeRock OAuth 2.0 authorization endpoint
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: oauth2authorize
- description: ForgeRock OAuth 2.0 token endpoint
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: oauth2token
- description: ForgeRock OAuth 2.0 token introspection
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: oauth2tokeninfo
- description: ForgeRock OpenID Connect UserInfo endpoint
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: oidcuserinfo
- description: ForgeRock OpenID Connect discovery
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: oidcdiscovery
---
