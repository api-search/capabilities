---
categories: []
consumed_apis: []
description: Unified workflow capability for managing and monitoring a Squid caching proxy. Combines cache statistics, connection monitoring, configuration management, and operational commands into a single workflow interface for network administrators and DevOps engineers managing proxy infrastructure.
layout: capability
name: Squid Proxy Management
operations:
- description: Get general Squid cache information
  method: GET
  name: get-cache-info
  path: /v1/cache/info
- description: Get detailed cache performance counters
  method: GET
  name: get-cache-counters
  path: /v1/cache/counters
- description: Get 5-minute rolling cache statistics
  method: GET
  name: get-5min-statistics
  path: /v1/cache/statistics/5min
- description: Get 60-minute rolling cache statistics
  method: GET
  name: get-60min-statistics
  path: /v1/cache/statistics/60min
- description: Get cache utilization and capacity
  method: GET
  name: get-cache-utilization
  path: /v1/cache/utilization
- description: Get memory allocation statistics
  method: GET
  name: get-memory-usage
  path: /v1/cache/memory
- description: Get all active connections
  method: GET
  name: get-connections
  path: /v1/connections
- description: List active HTTP requests being processed
  method: GET
  name: get-active-requests
  path: /v1/requests
- description: Get current Squid configuration
  method: GET
  name: get-cache-config
  path: /v1/config
- description: Get all ACLs and their membership
  method: GET
  name: get-acl-list
  path: /v1/acls
- description: List cached objects
  method: GET
  name: get-cache-objects
  path: /v1/objects
- description: Reload Squid configuration
  method: POST
  name: reconfigure-squid
  path: /v1/operations/reconfigure
- description: Rotate Squid log files
  method: POST
  name: rotate-log-files
  path: /v1/operations/rotate-logs
personas: []
provider_name: Squid
provider_slug: squid
search_terms:
- active http requests
- get cache utilization
- rotate squid log files
- web cache
- get all active client and server connections with state and bytes
- cached objects
- trigger squid to reload its configuration file without restart
- 60-minute rolling statistics
- get 60min statistics
- get memory allocation statistics
- cache information and general statistics
- access control lists
- get general squid cache information
- squid
- get active requests
- reconfigure squid
- cache utilization metrics
- get all active connections
- rotate log files
- cache configuration
- get all defined squid acls for access control auditing
- 5-minute rolling statistics
- get cache config
- get 60-minute rolling averages for cache activity
- get current squid configuration
- get current cache utilization, object count, and capacity
- access control
- cache management
- caching proxy
- content filtering
- get acl list
- performance counters
- get cache info
- list active http requests being processed
- get 60-minute rolling cache statistics
- list cached objects
- active connections
- get 5-minute rolling averages for cache activity
- get memory usage
- get detailed cache performance counters
- http proxy
- list all currently active http requests being processed by squid
- get general squid cache information including version, uptime, and basic statistics
- trigger squid log file rotation
- get cache counters
- memory usage statistics
- get current squid runtime configuration
- network administration
- get connections
- get squid memory pool and allocation statistics
- get 5min statistics
- get cache utilization and capacity
- get all acls and their membership
- get detailed squid performance counters including hit rates and byte counts
- get 5-minute rolling cache statistics
- reload squid configuration
- list objects stored in the squid cache with optional url pattern filter
- get cache objects
- proxy
slug: proxy-management
source_filename: proxy-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Squid Proxy Management\n  description: Unified workflow capability for managing and monitoring a Squid caching proxy. Combines cache statistics, connection\n    monitoring, configuration management, and operational commands into a single workflow interface for network administrators\n    and DevOps engineers managing proxy infrastructure.\n  tags:\n  - Squid\n  - Caching Proxy\n  - HTTP Proxy\n  - Network Administration\n  - Cache Management\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SQUID_CACHEMGR_PASSWORD: SQUID_CACHEMGR_PASSWORD\ncapability:\n  consumes:\n  - type: http\n    namespace: squid-cache-manager\n    baseUri: http://localhost:3128/squid-internal-mgr\n    description: Squid cache manager internal management interface\n    authentication:\n      type: basic\n      username: cachemgr\n      password: '{{SQUID_CACHEMGR_PASSWORD}}'\n    resources:\n    - name: cache-statistics\n \
  \     path: /info\n      description: Cache information and statistics\n      operations:\n      - name: get-cache-info\n        method: GET\n        description: Get general cache information\n        outputRawFormat: text\n        outputParameters:\n        - name: result\n          type: string\n          value: $.\n    - name: counters\n      path: /counters\n      description: Performance counters\n      operations:\n      - name: get-cache-counters\n        method: GET\n        description: Get detailed performance counters\n        outputRawFormat: text\n        outputParameters:\n        - name: result\n          type: string\n          value: $.\n    - name: statistics-5min\n      path: /5min\n      description: 5-minute rolling statistics\n      operations:\n      - name: get-5min-statistics\n        method: GET\n        description: Get 5-minute rolling statistics\n        outputRawFormat: text\n        outputParameters:\n        - name: result\n          type: string\n    \
  \      value: $.\n    - name: statistics-60min\n      path: /60min\n      description: 60-minute rolling statistics\n      operations:\n      - name: get-60min-statistics\n        method: GET\n        description: Get 60-minute rolling statistics\n        outputRawFormat: text\n        outputParameters:\n        - name: result\n          type: string\n          value: $.\n    - name: utilization\n      path: /utilization\n      description: Cache utilization metrics\n      operations:\n      - name: get-cache-utilization\n        method: GET\n        description: Get cache utilization statistics\n        outputRawFormat: text\n        outputParameters:\n        - name: result\n          type: string\n          value: $.\n    - name: memory\n      path: /mem\n      description: Memory usage statistics\n      operations:\n      - name: get-memory-usage\n        method: GET\n        description: Get memory allocation and pool statistics\n        outputRawFormat: text\n        outputParameters:\n\
  \        - name: result\n          type: string\n          value: $.\n    - name: active-requests\n      path: /active_requests\n      description: Active HTTP requests\n      operations:\n      - name: get-active-requests\n        method: GET\n        description: List all currently active HTTP requests\n        outputRawFormat: text\n        outputParameters:\n        - name: result\n          type: string\n          value: $.\n    - name: connections\n      path: /connections\n      description: Active connections\n      operations:\n      - name: get-connections\n        method: GET\n        description: Get all active client and server connections\n        outputRawFormat: text\n        outputParameters:\n        - name: result\n          type: string\n          value: $.\n    - name: configuration\n      path: /config\n      description: Squid configuration\n      operations:\n      - name: get-cache-config\n        method: GET\n        description: Get current Squid configuration\n\
  \        outputRawFormat: text\n        outputParameters:\n        - name: result\n          type: string\n          value: $.\n    - name: acl\n      path: /acl_list\n      description: Access control lists\n      operations:\n      - name: get-acl-list\n        method: GET\n        description: Get all defined ACLs and their membership\n        outputRawFormat: text\n        outputParameters:\n        - name: result\n          type: string\n          value: $.\n    - name: objects\n      path: /objects\n      description: Cached objects\n      operations:\n      - name: get-cache-objects\n        method: GET\n        description: List objects currently stored in the cache\n        inputParameters:\n        - name: pattern\n          in: query\n          type: string\n          required: false\n          description: URL pattern filter\n        outputRawFormat: text\n        outputParameters:\n        - name: result\n          type: string\n          value: $.\n    - name: operations\n\
  \      path: /reconfigure\n      description: Operational commands\n      operations:\n      - name: reconfigure-squid\n        method: GET\n        description: Trigger Squid to reload configuration\n        outputRawFormat: text\n        outputParameters:\n        - name: result\n          type: string\n          value: $.\n      - name: rotate-log-files\n        method: GET\n        description: Trigger Squid log file rotation\n        outputRawFormat: text\n        outputParameters:\n        - name: result\n          type: string\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: squid-proxy-management-api\n    description: Unified REST API for Squid proxy management and monitoring.\n    resources:\n    - path: /v1/cache/info\n      name: cache-info\n      description: Cache information and general statistics\n      operations:\n      - method: GET\n        name: get-cache-info\n        description: Get general Squid cache information\n        call: squid-cache-manager.get-cache-info\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/cache/counters\n      name: cache-counters\n      description: Performance counters\n      operations:\n      - method: GET\n        name: get-cache-counters\n        description: Get detailed cache performance counters\n        call: squid-cache-manager.get-cache-counters\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/cache/statistics/5min\n      name: statistics-5min\n      description: 5-minute rolling statistics\n      operations:\n      - method: GET\n        name: get-5min-statistics\n        description: Get 5-minute rolling cache statistics\n        call: squid-cache-manager.get-5min-statistics\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/cache/statistics/60min\n      name: statistics-60min\n      description: 60-minute rolling statistics\n      operations:\n      - method: GET\n        name: get-60min-statistics\n\
  \        description: Get 60-minute rolling cache statistics\n        call: squid-cache-manager.get-60min-statistics\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/cache/utilization\n      name: cache-utilization\n      description: Cache utilization metrics\n      operations:\n      - method: GET\n        name: get-cache-utilization\n        description: Get cache utilization and capacity\n        call: squid-cache-manager.get-cache-utilization\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/cache/memory\n      name: memory\n      description: Memory usage statistics\n      operations:\n      - method: GET\n        name: get-memory-usage\n        description: Get memory allocation statistics\n        call: squid-cache-manager.get-memory-usage\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/connections\n      name: connections\n      description: Active connections\n\
  \      operations:\n      - method: GET\n        name: get-connections\n        description: Get all active connections\n        call: squid-cache-manager.get-connections\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/requests\n      name: active-requests\n      description: Active HTTP requests\n      operations:\n      - method: GET\n        name: get-active-requests\n        description: List active HTTP requests being processed\n        call: squid-cache-manager.get-active-requests\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/config\n      name: configuration\n      description: Cache configuration\n      operations:\n      - method: GET\n        name: get-cache-config\n        description: Get current Squid configuration\n        call: squid-cache-manager.get-cache-config\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/acls\n      name: acl-list\n  \
  \    description: Access control lists\n      operations:\n      - method: GET\n        name: get-acl-list\n        description: Get all ACLs and their membership\n        call: squid-cache-manager.get-acl-list\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/objects\n      name: cached-objects\n      description: Cached objects\n      operations:\n      - method: GET\n        name: get-cache-objects\n        description: List cached objects\n        call: squid-cache-manager.get-cache-objects\n        with:\n          pattern: rest.pattern\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/operations/reconfigure\n      name: reconfigure\n      description: Reconfigure Squid\n      operations:\n      - method: POST\n        name: reconfigure-squid\n        description: Reload Squid configuration\n        call: squid-cache-manager.reconfigure-squid\n        outputParameters:\n        - type: object\n     \
  \     mapping: $.\n    - path: /v1/operations/rotate-logs\n      name: rotate-logs\n      description: Rotate log files\n      operations:\n      - method: POST\n        name: rotate-log-files\n        description: Rotate Squid log files\n        call: squid-cache-manager.rotate-log-files\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: squid-proxy-management-mcp\n    transport: http\n    description: MCP server for AI-assisted Squid proxy management and troubleshooting.\n    tools:\n    - name: get-cache-info\n      description: Get general Squid cache information including version, uptime, and basic statistics\n      hints:\n        readOnly: true\n        idempotent: true\n      call: squid-cache-manager.get-cache-info\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-cache-counters\n      description: Get detailed Squid performance counters including hit rates and byte counts\n\
  \      hints:\n        readOnly: true\n        idempotent: true\n      call: squid-cache-manager.get-cache-counters\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-5min-statistics\n      description: Get 5-minute rolling averages for cache activity\n      hints:\n        readOnly: true\n        idempotent: true\n      call: squid-cache-manager.get-5min-statistics\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-60min-statistics\n      description: Get 60-minute rolling averages for cache activity\n      hints:\n        readOnly: true\n        idempotent: true\n      call: squid-cache-manager.get-60min-statistics\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-cache-utilization\n      description: Get current cache utilization, object count, and capacity\n      hints:\n        readOnly: true\n        idempotent: true\n      call: squid-cache-manager.get-cache-utilization\n     \
  \ outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-memory-usage\n      description: Get Squid memory pool and allocation statistics\n      hints:\n        readOnly: true\n        idempotent: true\n      call: squid-cache-manager.get-memory-usage\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-active-requests\n      description: List all currently active HTTP requests being processed by Squid\n      hints:\n        readOnly: true\n        idempotent: false\n      call: squid-cache-manager.get-active-requests\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-connections\n      description: Get all active client and server connections with state and bytes\n      hints:\n        readOnly: true\n        idempotent: false\n      call: squid-cache-manager.get-connections\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-cache-config\n      description: Get current\
  \ Squid runtime configuration\n      hints:\n        readOnly: true\n        idempotent: true\n      call: squid-cache-manager.get-cache-config\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-acl-list\n      description: Get all defined Squid ACLs for access control auditing\n      hints:\n        readOnly: true\n        idempotent: true\n      call: squid-cache-manager.get-acl-list\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-cache-objects\n      description: List objects stored in the Squid cache with optional URL pattern filter\n      hints:\n        readOnly: true\n        idempotent: true\n      call: squid-cache-manager.get-cache-objects\n      with:\n        pattern: tools.pattern\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: reconfigure-squid\n      description: Trigger Squid to reload its configuration file without restart\n      hints:\n        readOnly: false\n   \
  \     destructive: false\n        idempotent: true\n      call: squid-cache-manager.reconfigure-squid\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: rotate-log-files\n      description: Trigger Squid log file rotation\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: squid-cache-manager.rotate-log-files\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/squid/refs/heads/main/capabilities/proxy-management.yaml
tags:
- Squid
- Caching Proxy
- HTTP Proxy
- Network Administration
- Cache Management
tools:
- description: Get general Squid cache information including version, uptime, and basic statistics
  hints:
    idempotent: true
    readOnly: true
  name: get-cache-info
- description: Get detailed Squid performance counters including hit rates and byte counts
  hints:
    idempotent: true
    readOnly: true
  name: get-cache-counters
- description: Get 5-minute rolling averages for cache activity
  hints:
    idempotent: true
    readOnly: true
  name: get-5min-statistics
- description: Get 60-minute rolling averages for cache activity
  hints:
    idempotent: true
    readOnly: true
  name: get-60min-statistics
- description: Get current cache utilization, object count, and capacity
  hints:
    idempotent: true
    readOnly: true
  name: get-cache-utilization
- description: Get Squid memory pool and allocation statistics
  hints:
    idempotent: true
    readOnly: true
  name: get-memory-usage
- description: List all currently active HTTP requests being processed by Squid
  hints:
    idempotent: false
    readOnly: true
  name: get-active-requests
- description: Get all active client and server connections with state and bytes
  hints:
    idempotent: false
    readOnly: true
  name: get-connections
- description: Get current Squid runtime configuration
  hints:
    idempotent: true
    readOnly: true
  name: get-cache-config
- description: Get all defined Squid ACLs for access control auditing
  hints:
    idempotent: true
    readOnly: true
  name: get-acl-list
- description: List objects stored in the Squid cache with optional URL pattern filter
  hints:
    idempotent: true
    readOnly: true
  name: get-cache-objects
- description: Trigger Squid to reload its configuration file without restart
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: reconfigure-squid
- description: Trigger Squid log file rotation
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: rotate-log-files
---
