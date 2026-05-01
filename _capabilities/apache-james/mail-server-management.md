---
categories: []
consumed_apis:
- james-webadmin
description: Workflow capability for mail server administrators to manage domains, users, mailboxes, and monitor tasks in Apache James.
layout: capability
name: Apache James Mail Server Management
operations:
- description: ''
  method: GET
  name: list-domains
  path: /v1/domains
- description: ''
  method: POST
  name: create-domain
  path: /v1/domains
- description: ''
  method: GET
  name: list-users
  path: /v1/users
- description: ''
  method: POST
  name: create-user
  path: /v1/users
- description: ''
  method: GET
  name: list-tasks
  path: /v1/tasks
personas: []
provider_name: Apache James
provider_slug: apache-james
search_terms:
- mail server
- list domains
- list all email domains configured in the james server
- list asynchronous administrative tasks and their statuses
- smtp
- imap
- email administration
- apache james
- email
- administrators who manage james mail server domains, users, and queues
- Mail Administrator
- jmap
- create domain
- create a new email domain in the james server
- open source
- java
- list users
- list tasks
- list all user accounts in the james mail server
- create a new mail user account
- mail server management
- create user
slug: mail-server-management
source_filename: mail-server-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Apache James Mail Server Management\"\n  description: \"Workflow capability for mail server administrators to manage domains, users, mailboxes, and monitor tasks in Apache James.\"\n  tags:\n    - Apache James\n    - Email Administration\n    - Mail Server Management\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      JAMES_ADMIN_TOKEN: JAMES_ADMIN_TOKEN\n\ncapability:\n  consumes:\n    - import: james-webadmin\n      location: ./shared/webadmin-rest-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: james-mail-management-api\n      description: \"Unified REST API for Apache James mail server management.\"\n      resources:\n        - path: /v1/domains\n          name: domains\n          operations:\n            - method: GET\n              name: list-domains\n              call: \"james-webadmin.list-domains\"\n              outputParameters:\n      \
  \          - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-domain\n              call: \"james-webadmin.create-domain\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/users\n          name: users\n          operations:\n            - method: GET\n              name: list-users\n              call: \"james-webadmin.list-users\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-user\n              call: \"james-webadmin.create-user\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/tasks\n          name: tasks\n          operations:\n            - method: GET\n              name: list-tasks\n              call: \"james-webadmin.list-tasks\"\n              outputParameters:\n        \
  \        - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: james-mail-management-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Apache James mail server management.\"\n      tools:\n        - name: list-domains\n          description: List all email domains configured in the James server\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"james-webadmin.list-domains\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-domain\n          description: Create a new email domain in the James server\n          hints:\n            readOnly: false\n          call: \"james-webadmin.create-domain\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-users\n          description: List all user accounts in the James mail server\n          hints:\n         \
  \   readOnly: true\n            openWorld: true\n          call: \"james-webadmin.list-users\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-user\n          description: Create a new mail user account\n          hints:\n            readOnly: false\n          call: \"james-webadmin.create-user\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-tasks\n          description: List asynchronous administrative tasks and their statuses\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"james-webadmin.list-tasks\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/apache-james/refs/heads/main/capabilities/mail-server-management.yaml
tags:
- Apache James
- Email Administration
- Mail Server Management
tools:
- description: List all email domains configured in the James server
  hints:
    openWorld: true
    readOnly: true
  name: list-domains
- description: Create a new email domain in the James server
  hints:
    readOnly: false
  name: create-domain
- description: List all user accounts in the James mail server
  hints:
    openWorld: true
    readOnly: true
  name: list-users
- description: Create a new mail user account
  hints:
    readOnly: false
  name: create-user
- description: List asynchronous administrative tasks and their statuses
  hints:
    openWorld: true
    readOnly: true
  name: list-tasks
---
