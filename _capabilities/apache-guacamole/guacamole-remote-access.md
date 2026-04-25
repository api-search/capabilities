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
- create a new user account in guacamole
- remote access
- list all guacamole user accounts
- list all remote desktop connections
- create a new remote desktop connection
- security teams monitoring active sessions and auditing connection history
- administrators managing remote access infrastructure and user accounts
- vnc
- apache
- create remote connection
- list remote connections
- security
- vpn alternative
- list all guacamole users
- create guacamole user
- list all active remote desktop sessions
- rdp
- IT Administrator
- list connections
- user and group account administration
- web gateway
- remote desktop connection management
- session monitoring, access control, and audit logging
- list all configured remote desktop connections in guacamole
- user account management
- list active sessions
- active session monitoring
- list all currently active remote desktop sessions
- list users
- remote desktop
- open source
- it administration
- remote desktop connection management via vnc, rdp, ssh protocols
- ssh
- create connection
- apache guacamole
- list guacamole users
- Security Team
- manage remote desktop connections, users, and active sessions
- create a new remote desktop connection in guacamole
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
