---
categories: []
consumed_apis: []
description: REST API for managing JupyterHub users, groups, services, and single-user notebook servers. Authentication is performed via API tokens.
layout: capability
name: JupyterHub REST API
operations:
- description: Get JupyterHub version
  method: GET
  name: gethubinfo
  path: /
- description: Get detailed Hub info
  method: GET
  name: gethubdetailedinfo
  path: /info
- description: List users
  method: GET
  name: listusers
  path: /users
- description: Create multiple users
  method: POST
  name: createusers
  path: /users
- description: Get a user
  method: GET
  name: getuser
  path: /users/{name}
- description: Create a single user
  method: POST
  name: createuser
  path: /users/{name}
- description: Delete a user
  method: DELETE
  name: deleteuser
  path: /users/{name}
- description: Start a user's default server
  method: POST
  name: startuserserver
  path: /users/{name}/server
- description: Stop a user's default server
  method: DELETE
  name: stopuserserver
  path: /users/{name}/server
- description: Start a named server for a user
  method: POST
  name: startnamedserver
  path: /users/{name}/servers/{server_name}
- description: Stop a named server for a user
  method: DELETE
  name: stopnamedserver
  path: /users/{name}/servers/{server_name}
- description: List a user's tokens
  method: GET
  name: listusertokens
  path: /users/{name}/tokens
- description: Create a new token for a user
  method: POST
  name: createusertoken
  path: /users/{name}/tokens
- description: List groups
  method: GET
  name: listgroups
  path: /groups
- description: Get a group
  method: GET
  name: getgroup
  path: /groups/{name}
- description: Create a group
  method: POST
  name: creategroup
  path: /groups/{name}
- description: Delete a group
  method: DELETE
  name: deletegroup
  path: /groups/{name}
- description: Add users to a group
  method: POST
  name: adduserstogroup
  path: /groups/{name}/users
- description: Remove users from a group
  method: DELETE
  name: removeusersfromgroup
  path: /groups/{name}/users
- description: List services
  method: GET
  name: listservices
  path: /services
- description: Get a service
  method: GET
  name: getservice
  path: /services/{name}
- description: Get the proxy's routing table
  method: GET
  name: getproxyroutes
  path: /proxy
- description: Shut down the Hub
  method: POST
  name: shutdownhub
  path: /shutdown
personas: []
provider_name: JupyterHub
provider_slug: jupyter-hub
search_terms:
- list services
- get detailed hub info
- getproxyroutes
- start a user's default server
- adduserstogroup
- getservice
- listusertokens
- create multiple users
- list groups
- creategroup
- api
- delete a user
- add users to a group
- delete a group
- multi-user
- get a group
- getuser
- get a user
- gethubdetailedinfo
- create a new token for a user
- getgroup
- deleteuser
- listgroups
- removeusersfromgroup
- createusertoken
- listservices
- list users
- hub
- stopuserserver
- gethubinfo
- startuserserver
- stop a user's default server
- create a group
- data science
- notebooks
- get the proxy's routing table
- shutdownhub
- stopnamedserver
- get a service
- start a named server for a user
- createuser
- remove users from a group
- education
- createusers
- listusers
- shut down the hub
- stop a named server for a user
- list a user's tokens
- jupyter
- create a single user
- deletegroup
- get jupyterhub version
- startnamedserver
slug: jupyter-hub-capability
source_filename: jupyter-hub-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: JupyterHub REST API\n  description: REST API for managing JupyterHub users, groups, services, and single-user notebook servers. Authentication\n    is performed via API tokens.\n  tags:\n  - Jupyter\n  - Hub\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: jupyter-hub\n    baseUri: https://your-jupyterhub-domain.com/hub/api\n    description: JupyterHub REST API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{JUPYTER_HUB_TOKEN}}'\n    resources:\n    - name: resource\n      path: /\n      operations:\n      - name: gethubinfo\n        method: GET\n        description: Get JupyterHub version\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: info\n      path: /info\n      operations:\n      - name: gethubdetailedinfo\n        method: GET\n        description: Get\
  \ detailed Hub info\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users\n      path: /users\n      operations:\n      - name: listusers\n        method: GET\n        description: List users\n        inputParameters:\n        - name: state\n          in: query\n          type: string\n        - name: offset\n          in: query\n          type: integer\n        - name: limit\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createusers\n        method: POST\n        description: Create multiple users\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users-name\n      path: /users/{name}\n      operations:\n      - name: getuser\n        method: GET\n        description:\
  \ Get a user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createuser\n        method: POST\n        description: Create a single user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteuser\n        method: DELETE\n        description: Delete a user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users-name-server\n      path: /users/{name}/server\n      operations:\n      - name: startuserserver\n        method: POST\n        description: Start a user's default server\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: stopuserserver\n        method: DELETE\n        description: Stop a user's default server\n      \
  \  outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users-name-servers-server-name\n      path: /users/{name}/servers/{server_name}\n      operations:\n      - name: startnamedserver\n        method: POST\n        description: Start a named server for a user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: stopnamedserver\n        method: DELETE\n        description: Stop a named server for a user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users-name-tokens\n      path: /users/{name}/tokens\n      operations:\n      - name: listusertokens\n        method: GET\n        description: List a user's tokens\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n      - name: createusertoken\n        method: POST\n        description: Create a new token for a user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: groups\n      path: /groups\n      operations:\n      - name: listgroups\n        method: GET\n        description: List groups\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: groups-name\n      path: /groups/{name}\n      operations:\n      - name: getgroup\n        method: GET\n        description: Get a group\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: creategroup\n        method: POST\n        description: Create a group\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  \
  \    - name: deletegroup\n        method: DELETE\n        description: Delete a group\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: groups-name-users\n      path: /groups/{name}/users\n      operations:\n      - name: adduserstogroup\n        method: POST\n        description: Add users to a group\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: removeusersfromgroup\n        method: DELETE\n        description: Remove users from a group\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: services\n      path: /services\n      operations:\n      - name: listservices\n        method: GET\n        description: List services\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n    - name: services-name\n      path: /services/{name}\n      operations:\n      - name: getservice\n        method: GET\n        description: Get a service\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: proxy\n      path: /proxy\n      operations:\n      - name: getproxyroutes\n        method: GET\n        description: Get the proxy's routing table\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: shutdown\n      path: /shutdown\n      operations:\n      - name: shutdownhub\n        method: POST\n        description: Shut down the Hub\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: jupyter-hub-rest\n    description: REST adapter for JupyterHub\
  \ REST API.\n    resources:\n    - path: /\n      name: gethubinfo\n      operations:\n      - method: GET\n        name: gethubinfo\n        description: Get JupyterHub version\n        call: jupyter-hub.gethubinfo\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /info\n      name: gethubdetailedinfo\n      operations:\n      - method: GET\n        name: gethubdetailedinfo\n        description: Get detailed Hub info\n        call: jupyter-hub.gethubdetailedinfo\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users\n      name: listusers\n      operations:\n      - method: GET\n        name: listusers\n        description: List users\n        call: jupyter-hub.listusers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users\n      name: createusers\n      operations:\n      - method: POST\n        name: createusers\n        description: Create multiple users\n        call:\
  \ jupyter-hub.createusers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users/{name}\n      name: getuser\n      operations:\n      - method: GET\n        name: getuser\n        description: Get a user\n        call: jupyter-hub.getuser\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users/{name}\n      name: createuser\n      operations:\n      - method: POST\n        name: createuser\n        description: Create a single user\n        call: jupyter-hub.createuser\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users/{name}\n      name: deleteuser\n      operations:\n      - method: DELETE\n        name: deleteuser\n        description: Delete a user\n        call: jupyter-hub.deleteuser\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users/{name}/server\n      name: startuserserver\n      operations:\n      - method: POST\n\
  \        name: startuserserver\n        description: Start a user's default server\n        call: jupyter-hub.startuserserver\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users/{name}/server\n      name: stopuserserver\n      operations:\n      - method: DELETE\n        name: stopuserserver\n        description: Stop a user's default server\n        call: jupyter-hub.stopuserserver\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users/{name}/servers/{server_name}\n      name: startnamedserver\n      operations:\n      - method: POST\n        name: startnamedserver\n        description: Start a named server for a user\n        call: jupyter-hub.startnamedserver\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users/{name}/servers/{server_name}\n      name: stopnamedserver\n      operations:\n      - method: DELETE\n        name: stopnamedserver\n        description:\
  \ Stop a named server for a user\n        call: jupyter-hub.stopnamedserver\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users/{name}/tokens\n      name: listusertokens\n      operations:\n      - method: GET\n        name: listusertokens\n        description: List a user's tokens\n        call: jupyter-hub.listusertokens\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users/{name}/tokens\n      name: createusertoken\n      operations:\n      - method: POST\n        name: createusertoken\n        description: Create a new token for a user\n        call: jupyter-hub.createusertoken\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /groups\n      name: listgroups\n      operations:\n      - method: GET\n        name: listgroups\n        description: List groups\n        call: jupyter-hub.listgroups\n        outputParameters:\n        - type: object\n          mapping: $.\n\
  \    - path: /groups/{name}\n      name: getgroup\n      operations:\n      - method: GET\n        name: getgroup\n        description: Get a group\n        call: jupyter-hub.getgroup\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /groups/{name}\n      name: creategroup\n      operations:\n      - method: POST\n        name: creategroup\n        description: Create a group\n        call: jupyter-hub.creategroup\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /groups/{name}\n      name: deletegroup\n      operations:\n      - method: DELETE\n        name: deletegroup\n        description: Delete a group\n        call: jupyter-hub.deletegroup\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /groups/{name}/users\n      name: adduserstogroup\n      operations:\n      - method: POST\n        name: adduserstogroup\n        description: Add users to a group\n        call: jupyter-hub.adduserstogroup\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /groups/{name}/users\n      name: removeusersfromgroup\n      operations:\n      - method: DELETE\n        name: removeusersfromgroup\n        description: Remove users from a group\n        call: jupyter-hub.removeusersfromgroup\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /services\n      name: listservices\n      operations:\n      - method: GET\n        name: listservices\n        description: List services\n        call: jupyter-hub.listservices\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /services/{name}\n      name: getservice\n      operations:\n      - method: GET\n        name: getservice\n        description: Get a service\n        call: jupyter-hub.getservice\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /proxy\n      name: getproxyroutes\n      operations:\n     \
  \ - method: GET\n        name: getproxyroutes\n        description: Get the proxy's routing table\n        call: jupyter-hub.getproxyroutes\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /shutdown\n      name: shutdownhub\n      operations:\n      - method: POST\n        name: shutdownhub\n        description: Shut down the Hub\n        call: jupyter-hub.shutdownhub\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: jupyter-hub-mcp\n    transport: http\n    description: MCP adapter for JupyterHub REST API for AI agent use.\n    tools:\n    - name: gethubinfo\n      description: Get JupyterHub version\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: jupyter-hub.gethubinfo\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: gethubdetailedinfo\n      description: Get detailed Hub info\n      hints:\n\
  \        readOnly: true\n        destructive: false\n        idempotent: true\n      call: jupyter-hub.gethubdetailedinfo\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listusers\n      description: List users\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: jupyter-hub.listusers\n      with:\n        state: tools.state\n        offset: tools.offset\n        limit: tools.limit\n      inputParameters:\n      - name: state\n        type: string\n        description: state\n      - name: offset\n        type: integer\n        description: offset\n      - name: limit\n        type: integer\n        description: limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createusers\n      description: Create multiple users\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: jupyter-hub.createusers\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: getuser\n      description: Get a user\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: jupyter-hub.getuser\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createuser\n      description: Create a single user\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: jupyter-hub.createuser\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteuser\n      description: Delete a user\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: jupyter-hub.deleteuser\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: startuserserver\n      description: Start a user's default server\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: jupyter-hub.startuserserver\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: stopuserserver\n      description: Stop a user's default server\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: jupyter-hub.stopuserserver\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: startnamedserver\n      description: Start a named server for a user\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: jupyter-hub.startnamedserver\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: stopnamedserver\n      description: Stop a named server for a user\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: jupyter-hub.stopnamedserver\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listusertokens\n      description: List a user's tokens\n      hints:\n   \
  \     readOnly: true\n        destructive: false\n        idempotent: true\n      call: jupyter-hub.listusertokens\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createusertoken\n      description: Create a new token for a user\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: jupyter-hub.createusertoken\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listgroups\n      description: List groups\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: jupyter-hub.listgroups\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getgroup\n      description: Get a group\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: jupyter-hub.getgroup\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: creategroup\n      description:\
  \ Create a group\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: jupyter-hub.creategroup\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletegroup\n      description: Delete a group\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: jupyter-hub.deletegroup\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: adduserstogroup\n      description: Add users to a group\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: jupyter-hub.adduserstogroup\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: removeusersfromgroup\n      description: Remove users from a group\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: jupyter-hub.removeusersfromgroup\n      outputParameters:\n      - type:\
  \ object\n        mapping: $.\n    - name: listservices\n      description: List services\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: jupyter-hub.listservices\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getservice\n      description: Get a service\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: jupyter-hub.getservice\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getproxyroutes\n      description: Get the proxy's routing table\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: jupyter-hub.getproxyroutes\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: shutdownhub\n      description: Shut down the Hub\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: jupyter-hub.shutdownhub\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    JUPYTER_HUB_TOKEN: JUPYTER_HUB_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/jupyter-hub/refs/heads/main/capabilities/jupyter-hub-capability.yaml
tags:
- Jupyter
- Hub
- API
tools:
- description: Get JupyterHub version
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gethubinfo
- description: Get detailed Hub info
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gethubdetailedinfo
- description: List users
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listusers
- description: Create multiple users
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createusers
- description: Get a user
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getuser
- description: Create a single user
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createuser
- description: Delete a user
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteuser
- description: Start a user's default server
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: startuserserver
- description: Stop a user's default server
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: stopuserserver
- description: Start a named server for a user
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: startnamedserver
- description: Stop a named server for a user
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: stopnamedserver
- description: List a user's tokens
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listusertokens
- description: Create a new token for a user
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createusertoken
- description: List groups
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listgroups
- description: Get a group
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getgroup
- description: Create a group
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: creategroup
- description: Delete a group
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletegroup
- description: Add users to a group
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: adduserstogroup
- description: Remove users from a group
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: removeusersfromgroup
- description: List services
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listservices
- description: Get a service
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getservice
- description: Get the proxy's routing table
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getproxyroutes
- description: Shut down the Hub
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: shutdownhub
---
