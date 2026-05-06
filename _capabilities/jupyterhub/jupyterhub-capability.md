---
categories: []
consumed_apis: []
description: REST API for JupyterHub, the multi-user server for Jupyter notebooks. Provides endpoints for managing users, groups, services, shared servers, OAuth2 authorization, the proxy, and the hub itself. JupyterHub spawns, manages, and proxies multiple instances of the single-user Jupyter notebook server.
layout: capability
name: JupyterHub REST API
operations:
- description: JupyterHub Get version
  method: GET
  name: gethubversion
  path: /
- description: JupyterHub Get detailed info
  method: GET
  name: gethubinfo
  path: /info
- description: JupyterHub List users
  method: GET
  name: listusers
  path: /users
- description: JupyterHub Create users
  method: POST
  name: createusers
  path: /users
- description: JupyterHub Get user
  method: GET
  name: getuser
  path: /users/{name}
- description: JupyterHub Create user
  method: POST
  name: createuser
  path: /users/{name}
- description: JupyterHub Update user
  method: PATCH
  name: updateuser
  path: /users/{name}
- description: JupyterHub Delete user
  method: DELETE
  name: deleteuser
  path: /users/{name}
- description: JupyterHub Notify user activity
  method: POST
  name: notifyuseractivity
  path: /users/{name}/activity
- description: JupyterHub Start user server
  method: POST
  name: startuserserver
  path: /users/{name}/server
- description: JupyterHub Stop user server
  method: DELETE
  name: stopuserserver
  path: /users/{name}/server
- description: JupyterHub Start named server
  method: POST
  name: startnamedserver
  path: /users/{name}/servers/{server_name}
- description: JupyterHub Stop named server
  method: DELETE
  name: stopnamedserver
  path: /users/{name}/servers/{server_name}
- description: JupyterHub List user tokens
  method: GET
  name: listusertokens
  path: /users/{name}/tokens
- description: JupyterHub Create user token
  method: POST
  name: createusertoken
  path: /users/{name}/tokens
- description: JupyterHub Get user token
  method: GET
  name: getusertoken
  path: /users/{name}/tokens/{token_id}
- description: JupyterHub Revoke user token
  method: DELETE
  name: revokeusertoken
  path: /users/{name}/tokens/{token_id}
- description: JupyterHub List groups
  method: GET
  name: listgroups
  path: /groups
- description: JupyterHub Create groups
  method: POST
  name: creategroups
  path: /groups
- description: JupyterHub Get group
  method: GET
  name: getgroup
  path: /groups/{name}
- description: JupyterHub Create group
  method: POST
  name: creategroup
  path: /groups/{name}
- description: JupyterHub Delete group
  method: DELETE
  name: deletegroup
  path: /groups/{name}
- description: JupyterHub Add users to group
  method: POST
  name: addgroupusers
  path: /groups/{name}/users
- description: JupyterHub Remove users from group
  method: DELETE
  name: removegroupusers
  path: /groups/{name}/users
- description: JupyterHub List services
  method: GET
  name: listservices
  path: /services
- description: JupyterHub Get service
  method: GET
  name: getservice
  path: /services/{name}
- description: JupyterHub Get proxy routes
  method: GET
  name: getproxyroutes
  path: /proxy
- description: JupyterHub Sync proxy
  method: POST
  name: syncproxy
  path: /proxy
- description: JupyterHub Update proxy
  method: PATCH
  name: updateproxy
  path: /proxy
- description: JupyterHub Request token
  method: POST
  name: requesttoken
  path: /authorizations/token
- description: JupyterHub Identify token
  method: GET
  name: identifytoken
  path: /authorizations/token/{token}
- description: JupyterHub Identify cookie
  method: GET
  name: identifycookie
  path: /authorizations/cookie/{cookie_name}/{cookie_value}
- description: JupyterHub OAuth2 authorize
  method: GET
  name: oauth2authorize
  path: /oauth2/authorize
- description: JupyterHub OAuth2 token
  method: POST
  name: oauth2token
  path: /oauth2/token
- description: JupyterHub Shutdown
  method: POST
  name: shutdownhub
  path: /shutdown
personas: []
provider_name: JupyterHub
provider_slug: jupyterhub
search_terms:
- jupyterhub get user
- education
- jupyterhub shutdown
- jupyterhub oauth2 authorize
- jupyterhub get detailed info
- getusertoken
- api
- jupyterhub create groups
- syncproxy
- hub
- createusers
- getuser
- jupyterhub delete user
- listusertokens
- jupyterhub revoke user token
- updateuser
- multi-user
- data science
- deleteuser
- jupyterhub create user
- creategroup
- startnamedserver
- createuser
- creategroups
- jupyterhub get proxy routes
- removegroupusers
- oauth2authorize
- getservice
- jupyterhub
- gethubinfo
- jupyterhub list groups
- listgroups
- startuserserver
- notifyuseractivity
- jupyterhub start user server
- jupyterhub get user token
- jupyterhub request token
- jupyterhub list services
- authentication
- python
- jupyterhub identify cookie
- createusertoken
- listusers
- getgroup
- getproxyroutes
- identifycookie
- addgroupusers
- updateproxy
- jupyterhub identify token
- jupyterhub list users
- jupyterhub list user tokens
- shutdownhub
- stopuserserver
- revokeusertoken
- jupyterhub update proxy
- jupyterhub stop named server
- oauth2token
- jupyterhub update user
- jupyterhub oauth2 token
- jupyterhub remove users from group
- jupyterhub add users to group
- jupyterhub create user token
- jupyterhub get group
- notebooks
- deletegroup
- oauth2
- jupyterhub stop user server
- gethubversion
- jupyterhub notify user activity
- jupyterhub create users
- requesttoken
- stopnamedserver
- jupyterhub get service
- jupyterhub create group
- identifytoken
- jupyterhub delete group
- jupyterhub get version
- jupyterhub start named server
- jupyterhub sync proxy
- listservices
slug: jupyterhub-capability
source_filename: jupyterhub-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: JupyterHub REST API\n  description: REST API for JupyterHub, the multi-user server for Jupyter notebooks. Provides endpoints for managing users,\n    groups, services, shared servers, OAuth2 authorization, the proxy, and the hub itself. JupyterHub spawns, manages, and\n    proxies multiple instances of the single-user Jupyter notebook server.\n  tags:\n  - Jupyterhub\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: jupyterhub\n    baseUri: http://localhost:8000/hub/api\n    description: JupyterHub REST API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: Authorization\n      value: '{{JUPYTERHUB_TOKEN}}'\n    resources:\n    - name: resource\n      path: /\n      operations:\n      - name: gethubversion\n        method: GET\n        description: JupyterHub Get version\n        outputRawFormat: json\n        outputParameters:\n        -\
  \ name: result\n          type: object\n          value: $.\n    - name: info\n      path: /info\n      operations:\n      - name: gethubinfo\n        method: GET\n        description: JupyterHub Get detailed info\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users\n      path: /users\n      operations:\n      - name: listusers\n        method: GET\n        description: JupyterHub List users\n        inputParameters:\n        - name: state\n          in: query\n          type: string\n        - name: offset\n          in: query\n          type: integer\n        - name: limit\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createusers\n        method: POST\n        description: JupyterHub Create users\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: users-name\n      path: /users/{name}\n      operations:\n      - name: getuser\n        method: GET\n        description: JupyterHub Get user\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createuser\n        method: POST\n        description: JupyterHub Create user\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateuser\n        method: PATCH\n        description: JupyterHub Update user\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n    \
  \      required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteuser\n        method: DELETE\n        description: JupyterHub Delete user\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users-name-activity\n      path: /users/{name}/activity\n      operations:\n      - name: notifyuseractivity\n        method: POST\n        description: JupyterHub Notify user activity\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users-name-server\n      path: /users/{name}/server\n \
  \     operations:\n      - name: startuserserver\n        method: POST\n        description: JupyterHub Start user server\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: stopuserserver\n        method: DELETE\n        description: JupyterHub Stop user server\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users-name-servers-server-name\n      path: /users/{name}/servers/{server_name}\n      operations:\n      - name: startnamedserver\n        method: POST\n        description: JupyterHub Start named server\n        inputParameters:\n        - name: name\n          in: path\n\
  \          type: string\n          required: true\n        - name: server_name\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: stopnamedserver\n        method: DELETE\n        description: JupyterHub Stop named server\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n        - name: server_name\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users-name-tokens\n      path: /users/{name}/tokens\n      operations:\n      - name: listusertokens\n        method: GET\n        description: JupyterHub List user tokens\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n\
  \          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createusertoken\n        method: POST\n        description: JupyterHub Create user token\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users-name-tokens-token-id\n      path: /users/{name}/tokens/{token_id}\n      operations:\n      - name: getusertoken\n        method: GET\n        description: JupyterHub Get user token\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n        - name: token_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n      - name: revokeusertoken\n        method: DELETE\n        description: JupyterHub Revoke user token\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n        - name: token_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: groups\n      path: /groups\n      operations:\n      - name: listgroups\n        method: GET\n        description: JupyterHub List groups\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: creategroups\n        method: POST\n        description: JupyterHub Create groups\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n   \
  \ - name: groups-name\n      path: /groups/{name}\n      operations:\n      - name: getgroup\n        method: GET\n        description: JupyterHub Get group\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: creategroup\n        method: POST\n        description: JupyterHub Create group\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletegroup\n        method: DELETE\n        description: JupyterHub Delete group\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: groups-name-users\n      path: /groups/{name}/users\n      operations:\n      - name: addgroupusers\n        method: POST\n        description: JupyterHub Add users to group\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: removegroupusers\n        method: DELETE\n        description: JupyterHub Remove users from group\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: services\n      path: /services\n      operations:\n      - name: listservices\n        method: GET\n        description: JupyterHub\
  \ List services\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: services-name\n      path: /services/{name}\n      operations:\n      - name: getservice\n        method: GET\n        description: JupyterHub Get service\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: proxy\n      path: /proxy\n      operations:\n      - name: getproxyroutes\n        method: GET\n        description: JupyterHub Get proxy routes\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: syncproxy\n        method: POST\n        description: JupyterHub Sync proxy\n        outputRawFormat: json\n        outputParameters:\n       \
  \ - name: result\n          type: object\n          value: $.\n      - name: updateproxy\n        method: PATCH\n        description: JupyterHub Update proxy\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: authorizations-token\n      path: /authorizations/token\n      operations:\n      - name: requesttoken\n        method: POST\n        description: JupyterHub Request token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: authorizations-token-token\n      path: /authorizations/token/{token}\n      operations:\n      - name: identifytoken\n        method: GET\n        description: JupyterHub Identify token\n        inputParameters:\n        - name: token\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n    - name: authorizations-cookie-cookie-name-cookie-value\n      path: /authorizations/cookie/{cookie_name}/{cookie_value}\n      operations:\n      - name: identifycookie\n        method: GET\n        description: JupyterHub Identify cookie\n        inputParameters:\n        - name: cookie_name\n          in: path\n          type: string\n          required: true\n        - name: cookie_value\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: oauth2-authorize\n      path: /oauth2/authorize\n      operations:\n      - name: oauth2authorize\n        method: GET\n        description: JupyterHub OAuth2 authorize\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: oauth2-token\n      path: /oauth2/token\n\
  \      operations:\n      - name: oauth2token\n        method: POST\n        description: JupyterHub OAuth2 token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: shutdown\n      path: /shutdown\n      operations:\n      - name: shutdownhub\n        method: POST\n        description: JupyterHub Shutdown\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: jupyterhub-rest\n    description: REST adapter for JupyterHub REST API.\n    resources:\n    - path: /\n      name: gethubversion\n      operations:\n      - method: GET\n        name: gethubversion\n        description: JupyterHub Get version\n        call: jupyterhub.gethubversion\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /info\n      name: gethubinfo\n      operations:\n\
  \      - method: GET\n        name: gethubinfo\n        description: JupyterHub Get detailed info\n        call: jupyterhub.gethubinfo\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users\n      name: listusers\n      operations:\n      - method: GET\n        name: listusers\n        description: JupyterHub List users\n        call: jupyterhub.listusers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users\n      name: createusers\n      operations:\n      - method: POST\n        name: createusers\n        description: JupyterHub Create users\n        call: jupyterhub.createusers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users/{name}\n      name: getuser\n      operations:\n      - method: GET\n        name: getuser\n        description: JupyterHub Get user\n        call: jupyterhub.getuser\n        with:\n          name: rest.name\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /users/{name}\n      name: createuser\n      operations:\n      - method: POST\n        name: createuser\n        description: JupyterHub Create user\n        call: jupyterhub.createuser\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users/{name}\n      name: updateuser\n      operations:\n      - method: PATCH\n        name: updateuser\n        description: JupyterHub Update user\n        call: jupyterhub.updateuser\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users/{name}\n      name: deleteuser\n      operations:\n      - method: DELETE\n        name: deleteuser\n        description: JupyterHub Delete user\n        call: jupyterhub.deleteuser\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n\
  \    - path: /users/{name}/activity\n      name: notifyuseractivity\n      operations:\n      - method: POST\n        name: notifyuseractivity\n        description: JupyterHub Notify user activity\n        call: jupyterhub.notifyuseractivity\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users/{name}/server\n      name: startuserserver\n      operations:\n      - method: POST\n        name: startuserserver\n        description: JupyterHub Start user server\n        call: jupyterhub.startuserserver\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users/{name}/server\n      name: stopuserserver\n      operations:\n      - method: DELETE\n        name: stopuserserver\n        description: JupyterHub Stop user server\n        call: jupyterhub.stopuserserver\n        with:\n          name: rest.name\n        outputParameters:\n \
  \       - type: object\n          mapping: $.\n    - path: /users/{name}/servers/{server_name}\n      name: startnamedserver\n      operations:\n      - method: POST\n        name: startnamedserver\n        description: JupyterHub Start named server\n        call: jupyterhub.startnamedserver\n        with:\n          name: rest.name\n          server_name: rest.server_name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users/{name}/servers/{server_name}\n      name: stopnamedserver\n      operations:\n      - method: DELETE\n        name: stopnamedserver\n        description: JupyterHub Stop named server\n        call: jupyterhub.stopnamedserver\n        with:\n          name: rest.name\n          server_name: rest.server_name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users/{name}/tokens\n      name: listusertokens\n      operations:\n      - method: GET\n        name: listusertokens\n        description:\
  \ JupyterHub List user tokens\n        call: jupyterhub.listusertokens\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users/{name}/tokens\n      name: createusertoken\n      operations:\n      - method: POST\n        name: createusertoken\n        description: JupyterHub Create user token\n        call: jupyterhub.createusertoken\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users/{name}/tokens/{token_id}\n      name: getusertoken\n      operations:\n      - method: GET\n        name: getusertoken\n        description: JupyterHub Get user token\n        call: jupyterhub.getusertoken\n        with:\n          name: rest.name\n          token_id: rest.token_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users/{name}/tokens/{token_id}\n      name: revokeusertoken\n      operations:\n\
  \      - method: DELETE\n        name: revokeusertoken\n        description: JupyterHub Revoke user token\n        call: jupyterhub.revokeusertoken\n        with:\n          name: rest.name\n          token_id: rest.token_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /groups\n      name: listgroups\n      operations:\n      - method: GET\n        name: listgroups\n        description: JupyterHub List groups\n        call: jupyterhub.listgroups\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /groups\n      name: creategroups\n      operations:\n      - method: POST\n        name: creategroups\n        description: JupyterHub Create groups\n        call: jupyterhub.creategroups\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /groups/{name}\n      name: getgroup\n      operations:\n      - method: GET\n        name: getgroup\n        description: JupyterHub Get group\n\
  \        call: jupyterhub.getgroup\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /groups/{name}\n      name: creategroup\n      operations:\n      - method: POST\n        name: creategroup\n        description: JupyterHub Create group\n        call: jupyterhub.creategroup\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /groups/{name}\n      name: deletegroup\n      operations:\n      - method: DELETE\n        name: deletegroup\n        description: JupyterHub Delete group\n        call: jupyterhub.deletegroup\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /groups/{name}/users\n      name: addgroupusers\n      operations:\n      - method: POST\n        name: addgroupusers\n        description: JupyterHub Add users to group\n        call: jupyterhub.addgroupusers\n\
  \        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /groups/{name}/users\n      name: removegroupusers\n      operations:\n      - method: DELETE\n        name: removegroupusers\n        description: JupyterHub Remove users from group\n        call: jupyterhub.removegroupusers\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /services\n      name: listservices\n      operations:\n      - method: GET\n        name: listservices\n        description: JupyterHub List services\n        call: jupyterhub.listservices\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /services/{name}\n      name: getservice\n      operations:\n      - method: GET\n        name: getservice\n        description: JupyterHub Get service\n        call: jupyterhub.getservice\n        with:\n          name: rest.name\n      \
  \  outputParameters:\n        - type: object\n          mapping: $.\n    - path: /proxy\n      name: getproxyroutes\n      operations:\n      - method: GET\n        name: getproxyroutes\n        description: JupyterHub Get proxy routes\n        call: jupyterhub.getproxyroutes\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /proxy\n      name: syncproxy\n      operations:\n      - method: POST\n        name: syncproxy\n        description: JupyterHub Sync proxy\n        call: jupyterhub.syncproxy\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /proxy\n      name: updateproxy\n      operations:\n      - method: PATCH\n        name: updateproxy\n        description: JupyterHub Update proxy\n        call: jupyterhub.updateproxy\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /authorizations/token\n      name: requesttoken\n      operations:\n      - method: POST\n        name:\
  \ requesttoken\n        description: JupyterHub Request token\n        call: jupyterhub.requesttoken\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /authorizations/token/{token}\n      name: identifytoken\n      operations:\n      - method: GET\n        name: identifytoken\n        description: JupyterHub Identify token\n        call: jupyterhub.identifytoken\n        with:\n          token: rest.token\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /authorizations/cookie/{cookie_name}/{cookie_value}\n      name: identifycookie\n      operations:\n      - method: GET\n        name: identifycookie\n        description: JupyterHub Identify cookie\n        call: jupyterhub.identifycookie\n        with:\n          cookie_name: rest.cookie_name\n          cookie_value: rest.cookie_value\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /oauth2/authorize\n      name: oauth2authorize\n\
  \      operations:\n      - method: GET\n        name: oauth2authorize\n        description: JupyterHub OAuth2 authorize\n        call: jupyterhub.oauth2authorize\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /oauth2/token\n      name: oauth2token\n      operations:\n      - method: POST\n        name: oauth2token\n        description: JupyterHub OAuth2 token\n        call: jupyterhub.oauth2token\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /shutdown\n      name: shutdownhub\n      operations:\n      - method: POST\n        name: shutdownhub\n        description: JupyterHub Shutdown\n        call: jupyterhub.shutdownhub\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: jupyterhub-mcp\n    transport: http\n    description: MCP adapter for JupyterHub REST API for AI agent use.\n    tools:\n    - name: gethubversion\n      description: JupyterHub\
  \ Get version\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: jupyterhub.gethubversion\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: gethubinfo\n      description: JupyterHub Get detailed info\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: jupyterhub.gethubinfo\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listusers\n      description: JupyterHub List users\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: jupyterhub.listusers\n      with:\n        state: tools.state\n        offset: tools.offset\n        limit: tools.limit\n      inputParameters:\n      - name: state\n        type: string\n        description: state\n      - name: offset\n        type: integer\n        description: offset\n      - name: limit\n        type: integer\n        description:\
  \ limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createusers\n      description: JupyterHub Create users\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: jupyterhub.createusers\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getuser\n      description: JupyterHub Get user\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: jupyterhub.getuser\n      with:\n        name: tools.name\n      inputParameters:\n      - name: name\n        type: string\n        description: name\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createuser\n      description: JupyterHub Create user\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: jupyterhub.createuser\n      with:\n        name: tools.name\n      inputParameters:\n\
  \      - name: name\n        type: string\n        description: name\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateuser\n      description: JupyterHub Update user\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: jupyterhub.updateuser\n      with:\n        name: tools.name\n      inputParameters:\n      - name: name\n        type: string\n        description: name\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteuser\n      description: JupyterHub Delete user\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: jupyterhub.deleteuser\n      with:\n        name: tools.name\n      inputParameters:\n      - name: name\n        type: string\n        description: name\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n\
  \    - name: notifyuseractivity\n      description: JupyterHub Notify user activity\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: jupyterhub.notifyuseractivity\n      with:\n        name: tools.name\n      inputParameters:\n      - name: name\n        type: string\n        description: name\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: startuserserver\n      description: JupyterHub Start user server\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: jupyterhub.startuserserver\n      with:\n        name: tools.name\n      inputParameters:\n      - name: name\n        type: string\n        description: name\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: stopuserserver\n      description: JupyterHub Stop user server\n      hints:\n        readOnly: false\n  \
  \      destructive: true\n        idempotent: true\n      call: jupyterhub.stopuserserver\n      with:\n        name: tools.name\n      inputParameters:\n      - name: name\n        type: string\n        description: name\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: startnamedserver\n      description: JupyterHub Start named server\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: jupyterhub.startnamedserver\n      with:\n        name: tools.name\n        server_name: tools.server_name\n      inputParameters:\n      - name: name\n        type: string\n        description: name\n        required: true\n      - name: server_name\n        type: string\n        description: server_name\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: stopnamedserver\n      description: JupyterHub Stop named server\n      hints:\n      \
  \  readOnly: false\n        destructive: true\n        idempotent: true\n      call: jupyterhub.stopnamedserver\n      with:\n        name: tools.name\n        server_name: tools.server_name\n      inputParameters:\n      - name: name\n        type: string\n        description: name\n        required: true\n      - name: server_name\n        type: string\n        description: server_name\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listusertokens\n      description: JupyterHub List user tokens\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: jupyterhub.listusertokens\n      with:\n        name: tools.name\n      inputParameters:\n      - name: name\n        type: string\n        description: name\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createusertoken\n      description: JupyterHub Create user token\n      hints:\n\
  \        readOnly: false\n        destructive: false\n        idempotent: false\n      call: jupyterhub.createusertoken\n      with:\n        name: tools.name\n      inputParameters:\n      - name: name\n        type: string\n        description: name\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getusertoken\n      description: JupyterHub Get user token\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: jupyterhub.getusertoken\n      with:\n        name: tools.name\n        token_id: tools.token_id\n      inputParameters:\n      - name: name\n        type: string\n        description: name\n        required: true\n      - name: token_id\n        type: string\n        description: token_id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: revokeusertoken\n      description: JupyterHub Revoke user token\n      hints:\n  \
  \      readOnly: false\n        destructive: true\n        idempotent: true\n      call: jupyterhub.revokeusertoken\n      with:\n        name: tools.name\n        token_id: tools.token_id\n      inputParameters:\n      - name: name\n        type: string\n        description: name\n        required: true\n      - name: token_id\n        type: string\n        description: token_id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listgroups\n      description: JupyterHub List groups\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: jupyterhub.listgroups\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: creategroups\n      description: JupyterHub Create groups\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: jupyterhub.creategroups\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: getgroup\n      description: JupyterHub Get group\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: jupyterhub.getgroup\n      with:\n        name: tools.name\n      inputParameters:\n      - name: name\n        type: string\n        description: name\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: creategroup\n      description: JupyterHub Create group\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: jupyterhub.creategroup\n      with:\n        name: tools.name\n      inputParameters:\n      - name: name\n        type: string\n        description: name\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletegroup\n      description: JupyterHub Delete group\n      hints:\n        readOnly: false\n        destructive: true\n     \n\n# --- truncated\
  \ at 32 KB (36 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/jupyterhub/refs/heads/main/capabilities/jupyterhub-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/jupyterhub/refs/heads/main/capabilities/jupyterhub-capability.yaml
tags:
- Jupyterhub
- API
tools:
- description: JupyterHub Get version
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gethubversion
- description: JupyterHub Get detailed info
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gethubinfo
- description: JupyterHub List users
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listusers
- description: JupyterHub Create users
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createusers
- description: JupyterHub Get user
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getuser
- description: JupyterHub Create user
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createuser
- description: JupyterHub Update user
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateuser
- description: JupyterHub Delete user
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteuser
- description: JupyterHub Notify user activity
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: notifyuseractivity
- description: JupyterHub Start user server
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: startuserserver
- description: JupyterHub Stop user server
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: stopuserserver
- description: JupyterHub Start named server
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: startnamedserver
- description: JupyterHub Stop named server
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: stopnamedserver
- description: JupyterHub List user tokens
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listusertokens
- description: JupyterHub Create user token
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createusertoken
- description: JupyterHub Get user token
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getusertoken
- description: JupyterHub Revoke user token
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: revokeusertoken
- description: JupyterHub List groups
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listgroups
- description: JupyterHub Create groups
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: creategroups
- description: JupyterHub Get group
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getgroup
- description: JupyterHub Create group
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: creategroup
- description: JupyterHub Delete group
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletegroup
- description: JupyterHub Add users to group
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: addgroupusers
- description: JupyterHub Remove users from group
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: removegroupusers
- description: JupyterHub List services
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listservices
- description: JupyterHub Get service
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getservice
- description: JupyterHub Get proxy routes
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getproxyroutes
- description: JupyterHub Sync proxy
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: syncproxy
- description: JupyterHub Update proxy
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateproxy
- description: JupyterHub Request token
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: requesttoken
- description: JupyterHub Identify token
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: identifytoken
- description: JupyterHub Identify cookie
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: identifycookie
- description: JupyterHub OAuth2 authorize
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: oauth2authorize
- description: JupyterHub OAuth2 token
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: oauth2token
- description: JupyterHub Shutdown
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: shutdownhub
---
