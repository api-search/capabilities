---
categories:
- security
consumed_apis: []
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
- apache guacamole
- user account management
- session monitoring, access control, and audit logging
- vpn alternative
- administrators managing remote access infrastructure and user accounts
- list all guacamole users
- IT Administrator
- list guacamole users
- list all guacamole user accounts
- vnc
- create remote connection
- list all configured remote desktop connections in guacamole
- apache
- security
- active session monitoring
- list remote connections
- create a new user account in guacamole
- rdp
- ssh
- Security Team
- open source
- manage remote desktop connections, users, and active sessions
- list active sessions
- remote access
- remote desktop connection management
- list all active remote desktop sessions
- create guacamole user
- list connections
- user and group account administration
- list all currently active remote desktop sessions
- list users
- security teams monitoring active sessions and auditing connection history
- remote desktop connection management via vnc, rdp, ssh protocols
- create a new remote desktop connection in guacamole
- remote desktop
- it administration
- create a new remote desktop connection
- web gateway
- create connection
- list all remote desktop connections
slug: guacamole-remote-access
source_filename: guacamole-remote-access.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Apache Guacamole Remote Access\n  description: Unified capability for managing Apache Guacamole remote desktop gateway — managing connections, users, groups,\n    and monitoring active sessions. Designed for IT administrators and security teams managing remote access infrastructure.\n  tags:\n  - Apache Guacamole\n  - Remote Desktop\n  - Security\n  - IT Administration\n  - VPN Alternative\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    GUACAMOLE_URL: GUACAMOLE_URL\n    GUACAMOLE_TOKEN: GUACAMOLE_TOKEN\n    GUACAMOLE_DATA_SOURCE: GUACAMOLE_DATA_SOURCE\ncapability:\n  consumes:\n  - type: http\n    namespace: guacamole-rest\n    baseUri: http://localhost:8080/guacamole\n    description: Apache Guacamole REST API\n    authentication:\n      type: apikey\n      key: Guacamole-Token\n      value: '{{GUACAMOLE_TOKEN}}'\n      placement: header\n    resources:\n    - name: auth\n      path: /api/tokens\n\
  \      description: Authentication management\n      operations:\n      - name: authenticate\n        method: POST\n        description: Authenticate and get session token\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: connections\n      path: /api/session/data/{dataSource}/connections\n      description: Remote connection management\n      operations:\n      - name: list-connections\n        method: GET\n        description: List all remote desktop connections\n        inputParameters:\n        - name: dataSource\n          in: path\n          type: string\n          required: true\n          description: Data source identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-connection\n        method: POST\n        description: Create a new remote desktop connection\n\
  \        inputParameters:\n        - name: dataSource\n          in: path\n          type: string\n          required: true\n          description: Data source identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users\n      path: /api/session/data/{dataSource}/users\n      description: User management\n      operations:\n      - name: list-users\n        method: GET\n        description: List all Guacamole users\n        inputParameters:\n        - name: dataSource\n          in: path\n          type: string\n          required: true\n          description: Data source identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-user\n        method: POST\n        description: Create a new Guacamole user\n        inputParameters:\n        - name: dataSource\n          in: path\n          type:\
  \ string\n          required: true\n          description: Data source identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: active-connections\n      path: /api/session/data/{dataSource}/activeConnections\n      description: Active session management\n      operations:\n      - name: list-active-connections\n        method: GET\n        description: List all active remote desktop sessions\n        inputParameters:\n        - name: dataSource\n          in: path\n          type: string\n          required: true\n          description: Data source identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: guacamole-access-api\n    description: Unified REST API for Apache Guacamole remote access management.\n    resources:\n    - path: /v1/connections\n  \
  \    name: connections\n      description: Remote desktop connection management\n      operations:\n      - method: GET\n        name: list-connections\n        description: List all remote desktop connections\n        call: guacamole-rest.list-connections\n        with:\n          dataSource: rest.dataSource\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-connection\n        description: Create a new remote desktop connection\n        call: guacamole-rest.create-connection\n        with:\n          dataSource: rest.dataSource\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/users\n      name: users\n      description: User account management\n      operations:\n      - method: GET\n        name: list-users\n        description: List all Guacamole users\n        call: guacamole-rest.list-users\n        with:\n          dataSource: rest.dataSource\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /v1/sessions\n      name: sessions\n      description: Active session monitoring\n      operations:\n      - method: GET\n        name: list-active-sessions\n        description: List all active remote desktop sessions\n        call: guacamole-rest.list-active-connections\n        with:\n          dataSource: rest.dataSource\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: guacamole-access-mcp\n    transport: http\n    description: MCP server for AI-assisted Apache Guacamole remote access management.\n    tools:\n    - name: list-remote-connections\n      description: List all configured remote desktop connections in Guacamole\n      hints:\n        readOnly: true\n        openWorld: true\n      call: guacamole-rest.list-connections\n      with:\n        dataSource: tools.dataSource\n      outputParameters:\n      - type: object\n        mapping: $.\n    -\
  \ name: create-remote-connection\n      description: Create a new remote desktop connection in Guacamole\n      hints:\n        readOnly: false\n        destructive: false\n      call: guacamole-rest.create-connection\n      with:\n        dataSource: tools.dataSource\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-guacamole-users\n      description: List all Guacamole user accounts\n      hints:\n        readOnly: true\n        openWorld: true\n      call: guacamole-rest.list-users\n      with:\n        dataSource: tools.dataSource\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-active-sessions\n      description: List all currently active remote desktop sessions\n      hints:\n        readOnly: true\n        openWorld: true\n      call: guacamole-rest.list-active-connections\n      with:\n        dataSource: tools.dataSource\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-guacamole-user\n\
  \      description: Create a new user account in Guacamole\n      hints:\n        readOnly: false\n        destructive: false\n      call: guacamole-rest.create-user\n      with:\n        dataSource: tools.dataSource\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/apache-guacamole/refs/heads/main/capabilities/guacamole-remote-access.yaml
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
