---
api_specs:
- filename: mapmyfitness-openapi.yml
  format: yaml
  label: mapmyfitness
  slug: mapmyfitness
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/under-armour/refs/heads/main/openapi/mapmyfitness-openapi.yml
categories: []
consumed_apis:
- mapmyfitness
description: Unified capability for Under Armour's Connected Fitness platform. Combines workout tracking, route management, user profiles, and heart rate zones into a single workflow surface for fitness app developers, health platform integrators, and athlete analytics use cases.
layout: capability
name: Under Armour Connected Fitness
operations:
- description: List workouts for a user
  method: GET
  name: list-workouts
  path: /v1/workouts
- description: Create a new workout
  method: POST
  name: create-workout
  path: /v1/workouts
- description: Get a workout by ID
  method: GET
  name: get-workout
  path: /v1/workouts/{id}
- description: Delete a workout
  method: DELETE
  name: delete-workout
  path: /v1/workouts/{id}
- description: List routes for a user or near a location
  method: GET
  name: list-routes
  path: /v1/routes
- description: Create a new route
  method: POST
  name: create-route
  path: /v1/routes
- description: Get a route by ID
  method: GET
  name: get-route
  path: /v1/routes/{id}
- description: Get the authenticated user's profile
  method: GET
  name: get-current-user
  path: /v1/users/me
- description: Search users or retrieve friend connections
  method: GET
  name: list-users
  path: /v1/users
- description: Get heart rate zones for a user
  method: GET
  name: list-heart-rate-zones
  path: /v1/heart-rate-zones
- description: List fitness devices for a user
  method: GET
  name: list-devices
  path: /v1/devices
- description: List webhook subscriptions
  method: GET
  name: list-webhooks
  path: /v1/webhooks
- description: Create a webhook subscription
  method: POST
  name: create-webhook
  path: /v1/webhooks
personas: []
provider_name: Under Armour
provider_slug: under-armour
search_terms:
- list fitness workouts for a user with optional date and activity type filters
- get the authenticated user's profile
- create a new fitness route with gps waypoints
- get a route by id
- list users
- registered fitness devices
- connected fitness
- search for users or retrieve social connections and friend lists
- search users or retrieve friend connections
- record a new fitness workout with distance, time, and energy metrics
- create a new workout
- subscribe to fitness events like workout creation and updates via webhook
- delete a workout record
- get workout
- get current user
- under armour
- create workout
- delete a workout
- list fitness devices for a user
- user search and social connections
- webhook event subscriptions
- list fitness devices and wearables registered to a user
- routes
- current authenticated user profile
- create webhook
- list devices
- get route
- get a workout by id
- create route
- get heart rate zones for a user
- create a webhook subscription
- sports
- get a specific workout record including aggregate metrics and optional time series gps data
- list webhook subscriptions
- fitness
- get route details including gps waypoints and elevation data
- list fitness routes for a user or near a geographic location
- workouts
- list workouts
- list routes for a user or near a location
- get the profile of the currently authenticated user
- fitness workouts with aggregates
- create a new route
- list routes
- get heart rate training zones configured for a user
- list workouts for a user
- health
- heart rate training zones
- wearables
- fortune 1000
- single workout record
- list heart rate zones
- single route with optional gps waypoints
- list webhooks
- delete workout
- fitness routes with gps data
slug: connected-fitness
source_filename: connected-fitness.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Under Armour Connected Fitness\"\n  description: >-\n    Unified capability for Under Armour's Connected Fitness platform.\n    Combines workout tracking, route management, user profiles, and heart\n    rate zones into a single workflow surface for fitness app developers,\n    health platform integrators, and athlete analytics use cases.\n  tags:\n    - Under Armour\n    - Fitness\n    - Connected Fitness\n    - Workouts\n    - Routes\n    - Health\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      MAPMYFITNESS_ACCESS_TOKEN: MAPMYFITNESS_ACCESS_TOKEN\n\ncapability:\n  consumes:\n    - import: mapmyfitness\n      location: ./shared/mapmyfitness.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: connected-fitness-api\n      description: \"Unified REST API for Under Armour Connected Fitness.\"\n      resources:\n        - path: /v1/workouts\n          name:\
  \ workouts\n          description: \"Fitness workouts with aggregates\"\n          operations:\n            - method: GET\n              name: list-workouts\n              description: \"List workouts for a user\"\n              call: \"mapmyfitness.list-workouts\"\n              with:\n                user: \"rest.user\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-workout\n              description: \"Create a new workout\"\n              call: \"mapmyfitness.create-workout\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/workouts/{id}\n          name: workout-item\n          description: \"Single workout record\"\n          operations:\n            - method: GET\n              name: get-workout\n              description: \"Get a workout by ID\"\n              call: \"mapmyfitness.get-workout\"\n    \
  \          with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-workout\n              description: \"Delete a workout\"\n              call: \"mapmyfitness.delete-workout\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/routes\n          name: routes\n          description: \"Fitness routes with GPS data\"\n          operations:\n            - method: GET\n              name: list-routes\n              description: \"List routes for a user or near a location\"\n              call: \"mapmyfitness.list-routes\"\n              with:\n                user: \"rest.user\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-route\n\
  \              description: \"Create a new route\"\n              call: \"mapmyfitness.create-route\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/routes/{id}\n          name: route-item\n          description: \"Single route with optional GPS waypoints\"\n          operations:\n            - method: GET\n              name: get-route\n              description: \"Get a route by ID\"\n              call: \"mapmyfitness.get-route\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/users/me\n          name: current-user\n          description: \"Current authenticated user profile\"\n          operations:\n            - method: GET\n              name: get-current-user\n              description: \"Get the authenticated user's profile\"\n              call: \"mapmyfitness.get-current-user\"\n\
  \              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/users\n          name: users\n          description: \"User search and social connections\"\n          operations:\n            - method: GET\n              name: list-users\n              description: \"Search users or retrieve friend connections\"\n              call: \"mapmyfitness.list-users\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/heart-rate-zones\n          name: heart-rate-zones\n          description: \"Heart rate training zones\"\n          operations:\n            - method: GET\n              name: list-heart-rate-zones\n              description: \"Get heart rate zones for a user\"\n              call: \"mapmyfitness.list-heart-rate-zones\"\n              with:\n                user: \"rest.user\"\n              outputParameters:\n                - type: object\n            \
  \      mapping: \"$.\"\n        - path: /v1/devices\n          name: devices\n          description: \"Registered fitness devices\"\n          operations:\n            - method: GET\n              name: list-devices\n              description: \"List fitness devices for a user\"\n              call: \"mapmyfitness.list-devices\"\n              with:\n                user: \"rest.user\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/webhooks\n          name: webhooks\n          description: \"Webhook event subscriptions\"\n          operations:\n            - method: GET\n              name: list-webhooks\n              description: \"List webhook subscriptions\"\n              call: \"mapmyfitness.list-webhooks\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-webhook\n              description: \"Create a\
  \ webhook subscription\"\n              call: \"mapmyfitness.create-webhook\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: connected-fitness-mcp\n      transport: http\n      description: \"MCP server for AI-assisted fitness tracking and analysis with Under Armour Connected Fitness.\"\n      tools:\n        - name: list-workouts\n          description: \"List fitness workouts for a user with optional date and activity type filters\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"mapmyfitness.list-workouts\"\n          with:\n            user: \"tools.user\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-workout\n          description: \"Get a specific workout record including aggregate metrics and optional time series GPS data\"\n          hints:\n            readOnly:\
  \ true\n            openWorld: false\n          call: \"mapmyfitness.get-workout\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-workout\n          description: \"Record a new fitness workout with distance, time, and energy metrics\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"mapmyfitness.create-workout\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-workout\n          description: \"Delete a workout record\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"mapmyfitness.delete-workout\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-routes\n\
  \          description: \"List fitness routes for a user or near a geographic location\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"mapmyfitness.list-routes\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-route\n          description: \"Get route details including GPS waypoints and elevation data\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"mapmyfitness.get-route\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-route\n          description: \"Create a new fitness route with GPS waypoints\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"mapmyfitness.create-route\"\n          outputParameters:\n            - type: object\n           \
  \   mapping: \"$.\"\n        - name: get-current-user\n          description: \"Get the profile of the currently authenticated user\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"mapmyfitness.get-current-user\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-users\n          description: \"Search for users or retrieve social connections and friend lists\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"mapmyfitness.list-users\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-heart-rate-zones\n          description: \"Get heart rate training zones configured for a user\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"mapmyfitness.list-heart-rate-zones\"\n          with:\n            user: \"tools.user\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n        - name: list-devices\n          description: \"List fitness devices and wearables registered to a user\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"mapmyfitness.list-devices\"\n          with:\n            user: \"tools.user\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-webhook\n          description: \"Subscribe to fitness events like workout creation and updates via webhook\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"mapmyfitness.create-webhook\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/under-armour/refs/heads/main/capabilities/connected-fitness.yaml
tags:
- Under Armour
- Fitness
- Connected Fitness
- Workouts
- Routes
- Health
tools:
- description: List fitness workouts for a user with optional date and activity type filters
  hints:
    openWorld: false
    readOnly: true
  name: list-workouts
- description: Get a specific workout record including aggregate metrics and optional time series GPS data
  hints:
    openWorld: false
    readOnly: true
  name: get-workout
- description: Record a new fitness workout with distance, time, and energy metrics
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-workout
- description: Delete a workout record
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-workout
- description: List fitness routes for a user or near a geographic location
  hints:
    openWorld: true
    readOnly: true
  name: list-routes
- description: Get route details including GPS waypoints and elevation data
  hints:
    openWorld: false
    readOnly: true
  name: get-route
- description: Create a new fitness route with GPS waypoints
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-route
- description: Get the profile of the currently authenticated user
  hints:
    openWorld: false
    readOnly: true
  name: get-current-user
- description: Search for users or retrieve social connections and friend lists
  hints:
    openWorld: true
    readOnly: true
  name: list-users
- description: Get heart rate training zones configured for a user
  hints:
    openWorld: false
    readOnly: true
  name: list-heart-rate-zones
- description: List fitness devices and wearables registered to a user
  hints:
    openWorld: false
    readOnly: true
  name: list-devices
- description: Subscribe to fitness events like workout creation and updates via webhook
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-webhook
---
