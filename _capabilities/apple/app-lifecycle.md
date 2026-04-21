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
- beta tester management.
- get beta tester details.
- delete a beta group.
- delete beta tester
- apple
- app management.
- beta group management.
- create a beta group.
- testflight
- list all beta testers.
- create beta tester
- read beta group
- modify app
- update a beta group.
- ios
- modify beta group
- list apps
- create tester
- list all apps in app store connect.
- list beta groups.
- read app
- read beta tester
- list beta groups
- remove a beta tester.
- list testers
- list groups
- delete beta group
- add a beta tester.
- list all beta groups.
- list all builds.
- list beta testers.
- list all apps.
- modify build
- get build details.
- list builds
- read build
- create a new beta group.
- technology
- developer
- build management.
- add a new beta tester.
- get details of a specific app.
- app management
- create beta group
- create group
- app store
- macos
- update build information.
- list beta testers
- update app metadata.
- mobile
- get beta group details.
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
