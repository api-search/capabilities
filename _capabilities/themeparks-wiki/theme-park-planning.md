---
categories: []
consumed_apis: []
description: Unified workflow for theme park trip planning and real-time park monitoring. Combines destination discovery, live wait time monitoring, schedule lookups, and attraction browsing for park visitors, travel planners, and AI assistants.
layout: capability
name: ThemeParks.wiki Theme Park Planning
operations:
- description: List all supported theme park destinations
  method: GET
  name: list-destinations
  path: /v1/destinations
- description: Get details for a specific park
  method: GET
  name: get-park
  path: /v1/parks/{id}
- description: Get all attractions and entities in a park
  method: GET
  name: get-attractions
  path: /v1/parks/{id}/attractions
- description: Get current live wait times for all attractions
  method: GET
  name: get-live-wait-times
  path: /v1/parks/{id}/live
- description: Get upcoming park operating schedule
  method: GET
  name: get-schedule
  path: /v1/parks/{id}/schedule
- description: Get park schedule for a specific month and year
  method: GET
  name: get-monthly-schedule
  path: /v1/parks/{id}/schedule/{year}/{month}
personas: []
provider_name: ThemeParks.wiki
provider_slug: themeparks-wiki
search_terms:
- get entity details
- attractions within a park
- get current live wait times and operational status for all attractions in a park
- list destinations
- get monthly schedule
- theme parks
- get park schedule
- all theme park resort destinations
- wait times
- get all attractions, shows, and restaurants within a park
- park entity details
- get park schedule for a specific month and year
- get details for a specific park
- list all supported theme park destinations worldwide (disney, universal, cedar fair, six flags, etc.)
- get details for a specific park entity including location and metadata
- get current live wait times for all attractions
- get park details
- get park
- get live wait times
- travel planning
- get park operating schedule for a specific month and year for trip planning
- get upcoming park operating hours and special event schedules
- get attractions
- get all attractions and entities in a park
- get park attractions
- travel
- park operating hours
- entertainment
- get details for any entity (destination, park, attraction, show, or restaurant) by uuid
- list all supported theme park destinations
- park schedule for a specific month
- get schedule
- live wait times and operational status
- get upcoming park operating schedule
- real-time
slug: theme-park-planning
source_filename: theme-park-planning.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: ThemeParks.wiki Theme Park Planning\n  description: Unified workflow for theme park trip planning and real-time park monitoring. Combines destination discovery,\n    live wait time monitoring, schedule lookups, and attraction browsing for park visitors, travel planners, and AI assistants.\n  tags:\n  - Theme Parks\n  - Entertainment\n  - Real-Time\n  - Wait Times\n  - Travel Planning\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds: []\ncapability:\n  consumes:\n  - type: http\n    namespace: themeparks\n    baseUri: https://api.themeparks.wiki/v1\n    description: Real-time theme park data API\n    resources:\n    - name: destinations\n      path: /destinations\n      description: List all theme park destinations\n      operations:\n      - name: get-destinations\n        method: GET\n        description: Get all supported theme park destinations\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n    - name: entity\n      path: /entity/{entityID}\n      description: Get entity details\n      operations:\n      - name: get-entity\n        method: GET\n        description: Get entity document for a park, attraction, show, or restaurant\n        inputParameters:\n        - name: entityID\n          in: path\n          type: string\n          required: true\n          description: Entity UUID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: entity-children\n      path: /entity/{entityID}/children\n      description: Get child entities\n      operations:\n      - name: get-entity-children\n        method: GET\n        description: Get all children for a given entity\n        inputParameters:\n        - name: entityID\n          in: path\n          type: string\n          required: true\n          description: Entity UUID\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: entity-live\n      path: /entity/{entityID}/live\n      description: Get live wait times and status\n      operations:\n      - name: get-entity-live-data\n        method: GET\n        description: Get live wait times and operational status for an entity and its children\n        inputParameters:\n        - name: entityID\n          in: path\n          type: string\n          required: true\n          description: Entity UUID (typically a park ID)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: entity-schedule\n      path: /entity/{entityID}/schedule\n      description: Get park operating schedule\n      operations:\n      - name: get-entity-schedule\n        method: GET\n        description: Get operating schedule for a park entity\n        inputParameters:\n        - name: entityID\n  \
  \        in: path\n          type: string\n          required: true\n          description: Entity UUID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: entity-schedule-by-month\n      path: /entity/{entityID}/schedule/{year}/{month}\n      description: Get schedule for specific month\n      operations:\n      - name: get-entity-schedule-by-month\n        method: GET\n        description: Get park schedule for a specific month and year\n        inputParameters:\n        - name: entityID\n          in: path\n          type: string\n          required: true\n          description: Entity UUID\n        - name: year\n          in: path\n          type: integer\n          required: true\n          description: Four-digit year\n        - name: month\n          in: path\n          type: integer\n          required: true\n          description: Month number (1-12)\n        outputRawFormat: json\n       \
  \ outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: theme-park-planning-api\n    description: Unified REST API for theme park trip planning and real-time monitoring.\n    resources:\n    - path: /v1/destinations\n      name: destinations\n      description: All theme park resort destinations\n      operations:\n      - method: GET\n        name: list-destinations\n        description: List all supported theme park destinations\n        call: themeparks.get-destinations\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/parks/{id}\n      name: park-detail\n      description: Park entity details\n      operations:\n      - method: GET\n        name: get-park\n        description: Get details for a specific park\n        call: themeparks.get-entity\n        with:\n          entityID: rest.id\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /v1/parks/{id}/attractions\n      name: park-attractions\n      description: Attractions within a park\n      operations:\n      - method: GET\n        name: get-attractions\n        description: Get all attractions and entities in a park\n        call: themeparks.get-entity-children\n        with:\n          entityID: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/parks/{id}/live\n      name: park-live-data\n      description: Live wait times and operational status\n      operations:\n      - method: GET\n        name: get-live-wait-times\n        description: Get current live wait times for all attractions\n        call: themeparks.get-entity-live-data\n        with:\n          entityID: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/parks/{id}/schedule\n      name: park-schedule\n      description: Park operating hours\n      operations:\n      - method: GET\n  \
  \      name: get-schedule\n        description: Get upcoming park operating schedule\n        call: themeparks.get-entity-schedule\n        with:\n          entityID: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/parks/{id}/schedule/{year}/{month}\n      name: park-monthly-schedule\n      description: Park schedule for a specific month\n      operations:\n      - method: GET\n        name: get-monthly-schedule\n        description: Get park schedule for a specific month and year\n        call: themeparks.get-entity-schedule-by-month\n        with:\n          entityID: rest.id\n          year: rest.year\n          month: rest.month\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: theme-park-planning-mcp\n    transport: http\n    description: MCP server for AI-assisted theme park trip planning and real-time monitoring.\n    tools:\n    - name: list-destinations\n \
  \     description: List all supported theme park destinations worldwide (Disney, Universal, Cedar Fair, Six Flags, etc.)\n      hints:\n        readOnly: true\n        openWorld: true\n      call: themeparks.get-destinations\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-park-details\n      description: Get details for a specific park entity including location and metadata\n      hints:\n        readOnly: true\n        openWorld: true\n      call: themeparks.get-entity\n      with:\n        entityID: tools.entityID\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-park-attractions\n      description: Get all attractions, shows, and restaurants within a park\n      hints:\n        readOnly: true\n        openWorld: true\n      call: themeparks.get-entity-children\n      with:\n        entityID: tools.entityID\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-live-wait-times\n    \
  \  description: Get current live wait times and operational status for all attractions in a park\n      hints:\n        readOnly: true\n        openWorld: true\n      call: themeparks.get-entity-live-data\n      with:\n        entityID: tools.entityID\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-park-schedule\n      description: Get upcoming park operating hours and special event schedules\n      hints:\n        readOnly: true\n        openWorld: true\n      call: themeparks.get-entity-schedule\n      with:\n        entityID: tools.entityID\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-monthly-schedule\n      description: Get park operating schedule for a specific month and year for trip planning\n      hints:\n        readOnly: true\n        openWorld: true\n      call: themeparks.get-entity-schedule-by-month\n      with:\n        entityID: tools.entityID\n        year: tools.year\n        month: tools.month\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-entity-details\n      description: Get details for any entity (destination, park, attraction, show, or restaurant) by UUID\n      hints:\n        readOnly: true\n        openWorld: true\n      call: themeparks.get-entity\n      with:\n        entityID: tools.entityID\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/themeparks-wiki/refs/heads/main/capabilities/theme-park-planning.yaml
tags:
- Theme Parks
- Entertainment
- Real-Time
- Wait Times
- Travel Planning
tools:
- description: List all supported theme park destinations worldwide (Disney, Universal, Cedar Fair, Six Flags, etc.)
  hints:
    openWorld: true
    readOnly: true
  name: list-destinations
- description: Get details for a specific park entity including location and metadata
  hints:
    openWorld: true
    readOnly: true
  name: get-park-details
- description: Get all attractions, shows, and restaurants within a park
  hints:
    openWorld: true
    readOnly: true
  name: get-park-attractions
- description: Get current live wait times and operational status for all attractions in a park
  hints:
    openWorld: true
    readOnly: true
  name: get-live-wait-times
- description: Get upcoming park operating hours and special event schedules
  hints:
    openWorld: true
    readOnly: true
  name: get-park-schedule
- description: Get park operating schedule for a specific month and year for trip planning
  hints:
    openWorld: true
    readOnly: true
  name: get-monthly-schedule
- description: Get details for any entity (destination, park, attraction, show, or restaurant) by UUID
  hints:
    openWorld: true
    readOnly: true
  name: get-entity-details
---
