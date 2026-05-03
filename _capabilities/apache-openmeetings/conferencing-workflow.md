---
categories: []
consumed_apis:
- openmeetings
description: Unified workflow capability for managing web conferencing sessions, users, rooms, recordings, and calendars in Apache OpenMeetings.
layout: capability
name: Apache OpenMeetings Conferencing Workflow
operations:
- description: List public rooms
  method: GET
  name: list-rooms
  path: /v1/rooms
- description: Create a new room
  method: POST
  name: create-room
  path: /v1/rooms
- description: List users
  method: GET
  name: list-users
  path: /v1/users
- description: Get recordings by type
  method: GET
  name: list-recordings
  path: /v1/recordings
- description: Get upcoming meetings
  method: GET
  name: list-upcoming
  path: /v1/calendar
personas: []
provider_name: Apache OpenMeetings
provider_slug: apache-openmeetings
search_terms:
- Meeting Organizer
- list upcoming
- get room hash
- get upcoming calendar meetings
- list all public conference rooms
- open source
- unified workflow for managing conferencing sessions
- create a new room
- calendar and scheduling
- check system health status
- create a new conference room
- apache openmeetings
- close a conference room
- conference room management
- list public rooms
- list session recordings
- authenticate a user to openmeetings
- create room
- web conferencing
- check health
- video conferencing
- conferencing
- collaboration
- list users
- list recordings
- user management
- get recordings by type
- list all registered users
- manages users, groups, and system health
- close room
- apache
- manages conference rooms, invites participants, and handles recordings
- System Administrator
- login
- session recordings
- list groups
- generate a secure room access hash
- list all user groups
- get upcoming meetings
- whiteboard
- list rooms
slug: conferencing-workflow
source_filename: conferencing-workflow.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Apache OpenMeetings Conferencing Workflow\"\n  description: \"Unified workflow capability for managing web conferencing sessions, users, rooms, recordings, and calendars in Apache OpenMeetings.\"\n  tags:\n    - Apache OpenMeetings\n    - Conferencing\n    - Collaboration\n    - Web Conferencing\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      OPENMEETINGS_API_KEY: OPENMEETINGS_API_KEY\n\ncapability:\n  consumes:\n    - import: openmeetings\n      location: ./shared/openmeetings-rest-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: conferencing-api\n      description: \"Unified REST API for Apache OpenMeetings conferencing workflow.\"\n      resources:\n        - path: /v1/rooms\n          name: rooms\n          description: \"Conference room management\"\n          operations:\n            - method: GET\n              name: list-rooms\n         \
  \     description: \"List public rooms\"\n              call: \"openmeetings.getPublic\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-room\n              description: \"Create a new room\"\n              call: \"openmeetings.add_2\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/users\n          name: users\n          description: \"User management\"\n          operations:\n            - method: GET\n              name: list-users\n              description: \"List users\"\n              call: \"openmeetings.get_3\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/recordings\n          name: recordings\n          description: \"Session recordings\"\n          operations:\n            - method: GET\n              name: list-recordings\n\
  \              description: \"Get recordings by type\"\n              call: \"openmeetings.getExternalByType\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/calendar\n          name: calendar\n          description: \"Calendar and scheduling\"\n          operations:\n            - method: GET\n              name: list-upcoming\n              description: \"Get upcoming meetings\"\n              call: \"openmeetings.next\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: conferencing-mcp\n      transport: http\n      description: \"MCP server for AI-assisted conferencing management.\"\n      tools:\n        - name: list-rooms\n          description: \"List all public conference rooms\"\n          hints:\n            readOnly: true\n          call: \"openmeetings.getPublic\"\n          outputParameters:\n    \
  \        - type: object\n              mapping: \"$.\"\n        - name: create-room\n          description: \"Create a new conference room\"\n          hints:\n            readOnly: false\n          call: \"openmeetings.add_2\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: close-room\n          description: \"Close a conference room\"\n          hints:\n            readOnly: false\n            destructive: true\n          call: \"openmeetings.close\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-users\n          description: \"List all registered users\"\n          hints:\n            readOnly: true\n          call: \"openmeetings.get_3\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: login\n          description: \"Authenticate a user to OpenMeetings\"\n          hints:\n            readOnly: false\n      \
  \    call: \"openmeetings.login\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-room-hash\n          description: \"Generate a secure room access hash\"\n          hints:\n            readOnly: false\n          call: \"openmeetings.hash\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-recordings\n          description: \"List session recordings\"\n          hints:\n            readOnly: true\n          call: \"openmeetings.getExternalByType\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-upcoming-meetings\n          description: \"Get upcoming calendar meetings\"\n          hints:\n            readOnly: true\n          call: \"openmeetings.next\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-groups\n          description: \"List all user\
  \ groups\"\n          hints:\n            readOnly: true\n          call: \"openmeetings.get_1\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: check-health\n          description: \"Check system health status\"\n          hints:\n            readOnly: true\n          call: \"openmeetings.getHealth\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/apache-openmeetings/refs/heads/main/capabilities/conferencing-workflow.yaml
tags:
- Apache OpenMeetings
- Conferencing
- Collaboration
- Web Conferencing
tools:
- description: List all public conference rooms
  hints:
    readOnly: true
  name: list-rooms
- description: Create a new conference room
  hints:
    readOnly: false
  name: create-room
- description: Close a conference room
  hints:
    destructive: true
    readOnly: false
  name: close-room
- description: List all registered users
  hints:
    readOnly: true
  name: list-users
- description: Authenticate a user to OpenMeetings
  hints:
    readOnly: false
  name: login
- description: Generate a secure room access hash
  hints:
    readOnly: false
  name: get-room-hash
- description: List session recordings
  hints:
    readOnly: true
  name: list-recordings
- description: Get upcoming calendar meetings
  hints:
    readOnly: true
  name: get-upcoming-meetings
- description: List all user groups
  hints:
    readOnly: true
  name: list-groups
- description: Check system health status
  hints:
    readOnly: true
  name: check-health
---
