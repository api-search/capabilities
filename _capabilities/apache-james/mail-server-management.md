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
- email
- list tasks
- list asynchronous administrative tasks and their statuses
- create a new mail user account
- mail server management
- jmap
- Mail Administrator
- list all user accounts in the james mail server
- email administration
- smtp
- apache james
- java
- list domains
- open source
- list users
- create a new email domain in the james server
- list all email domains configured in the james server
- imap
- administrators who manage james mail server domains, users, and queues
- create domain
- create user
- mail server
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
