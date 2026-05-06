---
categories: []
consumed_apis: []
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
- check health
- conference room management
- apache openmeetings
- get upcoming meetings
- System Administrator
- list upcoming
- close a conference room
- calendar and scheduling
- whiteboard
- conferencing
- create room
- collaboration
- generate a secure room access hash
- apache
- list session recordings
- create a new room
- list all registered users
- check system health status
- unified workflow for managing conferencing sessions
- manages conference rooms, invites participants, and handles recordings
- open source
- manages users, groups, and system health
- list public rooms
- get room hash
- login
- get upcoming calendar meetings
- list rooms
- video conferencing
- create a new conference room
- list all user groups
- authenticate a user to openmeetings
- list users
- list recordings
- Meeting Organizer
- web conferencing
- list groups
- list all public conference rooms
- get recordings by type
- close room
- user management
- session recordings
slug: conferencing-workflow
source_filename: conferencing-workflow.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Apache OpenMeetings Conferencing Workflow\n  description: Unified workflow capability for managing web conferencing sessions, users, rooms, recordings, and calendars\n    in Apache OpenMeetings.\n  tags:\n  - Apache OpenMeetings\n  - Conferencing\n  - Collaboration\n  - Web Conferencing\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    OPENMEETINGS_API_KEY: OPENMEETINGS_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: openmeetings\n    baseUri: https://localhost:5443/openmeetings/services\n    description: Apache OpenMeetings REST API\n    authentication:\n      type: apikey\n      key: Authorization\n      value: '{{OPENMEETINGS_API_KEY}}'\n      placement: header\n    resources:\n    - name: calendars\n      path: /calendar\n      description: CalendarService operations\n      operations:\n      - name: delete\n        method: DELETE\n        description: Apache OpenMeetings Delete\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getByRoom\n        method: GET\n        description: Apache OpenMeetings GetByRoom\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getByTitle\n        method: GET\n        description: Apache OpenMeetings GetByTitle\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: next\n        method: GET\n        description: Apache OpenMeetings Next\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: nextForUser\n        method: GET\n        description: Apache OpenMeetings NextForUser\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n    - name: errors\n      path: /error\n      description: ErrorService operations\n      operations:\n      - name: get\n        method: GET\n        description: Apache OpenMeetings Get\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: report\n        method: POST\n        description: Apache OpenMeetings Report\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: files\n      path: /file\n      description: FileService operations\n      operations:\n      - name: add\n        method: POST\n        description: Apache OpenMeetings Add\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete_1\n        method: DELETE\n        description: Apache OpenMeetings Delete_1\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteExternal\n        method: DELETE\n        description: Apache OpenMeetings DeleteExternal\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getAllExternal\n        method: GET\n        description: Apache OpenMeetings GetAllExternal\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getRoom\n        method: GET\n        description: Apache OpenMeetings GetRoom\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: groups\n      path: /group\n      description: GroupService operations\n      operations:\n      - name: get_1\n        method: GET\n        description: Apache OpenMeetings Get_1\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: add_1\n        method: POST\n        description: Apache OpenMeetings Add_1\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: addRoom\n        method: POST\n        description: Apache OpenMeetings AddRoom\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: addUser\n        method: POST\n        description: Apache OpenMeetings AddUser\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: removeUser\n        method: DELETE\n        description: Apache OpenMeetings RemoveUser\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n   \
  \ - name: infos\n      path: /info\n      description: InfoService operations\n      operations:\n      - name: getHealth\n        method: GET\n        description: Apache OpenMeetings GetHealth\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getManifest\n        method: GET\n        description: Apache OpenMeetings GetManifest\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getVersion\n        method: GET\n        description: Apache OpenMeetings GetVersion\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: nettests\n      path: /nettest\n      description: NetTestService operations\n      operations:\n      - name: get_2\n        method: GET\n        description: Apache OpenMeetings Get_2\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: upload\n        method: POST\n        description: Apache OpenMeetings Upload\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: recordings\n      path: /recording\n      description: RecordingService operations\n      operations:\n      - name: delete_3\n        method: DELETE\n        description: Apache OpenMeetings Delete_3\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getExternal\n        method: GET\n        description: Apache OpenMeetings GetExternal\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getExternalByRoom\n        method: GET\n        description: Apache OpenMeetings GetExternalByRoom\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getExternalByType\n        method: GET\n        description: Apache OpenMeetings GetExternalByType\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: rooms\n      path: /room\n      description: RoomService operations\n      operations:\n      - name: add_2\n        method: POST\n        description: Apache OpenMeetings Add_2\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: close\n        method: GET\n        description: Apache OpenMeetings Close\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: count\n        method: GET\n        description: Apache OpenMeetings Count\n     \
  \   outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getRoomById\n        method: GET\n        description: Apache OpenMeetings GetRoomById\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete_4\n        method: DELETE\n        description: Apache OpenMeetings Delete_4\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users\n      path: /user\n      description: UserService operations\n      operations:\n      - name: get_3\n        method: GET\n        description: Apache OpenMeetings Get_3\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: add_3\n        method: POST\n        description: Apache OpenMeetings Add_3\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete_5\n        method: DELETE\n        description: Apache OpenMeetings Delete_5\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteExternal_1\n        method: DELETE\n        description: Apache OpenMeetings DeleteExternal_1\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getRoomHash\n        method: POST\n        description: Apache OpenMeetings GetRoomHash\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: wbs\n      path: /wb\n      description: WbService operations\n      operations:\n      - name: cleanSlide\n        method: GET\n        description: Apache OpenMeetings CleanSlide\n   \
  \     outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: cleanWb\n        method: GET\n        description: Apache OpenMeetings CleanWb\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: resetWb\n        method: GET\n        description: Apache OpenMeetings ResetWb\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: uploadWb\n        method: POST\n        description: Apache OpenMeetings UploadWb\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: conferencing-api\n    description: Unified REST API for Apache OpenMeetings conferencing workflow.\n    resources:\n    - path: /v1/rooms\n      name:\
  \ rooms\n      description: Conference room management\n      operations:\n      - method: GET\n        name: list-rooms\n        description: List public rooms\n        call: openmeetings.getPublic\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-room\n        description: Create a new room\n        call: openmeetings.add_2\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/users\n      name: users\n      description: User management\n      operations:\n      - method: GET\n        name: list-users\n        description: List users\n        call: openmeetings.get_3\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/recordings\n      name: recordings\n      description: Session recordings\n      operations:\n      - method: GET\n        name: list-recordings\n        description: Get recordings by type\n        call: openmeetings.getExternalByType\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/calendar\n      name: calendar\n      description: Calendar and scheduling\n      operations:\n      - method: GET\n        name: list-upcoming\n        description: Get upcoming meetings\n        call: openmeetings.next\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: conferencing-mcp\n    transport: http\n    description: MCP server for AI-assisted conferencing management.\n    tools:\n    - name: list-rooms\n      description: List all public conference rooms\n      hints:\n        readOnly: true\n      call: openmeetings.getPublic\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-room\n      description: Create a new conference room\n      hints:\n        readOnly: false\n      call: openmeetings.add_2\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: close-room\n\
  \      description: Close a conference room\n      hints:\n        readOnly: false\n        destructive: true\n      call: openmeetings.close\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-users\n      description: List all registered users\n      hints:\n        readOnly: true\n      call: openmeetings.get_3\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: login\n      description: Authenticate a user to OpenMeetings\n      hints:\n        readOnly: false\n      call: openmeetings.login\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-room-hash\n      description: Generate a secure room access hash\n      hints:\n        readOnly: false\n      call: openmeetings.hash\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-recordings\n      description: List session recordings\n      hints:\n        readOnly: true\n      call: openmeetings.getExternalByType\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-upcoming-meetings\n      description: Get upcoming calendar meetings\n      hints:\n        readOnly: true\n      call: openmeetings.next\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-groups\n      description: List all user groups\n      hints:\n        readOnly: true\n      call: openmeetings.get_1\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: check-health\n      description: Check system health status\n      hints:\n        readOnly: true\n      call: openmeetings.getHealth\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
