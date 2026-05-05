---
categories: []
consumed_apis:
- scw-portal
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
- get developer leaderboard
- training time metrics
- training progress reporting
- devsecops
- list users
- get training progress per developer
- list all courses
- security training
- create user
- enroll a new developer in the secure code warrior security training platform
- get detailed training progress for all developers including realm, level, and quest completion
- developer training leaderboard
- get audit log
- get system audit log
- appsec
- application security
- security education
- list all assessments
- get time spent
- developer training
- list assessments
- get time spent on training activities
- list all platform users
- list all security training teams within the organization
- get developer security training leaderboard showing points, completions, and rank changes
- security training courses
- create a new user
- list security knowledge assessments with their status, language coverage, and difficulty levels
- list all developers enrolled in secure code warrior security training
- get training progress
- get developer leaderboard with training stats
- retrieve platform audit log showing user actions and administrative changes
- list teams
- system audit log
- team management
- list courses
- list available secure coding courses organized by language and security topic
- secure coding
- list all teams
- user management
- get developers progress
- get total time developers have spent on security training, assessments, courses, and tournaments
- security assessments
- reporting
slug: developer-security-training
source_filename: developer-security-training.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Secure Code Warrior Developer Security Training\"\n  description: >-\n    Unified developer security training capability for the Secure Code Warrior platform.\n    Enables security and engineering leaders to manage users, teams, and assessments,\n    track training progress and engagement, generate security training reports, and\n    audit platform activity across the organization.\n  tags:\n    - Security Training\n    - Application Security\n    - DevSecOps\n    - Developer Training\n    - Reporting\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SCW_API_KEY: SCW_API_KEY\n\ncapability:\n  consumes:\n    - import: scw-portal\n      location: ./shared/portal.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: security-training-api\n      description: \"Unified REST API for Secure Code Warrior developer security training management.\"\n      resources:\n\
  \        - path: /v1/users\n          name: users\n          description: \"User management\"\n          operations:\n            - method: GET\n              name: list-users\n              description: \"List all platform users\"\n              call: \"scw-portal.list-users\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-user\n              description: \"Create a new user\"\n              call: \"scw-portal.create-user\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/teams\n          name: teams\n          description: \"Team management\"\n          operations:\n            - method: GET\n              name: list-teams\n              description: \"List all teams\"\n              call: \"scw-portal.list-teams\"\n              outputParameters:\n                - type: object\n                  mapping:\
  \ \"$.\"\n\n        - path: /v1/training/leaderboard\n          name: developer-leaderboard\n          description: \"Developer training leaderboard\"\n          operations:\n            - method: GET\n              name: get-developer-leaderboard\n              description: \"Get developer leaderboard with training stats\"\n              call: \"scw-portal.get-developer-leaderboard\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/training/progress\n          name: training-progress\n          description: \"Training progress reporting\"\n          operations:\n            - method: GET\n              name: get-developers-progress\n              description: \"Get training progress per developer\"\n              call: \"scw-portal.get-developers-progress\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/assessments\n          name: assessments\n\
  \          description: \"Security assessments\"\n          operations:\n            - method: GET\n              name: list-assessments\n              description: \"List all assessments\"\n              call: \"scw-portal.list-assessments\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/courses\n          name: courses\n          description: \"Security training courses\"\n          operations:\n            - method: GET\n              name: list-courses\n              description: \"List all courses\"\n              call: \"scw-portal.list-courses\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/metrics/time-spent\n          name: time-spent\n          description: \"Training time metrics\"\n          operations:\n            - method: GET\n              name: get-time-spent\n              description: \"Get time spent on training activities\"\
  \n              call: \"scw-portal.get-time-spent\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/audit-log\n          name: audit-log\n          description: \"System audit log\"\n          operations:\n            - method: GET\n              name: get-audit-log\n              description: \"Get system audit log\"\n              call: \"scw-portal.get-audit-log\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: security-training-mcp\n      transport: http\n      description: \"MCP server for AI-assisted developer security training management.\"\n      tools:\n        - name: list-users\n          description: \"List all developers enrolled in Secure Code Warrior security training\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"scw-portal.list-users\"\n   \
  \       outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-user\n          description: \"Enroll a new developer in the Secure Code Warrior security training platform\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"scw-portal.create-user\"\n          with:\n            email: \"tools.email\"\n            firstName: \"tools.firstName\"\n            lastName: \"tools.lastName\"\n            role: \"tools.role\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-teams\n          description: \"List all security training teams within the organization\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"scw-portal.list-teams\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-developer-leaderboard\n\
  \          description: \"Get developer security training leaderboard showing points, completions, and rank changes\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"scw-portal.get-developer-leaderboard\"\n          with:\n            report_period: \"tools.report_period\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-training-progress\n          description: \"Get detailed training progress for all developers including realm, level, and quest completion\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"scw-portal.get-developers-progress\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-assessments\n          description: \"List security knowledge assessments with their status, language coverage, and difficulty levels\"\n          hints:\n            readOnly: true\n\
  \            openWorld: false\n          call: \"scw-portal.list-assessments\"\n          with:\n            startdate: \"tools.startdate\"\n            enddate: \"tools.enddate\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-courses\n          description: \"List available secure coding courses organized by language and security topic\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"scw-portal.list-courses\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-time-spent\n          description: \"Get total time developers have spent on security training, assessments, courses, and tournaments\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"scw-portal.get-time-spent\"\n          with:\n            team: \"tools.team\"\n            startdate: \"tools.startdate\"\n      \
  \      enddate: \"tools.enddate\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-audit-log\n          description: \"Retrieve platform audit log showing user actions and administrative changes\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"scw-portal.get-audit-log\"\n          with:\n            from_date: \"tools.from_date\"\n            to_date: \"tools.to_date\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
