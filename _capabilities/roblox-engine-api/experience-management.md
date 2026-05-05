---
categories: []
consumed_apis:
- roblox
description: Unified workflow capability for managing Roblox experiences using the Open Cloud API. Combines universe configuration, place publishing, data store management, cross-server messaging, player moderation, and community management into workflows for Roblox game developers and operations teams.
layout: capability
name: Roblox Experience Management
operations:
- description: Get details about a Roblox experience
  method: GET
  name: get-universe
  path: /v1/universes/{universeId}
- description: Update experience settings
  method: PATCH
  name: update-universe
  path: /v1/universes/{universeId}
- description: Get details about a place
  method: GET
  name: get-place
  path: /v1/universes/{universeId}/places/{placeId}
- description: List all data stores in a universe
  method: GET
  name: list-data-stores
  path: /v1/universes/{universeId}/data-stores
- description: Get a data store entry
  method: GET
  name: get-entry
  path: /v1/universes/{universeId}/data-stores/{storeName}/entries
- description: Set a data store entry
  method: POST
  name: set-entry
  path: /v1/universes/{universeId}/data-stores/{storeName}/entries
- description: Delete a data store entry
  method: DELETE
  name: delete-entry
  path: /v1/universes/{universeId}/data-stores/{storeName}/entries
- description: Publish a message to all universe servers
  method: POST
  name: publish-message
  path: /v1/universes/{universeId}/messaging/{topic}
- description: Check player restriction status
  method: GET
  name: get-restriction
  path: /v1/universes/{universeId}/user-restrictions/{userId}
- description: Ban or unban a player
  method: PATCH
  name: update-restriction
  path: /v1/universes/{universeId}/user-restrictions/{userId}
- description: Get a Roblox user
  method: GET
  name: get-user
  path: /v1/users/{userId}
- description: Get a Roblox group
  method: GET
  name: get-group
  path: /v1/groups/{groupId}
- description: List group members and roles
  method: GET
  name: list-memberships
  path: /v1/groups/{groupId}/memberships
personas: []
provider_name: Roblox Engine API
provider_slug: roblox-engine-api
search_terms:
- data store management
- delete a data store entry
- set a data store entry
- list memberships
- update restriction
- ban a player from accessing a universe (set user restriction)
- set or update a data store entry value
- get details about a specific place within a universe
- get details about a roblox experience including settings and metadata
- roblox
- metaverse
- group membership
- broadcast a message to all active servers in a universe
- get user
- update experience settings
- retrieve a player or game data store entry by key
- player moderation
- list group members and roles
- check player restriction status
- get place
- get details about a place
- set data store entry
- list group memberships
- update the settings for a roblox experience
- get restriction
- experience universe management
- open cloud
- get information about a roblox player by user id
- ban player
- list members and their roles in a roblox group
- check if a player is banned or restricted from a universe
- publish message
- user information
- ban or unban a player
- get details about a roblox experience
- publish a message to all universe servers
- set entry
- delete entry
- gaming
- get a roblox user
- experiences
- get universe
- update universe
- get group
- list data stores
- get entry
- list all data stores available in a universe
- get data store entry
- get user restriction
- place management
- get a data store entry
- cross-server messaging
- get a roblox group
- game development
- community group management
- data store entry management
- list all data stores in a universe
- get information about a roblox community group
- delete data store entry
slug: experience-management
source_filename: experience-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Roblox Experience Management\"\n  description: >-\n    Unified workflow capability for managing Roblox experiences using the\n    Open Cloud API. Combines universe configuration, place publishing, data\n    store management, cross-server messaging, player moderation, and community\n    management into workflows for Roblox game developers and operations teams.\n  tags:\n    - Gaming\n    - Game Development\n    - Roblox\n    - Open Cloud\n    - Experiences\n    - Metaverse\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      ROBLOX_API_KEY: ROBLOX_API_KEY\n\ncapability:\n  consumes:\n    - import: roblox\n      location: ./shared/open-cloud.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: roblox-experience-api\n      description: \"Unified REST API for Roblox experience management including universes, data stores, players, and communities.\"\n      resources:\n\
  \        - path: /v1/universes/{universeId}\n          name: universe\n          description: \"Experience universe management\"\n          operations:\n            - method: GET\n              name: get-universe\n              description: \"Get details about a Roblox experience\"\n              call: \"roblox.get-universe\"\n              with:\n                universeId: \"rest.universeId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PATCH\n              name: update-universe\n              description: \"Update experience settings\"\n              call: \"roblox.update-universe\"\n              with:\n                universeId: \"rest.universeId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/universes/{universeId}/places/{placeId}\n          name: place\n          description: \"Place management\"\n          operations:\n   \
  \         - method: GET\n              name: get-place\n              description: \"Get details about a place\"\n              call: \"roblox.get-place\"\n              with:\n                universeId: \"rest.universeId\"\n                placeId: \"rest.placeId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/universes/{universeId}/data-stores\n          name: data-stores\n          description: \"Data store management\"\n          operations:\n            - method: GET\n              name: list-data-stores\n              description: \"List all data stores in a universe\"\n              call: \"roblox.list-data-stores\"\n              with:\n                universeId: \"rest.universeId\"\n                prefix: \"rest.prefix\"\n                limit: \"rest.limit\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/universes/{universeId}/data-stores/{storeName}/entries\n\
  \          name: data-store-entries\n          description: \"Data store entry management\"\n          operations:\n            - method: GET\n              name: get-entry\n              description: \"Get a data store entry\"\n              call: \"roblox.get-data-store-entry\"\n              with:\n                universeId: \"rest.universeId\"\n                datastoreName: \"rest.storeName\"\n                entryKey: \"rest.entryKey\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: set-entry\n              description: \"Set a data store entry\"\n              call: \"roblox.set-data-store-entry\"\n              with:\n                universeId: \"rest.universeId\"\n                datastoreName: \"rest.storeName\"\n                entryKey: \"rest.entryKey\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method:\
  \ DELETE\n              name: delete-entry\n              description: \"Delete a data store entry\"\n              call: \"roblox.delete-data-store-entry\"\n              with:\n                universeId: \"rest.universeId\"\n                datastoreName: \"rest.storeName\"\n                entryKey: \"rest.entryKey\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/universes/{universeId}/messaging/{topic}\n          name: messaging\n          description: \"Cross-server messaging\"\n          operations:\n            - method: POST\n              name: publish-message\n              description: \"Publish a message to all universe servers\"\n              call: \"roblox.publish-message\"\n              with:\n                universeId: \"rest.universeId\"\n                topic: \"rest.topic\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path:\
  \ /v1/universes/{universeId}/user-restrictions/{userId}\n          name: user-restrictions\n          description: \"Player moderation\"\n          operations:\n            - method: GET\n              name: get-restriction\n              description: \"Check player restriction status\"\n              call: \"roblox.get-user-restriction\"\n              with:\n                universeId: \"rest.universeId\"\n                userId: \"rest.userId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PATCH\n              name: update-restriction\n              description: \"Ban or unban a player\"\n              call: \"roblox.update-user-restriction\"\n              with:\n                universeId: \"rest.universeId\"\n                userId: \"rest.userId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/users/{userId}\n          name: users\n\
  \          description: \"User information\"\n          operations:\n            - method: GET\n              name: get-user\n              description: \"Get a Roblox user\"\n              call: \"roblox.get-user\"\n              with:\n                userId: \"rest.userId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/groups/{groupId}\n          name: groups\n          description: \"Community group management\"\n          operations:\n            - method: GET\n              name: get-group\n              description: \"Get a Roblox group\"\n              call: \"roblox.get-group\"\n              with:\n                groupId: \"rest.groupId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/groups/{groupId}/memberships\n          name: group-memberships\n          description: \"Group membership\"\n          operations:\n        \
  \    - method: GET\n              name: list-memberships\n              description: \"List group members and roles\"\n              call: \"roblox.list-group-memberships\"\n              with:\n                groupId: \"rest.groupId\"\n                maxPageSize: \"rest.maxPageSize\"\n                pageToken: \"rest.pageToken\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9080\n      namespace: roblox-experience-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Roblox experience management and community operations.\"\n      tools:\n        - name: get-universe\n          description: \"Get details about a Roblox experience including settings and metadata\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"roblox.get-universe\"\n          with:\n            universeId: \"tools.universeId\"\n          outputParameters:\n      \
  \      - type: object\n              mapping: \"$.\"\n\n        - name: update-universe\n          description: \"Update the settings for a Roblox experience\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"roblox.update-universe\"\n          with:\n            universeId: \"tools.universeId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-place\n          description: \"Get details about a specific place within a universe\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"roblox.get-place\"\n          with:\n            universeId: \"tools.universeId\"\n            placeId: \"tools.placeId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-data-stores\n          description: \"List all data stores available in a universe\"\n          hints:\n\
  \            readOnly: true\n            openWorld: false\n          call: \"roblox.list-data-stores\"\n          with:\n            universeId: \"tools.universeId\"\n            prefix: \"tools.prefix\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-data-store-entry\n          description: \"Retrieve a player or game data store entry by key\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"roblox.get-data-store-entry\"\n          with:\n            universeId: \"tools.universeId\"\n            datastoreName: \"tools.datastoreName\"\n            entryKey: \"tools.entryKey\"\n            scope: \"tools.scope\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: set-data-store-entry\n          description: \"Set or update a data store entry value\"\n          hints:\n            readOnly: false\n            destructive: false\n\
  \            idempotent: true\n          call: \"roblox.set-data-store-entry\"\n          with:\n            universeId: \"tools.universeId\"\n            datastoreName: \"tools.datastoreName\"\n            entryKey: \"tools.entryKey\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: delete-data-store-entry\n          description: \"Delete a data store entry\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"roblox.delete-data-store-entry\"\n          with:\n            universeId: \"tools.universeId\"\n            datastoreName: \"tools.datastoreName\"\n            entryKey: \"tools.entryKey\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: publish-message\n          description: \"Broadcast a message to all active servers in a universe\"\n          hints:\n            readOnly: false\n      \
  \      destructive: false\n          call: \"roblox.publish-message\"\n          with:\n            universeId: \"tools.universeId\"\n            topic: \"tools.topic\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-user\n          description: \"Get information about a Roblox player by user ID\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"roblox.get-user\"\n          with:\n            userId: \"tools.userId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-group\n          description: \"Get information about a Roblox community group\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"roblox.get-group\"\n          with:\n            groupId: \"tools.groupId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-group-memberships\n\
  \          description: \"List members and their roles in a Roblox group\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"roblox.list-group-memberships\"\n          with:\n            groupId: \"tools.groupId\"\n            maxPageSize: \"tools.maxPageSize\"\n            pageToken: \"tools.pageToken\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-user-restriction\n          description: \"Check if a player is banned or restricted from a universe\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"roblox.get-user-restriction\"\n          with:\n            universeId: \"tools.universeId\"\n            userId: \"tools.userId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: ban-player\n          description: \"Ban a player from accessing a universe (set user restriction)\"\n\
  \          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"roblox.update-user-restriction\"\n          with:\n            universeId: \"tools.universeId\"\n            userId: \"tools.userId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/roblox-engine-api/refs/heads/main/capabilities/experience-management.yaml
tags:
- Gaming
- Game Development
- Roblox
- Open Cloud
- Experiences
- Metaverse
tools:
- description: Get details about a Roblox experience including settings and metadata
  hints:
    openWorld: false
    readOnly: true
  name: get-universe
- description: Update the settings for a Roblox experience
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: update-universe
- description: Get details about a specific place within a universe
  hints:
    openWorld: false
    readOnly: true
  name: get-place
- description: List all data stores available in a universe
  hints:
    openWorld: false
    readOnly: true
  name: list-data-stores
- description: Retrieve a player or game data store entry by key
  hints:
    openWorld: false
    readOnly: true
  name: get-data-store-entry
- description: Set or update a data store entry value
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: set-data-store-entry
- description: Delete a data store entry
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-data-store-entry
- description: Broadcast a message to all active servers in a universe
  hints:
    destructive: false
    readOnly: false
  name: publish-message
- description: Get information about a Roblox player by user ID
  hints:
    openWorld: true
    readOnly: true
  name: get-user
- description: Get information about a Roblox community group
  hints:
    openWorld: true
    readOnly: true
  name: get-group
- description: List members and their roles in a Roblox group
  hints:
    openWorld: false
    readOnly: true
  name: list-group-memberships
- description: Check if a player is banned or restricted from a universe
  hints:
    openWorld: false
    readOnly: true
  name: get-user-restriction
- description: Ban a player from accessing a universe (set user restriction)
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: ban-player
---
