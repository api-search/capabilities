---
categories: []
consumed_apis: []
description: Node-RED's Admin HTTP API enables remote administration of the runtime. It is used by the Node-RED Editor and the command-line admin tool to manage flows, nodes, settings, and authentication.
layout: capability
name: Node-RED Admin API
operations:
- description: Get the active authentication scheme
  method: GET
  name: getauthlogin
  path: /auth/login
- description: Exchange credentials for an access token
  method: POST
  name: postauthtoken
  path: /auth/token
- description: Revoke an access token
  method: POST
  name: postauthrevoke
  path: /auth/revoke
- description: Get the runtime settings
  method: GET
  name: getsettings
  path: /settings
- description: Get the runtime diagnostics
  method: GET
  name: getdiagnostics
  path: /diagnostics
- description: Get the active flow configuration
  method: GET
  name: getflows
  path: /flows
- description: Set the active flow configuration
  method: POST
  name: postflows
  path: /flows
- description: Get the active flow runtime state
  method: GET
  name: getflowsstate
  path: /flows/state
- description: Set the active flow runtime state
  method: POST
  name: postflowsstate
  path: /flows/state
- description: Add a flow to the active configuration
  method: POST
  name: postflow
  path: /flow
- description: Get an individual flow configuration
  method: GET
  name: getflowbyid
  path: /flow/{id}
- description: Update an individual flow configuration
  method: PUT
  name: putflowbyid
  path: /flow/{id}
- description: Delete an individual flow configuration
  method: DELETE
  name: deleteflowbyid
  path: /flow/{id}
- description: Get a list of the installed nodes
  method: GET
  name: getnodes
  path: /nodes
- description: Install a new node module
  method: POST
  name: postnodes
  path: /nodes
- description: Get a node module information
  method: GET
  name: getnodemodule
  path: /nodes/{module}
- description: Enable or disable a node module
  method: PUT
  name: putnodemodule
  path: /nodes/{module}
- description: Remove a node module
  method: DELETE
  name: deletenodemodule
  path: /nodes/{module}
- description: Get a node module set information
  method: GET
  name: getnodemoduleset
  path: /nodes/{module}/{set}
- description: Enable or disable a node set
  method: PUT
  name: putnodemoduleset
  path: /nodes/{module}/{set}
personas: []
provider_name: Node-RED
provider_slug: node-red
search_terms:
- set the active flow configuration
- node
- get the active flow configuration
- enable or disable a node module
- postauthtoken
- get a node module information
- getflowbyid
- getnodemoduleset
- postflowsstate
- putnodemoduleset
- add a flow to the active configuration
- self-hosted
- postflow
- enable or disable a node set
- red
- deleteflowbyid
- getnodes
- get a list of the installed nodes
- iot
- get the runtime settings
- get the active authentication scheme
- set the active flow runtime state
- get a node module set information
- getflows
- install a new node module
- postnodes
- getflowsstate
- putnodemodule
- postflows
- deletenodemodule
- api
- workflow automation
- get the runtime diagnostics
- get the active flow runtime state
- putflowbyid
- exchange credentials for an access token
- flow-based programming
- getnodemodule
- get an individual flow configuration
- revoke an access token
- getsettings
- getauthlogin
- delete an individual flow configuration
- postauthrevoke
- update an individual flow configuration
- getdiagnostics
- remove a node module
slug: node-red-capability
source_filename: node-red-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Node-RED Admin API\n  description: Node-RED's Admin HTTP API enables remote administration of the runtime. It is used by the Node-RED Editor and\n    the command-line admin tool to manage flows, nodes, settings, and authentication.\n  tags:\n  - Node\n  - Red\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: node-red\n    baseUri: http://localhost:1880\n    description: Node-RED Admin API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{NODE_RED_TOKEN}}'\n    resources:\n    - name: auth-login\n      path: /auth/login\n      operations:\n      - name: getauthlogin\n        method: GET\n        description: Get the active authentication scheme\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: auth-token\n      path: /auth/token\n      operations:\n      - name: postauthtoken\n\
  \        method: POST\n        description: Exchange credentials for an access token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: auth-revoke\n      path: /auth/revoke\n      operations:\n      - name: postauthrevoke\n        method: POST\n        description: Revoke an access token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: settings\n      path: /settings\n      operations:\n      - name: getsettings\n        method: GET\n        description: Get the runtime settings\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: diagnostics\n      path: /diagnostics\n      operations:\n      - name: getdiagnostics\n        method: GET\n        description: Get the runtime diagnostics\n        outputRawFormat: json\n    \
  \    outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: flows\n      path: /flows\n      operations:\n      - name: getflows\n        method: GET\n        description: Get the active flow configuration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: postflows\n        method: POST\n        description: Set the active flow configuration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: flows-state\n      path: /flows/state\n      operations:\n      - name: getflowsstate\n        method: GET\n        description: Get the active flow runtime state\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: postflowsstate\n        method: POST\n        description: Set the active\
  \ flow runtime state\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: flow\n      path: /flow\n      operations:\n      - name: postflow\n        method: POST\n        description: Add a flow to the active configuration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: flow-id\n      path: /flow/{id}\n      operations:\n      - name: getflowbyid\n        method: GET\n        description: Get an individual flow configuration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: putflowbyid\n        method: PUT\n        description: Update an individual flow configuration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteflowbyid\n\
  \        method: DELETE\n        description: Delete an individual flow configuration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: nodes\n      path: /nodes\n      operations:\n      - name: getnodes\n        method: GET\n        description: Get a list of the installed nodes\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: postnodes\n        method: POST\n        description: Install a new node module\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: nodes-module\n      path: /nodes/{module}\n      operations:\n      - name: getnodemodule\n        method: GET\n        description: Get a node module information\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n      - name: putnodemodule\n        method: PUT\n        description: Enable or disable a node module\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletenodemodule\n        method: DELETE\n        description: Remove a node module\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: nodes-module-set\n      path: /nodes/{module}/{set}\n      operations:\n      - name: getnodemoduleset\n        method: GET\n        description: Get a node module set information\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: putnodemoduleset\n        method: PUT\n        description: Enable or disable a node set\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: node-red-rest\n    description: REST adapter for Node-RED Admin API.\n    resources:\n    - path: /auth/login\n      name: getauthlogin\n      operations:\n      - method: GET\n        name: getauthlogin\n        description: Get the active authentication scheme\n        call: node-red.getauthlogin\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth/token\n      name: postauthtoken\n      operations:\n      - method: POST\n        name: postauthtoken\n        description: Exchange credentials for an access token\n        call: node-red.postauthtoken\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth/revoke\n      name: postauthrevoke\n      operations:\n      - method: POST\n        name: postauthrevoke\n        description: Revoke an access token\n        call: node-red.postauthrevoke\n        outputParameters:\n \
  \       - type: object\n          mapping: $.\n    - path: /settings\n      name: getsettings\n      operations:\n      - method: GET\n        name: getsettings\n        description: Get the runtime settings\n        call: node-red.getsettings\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /diagnostics\n      name: getdiagnostics\n      operations:\n      - method: GET\n        name: getdiagnostics\n        description: Get the runtime diagnostics\n        call: node-red.getdiagnostics\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /flows\n      name: getflows\n      operations:\n      - method: GET\n        name: getflows\n        description: Get the active flow configuration\n        call: node-red.getflows\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /flows\n      name: postflows\n      operations:\n      - method: POST\n        name: postflows\n        description:\
  \ Set the active flow configuration\n        call: node-red.postflows\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /flows/state\n      name: getflowsstate\n      operations:\n      - method: GET\n        name: getflowsstate\n        description: Get the active flow runtime state\n        call: node-red.getflowsstate\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /flows/state\n      name: postflowsstate\n      operations:\n      - method: POST\n        name: postflowsstate\n        description: Set the active flow runtime state\n        call: node-red.postflowsstate\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /flow\n      name: postflow\n      operations:\n      - method: POST\n        name: postflow\n        description: Add a flow to the active configuration\n        call: node-red.postflow\n        outputParameters:\n        - type: object\n          mapping: $.\n\
  \    - path: /flow/{id}\n      name: getflowbyid\n      operations:\n      - method: GET\n        name: getflowbyid\n        description: Get an individual flow configuration\n        call: node-red.getflowbyid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /flow/{id}\n      name: putflowbyid\n      operations:\n      - method: PUT\n        name: putflowbyid\n        description: Update an individual flow configuration\n        call: node-red.putflowbyid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /flow/{id}\n      name: deleteflowbyid\n      operations:\n      - method: DELETE\n        name: deleteflowbyid\n        description: Delete an individual flow configuration\n        call: node-red.deleteflowbyid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /nodes\n      name: getnodes\n      operations:\n      - method: GET\n        name: getnodes\n        description:\
  \ Get a list of the installed nodes\n        call: node-red.getnodes\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /nodes\n      name: postnodes\n      operations:\n      - method: POST\n        name: postnodes\n        description: Install a new node module\n        call: node-red.postnodes\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /nodes/{module}\n      name: getnodemodule\n      operations:\n      - method: GET\n        name: getnodemodule\n        description: Get a node module information\n        call: node-red.getnodemodule\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /nodes/{module}\n      name: putnodemodule\n      operations:\n      - method: PUT\n        name: putnodemodule\n        description: Enable or disable a node module\n        call: node-red.putnodemodule\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path:\
  \ /nodes/{module}\n      name: deletenodemodule\n      operations:\n      - method: DELETE\n        name: deletenodemodule\n        description: Remove a node module\n        call: node-red.deletenodemodule\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /nodes/{module}/{set}\n      name: getnodemoduleset\n      operations:\n      - method: GET\n        name: getnodemoduleset\n        description: Get a node module set information\n        call: node-red.getnodemoduleset\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /nodes/{module}/{set}\n      name: putnodemoduleset\n      operations:\n      - method: PUT\n        name: putnodemoduleset\n        description: Enable or disable a node set\n        call: node-red.putnodemoduleset\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: node-red-mcp\n    transport: http\n    description: MCP adapter\
  \ for Node-RED Admin API for AI agent use.\n    tools:\n    - name: getauthlogin\n      description: Get the active authentication scheme\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: node-red.getauthlogin\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: postauthtoken\n      description: Exchange credentials for an access token\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: node-red.postauthtoken\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: postauthrevoke\n      description: Revoke an access token\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: node-red.postauthrevoke\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getsettings\n      description: Get the runtime settings\n      hints:\n        readOnly: true\n \
  \       destructive: false\n        idempotent: true\n      call: node-red.getsettings\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getdiagnostics\n      description: Get the runtime diagnostics\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: node-red.getdiagnostics\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getflows\n      description: Get the active flow configuration\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: node-red.getflows\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: postflows\n      description: Set the active flow configuration\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: node-red.postflows\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getflowsstate\n     \
  \ description: Get the active flow runtime state\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: node-red.getflowsstate\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: postflowsstate\n      description: Set the active flow runtime state\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: node-red.postflowsstate\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: postflow\n      description: Add a flow to the active configuration\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: node-red.postflow\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getflowbyid\n      description: Get an individual flow configuration\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: node-red.getflowbyid\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: putflowbyid\n      description: Update an individual flow configuration\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: node-red.putflowbyid\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteflowbyid\n      description: Delete an individual flow configuration\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: node-red.deleteflowbyid\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getnodes\n      description: Get a list of the installed nodes\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: node-red.getnodes\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: postnodes\n      description: Install a new node module\n      hints:\n        readOnly:\
  \ false\n        destructive: false\n        idempotent: false\n      call: node-red.postnodes\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getnodemodule\n      description: Get a node module information\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: node-red.getnodemodule\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: putnodemodule\n      description: Enable or disable a node module\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: node-red.putnodemodule\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletenodemodule\n      description: Remove a node module\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: node-red.deletenodemodule\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getnodemoduleset\n\
  \      description: Get a node module set information\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: node-red.getnodemoduleset\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: putnodemoduleset\n      description: Enable or disable a node set\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: node-red.putnodemoduleset\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    NODE_RED_TOKEN: NODE_RED_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/node-red/refs/heads/main/capabilities/node-red-capability.yaml
tags:
- Node
- Red
- API
tools:
- description: Get the active authentication scheme
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getauthlogin
- description: Exchange credentials for an access token
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: postauthtoken
- description: Revoke an access token
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: postauthrevoke
- description: Get the runtime settings
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getsettings
- description: Get the runtime diagnostics
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdiagnostics
- description: Get the active flow configuration
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getflows
- description: Set the active flow configuration
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: postflows
- description: Get the active flow runtime state
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getflowsstate
- description: Set the active flow runtime state
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: postflowsstate
- description: Add a flow to the active configuration
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: postflow
- description: Get an individual flow configuration
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getflowbyid
- description: Update an individual flow configuration
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: putflowbyid
- description: Delete an individual flow configuration
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteflowbyid
- description: Get a list of the installed nodes
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getnodes
- description: Install a new node module
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: postnodes
- description: Get a node module information
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getnodemodule
- description: Enable or disable a node module
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: putnodemodule
- description: Remove a node module
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletenodemodule
- description: Get a node module set information
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getnodemoduleset
- description: Enable or disable a node set
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: putnodemoduleset
---
