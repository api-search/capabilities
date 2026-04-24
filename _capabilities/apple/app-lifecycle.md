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
- create tester
- beta group management.
- developer
- apple
- create group
- list all beta testers.
- technology
- read build
- delete a beta group.
- get details of a specific app.
- create a new beta group.
- list beta testers.
- list all beta groups.
- update a beta group.
- delete beta group
- list beta groups
- create beta tester
- get build details.
- testflight
- add a beta tester.
- list all apps in app store connect.
- create beta group
- read beta group
- list all apps.
- create a beta group.
- remove a beta tester.
- list builds
- list beta groups.
- list beta testers
- macos
- update build information.
- read app
- app management.
- ios
- list testers
- add a new beta tester.
- app store
- modify app
- get beta group details.
- mobile
- build management.
- modify build
- list apps
- delete beta tester
- beta tester management.
- read beta tester
- modify beta group
- list all builds.
- get beta tester details.
- list groups
- app management
- update app metadata.
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
