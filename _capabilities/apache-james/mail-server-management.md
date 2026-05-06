---
categories: []
consumed_apis: []
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
- email administration
- Mail Administrator
- list all user accounts in the james mail server
- list all email domains configured in the james server
- administrators who manage james mail server domains, users, and queues
- java
- mail server management
- list tasks
- apache james
- imap
- create user
- smtp
- create domain
- open source
- list asynchronous administrative tasks and their statuses
- jmap
- create a new mail user account
- list domains
- email
- mail server
- list users
- create a new email domain in the james server
slug: mail-server-management
source_filename: mail-server-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Apache James Mail Server Management\n  description: Workflow capability for mail server administrators to manage domains, users, mailboxes, and monitor tasks in\n    Apache James.\n  tags:\n  - Apache James\n  - Email Administration\n  - Mail Server Management\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    JAMES_ADMIN_TOKEN: JAMES_ADMIN_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: james-webadmin\n    baseUri: http://localhost:8000\n    description: Apache James WebAdmin REST API\n    authentication:\n      type: bearer\n      token: '{{JAMES_ADMIN_TOKEN}}'\n    resources:\n    - name: domains\n      path: /domains\n      description: Email domain management\n      operations:\n      - name: list-domains\n        method: GET\n        description: List all domains\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n     \
  \     value: $.\n      - name: create-domain\n        method: POST\n        description: Create a domain\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users\n      path: /users\n      description: User account management\n      operations:\n      - name: list-users\n        method: GET\n        description: List all users\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-user\n        method: POST\n        description: Create a user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tasks\n      path: /tasks\n      description: Async task management\n      operations:\n      - name: list-tasks\n        method: GET\n        description: List all tasks\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: james-mail-management-api\n    description: Unified REST API for Apache James mail server management.\n    resources:\n    - path: /v1/domains\n      name: domains\n      operations:\n      - method: GET\n        name: list-domains\n        call: james-webadmin.list-domains\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-domain\n        call: james-webadmin.create-domain\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/users\n      name: users\n      operations:\n      - method: GET\n        name: list-users\n        call: james-webadmin.list-users\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-user\n        call: james-webadmin.create-user\n        outputParameters:\n        - type:\
  \ object\n          mapping: $.\n    - path: /v1/tasks\n      name: tasks\n      operations:\n      - method: GET\n        name: list-tasks\n        call: james-webadmin.list-tasks\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: james-mail-management-mcp\n    transport: http\n    description: MCP server for AI-assisted Apache James mail server management.\n    tools:\n    - name: list-domains\n      description: List all email domains configured in the James server\n      hints:\n        readOnly: true\n        openWorld: true\n      call: james-webadmin.list-domains\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-domain\n      description: Create a new email domain in the James server\n      hints:\n        readOnly: false\n      call: james-webadmin.create-domain\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-users\n      description:\
  \ List all user accounts in the James mail server\n      hints:\n        readOnly: true\n        openWorld: true\n      call: james-webadmin.list-users\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-user\n      description: Create a new mail user account\n      hints:\n        readOnly: false\n      call: james-webadmin.create-user\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-tasks\n      description: List asynchronous administrative tasks and their statuses\n      hints:\n        readOnly: true\n        openWorld: true\n      call: james-webadmin.list-tasks\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
