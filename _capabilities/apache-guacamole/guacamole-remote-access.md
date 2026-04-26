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
- create remote connection
- apache guacamole
- list active sessions
- list all active remote desktop sessions
- user and group account administration
- list all remote desktop connections
- remote desktop
- list all currently active remote desktop sessions
- create guacamole user
- user account management
- list all configured remote desktop connections in guacamole
- vnc
- web gateway
- rdp
- apache
- remote access
- vpn alternative
- list users
- manage remote desktop connections, users, and active sessions
- Security Team
- IT Administrator
- security teams monitoring active sessions and auditing connection history
- remote desktop connection management
- remote desktop connection management via vnc, rdp, ssh protocols
- list remote connections
- security
- open source
- list guacamole users
- session monitoring, access control, and audit logging
- create a new user account in guacamole
- list all guacamole users
- ssh
- list connections
- create connection
- active session monitoring
- create a new remote desktop connection
- administrators managing remote access infrastructure and user accounts
- it administration
- create a new remote desktop connection in guacamole
- list all guacamole user accounts
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
