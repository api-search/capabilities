---
categories: []
consumed_apis:
- nexus
description: Workflow capability for managing Nexus Repository security including users, roles, privileges, LDAP, SAML, content selectors, and authentication realms. Used by platform administrators and security teams.
layout: capability
name: Sonatype Nexus Security Administration
operations:
- description: List all users
  method: GET
  name: list-users
  path: /v1/users
- description: Create a new user
  method: POST
  name: create-user
  path: /v1/users
- description: Delete a user
  method: DELETE
  name: delete-user
  path: /v1/users
- description: List all roles
  method: GET
  name: list-roles
  path: /v1/roles
- description: Create a new role
  method: POST
  name: create-role
  path: /v1/roles
- description: Check system health status
  method: GET
  name: get-status
  path: /v1/system-status
- description: List all tasks
  method: GET
  name: list-tasks
  path: /v1/tasks
- description: Get a task by ID
  method: GET
  name: get-task
  path: /v1/tasks
- description: Run a task by ID
  method: POST
  name: run-task
  path: /v1/tasks
personas: []
provider_name: Sonatype Nexus
provider_slug: sonatype-nexus
search_terms:
- delete a user
- check system health status
- create role
- list users
- delete a nexus user by id
- security
- background task management
- npm
- user account management
- create user
- repository
- docker
- roles
- list all background tasks in nexus
- sonatype nexus
- list roles
- list all tasks
- check nexus system health and status
- artifact management
- create a new nexus role with privileges
- execute a nexus background task by id
- role and permission management
- run task
- administration
- list all roles
- users
- system health and status
- devops
- get a task by id
- delete user
- create a new user
- get status
- access control
- maven
- list all users
- list all nexus roles
- list all nexus users
- get task
- package management
- check system status
- software supply chain
- create a new nexus user account
- list tasks
- create a new role
- run a task by id
slug: security-administration
source_filename: security-administration.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Sonatype Nexus Security Administration\"\n  description: >-\n    Workflow capability for managing Nexus Repository security including users,\n    roles, privileges, LDAP, SAML, content selectors, and authentication realms.\n    Used by platform administrators and security teams.\n  tags:\n    - Sonatype Nexus\n    - Security\n    - Access Control\n    - Users\n    - Roles\n    - Administration\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      NEXUS_USERNAME: NEXUS_USERNAME\n      NEXUS_PASSWORD: NEXUS_PASSWORD\n\ncapability:\n  consumes:\n    - import: nexus\n      location: ./shared/nexus-repository.yaml\n\n  exposes:\n    - type: rest\n      port: 8081\n      namespace: nexus-security-api\n      description: \"Unified REST API for Nexus security administration.\"\n      resources:\n        - path: /v1/users\n          name: users\n          description: \"User account management\"\
  \n          operations:\n            - method: GET\n              name: list-users\n              description: \"List all users\"\n              call: \"nexus.list-users\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-user\n              description: \"Create a new user\"\n              call: \"nexus.create-user\"\n              with:\n                userId: \"rest.userId\"\n                firstName: \"rest.firstName\"\n                lastName: \"rest.lastName\"\n                emailAddress: \"rest.emailAddress\"\n                password: \"rest.password\"\n                status: \"rest.status\"\n                roles: \"rest.roles\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-user\n              description: \"Delete a user\"\n              call: \"nexus.delete-user\"\
  \n              with:\n                userId: \"rest.userId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/roles\n          name: roles\n          description: \"Role and permission management\"\n          operations:\n            - method: GET\n              name: list-roles\n              description: \"List all roles\"\n              call: \"nexus.list-roles\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-role\n              description: \"Create a new role\"\n              call: \"nexus.create-role\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/system-status\n          name: system-status\n          description: \"System health and status\"\n          operations:\n            - method: GET\n              name: get-status\n\
  \              description: \"Check system health status\"\n              call: \"nexus.get-status\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/tasks\n          name: tasks\n          description: \"Background task management\"\n          operations:\n            - method: GET\n              name: list-tasks\n              description: \"List all tasks\"\n              call: \"nexus.list-tasks\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: GET\n              name: get-task\n              description: \"Get a task by ID\"\n              call: \"nexus.get-task\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: run-task\n              description: \"Run a task by ID\"\n              call:\
  \ \"nexus.run-task\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9081\n      namespace: nexus-security-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Nexus security administration.\"\n      tools:\n        - name: list-users\n          description: \"List all Nexus users\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"nexus.list-users\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-user\n          description: \"Create a new Nexus user account\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"nexus.create-user\"\n          with:\n            userId: \"tools.userId\"\n            firstName: \"tools.firstName\"\n            lastName:\
  \ \"tools.lastName\"\n            emailAddress: \"tools.emailAddress\"\n            password: \"tools.password\"\n            status: \"tools.status\"\n            roles: \"tools.roles\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-user\n          description: \"Delete a Nexus user by ID\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"nexus.delete-user\"\n          with:\n            userId: \"tools.userId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-roles\n          description: \"List all Nexus roles\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"nexus.list-roles\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-role\n          description: \"Create a new Nexus\
  \ role with privileges\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"nexus.create-role\"\n          with:\n            id: \"tools.id\"\n            name: \"tools.name\"\n            description: \"tools.description\"\n            privileges: \"tools.privileges\"\n            roles: \"tools.roles\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: check-system-status\n          description: \"Check Nexus system health and status\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"nexus.get-status\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-tasks\n          description: \"List all background tasks in Nexus\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"nexus.list-tasks\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n        - name: run-task\n          description: \"Execute a Nexus background task by ID\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"nexus.run-task\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/sonatype-nexus/refs/heads/main/capabilities/security-administration.yaml
tags:
- Sonatype Nexus
- Security
- Access Control
- Users
- Roles
- Administration
tools:
- description: List all Nexus users
  hints:
    idempotent: true
    readOnly: true
  name: list-users
- description: Create a new Nexus user account
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-user
- description: Delete a Nexus user by ID
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-user
- description: List all Nexus roles
  hints:
    idempotent: true
    readOnly: true
  name: list-roles
- description: Create a new Nexus role with privileges
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-role
- description: Check Nexus system health and status
  hints:
    idempotent: true
    readOnly: true
  name: check-system-status
- description: List all background tasks in Nexus
  hints:
    idempotent: true
    readOnly: true
  name: list-tasks
- description: Execute a Nexus background task by ID
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: run-task
---
