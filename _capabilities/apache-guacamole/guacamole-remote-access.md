---
categories:
- security
consumed_apis:
- guacamole-rest
description: Unified capability for managing Apache Guacamole remote desktop gateway — managing connections, users, groups, and monitoring active sessions. Designed for IT administrators and security teams managing remote access infrastructure.
layout: capability
name: Apache Guacamole Remote Access
operations:
- description: List all remote desktop connections
  method: GET
  name: list-connections
  path: /v1/connections
- description: Create a new remote desktop connection
  method: POST
  name: create-connection
  path: /v1/connections
- description: List all Guacamole users
  method: GET
  name: list-users
  path: /v1/users
- description: List all active remote desktop sessions
  method: GET
  name: list-active-sessions
  path: /v1/sessions
personas: []
provider_name: Apache Guacamole
provider_slug: apache-guacamole
search_terms:
- list active sessions
- list connections
- list guacamole users
- rdp
- administrators managing remote access infrastructure and user accounts
- create a new user account in guacamole
- remote access
- apache
- IT Administrator
- create connection
- remote desktop connection management via vnc, rdp, ssh protocols
- security
- vpn alternative
- list all active remote desktop sessions
- create a new remote desktop connection in guacamole
- session monitoring, access control, and audit logging
- user and group account administration
- web gateway
- open source
- manage remote desktop connections, users, and active sessions
- it administration
- create a new remote desktop connection
- active session monitoring
- Security Team
- list users
- list all guacamole user accounts
- vnc
- remote desktop
- ssh
- user account management
- create guacamole user
- apache guacamole
- list all configured remote desktop connections in guacamole
- list remote connections
- security teams monitoring active sessions and auditing connection history
- list all guacamole users
- create remote connection
- remote desktop connection management
- list all currently active remote desktop sessions
- list all remote desktop connections
slug: guacamole-remote-access
tags:
- Apache Guacamole
- Remote Desktop
- Security
- IT Administration
- VPN Alternative
tools:
- description: List all configured remote desktop connections in Guacamole
  hints:
    openWorld: true
    readOnly: true
  name: list-remote-connections
- description: Create a new remote desktop connection in Guacamole
  hints:
    destructive: false
    readOnly: false
  name: create-remote-connection
- description: List all Guacamole user accounts
  hints:
    openWorld: true
    readOnly: true
  name: list-guacamole-users
- description: List all currently active remote desktop sessions
  hints:
    openWorld: true
    readOnly: true
  name: list-active-sessions
- description: Create a new user account in Guacamole
  hints:
    destructive: false
    readOnly: false
  name: create-guacamole-user
---
