---
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
- apache
- ssh
- list all active remote desktop sessions
- Security Team
- apache guacamole
- web gateway
- remote desktop
- create a new remote desktop connection
- create a new user account in guacamole
- list active sessions
- security teams monitoring active sessions and auditing connection history
- create a new remote desktop connection in guacamole
- list connections
- manage remote desktop connections, users, and active sessions
- remote access
- rdp
- vnc
- list all guacamole user accounts
- user and group account administration
- list all guacamole users
- list all configured remote desktop connections in guacamole
- list all currently active remote desktop sessions
- user account management
- create connection
- list remote connections
- list guacamole users
- list all remote desktop connections
- IT Administrator
- active session monitoring
- security
- session monitoring, access control, and audit logging
- create remote connection
- administrators managing remote access infrastructure and user accounts
- remote desktop connection management
- create guacamole user
- vpn alternative
- remote desktop connection management via vnc, rdp, ssh protocols
- it administration
- list users
- open source
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
