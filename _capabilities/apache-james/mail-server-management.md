---
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
- administrators who manage james mail server domains, users, and queues
- jmap
- java
- mail server management
- Mail Administrator
- mail server
- list all user accounts in the james mail server
- create a new mail user account
- create domain
- open source
- email
- imap
- smtp
- list asynchronous administrative tasks and their statuses
- create a new email domain in the james server
- list all email domains configured in the james server
- email administration
- list domains
- apache james
- list tasks
- list users
- create user
slug: mail-server-management
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
