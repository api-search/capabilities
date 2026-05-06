---
categories: []
consumed_apis: []
description: The Envoy Admin API provides local administrative access to a running Envoy proxy instance. It exposes endpoints for inspecting configuration, checking health, viewing statistics, managing log levels, and controlling the runtime state of the proxy. The Admin API is typically bound to a local interface (default port 9901) and is not intended for external exposure in production environments.
layout: capability
name: Envoy Admin API
operations:
- description: Envoy Get server information
  method: GET
  name: getserverinfo
  path: /server_info
- description: Envoy Get upstream cluster information
  method: GET
  name: getclusters
  path: /clusters
- description: Dump current Envoy configuration
  method: GET
  name: getconfigdump
  path: /config_dump
- description: Envoy Get listener information
  method: GET
  name: getlisteners
  path: /listeners
- description: Get Envoy statistics
  method: GET
  name: getstats
  path: /stats
- description: Envoy Get statistics in Prometheus format
  method: GET
  name: getstatsprometheus
  path: /stats/prometheus
- description: Envoy Get recently looked-up stat names
  method: GET
  name: getrecentlookups
  path: /stats/recentlookups
- description: Envoy Force health check failure
  method: POST
  name: sethealthcheckfail
  path: /health_check/fail
- description: Envoy Restore health check passing
  method: POST
  name: sethealthcheckok
  path: /health_check/ok
- description: Envoy Get server readiness status
  method: GET
  name: getready
  path: /ready
- description: Envoy Get current log levels
  method: GET
  name: getlogging
  path: /logging
- description: Envoy Change log levels
  method: POST
  name: setlogging
  path: /logging
- description: Envoy Get runtime settings
  method: GET
  name: getruntime
  path: /runtime
- description: Envoy Modify runtime settings
  method: POST
  name: modifyruntime
  path: /runtime_modify
- description: Envoy Drain listeners
  method: POST
  name: drainlisteners
  path: /drain_listeners
- description: Shutdown Envoy server
  method: POST
  name: shutdownserver
  path: /quitquitquit
- description: Envoy Get TLS certificate information
  method: GET
  name: getcertificates
  path: /certs
- description: Envoy Get memory allocation information
  method: GET
  name: getmemory
  path: /memory
- description: Envoy Get hot restart compatibility version
  method: GET
  name: gethotrestartversion
  path: /hot_restart_version
- description: Envoy Reset all statistics counters
  method: POST
  name: resetcounters
  path: /reset_counters
personas: []
provider_name: Envoy
provider_slug: envoy
search_terms:
- getclusters
- envoy get listener information
- sethealthcheckok
- getready
- sethealthcheckfail
- getrecentlookups
- envoy drain listeners
- envoy get recently looked-up stat names
- envoy get tls certificate information
- service mesh
- getlisteners
- getruntime
- getlogging
- envoy
- envoy restore health check passing
- envoy get runtime settings
- getmemory
- gethotrestartversion
- envoy get hot restart compatibility version
- envoy get server readiness status
- envoy reset all statistics counters
- cloud native
- envoy get upstream cluster information
- modifyruntime
- envoy force health check failure
- getcertificates
- envoy get current log levels
- getserverinfo
- get envoy statistics
- api
- drainlisteners
- getstats
- dump current envoy configuration
- getconfigdump
- proxy
- shutdown envoy server
- shutdownserver
- envoy modify runtime settings
- setlogging
- getstatsprometheus
- resetcounters
- envoy get statistics in prometheus format
- load balancing
- envoy change log levels
- envoy get memory allocation information
- envoy get server information
slug: envoy-capability
source_filename: envoy-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Envoy Admin API\n  description: The Envoy Admin API provides local administrative access to a running Envoy proxy instance. It exposes endpoints\n    for inspecting configuration, checking health, viewing statistics, managing log levels, and controlling the runtime state\n    of the proxy. The Admin API is typically bound to a local interface (default port 9901) and is not intended for external\n    exposure in production environments.\n  tags:\n  - Envoy\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: envoy\n    baseUri: http://localhost:9901\n    description: Envoy Admin API HTTP API.\n    resources:\n    - name: server-info\n      path: /server_info\n      operations:\n      - name: getserverinfo\n        method: GET\n        description: Envoy Get server information\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n    - name: clusters\n      path: /clusters\n      operations:\n      - name: getclusters\n        method: GET\n        description: Envoy Get upstream cluster information\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: config-dump\n      path: /config_dump\n      operations:\n      - name: getconfigdump\n        method: GET\n        description: Dump current Envoy configuration\n        inputParameters:\n        - name: resource\n          in: query\n          type: string\n          description: Filter by resource type. Valid values include static_clusters, dynamic_active_clusters, static_listeners,\n            dynamic_active_listeners, dynamic_route_configs, stati\n        - name: name_regex\n          in: query\n          type: string\n          description: Filter resources by name using a regular expression pattern.\n        - name: include_eds\n          in:\
  \ query\n          type: boolean\n          description: Include EDS endpoint assignment data in the config dump.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: listeners\n      path: /listeners\n      operations:\n      - name: getlisteners\n        method: GET\n        description: Envoy Get listener information\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: stats\n      path: /stats\n      operations:\n      - name: getstats\n        method: GET\n        description: Get Envoy statistics\n        inputParameters:\n        - name: format\n          in: query\n          type: string\n          description: Output format for statistics data.\n        - name: filter\n          in: query\n          type: string\n          description: Regex pattern to filter stat names.\n        - name: type\n          in:\
  \ query\n          type: string\n          description: Filter statistics by type.\n        - name: usedonly\n          in: query\n          type: boolean\n          description: When true, only return statistics that have been written to at least once.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: stats-prometheus\n      path: /stats/prometheus\n      operations:\n      - name: getstatsprometheus\n        method: GET\n        description: Envoy Get statistics in Prometheus format\n        inputParameters:\n        - name: usedonly\n          in: query\n          type: boolean\n          description: When true, only return statistics that have been written to at least once.\n        - name: filter\n          in: query\n          type: string\n          description: Regex pattern to filter stat names.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n    - name: stats-recentlookups\n      path: /stats/recentlookups\n      operations:\n      - name: getrecentlookups\n        method: GET\n        description: Envoy Get recently looked-up stat names\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: health-check-fail\n      path: /health_check/fail\n      operations:\n      - name: sethealthcheckfail\n        method: POST\n        description: Envoy Force health check failure\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: health-check-ok\n      path: /health_check/ok\n      operations:\n      - name: sethealthcheckok\n        method: POST\n        description: Envoy Restore health check passing\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    -\
  \ name: ready\n      path: /ready\n      operations:\n      - name: getready\n        method: GET\n        description: Envoy Get server readiness status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: logging\n      path: /logging\n      operations:\n      - name: getlogging\n        method: GET\n        description: Envoy Get current log levels\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: setlogging\n        method: POST\n        description: Envoy Change log levels\n        inputParameters:\n        - name: level\n          in: query\n          type: string\n          description: Set log level for all loggers simultaneously. One of trace, debug, info, warning, error, critical,\n            or off.\n        - name: paths\n          in: query\n          type: string\n          description: Set log\
  \ level for a specific logger using logger_name:level format. Can be specified multiple times\n            for multiple loggers.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: runtime\n      path: /runtime\n      operations:\n      - name: getruntime\n        method: GET\n        description: Envoy Get runtime settings\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: runtime-modify\n      path: /runtime_modify\n      operations:\n      - name: modifyruntime\n        method: POST\n        description: Envoy Modify runtime settings\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: drain-listeners\n      path: /drain_listeners\n      operations:\n      - name: drainlisteners\n        method: POST\n        description: Envoy\
  \ Drain listeners\n        inputParameters:\n        - name: inboundonly\n          in: query\n          type: boolean\n          description: When true, only drain inbound listeners.\n        - name: graceful\n          in: query\n          type: boolean\n          description: When true, perform a graceful drain that allows time for connections to complete.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: quitquitquit\n      path: /quitquitquit\n      operations:\n      - name: shutdownserver\n        method: POST\n        description: Shutdown Envoy server\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: certs\n      path: /certs\n      operations:\n      - name: getcertificates\n        method: GET\n        description: Envoy Get TLS certificate information\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: memory\n      path: /memory\n      operations:\n      - name: getmemory\n        method: GET\n        description: Envoy Get memory allocation information\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: hot-restart-version\n      path: /hot_restart_version\n      operations:\n      - name: gethotrestartversion\n        method: GET\n        description: Envoy Get hot restart compatibility version\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: reset-counters\n      path: /reset_counters\n      operations:\n      - name: resetcounters\n        method: POST\n        description: Envoy Reset all statistics counters\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n       \
  \   value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: envoy-rest\n    description: REST adapter for Envoy Admin API.\n    resources:\n    - path: /server_info\n      name: getserverinfo\n      operations:\n      - method: GET\n        name: getserverinfo\n        description: Envoy Get server information\n        call: envoy.getserverinfo\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /clusters\n      name: getclusters\n      operations:\n      - method: GET\n        name: getclusters\n        description: Envoy Get upstream cluster information\n        call: envoy.getclusters\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /config_dump\n      name: getconfigdump\n      operations:\n      - method: GET\n        name: getconfigdump\n        description: Dump current Envoy configuration\n        call: envoy.getconfigdump\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /listeners\n      name: getlisteners\n      operations:\n      - method: GET\n        name: getlisteners\n        description: Envoy Get listener information\n        call: envoy.getlisteners\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /stats\n      name: getstats\n      operations:\n      - method: GET\n        name: getstats\n        description: Get Envoy statistics\n        call: envoy.getstats\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /stats/prometheus\n      name: getstatsprometheus\n      operations:\n      - method: GET\n        name: getstatsprometheus\n        description: Envoy Get statistics in Prometheus format\n        call: envoy.getstatsprometheus\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /stats/recentlookups\n      name: getrecentlookups\n      operations:\n      - method: GET\n        name: getrecentlookups\n        description:\
  \ Envoy Get recently looked-up stat names\n        call: envoy.getrecentlookups\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /health_check/fail\n      name: sethealthcheckfail\n      operations:\n      - method: POST\n        name: sethealthcheckfail\n        description: Envoy Force health check failure\n        call: envoy.sethealthcheckfail\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /health_check/ok\n      name: sethealthcheckok\n      operations:\n      - method: POST\n        name: sethealthcheckok\n        description: Envoy Restore health check passing\n        call: envoy.sethealthcheckok\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /ready\n      name: getready\n      operations:\n      - method: GET\n        name: getready\n        description: Envoy Get server readiness status\n        call: envoy.getready\n        outputParameters:\n        - type:\
  \ object\n          mapping: $.\n    - path: /logging\n      name: getlogging\n      operations:\n      - method: GET\n        name: getlogging\n        description: Envoy Get current log levels\n        call: envoy.getlogging\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /logging\n      name: setlogging\n      operations:\n      - method: POST\n        name: setlogging\n        description: Envoy Change log levels\n        call: envoy.setlogging\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /runtime\n      name: getruntime\n      operations:\n      - method: GET\n        name: getruntime\n        description: Envoy Get runtime settings\n        call: envoy.getruntime\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /runtime_modify\n      name: modifyruntime\n      operations:\n      - method: POST\n        name: modifyruntime\n        description: Envoy Modify runtime\
  \ settings\n        call: envoy.modifyruntime\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /drain_listeners\n      name: drainlisteners\n      operations:\n      - method: POST\n        name: drainlisteners\n        description: Envoy Drain listeners\n        call: envoy.drainlisteners\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /quitquitquit\n      name: shutdownserver\n      operations:\n      - method: POST\n        name: shutdownserver\n        description: Shutdown Envoy server\n        call: envoy.shutdownserver\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /certs\n      name: getcertificates\n      operations:\n      - method: GET\n        name: getcertificates\n        description: Envoy Get TLS certificate information\n        call: envoy.getcertificates\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /memory\n   \
  \   name: getmemory\n      operations:\n      - method: GET\n        name: getmemory\n        description: Envoy Get memory allocation information\n        call: envoy.getmemory\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /hot_restart_version\n      name: gethotrestartversion\n      operations:\n      - method: GET\n        name: gethotrestartversion\n        description: Envoy Get hot restart compatibility version\n        call: envoy.gethotrestartversion\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /reset_counters\n      name: resetcounters\n      operations:\n      - method: POST\n        name: resetcounters\n        description: Envoy Reset all statistics counters\n        call: envoy.resetcounters\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: envoy-mcp\n    transport: http\n    description: MCP adapter for Envoy Admin API for\
  \ AI agent use.\n    tools:\n    - name: getserverinfo\n      description: Envoy Get server information\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: envoy.getserverinfo\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getclusters\n      description: Envoy Get upstream cluster information\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: envoy.getclusters\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getconfigdump\n      description: Dump current Envoy configuration\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: envoy.getconfigdump\n      with:\n        resource: tools.resource\n        name_regex: tools.name_regex\n        include_eds: tools.include_eds\n      inputParameters:\n      - name: resource\n        type: string\n        description: Filter\
  \ by resource type. Valid values include static_clusters, dynamic_active_clusters, static_listeners,\n          dynamic_active_listeners, dynamic_route_configs, stati\n      - name: name_regex\n        type: string\n        description: Filter resources by name using a regular expression pattern.\n      - name: include_eds\n        type: boolean\n        description: Include EDS endpoint assignment data in the config dump.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getlisteners\n      description: Envoy Get listener information\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: envoy.getlisteners\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getstats\n      description: Get Envoy statistics\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: envoy.getstats\n      with:\n        format: tools.format\n        filter:\
  \ tools.filter\n        type: tools.type\n        usedonly: tools.usedonly\n      inputParameters:\n      - name: format\n        type: string\n        description: Output format for statistics data.\n      - name: filter\n        type: string\n        description: Regex pattern to filter stat names.\n      - name: type\n        type: string\n        description: Filter statistics by type.\n      - name: usedonly\n        type: boolean\n        description: When true, only return statistics that have been written to at least once.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getstatsprometheus\n      description: Envoy Get statistics in Prometheus format\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: envoy.getstatsprometheus\n      with:\n        usedonly: tools.usedonly\n        filter: tools.filter\n      inputParameters:\n      - name: usedonly\n        type: boolean\n        description: When\
  \ true, only return statistics that have been written to at least once.\n      - name: filter\n        type: string\n        description: Regex pattern to filter stat names.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getrecentlookups\n      description: Envoy Get recently looked-up stat names\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: envoy.getrecentlookups\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: sethealthcheckfail\n      description: Envoy Force health check failure\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: envoy.sethealthcheckfail\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: sethealthcheckok\n      description: Envoy Restore health check passing\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call:\
  \ envoy.sethealthcheckok\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getready\n      description: Envoy Get server readiness status\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: envoy.getready\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getlogging\n      description: Envoy Get current log levels\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: envoy.getlogging\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: setlogging\n      description: Envoy Change log levels\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: envoy.setlogging\n      with:\n        level: tools.level\n        paths: tools.paths\n      inputParameters:\n      - name: level\n        type: string\n        description: Set log level for all loggers\
  \ simultaneously. One of trace, debug, info, warning, error, critical, or\n          off.\n      - name: paths\n        type: string\n        description: Set log level for a specific logger using logger_name:level format. Can be specified multiple times for\n          multiple loggers.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getruntime\n      description: Envoy Get runtime settings\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: envoy.getruntime\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: modifyruntime\n      description: Envoy Modify runtime settings\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: envoy.modifyruntime\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: drainlisteners\n      description: Envoy Drain listeners\n      hints:\n        readOnly: false\n\
  \        destructive: false\n        idempotent: false\n      call: envoy.drainlisteners\n      with:\n        inboundonly: tools.inboundonly\n        graceful: tools.graceful\n      inputParameters:\n      - name: inboundonly\n        type: boolean\n        description: When true, only drain inbound listeners.\n      - name: graceful\n        type: boolean\n        description: When true, perform a graceful drain that allows time for connections to complete.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: shutdownserver\n      description: Shutdown Envoy server\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: envoy.shutdownserver\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcertificates\n      description: Envoy Get TLS certificate information\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: envoy.getcertificates\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getmemory\n      description: Envoy Get memory allocation information\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: envoy.getmemory\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: gethotrestartversion\n      description: Envoy Get hot restart compatibility version\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: envoy.gethotrestartversion\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: resetcounters\n      description: Envoy Reset all statistics counters\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: envoy.resetcounters\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/envoy/refs/heads/main/capabilities/envoy-capability.yaml
tags:
- Envoy
- API
tools:
- description: Envoy Get server information
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getserverinfo
- description: Envoy Get upstream cluster information
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getclusters
- description: Dump current Envoy configuration
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getconfigdump
- description: Envoy Get listener information
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getlisteners
- description: Get Envoy statistics
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getstats
- description: Envoy Get statistics in Prometheus format
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getstatsprometheus
- description: Envoy Get recently looked-up stat names
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getrecentlookups
- description: Envoy Force health check failure
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: sethealthcheckfail
- description: Envoy Restore health check passing
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: sethealthcheckok
- description: Envoy Get server readiness status
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getready
- description: Envoy Get current log levels
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getlogging
- description: Envoy Change log levels
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: setlogging
- description: Envoy Get runtime settings
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getruntime
- description: Envoy Modify runtime settings
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: modifyruntime
- description: Envoy Drain listeners
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: drainlisteners
- description: Shutdown Envoy server
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: shutdownserver
- description: Envoy Get TLS certificate information
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcertificates
- description: Envoy Get memory allocation information
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getmemory
- description: Envoy Get hot restart compatibility version
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gethotrestartversion
- description: Envoy Reset all statistics counters
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: resetcounters
---
