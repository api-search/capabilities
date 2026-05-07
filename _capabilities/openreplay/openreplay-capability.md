---
categories: []
consumed_apis: []
description: 'The OpenReplay Public REST API (v2) provides programmatic access to projects, sessions, events, users, background jobs, and live Assist sessions (Enterprise Edition). All endpoints accept and return JSON, with successful responses wrapped as `{ "data": ... }` and errors as `{ "error": "..." }`.'
layout: capability
name: OpenReplay API
operations:
- description: List projects
  method: GET
  name: listprojects
  path: /public/projects
- description: Create project
  method: POST
  name: createproject
  path: /public/projects
- description: Get project
  method: GET
  name: getproject
  path: /public/projects/{projectKey}
- description: Search users
  method: POST
  name: searchusers
  path: /public/{projectKey}/users
- description: Get user
  method: GET
  name: getuser
  path: /public/{projectKey}/users/{userId}
- description: Delete user
  method: DELETE
  name: deleteuser
  path: /public/{projectKey}/users/{userId}
- description: List user sessions
  method: POST
  name: listusersessions
  path: /public/{projectKey}/users/{userId}/sessions
- description: List session events
  method: POST
  name: listsessionevents
  path: /public/{projectKey}/sessions/{sessionId}/events
- description: List jobs
  method: GET
  name: listjobs
  path: /public/{projectKey}/jobs
- description: Get job
  method: GET
  name: getjob
  path: /public/{projectKey}/jobs/{jobId}
- description: Cancel job
  method: DELETE
  name: canceljob
  path: /public/{projectKey}/jobs/{jobId}
- description: List live sessions
  method: GET
  name: listlivesessions
  path: /public/{projectKey}/assist/sessions
- description: Search live sessions
  method: POST
  name: searchlivesessions
  path: /public/{projectKey}/assist/sessions
personas: []
provider_name: OpenReplay
provider_slug: openreplay
search_terms:
- getproject
- session replay
- openreplay
- searchusers
- api
- get job
- listsessionevents
- listjobs
- search live sessions
- open source
- list user sessions
- canceljob
- getuser
- delete user
- listusersessions
- deleteuser
- search users
- error tracking
- create project
- list projects
- cancel job
- listlivesessions
- performance monitoring
- debugging
- searchlivesessions
- list jobs
- get user
- getjob
- get project
- listprojects
- list session events
- user behavior
- list live sessions
- createproject
slug: openreplay-capability
source_filename: openreplay-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: OpenReplay API\n  description: 'The OpenReplay Public REST API (v2) provides programmatic access to projects, sessions, events, users, background\n    jobs, and live Assist sessions (Enterprise Edition). All endpoints accept and return JSON, with successful responses wrapped\n    as `{ \"data\": ... }` and errors as `{ \"error\": \"...\" }`.'\n  tags:\n  - Openreplay\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: openreplay\n    baseUri: https://api.openreplay.com/v2\n    description: OpenReplay API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{OPENREPLAY_TOKEN}}'\n    resources:\n    - name: public-projects\n      path: /public/projects\n      operations:\n      - name: listprojects\n        method: GET\n        description: List projects\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n      - name: createproject\n        method: POST\n        description: Create project\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: public-projects-projectkey\n      path: /public/projects/{projectKey}\n      operations:\n      - name: getproject\n        method: GET\n        description: Get project\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: public-projectkey-users\n      path: /public/{projectKey}/users\n      operations:\n      - name: searchusers\n        method: POST\n        description: Search users\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: public-projectkey-users-userid\n      path: /public/{projectKey}/users/{userId}\n      operations:\n      - name: getuser\n        method:\
  \ GET\n        description: Get user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteuser\n        method: DELETE\n        description: Delete user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: public-projectkey-users-userid-sessions\n      path: /public/{projectKey}/users/{userId}/sessions\n      operations:\n      - name: listusersessions\n        method: POST\n        description: List user sessions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: public-projectkey-sessions-sessionid-events\n      path: /public/{projectKey}/sessions/{sessionId}/events\n      operations:\n      - name: listsessionevents\n        method: POST\n        description: List session events\n        inputParameters:\n        - name:\
  \ sessionId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: public-projectkey-jobs\n      path: /public/{projectKey}/jobs\n      operations:\n      - name: listjobs\n        method: GET\n        description: List jobs\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n        - name: page\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: public-projectkey-jobs-jobid\n      path: /public/{projectKey}/jobs/{jobId}\n      operations:\n      - name: getjob\n        method: GET\n        description: Get job\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: canceljob\n\
  \        method: DELETE\n        description: Cancel job\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: public-projectkey-assist-sessions\n      path: /public/{projectKey}/assist/sessions\n      operations:\n      - name: listlivesessions\n        method: GET\n        description: List live sessions\n        inputParameters:\n        - name: userId\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: searchlivesessions\n        method: POST\n        description: Search live sessions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: openreplay-rest\n    description: REST adapter for OpenReplay API.\n    resources:\n    - path: /public/projects\n\
  \      name: listprojects\n      operations:\n      - method: GET\n        name: listprojects\n        description: List projects\n        call: openreplay.listprojects\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /public/projects\n      name: createproject\n      operations:\n      - method: POST\n        name: createproject\n        description: Create project\n        call: openreplay.createproject\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /public/projects/{projectKey}\n      name: getproject\n      operations:\n      - method: GET\n        name: getproject\n        description: Get project\n        call: openreplay.getproject\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /public/{projectKey}/users\n      name: searchusers\n      operations:\n      - method: POST\n        name: searchusers\n        description: Search users\n        call: openreplay.searchusers\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /public/{projectKey}/users/{userId}\n      name: getuser\n      operations:\n      - method: GET\n        name: getuser\n        description: Get user\n        call: openreplay.getuser\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /public/{projectKey}/users/{userId}\n      name: deleteuser\n      operations:\n      - method: DELETE\n        name: deleteuser\n        description: Delete user\n        call: openreplay.deleteuser\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /public/{projectKey}/users/{userId}/sessions\n      name: listusersessions\n      operations:\n      - method: POST\n        name: listusersessions\n        description: List user sessions\n        call: openreplay.listusersessions\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /public/{projectKey}/sessions/{sessionId}/events\n\
  \      name: listsessionevents\n      operations:\n      - method: POST\n        name: listsessionevents\n        description: List session events\n        call: openreplay.listsessionevents\n        with:\n          sessionId: rest.sessionId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /public/{projectKey}/jobs\n      name: listjobs\n      operations:\n      - method: GET\n        name: listjobs\n        description: List jobs\n        call: openreplay.listjobs\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /public/{projectKey}/jobs/{jobId}\n      name: getjob\n      operations:\n      - method: GET\n        name: getjob\n        description: Get job\n        call: openreplay.getjob\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /public/{projectKey}/jobs/{jobId}\n      name: canceljob\n      operations:\n      - method: DELETE\n        name: canceljob\n        description:\
  \ Cancel job\n        call: openreplay.canceljob\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /public/{projectKey}/assist/sessions\n      name: listlivesessions\n      operations:\n      - method: GET\n        name: listlivesessions\n        description: List live sessions\n        call: openreplay.listlivesessions\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /public/{projectKey}/assist/sessions\n      name: searchlivesessions\n      operations:\n      - method: POST\n        name: searchlivesessions\n        description: Search live sessions\n        call: openreplay.searchlivesessions\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: openreplay-mcp\n    transport: http\n    description: MCP adapter for OpenReplay API for AI agent use.\n    tools:\n    - name: listprojects\n      description: List projects\n      hints:\n        readOnly:\
  \ true\n        destructive: false\n        idempotent: true\n      call: openreplay.listprojects\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createproject\n      description: Create project\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: openreplay.createproject\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getproject\n      description: Get project\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: openreplay.getproject\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: searchusers\n      description: Search users\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: openreplay.searchusers\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getuser\n      description: Get user\n      hints:\n\
  \        readOnly: true\n        destructive: false\n        idempotent: true\n      call: openreplay.getuser\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteuser\n      description: Delete user\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: openreplay.deleteuser\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listusersessions\n      description: List user sessions\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: openreplay.listusersessions\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listsessionevents\n      description: List session events\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: openreplay.listsessionevents\n      with:\n        sessionId: tools.sessionId\n      inputParameters:\n      - name: sessionId\n\
  \        type: string\n        description: sessionId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listjobs\n      description: List jobs\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: openreplay.listjobs\n      with:\n        limit: tools.limit\n        page: tools.page\n      inputParameters:\n      - name: limit\n        type: integer\n        description: limit\n      - name: page\n        type: integer\n        description: page\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getjob\n      description: Get job\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: openreplay.getjob\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: canceljob\n      description: Cancel job\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent:\
  \ true\n      call: openreplay.canceljob\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listlivesessions\n      description: List live sessions\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: openreplay.listlivesessions\n      with:\n        userId: tools.userId\n      inputParameters:\n      - name: userId\n        type: string\n        description: userId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: searchlivesessions\n      description: Search live sessions\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: openreplay.searchlivesessions\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    OPENREPLAY_TOKEN: OPENREPLAY_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/openreplay/refs/heads/main/capabilities/openreplay-capability.yaml
tags:
- Openreplay
- API
tools:
- description: List projects
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listprojects
- description: Create project
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createproject
- description: Get project
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getproject
- description: Search users
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: searchusers
- description: Get user
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getuser
- description: Delete user
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteuser
- description: List user sessions
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: listusersessions
- description: List session events
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: listsessionevents
- description: List jobs
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listjobs
- description: Get job
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getjob
- description: Cancel job
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: canceljob
- description: List live sessions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listlivesessions
- description: Search live sessions
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: searchlivesessions
---
