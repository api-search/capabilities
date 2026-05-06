---
categories: []
consumed_apis: []
description: The Freshcaller API provides access to cloud-based phone system functionality for contact center operations. It allows developers to export call data, call recordings, user information, and agent team details stored in the Freshcaller system. The API supports integration of voice and telephony workflows into broader business applications, enabling organizations to automate call center reporting, synchronize agent data, and build custom dashboards around their phone operations.
layout: capability
name: Freshworks Freshcaller API
operations:
- description: List all calls
  method: GET
  name: listcalls
  path: /calls
- description: View a call
  method: GET
  name: getcall
  path: /calls/{call_id}
- description: Get call recording
  method: GET
  name: getcallrecording
  path: /calls/{call_id}/recording
- description: List all users
  method: GET
  name: listusers
  path: /users
- description: Create a user
  method: POST
  name: createuser
  path: /users
- description: View a user
  method: GET
  name: getuser
  path: /users/{user_id}
- description: Update a user
  method: PUT
  name: updateuser
  path: /users/{user_id}
- description: List all user statuses
  method: GET
  name: listuserstatuses
  path: /user_statuses
- description: List all teams
  method: GET
  name: listteams
  path: /teams
- description: Create a team
  method: POST
  name: createteam
  path: /teams
- description: View a team
  method: GET
  name: getteam
  path: /teams/{team_id}
- description: Update a team
  method: PUT
  name: updateteam
  path: /teams/{team_id}
- description: List call metrics
  method: GET
  name: listcallmetrics
  path: /call_metrics
personas: []
provider_name: freshworks
provider_slug: freshworks
search_terms:
- createuser
- view a team
- view a call
- list all users
- listuserstatuses
- getteam
- listcallmetrics
- freshworks
- updateteam
- list all calls
- listcalls
- api
- update a team
- view a user
- create a user
- listteams
- list all teams
- createteam
- list call metrics
- getuser
- create a team
- list all user statuses
- getcallrecording
- update a user
- listusers
- updateuser
- getcall
- get call recording
slug: freshworks-capability
source_filename: freshworks-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Freshworks Freshcaller API\n  description: The Freshcaller API provides access to cloud-based phone system functionality for contact center operations.\n    It allows developers to export call data, call recordings, user information, and agent team details stored in the Freshcaller\n    system. The API supports integration of voice and telephony workflows into broader business applications, enabling organizations\n    to automate call center reporting, synchronize agent data, and build custom dashboards around their phone operations.\n  tags:\n  - Freshworks\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: freshworks\n    baseUri: https://yourdomain.freshcaller.com/api/v1\n    description: Freshworks Freshcaller API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: X-Api-Auth\n      value: '{{FRESHWORKS_TOKEN}}'\n    resources:\n    - name:\
  \ calls\n      path: /calls\n      operations:\n      - name: listcalls\n        method: GET\n        description: List all calls\n        inputParameters:\n        - name: by_time[from]\n          in: query\n          type: string\n          description: Filter calls from this timestamp (ISO 8601).\n        - name: by_time[to]\n          in: query\n          type: string\n          description: Filter calls up to this timestamp (ISO 8601).\n        - name: has_ancestry\n          in: query\n          type: boolean\n          description: Filter calls that have parent-child relationships.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: calls-call-id\n      path: /calls/{call_id}\n      operations:\n      - name: getcall\n        method: GET\n        description: View a call\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n    - name: calls-call-id-recording\n      path: /calls/{call_id}/recording\n      operations:\n      - name: getcallrecording\n        method: GET\n        description: Get call recording\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users\n      path: /users\n      operations:\n      - name: listusers\n        method: GET\n        description: List all users\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createuser\n        method: POST\n        description: Create a user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users-user-id\n      path: /users/{user_id}\n      operations:\n      - name: getuser\n        method: GET\n        description: View a user\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: updateuser\n        method: PUT\n        description: Update a user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: user-statuses\n      path: /user_statuses\n      operations:\n      - name: listuserstatuses\n        method: GET\n        description: List all user statuses\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: teams\n      path: /teams\n      operations:\n      - name: listteams\n        method: GET\n        description: List all teams\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createteam\n        method: POST\n        description: Create a team\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n    - name: teams-team-id\n      path: /teams/{team_id}\n      operations:\n      - name: getteam\n        method: GET\n        description: View a team\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateteam\n        method: PUT\n        description: Update a team\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: call-metrics\n      path: /call_metrics\n      operations:\n      - name: listcallmetrics\n        method: GET\n        description: List call metrics\n        inputParameters:\n        - name: by_time[from]\n          in: query\n          type: string\n          description: Start of the time range (ISO 8601).\n        - name: by_time[to]\n          in: query\n          type: string\n          description: End of the time range (ISO 8601).\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: freshworks-rest\n    description: REST adapter for Freshworks Freshcaller API.\n    resources:\n    - path: /calls\n      name: listcalls\n      operations:\n      - method: GET\n        name: listcalls\n        description: List all calls\n        call: freshworks.listcalls\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /calls/{call_id}\n      name: getcall\n      operations:\n      - method: GET\n        name: getcall\n        description: View a call\n        call: freshworks.getcall\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /calls/{call_id}/recording\n      name: getcallrecording\n      operations:\n      - method: GET\n        name: getcallrecording\n        description: Get call recording\n        call: freshworks.getcallrecording\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users\n      name: listusers\n      operations:\n      - method: GET\n        name: listusers\n        description: List all users\n        call: freshworks.listusers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users\n      name: createuser\n      operations:\n      - method: POST\n        name: createuser\n        description: Create a user\n        call: freshworks.createuser\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users/{user_id}\n      name: getuser\n      operations:\n      - method: GET\n        name: getuser\n        description: View a user\n        call: freshworks.getuser\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users/{user_id}\n      name: updateuser\n      operations:\n      - method: PUT\n        name: updateuser\n        description: Update a user\n\
  \        call: freshworks.updateuser\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /user_statuses\n      name: listuserstatuses\n      operations:\n      - method: GET\n        name: listuserstatuses\n        description: List all user statuses\n        call: freshworks.listuserstatuses\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /teams\n      name: listteams\n      operations:\n      - method: GET\n        name: listteams\n        description: List all teams\n        call: freshworks.listteams\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /teams\n      name: createteam\n      operations:\n      - method: POST\n        name: createteam\n        description: Create a team\n        call: freshworks.createteam\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /teams/{team_id}\n      name: getteam\n      operations:\n      - method:\
  \ GET\n        name: getteam\n        description: View a team\n        call: freshworks.getteam\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /teams/{team_id}\n      name: updateteam\n      operations:\n      - method: PUT\n        name: updateteam\n        description: Update a team\n        call: freshworks.updateteam\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /call_metrics\n      name: listcallmetrics\n      operations:\n      - method: GET\n        name: listcallmetrics\n        description: List call metrics\n        call: freshworks.listcallmetrics\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: freshworks-mcp\n    transport: http\n    description: MCP adapter for Freshworks Freshcaller API for AI agent use.\n    tools:\n    - name: listcalls\n      description: List all calls\n      hints:\n        readOnly: true\n       \
  \ destructive: false\n        idempotent: true\n      call: freshworks.listcalls\n      with:\n        by_time[from]: tools.by_time[from]\n        by_time[to]: tools.by_time[to]\n        has_ancestry: tools.has_ancestry\n      inputParameters:\n      - name: by_time[from]\n        type: string\n        description: Filter calls from this timestamp (ISO 8601).\n      - name: by_time[to]\n        type: string\n        description: Filter calls up to this timestamp (ISO 8601).\n      - name: has_ancestry\n        type: boolean\n        description: Filter calls that have parent-child relationships.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcall\n      description: View a call\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: freshworks.getcall\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcallrecording\n      description: Get call recording\n      hints:\n\
  \        readOnly: true\n        destructive: false\n        idempotent: true\n      call: freshworks.getcallrecording\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listusers\n      description: List all users\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: freshworks.listusers\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createuser\n      description: Create a user\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: freshworks.createuser\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getuser\n      description: View a user\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: freshworks.getuser\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateuser\n      description: Update a user\n \
  \     hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: freshworks.updateuser\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listuserstatuses\n      description: List all user statuses\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: freshworks.listuserstatuses\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listteams\n      description: List all teams\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: freshworks.listteams\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createteam\n      description: Create a team\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: freshworks.createteam\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getteam\n \
  \     description: View a team\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: freshworks.getteam\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateteam\n      description: Update a team\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: freshworks.updateteam\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listcallmetrics\n      description: List call metrics\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: freshworks.listcallmetrics\n      with:\n        by_time[from]: tools.by_time[from]\n        by_time[to]: tools.by_time[to]\n      inputParameters:\n      - name: by_time[from]\n        type: string\n        description: Start of the time range (ISO 8601).\n      - name: by_time[to]\n        type: string\n        description: End of the time range (ISO\
  \ 8601).\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    FRESHWORKS_TOKEN: FRESHWORKS_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/freshworks/refs/heads/main/capabilities/freshworks-capability.yaml
tags:
- Freshworks
- API
tools:
- description: List all calls
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcalls
- description: View a call
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcall
- description: Get call recording
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcallrecording
- description: List all users
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listusers
- description: Create a user
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createuser
- description: View a user
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getuser
- description: Update a user
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateuser
- description: List all user statuses
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listuserstatuses
- description: List all teams
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listteams
- description: Create a team
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createteam
- description: View a team
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getteam
- description: Update a team
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateteam
- description: List call metrics
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcallmetrics
---
