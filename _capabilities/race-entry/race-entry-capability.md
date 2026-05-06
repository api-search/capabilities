---
categories: []
consumed_apis: []
description: The Race Entry Software API was designed for Director software and timing integrations. It provides programmatic access to events, registrations, participants, teams, results, check-in PINs, club memberships, and event creation flows. Authentication is performed via login to obtain a temporary key and secret that expire after 48 hours.
layout: capability
name: Race Entry Software API
operations:
- description: Create API user
  method: POST
  name: createuser
  path: /user/create
- description: Login
  method: POST
  name: login
  path: /login
- description: Get event creation data
  method: GET
  name: geteventcreatedata
  path: /event/get_create_data
- description: Create event
  method: POST
  name: createevent
  path: /event/create
- description: Copy event
  method: POST
  name: copyevent
  path: /event/copy
- description: List events
  method: GET
  name: getevents
  path: /get_events
- description: Get event categories
  method: GET
  name: geteventcategories
  path: /get_event_categories
- description: Get event registration questions
  method: GET
  name: geteventquestions
  path: /get_event_questions
- description: Get event participants
  method: GET
  name: geteventparticipants
  path: /get_event_participants
- description: Update event participant
  method: POST
  name: updateeventparticipant
  path: /update_event_participant
- description: Get event teams
  method: GET
  name: geteventteams
  path: /get_event_teams
- description: Get category teams
  method: GET
  name: getcategoryteams
  path: /get_category_teams
- description: Get event PIN
  method: GET
  name: geteventpin
  path: /get_event_pin
- description: Set event PIN
  method: POST
  name: seteventpin
  path: /set_event_pin
- description: Set event app access
  method: POST
  name: seteventappaccess
  path: /set_event_app_access
- description: Edit result
  method: POST
  name: editresult
  path: /result/edit
- description: Delete result
  method: POST
  name: deleteresult
  path: /result/delete
- description: Upload results
  method: POST
  name: uploadresults
  path: /upload/results
- description: Get clubs
  method: GET
  name: getclubs
  path: /memberships/get-clubs
- description: Get club members
  method: GET
  name: getclubmembers
  path: /memberships/get-members
personas: []
provider_name: Race Entry
provider_slug: race-entry
search_terms:
- create event
- list events
- create api user
- get event participants
- createuser
- geteventcreatedata
- geteventpin
- sports
- geteventcategories
- race registration
- upload results
- seteventappaccess
- getclubmembers
- get clubs
- race timing
- edit result
- set event app access
- get event teams
- getcategoryteams
- copy event
- entry
- copyevent
- update event participant
- get event categories
- geteventparticipants
- get event registration questions
- geteventquestions
- getclubs
- get event creation data
- createevent
- login
- updateeventparticipant
- api
- get category teams
- event management
- getevents
- race results
- editresult
- deleteresult
- get club members
- get event pin
- delete result
- geteventteams
- seteventpin
- uploadresults
- set event pin
- race
slug: race-entry-capability
source_filename: race-entry-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Race Entry Software API\n  description: The Race Entry Software API was designed for Director software and timing integrations. It provides programmatic\n    access to events, registrations, participants, teams, results, check-in PINs, club memberships, and event creation flows.\n    Authentication is performed via login to obtain a temporary key and secret that expire after 48 hours.\n  tags:\n  - Race\n  - Entry\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: race-entry\n    baseUri: https://www.raceentry.com/softwareapi\n    description: Race Entry Software API HTTP API.\n    authentication:\n      type: apikey\n      in: query\n      name: tmp_key\n      value: '{{RACE_ENTRY_TOKEN}}'\n    resources:\n    - name: user-create\n      path: /user/create\n      operations:\n      - name: createuser\n        method: POST\n        description: Create API user\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: login\n      path: /login\n      operations:\n      - name: login\n        method: POST\n        description: Login\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: event-get-create-data\n      path: /event/get_create_data\n      operations:\n      - name: geteventcreatedata\n        method: GET\n        description: Get event creation data\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: event-create\n      path: /event/create\n      operations:\n      - name: createevent\n        method: POST\n        description: Create event\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: event-copy\n      path: /event/copy\n\
  \      operations:\n      - name: copyevent\n        method: POST\n        description: Copy event\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: get-events\n      path: /get_events\n      operations:\n      - name: getevents\n        method: GET\n        description: List events\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: get-event-categories\n      path: /get_event_categories\n      operations:\n      - name: geteventcategories\n        method: GET\n        description: Get event categories\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: get-event-questions\n      path: /get_event_questions\n      operations:\n      - name: geteventquestions\n        method: GET\n        description: Get event registration questions\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: get-event-participants\n      path: /get_event_participants\n      operations:\n      - name: geteventparticipants\n        method: GET\n        description: Get event participants\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: update-event-participant\n      path: /update_event_participant\n      operations:\n      - name: updateeventparticipant\n        method: POST\n        description: Update event participant\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: get-event-teams\n      path: /get_event_teams\n      operations:\n      - name: geteventteams\n        method: GET\n        description: Get event teams\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: get-category-teams\n      path: /get_category_teams\n      operations:\n      - name: getcategoryteams\n        method: GET\n        description: Get category teams\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: get-event-pin\n      path: /get_event_pin\n      operations:\n      - name: geteventpin\n        method: GET\n        description: Get event PIN\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: set-event-pin\n      path: /set_event_pin\n      operations:\n      - name: seteventpin\n        method: POST\n        description: Set event PIN\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: set-event-app-access\n      path: /set_event_app_access\n\
  \      operations:\n      - name: seteventappaccess\n        method: POST\n        description: Set event app access\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: result-edit\n      path: /result/edit\n      operations:\n      - name: editresult\n        method: POST\n        description: Edit result\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: result-delete\n      path: /result/delete\n      operations:\n      - name: deleteresult\n        method: POST\n        description: Delete result\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: upload-results\n      path: /upload/results\n      operations:\n      - name: uploadresults\n        method: POST\n        description: Upload results\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: memberships-get-clubs\n      path: /memberships/get-clubs\n      operations:\n      - name: getclubs\n        method: GET\n        description: Get clubs\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: memberships-get-members\n      path: /memberships/get-members\n      operations:\n      - name: getclubmembers\n        method: GET\n        description: Get club members\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: race-entry-rest\n    description: REST adapter for Race Entry Software API.\n    resources:\n    - path: /user/create\n      name: createuser\n      operations:\n      - method: POST\n        name: createuser\n        description: Create\
  \ API user\n        call: race-entry.createuser\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /login\n      name: login\n      operations:\n      - method: POST\n        name: login\n        description: Login\n        call: race-entry.login\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /event/get_create_data\n      name: geteventcreatedata\n      operations:\n      - method: GET\n        name: geteventcreatedata\n        description: Get event creation data\n        call: race-entry.geteventcreatedata\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /event/create\n      name: createevent\n      operations:\n      - method: POST\n        name: createevent\n        description: Create event\n        call: race-entry.createevent\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /event/copy\n      name: copyevent\n      operations:\n\
  \      - method: POST\n        name: copyevent\n        description: Copy event\n        call: race-entry.copyevent\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /get_events\n      name: getevents\n      operations:\n      - method: GET\n        name: getevents\n        description: List events\n        call: race-entry.getevents\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /get_event_categories\n      name: geteventcategories\n      operations:\n      - method: GET\n        name: geteventcategories\n        description: Get event categories\n        call: race-entry.geteventcategories\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /get_event_questions\n      name: geteventquestions\n      operations:\n      - method: GET\n        name: geteventquestions\n        description: Get event registration questions\n        call: race-entry.geteventquestions\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /get_event_participants\n      name: geteventparticipants\n      operations:\n      - method: GET\n        name: geteventparticipants\n        description: Get event participants\n        call: race-entry.geteventparticipants\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /update_event_participant\n      name: updateeventparticipant\n      operations:\n      - method: POST\n        name: updateeventparticipant\n        description: Update event participant\n        call: race-entry.updateeventparticipant\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /get_event_teams\n      name: geteventteams\n      operations:\n      - method: GET\n        name: geteventteams\n        description: Get event teams\n        call: race-entry.geteventteams\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /get_category_teams\n   \
  \   name: getcategoryteams\n      operations:\n      - method: GET\n        name: getcategoryteams\n        description: Get category teams\n        call: race-entry.getcategoryteams\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /get_event_pin\n      name: geteventpin\n      operations:\n      - method: GET\n        name: geteventpin\n        description: Get event PIN\n        call: race-entry.geteventpin\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /set_event_pin\n      name: seteventpin\n      operations:\n      - method: POST\n        name: seteventpin\n        description: Set event PIN\n        call: race-entry.seteventpin\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /set_event_app_access\n      name: seteventappaccess\n      operations:\n      - method: POST\n        name: seteventappaccess\n        description: Set event app access\n        call: race-entry.seteventappaccess\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /result/edit\n      name: editresult\n      operations:\n      - method: POST\n        name: editresult\n        description: Edit result\n        call: race-entry.editresult\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /result/delete\n      name: deleteresult\n      operations:\n      - method: POST\n        name: deleteresult\n        description: Delete result\n        call: race-entry.deleteresult\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /upload/results\n      name: uploadresults\n      operations:\n      - method: POST\n        name: uploadresults\n        description: Upload results\n        call: race-entry.uploadresults\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /memberships/get-clubs\n      name: getclubs\n      operations:\n      - method: GET\n        name: getclubs\n\
  \        description: Get clubs\n        call: race-entry.getclubs\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /memberships/get-members\n      name: getclubmembers\n      operations:\n      - method: GET\n        name: getclubmembers\n        description: Get club members\n        call: race-entry.getclubmembers\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: race-entry-mcp\n    transport: http\n    description: MCP adapter for Race Entry Software API for AI agent use.\n    tools:\n    - name: createuser\n      description: Create API user\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: race-entry.createuser\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: login\n      description: Login\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n\
  \      call: race-entry.login\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: geteventcreatedata\n      description: Get event creation data\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: race-entry.geteventcreatedata\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createevent\n      description: Create event\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: race-entry.createevent\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: copyevent\n      description: Copy event\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: race-entry.copyevent\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getevents\n      description: List events\n      hints:\n        readOnly: true\n        destructive: false\n\
  \        idempotent: true\n      call: race-entry.getevents\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: geteventcategories\n      description: Get event categories\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: race-entry.geteventcategories\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: geteventquestions\n      description: Get event registration questions\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: race-entry.geteventquestions\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: geteventparticipants\n      description: Get event participants\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: race-entry.geteventparticipants\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateeventparticipant\n\
  \      description: Update event participant\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: race-entry.updateeventparticipant\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: geteventteams\n      description: Get event teams\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: race-entry.geteventteams\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcategoryteams\n      description: Get category teams\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: race-entry.getcategoryteams\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: geteventpin\n      description: Get event PIN\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: race-entry.geteventpin\n      outputParameters:\n \
  \     - type: object\n        mapping: $.\n    - name: seteventpin\n      description: Set event PIN\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: race-entry.seteventpin\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: seteventappaccess\n      description: Set event app access\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: race-entry.seteventappaccess\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: editresult\n      description: Edit result\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: race-entry.editresult\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteresult\n      description: Delete result\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: race-entry.deleteresult\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: uploadresults\n      description: Upload results\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: race-entry.uploadresults\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getclubs\n      description: Get clubs\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: race-entry.getclubs\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getclubmembers\n      description: Get club members\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: race-entry.getclubmembers\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    RACE_ENTRY_TOKEN: RACE_ENTRY_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/race-entry/refs/heads/main/capabilities/race-entry-capability.yaml
tags:
- Race
- Entry
- API
tools:
- description: Create API user
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createuser
- description: Login
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: login
- description: Get event creation data
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: geteventcreatedata
- description: Create event
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createevent
- description: Copy event
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: copyevent
- description: List events
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getevents
- description: Get event categories
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: geteventcategories
- description: Get event registration questions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: geteventquestions
- description: Get event participants
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: geteventparticipants
- description: Update event participant
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateeventparticipant
- description: Get event teams
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: geteventteams
- description: Get category teams
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcategoryteams
- description: Get event PIN
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: geteventpin
- description: Set event PIN
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: seteventpin
- description: Set event app access
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: seteventappaccess
- description: Edit result
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: editresult
- description: Delete result
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: deleteresult
- description: Upload results
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: uploadresults
- description: Get clubs
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getclubs
- description: Get club members
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getclubmembers
---
