---
api_specs:
- filename: themeparks-wiki-openapi.yml
  format: yaml
  label: themeparks
  slug: themeparks
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/themeparks-wiki/refs/heads/main/openapi/themeparks-wiki-openapi.yml
categories: []
consumed_apis:
- themeparks
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
- live wait times and operational status
- theme parks
- travel planning
- list all supported theme park destinations worldwide (disney, universal, cedar fair, six flags, etc.)
- entertainment
- list all supported theme park destinations
- park entity details
- get park
- get park attractions
- get details for any entity (destination, park, attraction, show, or restaurant) by uuid
- get park details
- get schedule
- get details for a specific park
- get upcoming park operating hours and special event schedules
- get monthly schedule
- get park schedule for a specific month and year
- park schedule for a specific month
- get park operating schedule for a specific month and year for trip planning
- get entity details
- get attractions
- all theme park resort destinations
- list destinations
- get park schedule
- wait times
- get all attractions, shows, and restaurants within a park
- get current live wait times for all attractions
- real-time
- get live wait times
- get current live wait times and operational status for all attractions in a park
- park operating hours
- travel
- get details for a specific park entity including location and metadata
- get upcoming park operating schedule
- attractions within a park
- get all attractions and entities in a park
slug: theme-park-planning
source_filename: theme-park-planning.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"ThemeParks.wiki Theme Park Planning\"\n  description: \"Unified workflow for theme park trip planning and real-time park monitoring. Combines destination discovery, live wait time monitoring, schedule lookups, and attraction browsing for park visitors, travel planners, and AI assistants.\"\n  tags:\n    - Theme Parks\n    - Entertainment\n    - Real-Time\n    - Wait Times\n    - Travel Planning\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds: []\n\ncapability:\n  consumes:\n    - import: themeparks\n      location: ./shared/themeparks-wiki.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: theme-park-planning-api\n      description: \"Unified REST API for theme park trip planning and real-time monitoring.\"\n      resources:\n        - path: /v1/destinations\n          name: destinations\n          description: \"All theme park resort destinations\"\n          operations:\n            - method:\
  \ GET\n              name: list-destinations\n              description: \"List all supported theme park destinations\"\n              call: \"themeparks.get-destinations\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/parks/{id}\n          name: park-detail\n          description: \"Park entity details\"\n          operations:\n            - method: GET\n              name: get-park\n              description: \"Get details for a specific park\"\n              call: \"themeparks.get-entity\"\n              with:\n                entityID: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/parks/{id}/attractions\n          name: park-attractions\n          description: \"Attractions within a park\"\n          operations:\n            - method: GET\n              name: get-attractions\n              description: \"Get all attractions\
  \ and entities in a park\"\n              call: \"themeparks.get-entity-children\"\n              with:\n                entityID: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/parks/{id}/live\n          name: park-live-data\n          description: \"Live wait times and operational status\"\n          operations:\n            - method: GET\n              name: get-live-wait-times\n              description: \"Get current live wait times for all attractions\"\n              call: \"themeparks.get-entity-live-data\"\n              with:\n                entityID: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/parks/{id}/schedule\n          name: park-schedule\n          description: \"Park operating hours\"\n          operations:\n            - method: GET\n              name: get-schedule\n              description:\
  \ \"Get upcoming park operating schedule\"\n              call: \"themeparks.get-entity-schedule\"\n              with:\n                entityID: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/parks/{id}/schedule/{year}/{month}\n          name: park-monthly-schedule\n          description: \"Park schedule for a specific month\"\n          operations:\n            - method: GET\n              name: get-monthly-schedule\n              description: \"Get park schedule for a specific month and year\"\n              call: \"themeparks.get-entity-schedule-by-month\"\n              with:\n                entityID: \"rest.id\"\n                year: \"rest.year\"\n                month: \"rest.month\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: theme-park-planning-mcp\n      transport: http\n      description:\
  \ \"MCP server for AI-assisted theme park trip planning and real-time monitoring.\"\n      tools:\n        - name: list-destinations\n          description: \"List all supported theme park destinations worldwide (Disney, Universal, Cedar Fair, Six Flags, etc.)\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"themeparks.get-destinations\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-park-details\n          description: \"Get details for a specific park entity including location and metadata\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"themeparks.get-entity\"\n          with:\n            entityID: \"tools.entityID\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-park-attractions\n          description: \"Get all attractions, shows, and restaurants within a park\"\n \
  \         hints:\n            readOnly: true\n            openWorld: true\n          call: \"themeparks.get-entity-children\"\n          with:\n            entityID: \"tools.entityID\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-live-wait-times\n          description: \"Get current live wait times and operational status for all attractions in a park\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"themeparks.get-entity-live-data\"\n          with:\n            entityID: \"tools.entityID\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-park-schedule\n          description: \"Get upcoming park operating hours and special event schedules\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"themeparks.get-entity-schedule\"\n          with:\n            entityID: \"tools.entityID\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-monthly-schedule\n          description: \"Get park operating schedule for a specific month and year for trip planning\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"themeparks.get-entity-schedule-by-month\"\n          with:\n            entityID: \"tools.entityID\"\n            year: \"tools.year\"\n            month: \"tools.month\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-entity-details\n          description: \"Get details for any entity (destination, park, attraction, show, or restaurant) by UUID\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"themeparks.get-entity\"\n          with:\n            entityID: \"tools.entityID\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\
  \n"
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
