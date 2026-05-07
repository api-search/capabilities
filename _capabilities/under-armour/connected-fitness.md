---
categories: []
consumed_apis: []
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
- workouts
- get heart rate training zones configured for a user
- list workouts
- list workouts for a user
- get route
- create a new route
- single route with optional gps waypoints
- get a route by id
- create workout
- create route
- user search and social connections
- connected fitness
- registered fitness devices
- get a workout by id
- health
- create webhook
- search for users or retrieve social connections and friend lists
- fitness workouts with aggregates
- delete workout
- list fitness devices for a user
- under armour
- fitness
- get the profile of the currently authenticated user
- list routes for a user or near a location
- record a new fitness workout with distance, time, and energy metrics
- get route details including gps waypoints and elevation data
- single workout record
- list users
- routes
- delete a workout record
- create a new workout
- list routes
- list webhooks
- fortune 1000
- webhook event subscriptions
- create a webhook subscription
- list devices
- get the authenticated user's profile
- list fitness routes for a user or near a geographic location
- sports
- list heart rate zones
- wearables
- get current user
- search users or retrieve friend connections
- list webhook subscriptions
- list fitness workouts for a user with optional date and activity type filters
- create a new fitness route with gps waypoints
- list fitness devices and wearables registered to a user
- get heart rate zones for a user
- get workout
- delete a workout
- subscribe to fitness events like workout creation and updates via webhook
- get a specific workout record including aggregate metrics and optional time series gps data
- heart rate training zones
- fitness routes with gps data
- current authenticated user profile
slug: connected-fitness
source_filename: connected-fitness.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Under Armour Connected Fitness\n  description: Unified capability for Under Armour's Connected Fitness platform. Combines workout tracking, route management,\n    user profiles, and heart rate zones into a single workflow surface for fitness app developers, health platform integrators,\n    and athlete analytics use cases.\n  tags:\n  - Under Armour\n  - Fitness\n  - Connected Fitness\n  - Workouts\n  - Routes\n  - Health\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    MAPMYFITNESS_ACCESS_TOKEN: MAPMYFITNESS_ACCESS_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: mapmyfitness\n    baseUri: https://api.ua.com\n    description: Under Armour MapMyFitness Connected Fitness REST API\n    authentication:\n      type: bearer\n      token: '{{MAPMYFITNESS_ACCESS_TOKEN}}'\n    resources:\n    - name: workouts\n      path: /v7.1/workout/\n      description: Fitness workout records with aggregates\
  \ and time series\n      operations:\n      - name: list-workouts\n        method: GET\n        description: List workouts for a user with optional filters\n        inputParameters:\n        - name: user\n          in: query\n          type: string\n          required: true\n          description: User ID to filter workouts by\n        - name: activity_type\n          in: query\n          type: string\n          required: false\n          description: Activity type filter\n        - name: order_by\n          in: query\n          type: string\n          required: false\n          description: Sort order (start_datetime or -start_datetime)\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Number of results per page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-workout\n        method: POST\n        description: Create\
  \ a new fitness workout\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            start_datetime: '{{tools.start_datetime}}'\n            start_locale_timezone: '{{tools.timezone}}'\n            aggregates: '{{tools.aggregates}}'\n    - name: workout-item\n      path: /v7.1/workout/{id}/\n      description: Single workout operations\n      operations:\n      - name: get-workout\n        method: GET\n        description: Get a single workout by ID\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Workout ID\n        - name: field_set\n          in: query\n          type: string\n          required: false\n          description: Set to time_series for GPS and metric data\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: delete-workout\n        method: DELETE\n        description: Delete a workout\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Workout ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: routes\n      path: /v7.1/route/\n      description: Fitness routes with GPS waypoints and elevation data\n      operations:\n      - name: list-routes\n        method: GET\n        description: List routes for a user or near a location\n        inputParameters:\n        - name: user\n          in: query\n          type: string\n          required: false\n          description: User ID\n        - name: close_to_location\n          in: query\n          type: string\n          required: false\n          description: Lat,lng for proximity search\n\
  \        - name: search_radius\n          in: query\n          type: integer\n          required: false\n          description: Search radius in meters\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-route\n        method: POST\n        description: Create a new route\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            distance: '{{tools.distance}}'\n            description: '{{tools.description}}'\n    - name: route-item\n      path: /v7.1/route/{id}/\n      description: Single route operations\n      operations:\n      - name: get-route\n        method: GET\n        description: Get a single route by ID\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required:\
  \ true\n          description: Route ID\n        - name: field_set\n          in: query\n          type: string\n          required: false\n          description: default or detailed (includes GPS points)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users\n      path: /v7.1/user/\n      description: User profile search and social connections\n      operations:\n      - name: list-users\n        method: GET\n        description: Search for users or get social connections\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: false\n          description: Search query\n        - name: friends_with\n          in: query\n          type: string\n          required: false\n          description: Get friends of this user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n\
  \    - name: user-self\n      path: /v7.1/user/self/\n      description: Current authenticated user profile\n      operations:\n      - name: get-current-user\n        method: GET\n        description: Get the current authenticated user's profile\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: heart-rate-zones\n      path: /v7.1/heart_rate_zone/\n      description: Heart rate zone configuration\n      operations:\n      - name: list-heart-rate-zones\n        method: GET\n        description: Get heart rate zones for a user\n        inputParameters:\n        - name: user\n          in: query\n          type: string\n          required: true\n          description: User ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: devices\n      path: /v7.1/device/\n      description: Registered fitness devices\n    \
  \  operations:\n      - name: list-devices\n        method: GET\n        description: List fitness devices for a user\n        inputParameters:\n        - name: user\n          in: query\n          type: string\n          required: true\n          description: User ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: webhooks\n      path: /v7.1/webhook/\n      description: Webhook event subscriptions\n      operations:\n      - name: list-webhooks\n        method: GET\n        description: List webhook subscriptions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-webhook\n        method: POST\n        description: Create a webhook subscription\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type:\
  \ json\n          data:\n            callback_url: '{{tools.callback_url}}'\n            event_type: '{{tools.event_type}}'\n            shared_secret: '{{tools.shared_secret}}'\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: connected-fitness-api\n    description: Unified REST API for Under Armour Connected Fitness.\n    resources:\n    - path: /v1/workouts\n      name: workouts\n      description: Fitness workouts with aggregates\n      operations:\n      - method: GET\n        name: list-workouts\n        description: List workouts for a user\n        call: mapmyfitness.list-workouts\n        with:\n          user: rest.user\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-workout\n        description: Create a new workout\n        call: mapmyfitness.create-workout\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/workouts/{id}\n      name: workout-item\n      description:\
  \ Single workout record\n      operations:\n      - method: GET\n        name: get-workout\n        description: Get a workout by ID\n        call: mapmyfitness.get-workout\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-workout\n        description: Delete a workout\n        call: mapmyfitness.delete-workout\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/routes\n      name: routes\n      description: Fitness routes with GPS data\n      operations:\n      - method: GET\n        name: list-routes\n        description: List routes for a user or near a location\n        call: mapmyfitness.list-routes\n        with:\n          user: rest.user\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-route\n        description: Create a new route\n\
  \        call: mapmyfitness.create-route\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/routes/{id}\n      name: route-item\n      description: Single route with optional GPS waypoints\n      operations:\n      - method: GET\n        name: get-route\n        description: Get a route by ID\n        call: mapmyfitness.get-route\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/users/me\n      name: current-user\n      description: Current authenticated user profile\n      operations:\n      - method: GET\n        name: get-current-user\n        description: Get the authenticated user's profile\n        call: mapmyfitness.get-current-user\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/users\n      name: users\n      description: User search and social connections\n      operations:\n      - method: GET\n        name: list-users\n\
  \        description: Search users or retrieve friend connections\n        call: mapmyfitness.list-users\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/heart-rate-zones\n      name: heart-rate-zones\n      description: Heart rate training zones\n      operations:\n      - method: GET\n        name: list-heart-rate-zones\n        description: Get heart rate zones for a user\n        call: mapmyfitness.list-heart-rate-zones\n        with:\n          user: rest.user\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/devices\n      name: devices\n      description: Registered fitness devices\n      operations:\n      - method: GET\n        name: list-devices\n        description: List fitness devices for a user\n        call: mapmyfitness.list-devices\n        with:\n          user: rest.user\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/webhooks\n      name: webhooks\n\
  \      description: Webhook event subscriptions\n      operations:\n      - method: GET\n        name: list-webhooks\n        description: List webhook subscriptions\n        call: mapmyfitness.list-webhooks\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-webhook\n        description: Create a webhook subscription\n        call: mapmyfitness.create-webhook\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: connected-fitness-mcp\n    transport: http\n    description: MCP server for AI-assisted fitness tracking and analysis with Under Armour Connected Fitness.\n    tools:\n    - name: list-workouts\n      description: List fitness workouts for a user with optional date and activity type filters\n      hints:\n        readOnly: true\n        openWorld: false\n      call: mapmyfitness.list-workouts\n      with:\n        user: tools.user\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: get-workout\n      description: Get a specific workout record including aggregate metrics and optional time series GPS data\n      hints:\n        readOnly: true\n        openWorld: false\n      call: mapmyfitness.get-workout\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-workout\n      description: Record a new fitness workout with distance, time, and energy metrics\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: mapmyfitness.create-workout\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-workout\n      description: Delete a workout record\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: mapmyfitness.delete-workout\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n      \
  \  mapping: $.\n    - name: list-routes\n      description: List fitness routes for a user or near a geographic location\n      hints:\n        readOnly: true\n        openWorld: true\n      call: mapmyfitness.list-routes\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-route\n      description: Get route details including GPS waypoints and elevation data\n      hints:\n        readOnly: true\n        openWorld: false\n      call: mapmyfitness.get-route\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-route\n      description: Create a new fitness route with GPS waypoints\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: mapmyfitness.create-route\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-current-user\n      description: Get the profile of the currently authenticated user\n      hints:\n\
  \        readOnly: true\n        openWorld: false\n      call: mapmyfitness.get-current-user\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-users\n      description: Search for users or retrieve social connections and friend lists\n      hints:\n        readOnly: true\n        openWorld: true\n      call: mapmyfitness.list-users\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-heart-rate-zones\n      description: Get heart rate training zones configured for a user\n      hints:\n        readOnly: true\n        openWorld: false\n      call: mapmyfitness.list-heart-rate-zones\n      with:\n        user: tools.user\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-devices\n      description: List fitness devices and wearables registered to a user\n      hints:\n        readOnly: true\n        openWorld: false\n      call: mapmyfitness.list-devices\n      with:\n        user: tools.user\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-webhook\n      description: Subscribe to fitness events like workout creation and updates via webhook\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: mapmyfitness.create-webhook\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
