---
categories: []
consumed_apis: []
description: Workflow capability for administering a Synapse Matrix homeserver. Enables server administrators to manage users, rooms, registration, federation, and monitor server health through a unified REST and MCP interface backed by the Synapse Admin API.
layout: capability
name: Synapse Homeserver Administration
operations:
- description: List all users on the homeserver
  method: GET
  name: list-users
  path: /v1/users
- description: Create or modify a user account
  method: POST
  name: create-user
  path: /v1/users
- description: Get user details
  method: GET
  name: get-user
  path: /v1/users/{userId}
- description: List all rooms on the homeserver
  method: GET
  name: list-rooms
  path: /v1/rooms
- description: List all members of a room
  method: GET
  name: get-room-members
  path: /v1/rooms/{roomId}/members
- description: List registration tokens
  method: GET
  name: list-tokens
  path: /v1/registration-tokens
- description: Create a new registration token
  method: POST
  name: create-token
  path: /v1/registration-tokens
- description: Get Synapse server version
  method: GET
  name: get-version
  path: /v1/server/version
personas: []
provider_name: Synapse
provider_slug: synapse
search_terms:
- decentralized
- user account management
- list all members of a room
- list all rooms hosted on the synapse homeserver with member counts
- get detailed information about a specific matrix room
- real-time
- users
- get room
- create a new registration token
- list all local users registered on the synapse homeserver
- create user
- collaboration
- get the current synapse homeserver version and python version
- list tokens
- synapse
- registration token management
- list all rooms on the homeserver
- get server version
- individual user operations
- messaging
- get version
- matrix
- create registration token
- room administration
- open-source
- get room members
- room membership management
- list rooms
- administration
- create a new registration token for controlled user sign-up
- get user
- chat
- list all users on the homeserver
- create or modify user
- list all members of a specific matrix room
- list users
- list all registration tokens and their usage status
- create or modify a user account
- get user details
- homeserver
- server information
- create token
- get detailed information about a specific matrix user
- federation
- list registration tokens
- get synapse server version
- create a new user or modify an existing user account on the homeserver
slug: homeserver-administration
source_filename: homeserver-administration.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Synapse Homeserver Administration\n  description: Workflow capability for administering a Synapse Matrix homeserver. Enables server administrators to manage\n    users, rooms, registration, federation, and monitor server health through a unified REST and MCP interface backed by the\n    Synapse Admin API.\n  tags:\n  - Administration\n  - Federation\n  - Homeserver\n  - Matrix\n  - Synapse\n  - Users\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SYNAPSE_ADMIN_TOKEN: SYNAPSE_ADMIN_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: synapse-admin\n    baseUri: https://matrix.example.com/_synapse/admin\n    description: Synapse Admin API for homeserver management\n    authentication:\n      type: bearer\n      token: '{{SYNAPSE_ADMIN_TOKEN}}'\n    resources:\n    - name: users\n      path: /v2/users\n      description: User account management\n      operations:\n      - name: list-users\n\
  \        method: GET\n        description: List all local users on the homeserver\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum results to return\n        - name: from\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset\n        - name: deactivated\n          in: query\n          type: boolean\n          required: false\n          description: Include deactivated accounts\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-user\n        method: GET\n        description: Get details about a specific user\n        inputParameters:\n        - name: userId\n          in: path\n          type: string\n          required: true\n          description: Matrix user ID\n        outputRawFormat: json\n        outputParameters:\n       \
  \ - name: result\n          type: object\n          value: $.\n      - name: upsert-user\n        method: PUT\n        description: Create or modify a user account\n        inputParameters:\n        - name: userId\n          in: path\n          type: string\n          required: true\n          description: Matrix user ID\n        body:\n          type: json\n          data:\n            password: '{{tools.password}}'\n            admin: '{{tools.admin}}'\n            displayname: '{{tools.displayname}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: rooms\n      path: /v1/rooms\n      description: Room administration\n      operations:\n      - name: list-rooms\n        method: GET\n        description: List all rooms on the homeserver\n        inputParameters:\n        - name: search_term\n          in: query\n          type: string\n          required: false\n          description: Filter by\
  \ room name or ID\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum results\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-room\n        method: GET\n        description: Get details about a specific room\n        inputParameters:\n        - name: roomId\n          in: path\n          type: string\n          required: true\n          description: Matrix room ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-room-members\n        method: GET\n        description: List all members of a room\n        inputParameters:\n        - name: roomId\n          in: path\n          type: string\n          required: true\n          description: Matrix room ID\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n    - name: registration-tokens\n      path: /v1/registration_tokens\n      description: Registration token management\n      operations:\n      - name: list-registration-tokens\n        method: GET\n        description: List all registration tokens\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-registration-token\n        method: POST\n        description: Create a new registration token\n        body:\n          type: json\n          data:\n            uses_allowed: '{{tools.usesAllowed}}'\n            expiry_time: '{{tools.expiryTime}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: server\n      path: /v1/server_version\n      description: Server information\n      operations:\n      - name: get-server-version\n        method: GET\n   \
  \     description: Get the current Synapse server version\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: synapse-homeserver-api\n    description: Unified REST API for Synapse homeserver administration.\n    resources:\n    - path: /v1/users\n      name: users\n      description: User account management\n      operations:\n      - method: GET\n        name: list-users\n        description: List all users on the homeserver\n        call: synapse-admin.list-users\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-user\n        description: Create or modify a user account\n        call: synapse-admin.upsert-user\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/users/{userId}\n      name: user\n      description: Individual user operations\n    \
  \  operations:\n      - method: GET\n        name: get-user\n        description: Get user details\n        call: synapse-admin.get-user\n        with:\n          userId: rest.userId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/rooms\n      name: rooms\n      description: Room administration\n      operations:\n      - method: GET\n        name: list-rooms\n        description: List all rooms on the homeserver\n        call: synapse-admin.list-rooms\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/rooms/{roomId}/members\n      name: room-members\n      description: Room membership management\n      operations:\n      - method: GET\n        name: get-room-members\n        description: List all members of a room\n        call: synapse-admin.get-room-members\n        with:\n          roomId: rest.roomId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/registration-tokens\n\
  \      name: registration-tokens\n      description: Registration token management\n      operations:\n      - method: GET\n        name: list-tokens\n        description: List registration tokens\n        call: synapse-admin.list-registration-tokens\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-token\n        description: Create a new registration token\n        call: synapse-admin.create-registration-token\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/server/version\n      name: server\n      description: Server information\n      operations:\n      - method: GET\n        name: get-version\n        description: Get Synapse server version\n        call: synapse-admin.get-server-version\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: synapse-homeserver-mcp\n    transport: http\n    description: MCP\
  \ server for AI-assisted Synapse homeserver administration.\n    tools:\n    - name: list-users\n      description: List all local users registered on the Synapse homeserver\n      hints:\n        readOnly: true\n        openWorld: false\n      call: synapse-admin.list-users\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-user\n      description: Get detailed information about a specific Matrix user\n      hints:\n        readOnly: true\n        openWorld: false\n      call: synapse-admin.get-user\n      with:\n        userId: tools.userId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-or-modify-user\n      description: Create a new user or modify an existing user account on the homeserver\n      hints:\n        readOnly: false\n        destructive: false\n      call: synapse-admin.upsert-user\n      with:\n        userId: tools.userId\n      outputParameters:\n      - type: object\n        mapping: $.\n    -\
  \ name: list-rooms\n      description: List all rooms hosted on the Synapse homeserver with member counts\n      hints:\n        readOnly: true\n        openWorld: false\n      call: synapse-admin.list-rooms\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-room\n      description: Get detailed information about a specific Matrix room\n      hints:\n        readOnly: true\n        openWorld: false\n      call: synapse-admin.get-room\n      with:\n        roomId: tools.roomId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-room-members\n      description: List all members of a specific Matrix room\n      hints:\n        readOnly: true\n        openWorld: false\n      call: synapse-admin.get-room-members\n      with:\n        roomId: tools.roomId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-registration-token\n      description: Create a new registration token for controlled\
  \ user sign-up\n      hints:\n        readOnly: false\n        destructive: false\n      call: synapse-admin.create-registration-token\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-registration-tokens\n      description: List all registration tokens and their usage status\n      hints:\n        readOnly: true\n        openWorld: false\n      call: synapse-admin.list-registration-tokens\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-server-version\n      description: Get the current Synapse homeserver version and Python version\n      hints:\n        readOnly: true\n        openWorld: false\n      call: synapse-admin.get-server-version\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/synapse/refs/heads/main/capabilities/homeserver-administration.yaml
tags:
- Administration
- Federation
- Homeserver
- Matrix
- Synapse
- Users
tools:
- description: List all local users registered on the Synapse homeserver
  hints:
    openWorld: false
    readOnly: true
  name: list-users
- description: Get detailed information about a specific Matrix user
  hints:
    openWorld: false
    readOnly: true
  name: get-user
- description: Create a new user or modify an existing user account on the homeserver
  hints:
    destructive: false
    readOnly: false
  name: create-or-modify-user
- description: List all rooms hosted on the Synapse homeserver with member counts
  hints:
    openWorld: false
    readOnly: true
  name: list-rooms
- description: Get detailed information about a specific Matrix room
  hints:
    openWorld: false
    readOnly: true
  name: get-room
- description: List all members of a specific Matrix room
  hints:
    openWorld: false
    readOnly: true
  name: get-room-members
- description: Create a new registration token for controlled user sign-up
  hints:
    destructive: false
    readOnly: false
  name: create-registration-token
- description: List all registration tokens and their usage status
  hints:
    openWorld: false
    readOnly: true
  name: list-registration-tokens
- description: Get the current Synapse homeserver version and Python version
  hints:
    openWorld: false
    readOnly: true
  name: get-server-version
---
