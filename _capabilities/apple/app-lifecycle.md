---
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
- testflight
- list groups
- read beta group
- list builds
- get build details.
- modify build
- get details of a specific app.
- add a new beta tester.
- create beta tester
- update a beta group.
- beta group management.
- list all apps in app store connect.
- get beta group details.
- modify beta group
- beta tester management.
- list testers
- build management.
- list beta groups.
- list all builds.
- delete a beta group.
- app management.
- app management
- read beta tester
- create tester
- read app
- create beta group
- add a beta tester.
- get beta tester details.
- technology
- delete beta tester
- developer
- macos
- update app metadata.
- remove a beta tester.
- mobile
- list all beta groups.
- list apps
- read build
- create a new beta group.
- modify app
- ios
- list beta groups
- list beta testers
- app store
- delete beta group
- list all beta testers.
- create a beta group.
- list beta testers.
- apple
- update build information.
- list all apps.
- create group
slug: app-lifecycle
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
