---
categories: []
consumed_apis: []
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
- get beta tester details.
- list builds
- list apps
- get details of a specific app.
- remove a beta tester.
- modify beta group
- list all builds.
- update build information.
- developer
- create a beta group.
- get beta group details.
- list all apps in app store connect.
- list all beta testers.
- create tester
- list all apps.
- add a beta tester.
- macos
- build management.
- app management.
- create beta group
- read build
- create beta tester
- ios
- list testers
- list beta testers
- list all beta groups.
- delete a beta group.
- beta group management.
- technology
- list beta groups.
- modify build
- update app metadata.
- list beta testers.
- apple
- create a new beta group.
- testflight
- get build details.
- update a beta group.
- add a new beta tester.
- mobile
- app store
- app management
- modify app
- delete beta group
- list groups
- beta tester management.
- read app
- delete beta tester
- create group
- read beta group
- list beta groups
- read beta tester
slug: app-lifecycle
source_filename: app-lifecycle.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Apple App Lifecycle\n  description: Unified workflow for managing the Apple app lifecycle including app metadata, builds, TestFlight beta testing,\n    and beta group management. Used by app developers and release managers.\n  tags:\n  - Apple\n  - App Store\n  - TestFlight\n  - App Management\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    APPLE_ASC_TOKEN: APPLE_ASC_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: app-store-connect\n    baseUri: https://api.appstoreconnect.apple.com\n    description: Apple App Store Connect REST API for managing apps, builds, and beta testing.\n    authentication:\n      type: bearer\n      token: '{{APPLE_ASC_TOKEN}}'\n    resources:\n    - name: apps\n      path: /v1/apps\n      description: App management operations.\n      operations:\n      - name: list-apps\n        method: GET\n        description: List all apps in App Store Connect.\n \
  \       inputParameters:\n        - name: filter[bundleId]\n          in: query\n          type: string\n          required: false\n          description: Filter by bundle identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: read-app\n        method: GET\n        description: Get details of a specific app.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The app resource ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: modify-app\n        method: PATCH\n        description: Update an app's metadata.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The app resource ID.\n        body:\n          type: json\n      \
  \    data:\n            data: '{{tools.data}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: builds\n      path: /v1/builds\n      description: Build management operations.\n      operations:\n      - name: list-builds\n        method: GET\n        description: List all builds.\n        inputParameters:\n        - name: filter[app]\n          in: query\n          type: string\n          required: false\n          description: Filter by app resource ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: read-build\n        method: GET\n        description: Get details of a specific build.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The build resource ID.\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: modify-build\n        method: PATCH\n        description: Update build information.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The build resource ID.\n        body:\n          type: json\n          data:\n            data: '{{tools.data}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: beta-testers\n      path: /v1/betaTesters\n      description: Beta tester management.\n      operations:\n      - name: list-beta-testers\n        method: GET\n        description: List all beta testers.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-beta-tester\n        method: POST\n        description: Create a new beta tester.\n  \
  \      body:\n          type: json\n          data:\n            data: '{{tools.data}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: read-beta-tester\n        method: GET\n        description: Get details of a beta tester.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The beta tester resource ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-beta-tester\n        method: DELETE\n        description: Remove a beta tester.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The beta tester resource ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n     \
  \     value: $.\n    - name: beta-groups\n      path: /v1/betaGroups\n      description: Beta group management.\n      operations:\n      - name: list-beta-groups\n        method: GET\n        description: List all beta groups.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-beta-group\n        method: POST\n        description: Create a new beta group.\n        body:\n          type: json\n          data:\n            data: '{{tools.data}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: read-beta-group\n        method: GET\n        description: Get details of a beta group.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The beta group resource ID.\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: modify-beta-group\n        method: PATCH\n        description: Update a beta group.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The beta group resource ID.\n        body:\n          type: json\n          data:\n            data: '{{tools.data}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-beta-group\n        method: DELETE\n        description: Delete a beta group.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The beta group resource ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace:\
  \ apple-app-lifecycle-api\n    description: Unified REST API for Apple app lifecycle management.\n    resources:\n    - path: /v1/apps\n      name: apps\n      description: App management.\n      operations:\n      - method: GET\n        name: list-apps\n        description: List all apps.\n        call: app-store-connect.list-apps\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/builds\n      name: builds\n      description: Build management.\n      operations:\n      - method: GET\n        name: list-builds\n        description: List all builds.\n        call: app-store-connect.list-builds\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/testers\n      name: testers\n      description: Beta tester management.\n      operations:\n      - method: GET\n        name: list-testers\n        description: List beta testers.\n        call: app-store-connect.list-beta-testers\n        outputParameters:\n      \
  \  - type: object\n          mapping: $.\n      - method: POST\n        name: create-tester\n        description: Add a beta tester.\n        call: app-store-connect.create-beta-tester\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/groups\n      name: groups\n      description: Beta group management.\n      operations:\n      - method: GET\n        name: list-groups\n        description: List beta groups.\n        call: app-store-connect.list-beta-groups\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-group\n        description: Create a beta group.\n        call: app-store-connect.create-beta-group\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: apple-app-lifecycle-mcp\n    transport: http\n    description: MCP server for AI-assisted Apple app lifecycle management.\n    tools:\n    - name: list-apps\n\
  \      description: List all apps in App Store Connect.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: app-store-connect.list-apps\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: read-app\n      description: Get details of a specific app.\n      hints:\n        readOnly: true\n      call: app-store-connect.read-app\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: modify-app\n      description: Update app metadata.\n      hints:\n        readOnly: false\n        idempotent: true\n      call: app-store-connect.modify-app\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-builds\n      description: List all builds.\n      hints:\n        readOnly: true\n      call: app-store-connect.list-builds\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: read-build\n      description:\
  \ Get build details.\n      hints:\n        readOnly: true\n      call: app-store-connect.read-build\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: modify-build\n      description: Update build information.\n      hints:\n        readOnly: false\n        idempotent: true\n      call: app-store-connect.modify-build\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-beta-testers\n      description: List all beta testers.\n      hints:\n        readOnly: true\n      call: app-store-connect.list-beta-testers\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-beta-tester\n      description: Add a new beta tester.\n      hints:\n        readOnly: false\n      call: app-store-connect.create-beta-tester\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: read-beta-tester\n      description: Get\
  \ beta tester details.\n      hints:\n        readOnly: true\n      call: app-store-connect.read-beta-tester\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-beta-tester\n      description: Remove a beta tester.\n      hints:\n        destructive: true\n        idempotent: true\n      call: app-store-connect.delete-beta-tester\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-beta-groups\n      description: List all beta groups.\n      hints:\n        readOnly: true\n      call: app-store-connect.list-beta-groups\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-beta-group\n      description: Create a new beta group.\n      hints:\n        readOnly: false\n      call: app-store-connect.create-beta-group\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: read-beta-group\n     \
  \ description: Get beta group details.\n      hints:\n        readOnly: true\n      call: app-store-connect.read-beta-group\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: modify-beta-group\n      description: Update a beta group.\n      hints:\n        readOnly: false\n        idempotent: true\n      call: app-store-connect.modify-beta-group\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-beta-group\n      description: Delete a beta group.\n      hints:\n        destructive: true\n        idempotent: true\n      call: app-store-connect.delete-beta-group\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
