---
categories: []
consumed_apis:
- app-store-connect
description: Unified workflow for managing the Apple app lifecycle including app metadata, builds, TestFlight beta testing, and beta group management. Used by app developers and release managers.
layout: capability
name: Apple App Lifecycle
operations:
- description: List all apps.
  method: GET
  name: list-apps
  path: /v1/apps
- description: List all builds.
  method: GET
  name: list-builds
  path: /v1/builds
- description: List beta testers.
  method: GET
  name: list-testers
  path: /v1/testers
- description: Add a beta tester.
  method: POST
  name: create-tester
  path: /v1/testers
- description: List beta groups.
  method: GET
  name: list-groups
  path: /v1/groups
- description: Create a beta group.
  method: POST
  name: create-group
  path: /v1/groups
personas: []
provider_name: Apple
provider_slug: apple
search_terms:
- read build
- developer
- add a beta tester.
- beta tester management.
- get build details.
- read beta group
- mobile
- list beta testers.
- list all builds.
- delete beta group
- get details of a specific app.
- modify build
- modify beta group
- app management
- delete a beta group.
- get beta group details.
- read app
- add a new beta tester.
- create beta group
- create group
- list all beta testers.
- macos
- create tester
- delete beta tester
- ios
- app store
- update app metadata.
- create beta tester
- list apps
- list beta testers
- create a beta group.
- update a beta group.
- testflight
- list all apps in app store connect.
- list all beta groups.
- technology
- beta group management.
- list all apps.
- app management.
- create a new beta group.
- read beta tester
- get beta tester details.
- list builds
- apple
- modify app
- list beta groups.
- list beta groups
- build management.
- update build information.
- remove a beta tester.
- list testers
- list groups
slug: app-lifecycle
source_filename: app-lifecycle.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Apple App Lifecycle\"\n  description: \"Unified workflow for managing the Apple app lifecycle including app metadata, builds, TestFlight beta testing, and beta group management. Used by app developers and release managers.\"\n  tags:\n    - Apple\n    - App Store\n    - TestFlight\n    - App Management\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      APPLE_ASC_TOKEN: APPLE_ASC_TOKEN\n\ncapability:\n  consumes:\n    - import: app-store-connect\n      location: ./shared/app-store-connect.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: apple-app-lifecycle-api\n      description: \"Unified REST API for Apple app lifecycle management.\"\n      resources:\n        - path: /v1/apps\n          name: apps\n          description: \"App management.\"\n          operations:\n            - method: GET\n              name: list-apps\n              description: \"\
  List all apps.\"\n              call: \"app-store-connect.list-apps\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/builds\n          name: builds\n          description: \"Build management.\"\n          operations:\n            - method: GET\n              name: list-builds\n              description: \"List all builds.\"\n              call: \"app-store-connect.list-builds\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/testers\n          name: testers\n          description: \"Beta tester management.\"\n          operations:\n            - method: GET\n              name: list-testers\n              description: \"List beta testers.\"\n              call: \"app-store-connect.list-beta-testers\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n             \
  \ name: create-tester\n              description: \"Add a beta tester.\"\n              call: \"app-store-connect.create-beta-tester\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/groups\n          name: groups\n          description: \"Beta group management.\"\n          operations:\n            - method: GET\n              name: list-groups\n              description: \"List beta groups.\"\n              call: \"app-store-connect.list-beta-groups\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-group\n              description: \"Create a beta group.\"\n              call: \"app-store-connect.create-beta-group\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: apple-app-lifecycle-mcp\n      transport:\
  \ http\n      description: \"MCP server for AI-assisted Apple app lifecycle management.\"\n      tools:\n        - name: list-apps\n          description: \"List all apps in App Store Connect.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"app-store-connect.list-apps\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: read-app\n          description: \"Get details of a specific app.\"\n          hints:\n            readOnly: true\n          call: \"app-store-connect.read-app\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: modify-app\n          description: \"Update app metadata.\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"app-store-connect.modify-app\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n        - name: list-builds\n          description: \"List all builds.\"\n          hints:\n            readOnly: true\n          call: \"app-store-connect.list-builds\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: read-build\n          description: \"Get build details.\"\n          hints:\n            readOnly: true\n          call: \"app-store-connect.read-build\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: modify-build\n          description: \"Update build information.\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"app-store-connect.modify-build\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-beta-testers\n\
  \          description: \"List all beta testers.\"\n          hints:\n            readOnly: true\n          call: \"app-store-connect.list-beta-testers\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-beta-tester\n          description: \"Add a new beta tester.\"\n          hints:\n            readOnly: false\n          call: \"app-store-connect.create-beta-tester\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: read-beta-tester\n          description: \"Get beta tester details.\"\n          hints:\n            readOnly: true\n          call: \"app-store-connect.read-beta-tester\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-beta-tester\n          description: \"Remove a beta tester.\"\n          hints:\n            destructive: true\n            idempotent:\
  \ true\n          call: \"app-store-connect.delete-beta-tester\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-beta-groups\n          description: \"List all beta groups.\"\n          hints:\n            readOnly: true\n          call: \"app-store-connect.list-beta-groups\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-beta-group\n          description: \"Create a new beta group.\"\n          hints:\n            readOnly: false\n          call: \"app-store-connect.create-beta-group\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: read-beta-group\n          description: \"Get beta group details.\"\n          hints:\n            readOnly: true\n          call: \"app-store-connect.read-beta-group\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n        - name: modify-beta-group\n          description: \"Update a beta group.\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"app-store-connect.modify-beta-group\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-beta-group\n          description: \"Delete a beta group.\"\n          hints:\n            destructive: true\n            idempotent: true\n          call: \"app-store-connect.delete-beta-group\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/apple/refs/heads/main/capabilities/app-lifecycle.yaml
tags:
- Apple
- App Store
- TestFlight
- App Management
tools:
- description: List all apps in App Store Connect.
  hints:
    openWorld: true
    readOnly: true
  name: list-apps
- description: Get details of a specific app.
  hints:
    readOnly: true
  name: read-app
- description: Update app metadata.
  hints:
    idempotent: true
    readOnly: false
  name: modify-app
- description: List all builds.
  hints:
    readOnly: true
  name: list-builds
- description: Get build details.
  hints:
    readOnly: true
  name: read-build
- description: Update build information.
  hints:
    idempotent: true
    readOnly: false
  name: modify-build
- description: List all beta testers.
  hints:
    readOnly: true
  name: list-beta-testers
- description: Add a new beta tester.
  hints:
    readOnly: false
  name: create-beta-tester
- description: Get beta tester details.
  hints:
    readOnly: true
  name: read-beta-tester
- description: Remove a beta tester.
  hints:
    destructive: true
    idempotent: true
  name: delete-beta-tester
- description: List all beta groups.
  hints:
    readOnly: true
  name: list-beta-groups
- description: Create a new beta group.
  hints:
    readOnly: false
  name: create-beta-group
- description: Get beta group details.
  hints:
    readOnly: true
  name: read-beta-group
- description: Update a beta group.
  hints:
    idempotent: true
    readOnly: false
  name: modify-beta-group
- description: Delete a beta group.
  hints:
    destructive: true
    idempotent: true
  name: delete-beta-group
---
