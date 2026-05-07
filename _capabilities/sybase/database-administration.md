---
categories: []
consumed_apis: []
description: Unified database administration capability for SAP Adaptive Server Enterprise. Enables DBAs and platform teams to monitor server health, manage databases, track performance, administer users, and execute backup operations via REST and MCP interfaces.
layout: capability
name: Sybase ASE Database Administration
operations:
- description: List ASE Servers
  method: GET
  name: list-servers
  path: /v1/servers
- description: Get Server Details
  method: GET
  name: get-server
  path: /v1/servers/{serverId}
- description: Get Server Status
  method: GET
  name: get-server-status
  path: /v1/servers/{serverId}/status
- description: List Databases
  method: GET
  name: list-databases
  path: /v1/servers/{serverId}/databases
- description: Create a Database
  method: POST
  name: create-database
  path: /v1/servers/{serverId}/databases
- description: Get Database Details
  method: GET
  name: get-database
  path: /v1/servers/{serverId}/databases/{databaseName}
- description: Get Performance Metrics
  method: GET
  name: get-performance-metrics
  path: /v1/servers/{serverId}/performance
- description: Get Cache Performance Metrics
  method: GET
  name: get-cache-metrics
  path: /v1/servers/{serverId}/performance/cache
- description: Get Lock Activity Metrics
  method: GET
  name: get-lock-metrics
  path: /v1/servers/{serverId}/performance/locks
- description: List Backup History
  method: GET
  name: list-backups
  path: /v1/servers/{serverId}/backups
- description: Initiate a Database Backup
  method: POST
  name: create-backup
  path: /v1/servers/{serverId}/backups
- description: Get Server Configuration
  method: GET
  name: get-configuration
  path: /v1/servers/{serverId}/configuration
personas: []
provider_name: Sybase
provider_slug: sybase
search_terms:
- database backup management
- get cache metrics
- create database
- create a database
- sybase ase
- get lock contention statistics, deadlock counts, and wait times
- get performance metrics
- list backup history with status and size for databases on a server
- get cache performance metrics
- get version, status, host, port, and configuration summary for a server
- get server details
- sap ase server management
- cache performance statistics
- get server status
- get lock metrics
- create a new database on a sap ase server
- monitoring
- database management
- get lock activity metrics
- list databases
- list all databases with status, size, and owner information
- sap
- sybase
- get cpu, i/o, tps, network, and process metrics for a server
- get database
- initiate a database backup
- server operational status
- list servers
- sql
- administration
- get real-time cpu, memory, active connections, and uptime
- get configuration
- backup
- get all server configuration parameters (sp_configure equivalent)
- get server
- get database details including data usage, log usage, and configuration
- list ase servers
- get data cache and procedure cache hit ratios for all named caches
- initiate a full, transaction log, or incremental database backup
- single server information
- enterprise
- lock contention statistics
- list backups
- get server configuration
- database
- list backup history
- performance
- server performance metrics
- get database details
- server configuration (sp_configure)
- database details and space usage
- create backup
- list all available sap ase server instances
slug: database-administration
source_filename: database-administration.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Sybase ASE Database Administration\n  description: Unified database administration capability for SAP Adaptive Server Enterprise. Enables DBAs and platform teams\n    to monitor server health, manage databases, track performance, administer users, and execute backup operations via REST\n    and MCP interfaces.\n  tags:\n  - Administration\n  - Backup\n  - Database Management\n  - Monitoring\n  - Performance\n  - SAP\n  - Sybase\n  - Sybase ASE\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SYBASE_USERNAME: SYBASE_USERNAME\n    SYBASE_PASSWORD: SYBASE_PASSWORD\ncapability:\n  consumes:\n  - type: http\n    namespace: sybase-ase\n    baseUri: https://{server}:{port}/ase/v1\n    description: SAP ASE REST API for database administration and monitoring\n    authentication:\n      type: basic\n      username: '{{SYBASE_USERNAME}}'\n      password: '{{SYBASE_PASSWORD}}'\n    resources:\n    - name:\
  \ servers\n      path: /servers\n      description: SAP ASE server management\n      operations:\n      - name: list-servers\n        method: GET\n        description: List ASE Servers\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: server-detail\n      path: /servers/{serverId}\n      description: Individual server operations\n      operations:\n      - name: get-server\n        method: GET\n        description: Get Server Details\n        inputParameters:\n        - name: serverId\n          in: path\n          type: string\n          required: true\n          description: SAP ASE server ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: server-status\n      path: /servers/{serverId}/status\n      description: Server operational status\n      operations:\n      - name: get-server-status\n        method:\
  \ GET\n        description: Get Server Status\n        inputParameters:\n        - name: serverId\n          in: path\n          type: string\n          required: true\n          description: SAP ASE server ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: databases\n      path: /servers/{serverId}/databases\n      description: Database management\n      operations:\n      - name: list-databases\n        method: GET\n        description: List Databases\n        inputParameters:\n        - name: serverId\n          in: path\n          type: string\n          required: true\n          description: SAP ASE server ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-database\n        method: POST\n        description: Create a Database\n        inputParameters:\n        - name: serverId\n          in:\
  \ path\n          type: string\n          required: true\n          description: SAP ASE server ID\n        - name: name\n          in: body\n          type: string\n          required: true\n          description: Database name\n        - name: deviceName\n          in: body\n          type: string\n          required: true\n          description: Storage device name\n        - name: sizeMB\n          in: body\n          type: number\n          required: true\n          description: Initial size in MB\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: database-detail\n      path: /servers/{serverId}/databases/{databaseName}\n      description: Single database details\n      operations:\n      - name: get-database\n        method: GET\n        description: Get Database Details\n        inputParameters:\n        - name: serverId\n          in: path\n          type: string\n          required: true\n\
  \          description: SAP ASE server ID\n        - name: databaseName\n          in: path\n          type: string\n          required: true\n          description: Database name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: performance\n      path: /servers/{serverId}/performance\n      description: Performance metrics\n      operations:\n      - name: get-performance-metrics\n        method: GET\n        description: Get Performance Metrics\n        inputParameters:\n        - name: serverId\n          in: path\n          type: string\n          required: true\n          description: SAP ASE server ID\n        - name: interval\n          in: query\n          type: integer\n          required: false\n          description: Sampling interval in seconds (10-3600)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n   \
  \ - name: cache-metrics\n      path: /servers/{serverId}/performance/cache\n      description: Cache performance statistics\n      operations:\n      - name: get-cache-metrics\n        method: GET\n        description: Get Cache Performance Metrics\n        inputParameters:\n        - name: serverId\n          in: path\n          type: string\n          required: true\n          description: SAP ASE server ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: lock-metrics\n      path: /servers/{serverId}/performance/locks\n      description: Lock management statistics\n      operations:\n      - name: get-lock-metrics\n        method: GET\n        description: Get Lock Activity Metrics\n        inputParameters:\n        - name: serverId\n          in: path\n          type: string\n          required: true\n          description: SAP ASE server ID\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: logins\n      path: /servers/{serverId}/logins\n      description: Server login management\n      operations:\n      - name: list-logins\n        method: GET\n        description: List Server Logins\n        inputParameters:\n        - name: serverId\n          in: path\n          type: string\n          required: true\n          description: SAP ASE server ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-login\n        method: POST\n        description: Create a Server Login\n        inputParameters:\n        - name: serverId\n          in: path\n          type: string\n          required: true\n          description: SAP ASE server ID\n        - name: name\n          in: body\n          type: string\n          required: true\n          description: Login name\n        - name: password\n          in: body\n\
  \          type: string\n          required: true\n          description: Login password\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: backups\n      path: /servers/{serverId}/backups\n      description: Backup operations\n      operations:\n      - name: list-backups\n        method: GET\n        description: List Backup History\n        inputParameters:\n        - name: serverId\n          in: path\n          type: string\n          required: true\n          description: SAP ASE server ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-backup\n        method: POST\n        description: Initiate a Database Backup\n        inputParameters:\n        - name: serverId\n          in: path\n          type: string\n          required: true\n          description: SAP ASE server ID\n        - name: databaseName\n\
  \          in: body\n          type: string\n          required: true\n          description: Database to back up\n        - name: type\n          in: body\n          type: string\n          required: true\n          description: 'Backup type: full, transaction_log, incremental'\n        - name: deviceName\n          in: body\n          type: string\n          required: true\n          description: Backup device path\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: devices\n      path: /servers/{serverId}/devices\n      description: Database device management\n      operations:\n      - name: list-devices\n        method: GET\n        description: List Database Devices\n        inputParameters:\n        - name: serverId\n          in: path\n          type: string\n          required: true\n          description: SAP ASE server ID\n        outputRawFormat: json\n        outputParameters:\n       \
  \ - name: result\n          type: object\n          value: $.\n    - name: configuration\n      path: /servers/{serverId}/configuration\n      description: Server configuration management\n      operations:\n      - name: get-configuration\n        method: GET\n        description: Get Server Configuration\n        inputParameters:\n        - name: serverId\n          in: path\n          type: string\n          required: true\n          description: SAP ASE server ID\n        - name: group\n          in: query\n          type: string\n          required: false\n          description: Filter by configuration group\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-configuration\n        method: PUT\n        description: Update Server Configuration\n        inputParameters:\n        - name: serverId\n          in: path\n          type: string\n          required: true\n          description:\
  \ SAP ASE server ID\n        - name: parameters\n          in: body\n          type: array\n          required: true\n          description: Configuration parameters to update\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: sybase-dba-api\n    description: Unified REST API for SAP ASE database administration.\n    resources:\n    - path: /v1/servers\n      name: servers\n      description: SAP ASE server management\n      operations:\n      - method: GET\n        name: list-servers\n        description: List ASE Servers\n        call: sybase-ase.list-servers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/servers/{serverId}\n      name: server-detail\n      description: Single server information\n      operations:\n      - method: GET\n        name: get-server\n        description: Get Server Details\n    \
  \    call: sybase-ase.get-server\n        with:\n          serverId: rest.serverId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/servers/{serverId}/status\n      name: server-status\n      description: Server operational status\n      operations:\n      - method: GET\n        name: get-server-status\n        description: Get Server Status\n        call: sybase-ase.get-server-status\n        with:\n          serverId: rest.serverId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/servers/{serverId}/databases\n      name: databases\n      description: Database management\n      operations:\n      - method: GET\n        name: list-databases\n        description: List Databases\n        call: sybase-ase.list-databases\n        with:\n          serverId: rest.serverId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-database\n        description:\
  \ Create a Database\n        call: sybase-ase.create-database\n        with:\n          serverId: rest.serverId\n          name: rest.name\n          deviceName: rest.deviceName\n          sizeMB: rest.sizeMB\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/servers/{serverId}/databases/{databaseName}\n      name: database-detail\n      description: Database details and space usage\n      operations:\n      - method: GET\n        name: get-database\n        description: Get Database Details\n        call: sybase-ase.get-database\n        with:\n          serverId: rest.serverId\n          databaseName: rest.databaseName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/servers/{serverId}/performance\n      name: performance\n      description: Server performance metrics\n      operations:\n      - method: GET\n        name: get-performance-metrics\n        description: Get Performance Metrics\n        call:\
  \ sybase-ase.get-performance-metrics\n        with:\n          serverId: rest.serverId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/servers/{serverId}/performance/cache\n      name: cache-metrics\n      description: Cache performance statistics\n      operations:\n      - method: GET\n        name: get-cache-metrics\n        description: Get Cache Performance Metrics\n        call: sybase-ase.get-cache-metrics\n        with:\n          serverId: rest.serverId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/servers/{serverId}/performance/locks\n      name: lock-metrics\n      description: Lock contention statistics\n      operations:\n      - method: GET\n        name: get-lock-metrics\n        description: Get Lock Activity Metrics\n        call: sybase-ase.get-lock-metrics\n        with:\n          serverId: rest.serverId\n        outputParameters:\n        - type: object\n          mapping: $.\n\
  \    - path: /v1/servers/{serverId}/backups\n      name: backups\n      description: Database backup management\n      operations:\n      - method: GET\n        name: list-backups\n        description: List Backup History\n        call: sybase-ase.list-backups\n        with:\n          serverId: rest.serverId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-backup\n        description: Initiate a Database Backup\n        call: sybase-ase.create-backup\n        with:\n          serverId: rest.serverId\n          databaseName: rest.databaseName\n          type: rest.type\n          deviceName: rest.deviceName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/servers/{serverId}/configuration\n      name: configuration\n      description: Server configuration (sp_configure)\n      operations:\n      - method: GET\n        name: get-configuration\n        description: Get Server Configuration\n\
  \        call: sybase-ase.get-configuration\n        with:\n          serverId: rest.serverId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: sybase-dba-mcp\n    transport: http\n    description: MCP server for AI-assisted SAP ASE database administration.\n    tools:\n    - name: list-servers\n      description: List all available SAP ASE server instances\n      hints:\n        readOnly: true\n        idempotent: true\n      call: sybase-ase.list-servers\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-server\n      description: Get version, status, host, port, and configuration summary for a server\n      hints:\n        readOnly: true\n        idempotent: true\n      call: sybase-ase.get-server\n      with:\n        serverId: tools.serverId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-server-status\n      description: Get real-time CPU,\
  \ memory, active connections, and uptime\n      hints:\n        readOnly: true\n        idempotent: true\n      call: sybase-ase.get-server-status\n      with:\n        serverId: tools.serverId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-databases\n      description: List all databases with status, size, and owner information\n      hints:\n        readOnly: true\n        idempotent: true\n      call: sybase-ase.list-databases\n      with:\n        serverId: tools.serverId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-database\n      description: Get database details including data usage, log usage, and configuration\n      hints:\n        readOnly: true\n        idempotent: true\n      call: sybase-ase.get-database\n      with:\n        serverId: tools.serverId\n        databaseName: tools.databaseName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-database\n     \
  \ description: Create a new database on a SAP ASE server\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: sybase-ase.create-database\n      with:\n        serverId: tools.serverId\n        name: tools.name\n        deviceName: tools.deviceName\n        sizeMB: tools.sizeMB\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-performance-metrics\n      description: Get CPU, I/O, TPS, network, and process metrics for a server\n      hints:\n        readOnly: true\n        idempotent: true\n      call: sybase-ase.get-performance-metrics\n      with:\n        serverId: tools.serverId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-cache-metrics\n      description: Get data cache and procedure cache hit ratios for all named caches\n      hints:\n        readOnly: true\n        idempotent: true\n      call: sybase-ase.get-cache-metrics\n      with:\n        serverId:\
  \ tools.serverId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-lock-metrics\n      description: Get lock contention statistics, deadlock counts, and wait times\n      hints:\n        readOnly: true\n        idempotent: true\n      call: sybase-ase.get-lock-metrics\n      with:\n        serverId: tools.serverId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-backups\n      description: List backup history with status and size for databases on a server\n      hints:\n        readOnly: true\n        idempotent: true\n      call: sybase-ase.list-backups\n      with:\n        serverId: tools.serverId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-backup\n      description: Initiate a full, transaction log, or incremental database backup\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: sybase-ase.create-backup\n      with:\n\
  \        serverId: tools.serverId\n        databaseName: tools.databaseName\n        type: tools.type\n        deviceName: tools.deviceName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-configuration\n      description: Get all server configuration parameters (sp_configure equivalent)\n      hints:\n        readOnly: true\n        idempotent: true\n      call: sybase-ase.get-configuration\n      with:\n        serverId: tools.serverId\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/sybase/refs/heads/main/capabilities/database-administration.yaml
tags:
- Administration
- Backup
- Database Management
- Monitoring
- Performance
- SAP
- Sybase
- Sybase ASE
tools:
- description: List all available SAP ASE server instances
  hints:
    idempotent: true
    readOnly: true
  name: list-servers
- description: Get version, status, host, port, and configuration summary for a server
  hints:
    idempotent: true
    readOnly: true
  name: get-server
- description: Get real-time CPU, memory, active connections, and uptime
  hints:
    idempotent: true
    readOnly: true
  name: get-server-status
- description: List all databases with status, size, and owner information
  hints:
    idempotent: true
    readOnly: true
  name: list-databases
- description: Get database details including data usage, log usage, and configuration
  hints:
    idempotent: true
    readOnly: true
  name: get-database
- description: Create a new database on a SAP ASE server
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-database
- description: Get CPU, I/O, TPS, network, and process metrics for a server
  hints:
    idempotent: true
    readOnly: true
  name: get-performance-metrics
- description: Get data cache and procedure cache hit ratios for all named caches
  hints:
    idempotent: true
    readOnly: true
  name: get-cache-metrics
- description: Get lock contention statistics, deadlock counts, and wait times
  hints:
    idempotent: true
    readOnly: true
  name: get-lock-metrics
- description: List backup history with status and size for databases on a server
  hints:
    idempotent: true
    readOnly: true
  name: list-backups
- description: Initiate a full, transaction log, or incremental database backup
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-backup
- description: Get all server configuration parameters (sp_configure equivalent)
  hints:
    idempotent: true
    readOnly: true
  name: get-configuration
---
