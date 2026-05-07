---
categories: []
consumed_apis: []
description: Unified developer security training capability for the Secure Code Warrior platform. Enables security and engineering leaders to manage users, teams, and assessments, track training progress and engagement, generate security training reports, and audit platform activity across the organization.
layout: capability
name: Secure Code Warrior Developer Security Training
operations:
- description: List all platform users
  method: GET
  name: list-users
  path: /v1/users
- description: Create a new user
  method: POST
  name: create-user
  path: /v1/users
- description: List all teams
  method: GET
  name: list-teams
  path: /v1/teams
- description: Get developer leaderboard with training stats
  method: GET
  name: get-developer-leaderboard
  path: /v1/training/leaderboard
- description: Get training progress per developer
  method: GET
  name: get-developers-progress
  path: /v1/training/progress
- description: List all assessments
  method: GET
  name: list-assessments
  path: /v1/assessments
- description: List all courses
  method: GET
  name: list-courses
  path: /v1/courses
- description: Get time spent on training activities
  method: GET
  name: get-time-spent
  path: /v1/metrics/time-spent
- description: Get system audit log
  method: GET
  name: get-audit-log
  path: /v1/audit-log
personas: []
provider_name: Secure Code Warrior
provider_slug: secure-code-warrior
search_terms:
- list courses
- training time metrics
- application security
- list all security training teams within the organization
- training progress reporting
- get developer leaderboard
- list all courses
- get audit log
- list all assessments
- team management
- devsecops
- developer training
- get developers progress
- list teams
- list assessments
- security training
- get developer security training leaderboard showing points, completions, and rank changes
- secure coding
- list users
- get detailed training progress for all developers including realm, level, and quest completion
- system audit log
- list all teams
- enroll a new developer in the secure code warrior security training platform
- get total time developers have spent on security training, assessments, courses, and tournaments
- security training courses
- security education
- get training progress per developer
- get system audit log
- list all platform users
- user management
- get developer leaderboard with training stats
- list security knowledge assessments with their status, language coverage, and difficulty levels
- get time spent
- list available secure coding courses organized by language and security topic
- create user
- retrieve platform audit log showing user actions and administrative changes
- create a new user
- reporting
- developer training leaderboard
- get training progress
- security assessments
- get time spent on training activities
- appsec
- list all developers enrolled in secure code warrior security training
slug: developer-security-training
source_filename: developer-security-training.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Secure Code Warrior Developer Security Training\n  description: Unified developer security training capability for the Secure Code Warrior platform. Enables security and engineering\n    leaders to manage users, teams, and assessments, track training progress and engagement, generate security training reports,\n    and audit platform activity across the organization.\n  tags:\n  - Security Training\n  - Application Security\n  - DevSecOps\n  - Developer Training\n  - Reporting\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SCW_API_KEY: SCW_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: scw-portal\n    baseUri: https://portal-api.securecodewarrior.com/api/v2\n    description: Secure Code Warrior Portal API for training management and reporting\n    authentication:\n      type: apikey\n      key: X-API-Key\n      value: '{{SCW_API_KEY}}'\n      placement: header\n    resources:\n\
  \    - name: users\n      path: /users\n      description: Manage platform users\n      operations:\n      - name: list-users\n        method: GET\n        description: List all users in the organization\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-user\n        method: POST\n        description: Create a new user account\n        body:\n          type: json\n          data:\n            email: '{{tools.email}}'\n            firstName: '{{tools.firstName}}'\n            lastName: '{{tools.lastName}}'\n            role: '{{tools.role}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: teams\n      path: /teams\n      description: Manage teams\n      operations:\n      - name:\
  \ list-teams\n        method: GET\n        description: List all teams in the organization\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n          required: false\n        - name: name\n          in: query\n          type: string\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: developer-leaderboard\n      path: /training/developer-leaderboard\n      description: Developer training leaderboard\n      operations:\n      - name: get-developer-leaderboard\n        method: GET\n        description: Get developer leaderboard with training stats\n        inputParameters:\n        - name: report_period\n          in: query\n          type: integer\n          required: false\n          description: Report period in days (1, 7, or 30)\n        - name: page\n          in: query\n          type: integer\n          required: false\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: developers-progress\n      path: /training/developers-progress\n      description: Developer training progress\n      operations:\n      - name: get-developers-progress\n        method: GET\n        description: Get training progress with realm, level, and quest data\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: assessments\n      path: /assessments\n      description: Manage security assessments\n      operations:\n      - name: list-assessments\n        method: GET\n        description: List all assessments in the organization\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n          required:\
  \ false\n        - name: startdate\n          in: query\n          type: string\n          required: false\n        - name: enddate\n          in: query\n          type: string\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: courses\n      path: /courses\n      description: Manage security courses\n      operations:\n      - name: list-courses\n        method: GET\n        description: List all available security training courses\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: time-spent\n      path: /metrics/time-spent\n      description: Time spent metrics\n      operations:\n      - name: get-time-spent\n        method: GET\n        description: Get time spent\
  \ across training activities\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n          required: false\n        - name: team\n          in: query\n          type: string\n          required: false\n        - name: startdate\n          in: query\n          type: string\n          required: false\n        - name: enddate\n          in: query\n          type: string\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: audit-log\n      path: /audit-log\n      description: System audit log\n      operations:\n      - name: get-audit-log\n        method: GET\n        description: Retrieve system audit logs\n        inputParameters:\n        - name: from_date\n          in: query\n          type: string\n          required: true\n        - name: to_date\n          in: query\n          type: string\n          required: true\n        -\
  \ name: page\n          in: query\n          type: integer\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: security-training-api\n    description: Unified REST API for Secure Code Warrior developer security training management.\n    resources:\n    - path: /v1/users\n      name: users\n      description: User management\n      operations:\n      - method: GET\n        name: list-users\n        description: List all platform users\n        call: scw-portal.list-users\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-user\n        description: Create a new user\n        call: scw-portal.create-user\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/teams\n      name: teams\n      description: Team management\n      operations:\n\
  \      - method: GET\n        name: list-teams\n        description: List all teams\n        call: scw-portal.list-teams\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/training/leaderboard\n      name: developer-leaderboard\n      description: Developer training leaderboard\n      operations:\n      - method: GET\n        name: get-developer-leaderboard\n        description: Get developer leaderboard with training stats\n        call: scw-portal.get-developer-leaderboard\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/training/progress\n      name: training-progress\n      description: Training progress reporting\n      operations:\n      - method: GET\n        name: get-developers-progress\n        description: Get training progress per developer\n        call: scw-portal.get-developers-progress\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/assessments\n\
  \      name: assessments\n      description: Security assessments\n      operations:\n      - method: GET\n        name: list-assessments\n        description: List all assessments\n        call: scw-portal.list-assessments\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/courses\n      name: courses\n      description: Security training courses\n      operations:\n      - method: GET\n        name: list-courses\n        description: List all courses\n        call: scw-portal.list-courses\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/metrics/time-spent\n      name: time-spent\n      description: Training time metrics\n      operations:\n      - method: GET\n        name: get-time-spent\n        description: Get time spent on training activities\n        call: scw-portal.get-time-spent\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/audit-log\n      name: audit-log\n\
  \      description: System audit log\n      operations:\n      - method: GET\n        name: get-audit-log\n        description: Get system audit log\n        call: scw-portal.get-audit-log\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: security-training-mcp\n    transport: http\n    description: MCP server for AI-assisted developer security training management.\n    tools:\n    - name: list-users\n      description: List all developers enrolled in Secure Code Warrior security training\n      hints:\n        readOnly: true\n        openWorld: false\n      call: scw-portal.list-users\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-user\n      description: Enroll a new developer in the Secure Code Warrior security training platform\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: scw-portal.create-user\n      with:\n  \
  \      email: tools.email\n        firstName: tools.firstName\n        lastName: tools.lastName\n        role: tools.role\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-teams\n      description: List all security training teams within the organization\n      hints:\n        readOnly: true\n        openWorld: false\n      call: scw-portal.list-teams\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-developer-leaderboard\n      description: Get developer security training leaderboard showing points, completions, and rank changes\n      hints:\n        readOnly: true\n        openWorld: false\n      call: scw-portal.get-developer-leaderboard\n      with:\n        report_period: tools.report_period\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-training-progress\n      description: Get detailed training progress for all developers including realm, level, and quest completion\n  \
  \    hints:\n        readOnly: true\n        openWorld: false\n      call: scw-portal.get-developers-progress\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-assessments\n      description: List security knowledge assessments with their status, language coverage, and difficulty levels\n      hints:\n        readOnly: true\n        openWorld: false\n      call: scw-portal.list-assessments\n      with:\n        startdate: tools.startdate\n        enddate: tools.enddate\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-courses\n      description: List available secure coding courses organized by language and security topic\n      hints:\n        readOnly: true\n        openWorld: false\n      call: scw-portal.list-courses\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-time-spent\n      description: Get total time developers have spent on security training, assessments, courses,\
  \ and tournaments\n      hints:\n        readOnly: true\n        openWorld: false\n      call: scw-portal.get-time-spent\n      with:\n        team: tools.team\n        startdate: tools.startdate\n        enddate: tools.enddate\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-audit-log\n      description: Retrieve platform audit log showing user actions and administrative changes\n      hints:\n        readOnly: true\n        openWorld: false\n      call: scw-portal.get-audit-log\n      with:\n        from_date: tools.from_date\n        to_date: tools.to_date\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/secure-code-warrior/refs/heads/main/capabilities/developer-security-training.yaml
tags:
- Security Training
- Application Security
- DevSecOps
- Developer Training
- Reporting
tools:
- description: List all developers enrolled in Secure Code Warrior security training
  hints:
    openWorld: false
    readOnly: true
  name: list-users
- description: Enroll a new developer in the Secure Code Warrior security training platform
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-user
- description: List all security training teams within the organization
  hints:
    openWorld: false
    readOnly: true
  name: list-teams
- description: Get developer security training leaderboard showing points, completions, and rank changes
  hints:
    openWorld: false
    readOnly: true
  name: get-developer-leaderboard
- description: Get detailed training progress for all developers including realm, level, and quest completion
  hints:
    openWorld: false
    readOnly: true
  name: get-training-progress
- description: List security knowledge assessments with their status, language coverage, and difficulty levels
  hints:
    openWorld: false
    readOnly: true
  name: list-assessments
- description: List available secure coding courses organized by language and security topic
  hints:
    openWorld: false
    readOnly: true
  name: list-courses
- description: Get total time developers have spent on security training, assessments, courses, and tournaments
  hints:
    openWorld: false
    readOnly: true
  name: get-time-spent
- description: Retrieve platform audit log showing user actions and administrative changes
  hints:
    openWorld: false
    readOnly: true
  name: get-audit-log
---
