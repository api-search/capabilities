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
- rdp
- list users
- create a new remote desktop connection
- list remote connections
- administrators managing remote access infrastructure and user accounts
- create remote connection
- remote access
- create guacamole user
- list all guacamole users
- remote desktop connection management
- active session monitoring
- session monitoring, access control, and audit logging
- ssh
- create a new remote desktop connection in guacamole
- vpn alternative
- list guacamole users
- it administration
- list active sessions
- list all remote desktop connections
- user account management
- vnc
- security teams monitoring active sessions and auditing connection history
- user and group account administration
- apache
- list all active remote desktop sessions
- remote desktop
- list all configured remote desktop connections in guacamole
- list connections
- remote desktop connection management via vnc, rdp, ssh protocols
- security
- list all currently active remote desktop sessions
- open source
- manage remote desktop connections, users, and active sessions
- create a new user account in guacamole
- web gateway
- list all guacamole user accounts
- IT Administrator
- Security Team
- apache guacamole
- create connection
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
