---
categories: []
consumed_apis: []
description: The Envoy Proxy Administration Interface provides a local HTTP-based management API for querying and modifying various aspects of the Envoy server at runtime. It serves as a critical operational tool for monitoring, debugging, and managing Envoy proxy instances. The admin interface typically runs on port 9901 by default. All mutation operations must be sent as HTTP POST requests; GET requests will not perform changes. Note that this endpoint is not authenticated, so access should be restricted in production environments.
layout: capability
name: Envoy Proxy Admin API
operations:
- description: Envoy Proxy Admin Home
  method: GET
  name: getadminhome
  path: /
- description: Envoy Proxy List Available Endpoints
  method: GET
  name: gethelp
  path: /help
- description: Envoy Proxy Check Server Readiness
  method: GET
  name: getready
  path: /ready
- description: Envoy Proxy Get Server Information
  method: GET
  name: getserverinfo
  path: /server_info
- description: Envoy Proxy Get Statistics
  method: GET
  name: getstats
  path: /stats
- description: Envoy Proxy Get Statistics in Prometheus Format
  method: GET
  name: getstatsprometheus
  path: /stats/prometheus
- description: Envoy Proxy Get Recent Stat Lookups
  method: GET
  name: getstatsrecentlookups
  path: /stats/recentlookups
- description: Envoy Proxy Get Cluster Information
  method: GET
  name: getclusters
  path: /clusters
- description: Envoy Proxy Dump Current Configuration
  method: GET
  name: getconfigdump
  path: /config_dump
- description: Envoy Proxy Dump Initialization Configuration
  method: GET
  name: getinitdump
  path: /init_dump
- description: Envoy Proxy List Listeners
  method: GET
  name: getlisteners
  path: /listeners
- description: Envoy Proxy List TLS Certificates
  method: GET
  name: getcerts
  path: /certs
- description: Envoy Proxy Get Runtime Settings
  method: GET
  name: getruntime
  path: /runtime
- description: Envoy Proxy Modify Runtime Settings
  method: POST
  name: postruntimemodify
  path: /runtime_modify
- description: Envoy Proxy View or Modify Log Levels
  method: POST
  name: postlogging
  path: /logging
- description: Envoy Proxy Get Memory Usage
  method: GET
  name: getmemory
  path: /memory
- description: Envoy Proxy Get Hot Restart Version
  method: GET
  name: gethotrestartversion
  path: /hot_restart_version
- description: Envoy Proxy Reset Counters
  method: POST
  name: postresetcounters
  path: /reset_counters
- description: Envoy Proxy Drain Listeners
  method: POST
  name: postdrainlisteners
  path: /drain_listeners
- description: Envoy Proxy Fail Health Checks
  method: POST
  name: posthealthcheckfail
  path: /healthcheck/fail
- description: Envoy Proxy Resume Health Checks
  method: POST
  name: posthealthcheckok
  path: /healthcheck/ok
- description: Envoy Proxy Shutdown Server
  method: POST
  name: postquitquitquit
  path: /quitquitquit
- description: Envoy Proxy Enable or Disable CPU Profiler
  method: POST
  name: postcpuprofiler
  path: /cpuprofiler
- description: Envoy Proxy Enable or Disable Heap Profiler
  method: POST
  name: postheapprofiler
  path: /heapprofiler
- description: Envoy Proxy Tap Traffic
  method: POST
  name: posttap
  path: /tap
- description: Envoy Proxy Get Mutex Contention Stats
  method: GET
  name: getcontention
  path: /contention
personas: []
provider_name: Envoy Proxy
provider_slug: envoy-proxy
search_terms:
- envoy proxy shutdown server
- getconfigdump
- postdrainlisteners
- envoy proxy resume health checks
- getmemory
- api
- envoy proxy list listeners
- envoy proxy drain listeners
- posttap
- envoy proxy reset counters
- getstatsprometheus
- gateways
- envoy proxy get runtime settings
- envoy proxy tap traffic
- getadminhome
- envoy proxy list available endpoints
- gethotrestartversion
- envoy proxy check server readiness
- envoy proxy get server information
- getclusters
- envoy proxy get memory usage
- envoy proxy modify runtime settings
- envoy proxy get hot restart version
- getstats
- postcpuprofiler
- envoy proxy enable or disable heap profiler
- envoy proxy view or modify log levels
- getcontention
- postheapprofiler
- postlogging
- postresetcounters
- envoy proxy fail health checks
- envoy proxy get statistics
- getruntime
- postquitquitquit
- posthealthcheckfail
- envoy proxy dump current configuration
- envoy proxy enable or disable cpu profiler
- gethelp
- envoy
- getready
- envoy proxy get statistics in prometheus format
- envoy proxy dump initialization configuration
- getlisteners
- envoy proxy get cluster information
- envoy proxy list tls certificates
- postruntimemodify
- posthealthcheckok
- getinitdump
- getcerts
- getserverinfo
- envoy proxy admin home
- proxies
- envoy proxy get recent stat lookups
- getstatsrecentlookups
- proxy
- envoy proxy get mutex contention stats
slug: envoy-proxy-capability
source_filename: envoy-proxy-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Envoy Proxy Admin API\n  description: The Envoy Proxy Administration Interface provides a local HTTP-based management API for querying and modifying\n    various aspects of the Envoy server at runtime. It serves as a critical operational tool for monitoring, debugging, and\n    managing Envoy proxy instances. The admin interface typically runs on port 9901 by default. All mutation operations must\n    be sent as HTTP POST requests; GET requests will not perform changes. Note that this endpoint is not authenticated, so\n    access should be restricted in production environments.\n  tags:\n  - Envoy\n  - Proxy\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: envoy-proxy\n    baseUri: http://localhost:9901\n    description: Envoy Proxy Admin API HTTP API.\n    resources:\n    - name: resource\n      path: /\n      operations:\n      - name: getadminhome\n        method:\
  \ GET\n        description: Envoy Proxy Admin Home\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: help\n      path: /help\n      operations:\n      - name: gethelp\n        method: GET\n        description: Envoy Proxy List Available Endpoints\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ready\n      path: /ready\n      operations:\n      - name: getready\n        method: GET\n        description: Envoy Proxy Check Server Readiness\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: server-info\n      path: /server_info\n      operations:\n      - name: getserverinfo\n        method: GET\n        description: Envoy Proxy Get Server Information\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n    - name: stats\n      path: /stats\n      operations:\n      - name: getstats\n        method: GET\n        description: Envoy Proxy Get Statistics\n        inputParameters:\n        - name: format\n          in: query\n          type: string\n          description: Output format for the statistics.\n        - name: filter\n          in: query\n          type: string\n          description: Regular expression to filter the returned statistics by name.\n        - name: usedonly\n          in: query\n          type: boolean\n          description: Only return statistics that have been written to by Envoy.\n        - name: histogram_buckets\n          in: query\n          type: string\n          description: Control histogram output mode.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: stats-prometheus\n      path: /stats/prometheus\n      operations:\n\
  \      - name: getstatsprometheus\n        method: GET\n        description: Envoy Proxy Get Statistics in Prometheus Format\n        inputParameters:\n        - name: usedonly\n          in: query\n          type: boolean\n          description: Only return statistics that have been written to by Envoy.\n        - name: text_readouts\n          in: query\n          type: boolean\n          description: Include text readout gauges in the output.\n        - name: filter\n          in: query\n          type: string\n          description: Regular expression to filter the returned statistics by name.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: stats-recentlookups\n      path: /stats/recentlookups\n      operations:\n      - name: getstatsrecentlookups\n        method: GET\n        description: Envoy Proxy Get Recent Stat Lookups\n        outputRawFormat: json\n        outputParameters:\n      \
  \  - name: result\n          type: object\n          value: $.\n    - name: clusters\n      path: /clusters\n      operations:\n      - name: getclusters\n        method: GET\n        description: Envoy Proxy Get Cluster Information\n        inputParameters:\n        - name: format\n          in: query\n          type: string\n          description: Output format for cluster information.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: config-dump\n      path: /config_dump\n      operations:\n      - name: getconfigdump\n        method: GET\n        description: Envoy Proxy Dump Current Configuration\n        inputParameters:\n        - name: resource\n          in: query\n          type: string\n          description: Filter the configuration dump to only return the specified resource type.\n        - name: mask\n          in: query\n          type: string\n          description: Field mask to apply\
  \ to the configuration dump, limiting which fields are returned.\n        - name: name_regex\n          in: query\n          type: string\n          description: Regular expression to filter the returned configuration by resource name.\n        - name: include_eds\n          in: query\n          type: boolean\n          description: Include EDS configuration in the dump.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: init-dump\n      path: /init_dump\n      operations:\n      - name: getinitdump\n        method: GET\n        description: Envoy Proxy Dump Initialization Configuration\n        inputParameters:\n        - name: mask\n          in: query\n          type: string\n          description: Field mask to apply to the initialization dump.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: listeners\n\
  \      path: /listeners\n      operations:\n      - name: getlisteners\n        method: GET\n        description: Envoy Proxy List Listeners\n        inputParameters:\n        - name: format\n          in: query\n          type: string\n          description: Output format for listener information.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: certs\n      path: /certs\n      operations:\n      - name: getcerts\n        method: GET\n        description: Envoy Proxy List TLS Certificates\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: runtime\n      path: /runtime\n      operations:\n      - name: getruntime\n        method: GET\n        description: Envoy Proxy Get Runtime Settings\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n    - name: runtime-modify\n      path: /runtime_modify\n      operations:\n      - name: postruntimemodify\n        method: POST\n        description: Envoy Proxy Modify Runtime Settings\n        inputParameters:\n        - name: key\n          in: query\n          type: string\n          description: Key-value pairs to set as runtime overrides. Multiple parameters can be passed.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: logging\n      path: /logging\n      operations:\n      - name: postlogging\n        method: POST\n        description: Envoy Proxy View or Modify Log Levels\n        inputParameters:\n        - name: level\n          in: query\n          type: string\n          description: Set the log level for all loggers. Valid values include trace, debug, info, warning/warn, error, critical,\n            and off.\n        - name: paths\n          in: query\n          type: string\n\
  \          description: Set a glob pattern for file path to filter the log output.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: memory\n      path: /memory\n      operations:\n      - name: getmemory\n        method: GET\n        description: Envoy Proxy Get Memory Usage\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: hot-restart-version\n      path: /hot_restart_version\n      operations:\n      - name: gethotrestartversion\n        method: GET\n        description: Envoy Proxy Get Hot Restart Version\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: reset-counters\n      path: /reset_counters\n      operations:\n      - name: postresetcounters\n        method: POST\n        description: Envoy Proxy Reset Counters\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: drain-listeners\n      path: /drain_listeners\n      operations:\n      - name: postdrainlisteners\n        method: POST\n        description: Envoy Proxy Drain Listeners\n        inputParameters:\n        - name: graceful\n          in: query\n          type: boolean\n          description: When set, listeners are drained gracefully with a period where both old and new listeners accept connections.\n        - name: inboundonly\n          in: query\n          type: boolean\n          description: Drain only inbound listeners and leave outbound listeners intact.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: healthcheck-fail\n      path: /healthcheck/fail\n      operations:\n      - name: posthealthcheckfail\n        method: POST\n        description: Envoy\
  \ Proxy Fail Health Checks\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: healthcheck-ok\n      path: /healthcheck/ok\n      operations:\n      - name: posthealthcheckok\n        method: POST\n        description: Envoy Proxy Resume Health Checks\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: quitquitquit\n      path: /quitquitquit\n      operations:\n      - name: postquitquitquit\n        method: POST\n        description: Envoy Proxy Shutdown Server\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cpuprofiler\n      path: /cpuprofiler\n      operations:\n      - name: postcpuprofiler\n        method: POST\n        description: Envoy Proxy Enable or Disable CPU Profiler\n        inputParameters:\n        - name:\
  \ enable\n          in: query\n          type: string\n          description: Enable (y) or disable (n) the CPU profiler.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: heapprofiler\n      path: /heapprofiler\n      operations:\n      - name: postheapprofiler\n        method: POST\n        description: Envoy Proxy Enable or Disable Heap Profiler\n        inputParameters:\n        - name: enable\n          in: query\n          type: string\n          description: Enable (y) or disable (n) the heap profiler.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tap\n      path: /tap\n      operations:\n      - name: posttap\n        method: POST\n        description: Envoy Proxy Tap Traffic\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n    - name: contention\n      path: /contention\n      operations:\n      - name: getcontention\n        method: GET\n        description: Envoy Proxy Get Mutex Contention Stats\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: envoy-proxy-rest\n    description: REST adapter for Envoy Proxy Admin API.\n    resources:\n    - path: /\n      name: getadminhome\n      operations:\n      - method: GET\n        name: getadminhome\n        description: Envoy Proxy Admin Home\n        call: envoy-proxy.getadminhome\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /help\n      name: gethelp\n      operations:\n      - method: GET\n        name: gethelp\n        description: Envoy Proxy List Available Endpoints\n        call: envoy-proxy.gethelp\n        outputParameters:\n        - type: object\n          mapping: $.\n\
  \    - path: /ready\n      name: getready\n      operations:\n      - method: GET\n        name: getready\n        description: Envoy Proxy Check Server Readiness\n        call: envoy-proxy.getready\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /server_info\n      name: getserverinfo\n      operations:\n      - method: GET\n        name: getserverinfo\n        description: Envoy Proxy Get Server Information\n        call: envoy-proxy.getserverinfo\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /stats\n      name: getstats\n      operations:\n      - method: GET\n        name: getstats\n        description: Envoy Proxy Get Statistics\n        call: envoy-proxy.getstats\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /stats/prometheus\n      name: getstatsprometheus\n      operations:\n      - method: GET\n        name: getstatsprometheus\n        description: Envoy Proxy\
  \ Get Statistics in Prometheus Format\n        call: envoy-proxy.getstatsprometheus\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /stats/recentlookups\n      name: getstatsrecentlookups\n      operations:\n      - method: GET\n        name: getstatsrecentlookups\n        description: Envoy Proxy Get Recent Stat Lookups\n        call: envoy-proxy.getstatsrecentlookups\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /clusters\n      name: getclusters\n      operations:\n      - method: GET\n        name: getclusters\n        description: Envoy Proxy Get Cluster Information\n        call: envoy-proxy.getclusters\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /config_dump\n      name: getconfigdump\n      operations:\n      - method: GET\n        name: getconfigdump\n        description: Envoy Proxy Dump Current Configuration\n        call: envoy-proxy.getconfigdump\n   \
  \     outputParameters:\n        - type: object\n          mapping: $.\n    - path: /init_dump\n      name: getinitdump\n      operations:\n      - method: GET\n        name: getinitdump\n        description: Envoy Proxy Dump Initialization Configuration\n        call: envoy-proxy.getinitdump\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /listeners\n      name: getlisteners\n      operations:\n      - method: GET\n        name: getlisteners\n        description: Envoy Proxy List Listeners\n        call: envoy-proxy.getlisteners\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /certs\n      name: getcerts\n      operations:\n      - method: GET\n        name: getcerts\n        description: Envoy Proxy List TLS Certificates\n        call: envoy-proxy.getcerts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /runtime\n      name: getruntime\n      operations:\n      - method:\
  \ GET\n        name: getruntime\n        description: Envoy Proxy Get Runtime Settings\n        call: envoy-proxy.getruntime\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /runtime_modify\n      name: postruntimemodify\n      operations:\n      - method: POST\n        name: postruntimemodify\n        description: Envoy Proxy Modify Runtime Settings\n        call: envoy-proxy.postruntimemodify\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /logging\n      name: postlogging\n      operations:\n      - method: POST\n        name: postlogging\n        description: Envoy Proxy View or Modify Log Levels\n        call: envoy-proxy.postlogging\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /memory\n      name: getmemory\n      operations:\n      - method: GET\n        name: getmemory\n        description: Envoy Proxy Get Memory Usage\n        call: envoy-proxy.getmemory\n   \
  \     outputParameters:\n        - type: object\n          mapping: $.\n    - path: /hot_restart_version\n      name: gethotrestartversion\n      operations:\n      - method: GET\n        name: gethotrestartversion\n        description: Envoy Proxy Get Hot Restart Version\n        call: envoy-proxy.gethotrestartversion\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /reset_counters\n      name: postresetcounters\n      operations:\n      - method: POST\n        name: postresetcounters\n        description: Envoy Proxy Reset Counters\n        call: envoy-proxy.postresetcounters\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /drain_listeners\n      name: postdrainlisteners\n      operations:\n      - method: POST\n        name: postdrainlisteners\n        description: Envoy Proxy Drain Listeners\n        call: envoy-proxy.postdrainlisteners\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /healthcheck/fail\n      name: posthealthcheckfail\n      operations:\n      - method: POST\n        name: posthealthcheckfail\n        description: Envoy Proxy Fail Health Checks\n        call: envoy-proxy.posthealthcheckfail\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /healthcheck/ok\n      name: posthealthcheckok\n      operations:\n      - method: POST\n        name: posthealthcheckok\n        description: Envoy Proxy Resume Health Checks\n        call: envoy-proxy.posthealthcheckok\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /quitquitquit\n      name: postquitquitquit\n      operations:\n      - method: POST\n        name: postquitquitquit\n        description: Envoy Proxy Shutdown Server\n        call: envoy-proxy.postquitquitquit\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /cpuprofiler\n      name: postcpuprofiler\n      operations:\n\
  \      - method: POST\n        name: postcpuprofiler\n        description: Envoy Proxy Enable or Disable CPU Profiler\n        call: envoy-proxy.postcpuprofiler\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /heapprofiler\n      name: postheapprofiler\n      operations:\n      - method: POST\n        name: postheapprofiler\n        description: Envoy Proxy Enable or Disable Heap Profiler\n        call: envoy-proxy.postheapprofiler\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /tap\n      name: posttap\n      operations:\n      - method: POST\n        name: posttap\n        description: Envoy Proxy Tap Traffic\n        call: envoy-proxy.posttap\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /contention\n      name: getcontention\n      operations:\n      - method: GET\n        name: getcontention\n        description: Envoy Proxy Get Mutex Contention Stats\n        call:\
  \ envoy-proxy.getcontention\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: envoy-proxy-mcp\n    transport: http\n    description: MCP adapter for Envoy Proxy Admin API for AI agent use.\n    tools:\n    - name: getadminhome\n      description: Envoy Proxy Admin Home\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: envoy-proxy.getadminhome\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: gethelp\n      description: Envoy Proxy List Available Endpoints\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: envoy-proxy.gethelp\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getready\n      description: Envoy Proxy Check Server Readiness\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: envoy-proxy.getready\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getserverinfo\n      description: Envoy Proxy Get Server Information\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: envoy-proxy.getserverinfo\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getstats\n      description: Envoy Proxy Get Statistics\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: envoy-proxy.getstats\n      with:\n        format: tools.format\n        filter: tools.filter\n        usedonly: tools.usedonly\n        histogram_buckets: tools.histogram_buckets\n      inputParameters:\n      - name: format\n        type: string\n        description: Output format for the statistics.\n      - name: filter\n        type: string\n        description: Regular expression to filter the returned statistics by name.\n      - name: usedonly\n        type: boolean\n\
  \        description: Only return statistics that have been written to by Envoy.\n      - name: histogram_buckets\n        type: string\n        description: Control histogram output mode.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getstatsprometheus\n      description: Envoy Proxy Get Statistics in Prometheus Format\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: envoy-proxy.getstatsprometheus\n      with:\n        usedonly: tools.usedonly\n        text_readouts: tools.text_readouts\n        filter: tools.filter\n      inputParameters:\n      - name: usedonly\n        type: boolean\n        description: Only return statistics that have been written to by Envoy.\n      - name: text_readouts\n        type: boolean\n        description: Include text readout gauges in the output.\n      - name: filter\n        type: string\n        description: Regular expression to filter the returned statistics\
  \ by name.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getstatsrecentlookups\n      description: Envoy Proxy Get Recent Stat Lookups\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: envoy-proxy.getstatsrecentlookups\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getclusters\n      description: Envoy Proxy Get Cluster Information\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: envoy-proxy.getclusters\n      with:\n        format: tools.format\n      inputParameters:\n      - name: format\n        type: string\n        description: Output format for cluster information.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getconfigdump\n      description: Envoy Proxy Dump Current Configuration\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent:\
  \ true\n      call: envoy-proxy.getconfigdump\n      with:\n        resource: tools.resource\n        mask: tools.mask\n        name_regex: tools.name_regex\n        include_eds: tools.include_eds\n      inputParameters:\n      - name: resource\n        type: string\n        description: Filter the configuration dump to only return the specified resource type.\n      - name: mask\n        type: string\n        description: Field mask to apply to the configuration dump, limiting which fields are returned.\n      - name: name_regex\n        type: string\n        description: Regular expression to filter the returned configuration by resource name.\n      - name: include_eds\n        type: boolean\n        description: Include EDS configuration in the dump.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getinitdump\n      description: Envoy Proxy Dump Initialization Configuration\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent:\
  \ true\n      call: envoy-proxy.getinitdump\n      with:\n        mask: tools.mask\n      inputParameters:\n      - name: mask\n        type: string\n        description: Field mask to apply to the initialization dump.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getlisteners\n      description: Envoy Proxy List Listeners\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: envoy-proxy.getlisteners\n      with:\n        format: tools.format\n      inputParameters:\n      - name: format\n        type: string\n        description: Output format for listener information.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcerts\n      description: Envoy Proxy List TLS Certificates\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: envoy-proxy.getcerts\n      outputParameters:\n      - type: object\n        mapping: $.\n\
  \    - name: getruntime\n      description: Envoy Proxy Get Runtime Settings\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: envoy-proxy.getruntime\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: postruntimemodify\n      description: Envoy Proxy Modify Runtime Settings\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: envoy-proxy.postruntimemodify\n      with:\n        key: tools.key\n      inputParameters:\n      - name: key\n        type: string\n        description: Key-value pairs to set as runtime overrides. Multiple parameters can be passed.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: postlogging\n      description: Envoy Proxy View or Modify Log Levels\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: envoy-proxy.postlogging\n      with:\n  \
  \      level: tools.level\n        paths: tools.paths\n      inputParameters:\n      - name: level\n        type: string\n        description: Set the log level for all loggers. Valid values include trace, debug, info, warning/warn, error, critical,\n          and off.\n      - name: paths\n        type: string\n        description: Set a glob pattern for file path to filter the log output.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getmemory\n      description: Envoy Proxy Get Memory Usage\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: envoy-proxy.getmemory\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: gethotrestartversion\n      description: Envoy Proxy Get Hot Restart Version\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: envoy-proxy.gethotrestartversion\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n    - name: postresetcounters\n      description: Envoy Proxy Reset Counters\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: envoy-proxy.postresetcounters\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: postdrainlisteners\n      description: Envoy Proxy Drain Listeners\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: envoy-proxy.postdrainlisteners\n      with:\n        graceful: tools.graceful\n        inboundonly: tools.inboundonly\n      inputParameters:\n      - name: graceful\n        type: boolean\n        description: When set, listeners are drained gracefully with a period where both old and new listeners accept connections.\n      - name: inboundonly\n        type: boolean\n        description: Drain only inbound listeners and leave outbound listeners intact.\n      outputParameters:\n      - type: object\n \
  \       mapping: $.\n    - name: posthealthcheckfail\n      description: Envoy Proxy Fail Health Checks\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: envoy-proxy.posthealthcheckfail\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: posthealthcheckok\n      description: Envoy Proxy Resume Health Checks\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: envoy-proxy.posthealthcheckok\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: postquitquitquit\n      description: Envoy Proxy Shutdown Server\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: envoy-proxy.postquitquitquit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: postcpuprofiler\n      description: Envoy Proxy Enable or Disable CPU Profiler\n      hints:\n        readOnly:\
  \ false\n        destructive: false\n        idempotent: false\n      call: envoy-proxy.postcpuprofiler\n      with:\n        enable: tools.enable\n      inputParameters:\n      - name: enable\n        type: string\n        description: Enable (y) or disable (n) the CPU profiler.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: postheapprofiler\n      description: Envoy Proxy Enable or Disable Heap Profiler\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: envoy-proxy.postheapprofiler\n      with:\n        enable: tools.enable\n      inputParameters:\n      - name: enable\n        type: string\n        description: Enable (y) or disable (n) the heap profiler.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: posttap\n      description: Envoy Proxy Tap Traffic\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: envoy-proxy.posttap\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcontention\n      description: Envoy Proxy Get Mutex Contention Stats\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: envoy-proxy.getcontention\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/envoy-proxy/refs/heads/main/capabilities/envoy-proxy-capability.yaml
tags:
- Envoy
- Proxy
- API
tools:
- description: Envoy Proxy Admin Home
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getadminhome
- description: Envoy Proxy List Available Endpoints
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gethelp
- description: Envoy Proxy Check Server Readiness
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getready
- description: Envoy Proxy Get Server Information
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getserverinfo
- description: Envoy Proxy Get Statistics
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getstats
- description: Envoy Proxy Get Statistics in Prometheus Format
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getstatsprometheus
- description: Envoy Proxy Get Recent Stat Lookups
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getstatsrecentlookups
- description: Envoy Proxy Get Cluster Information
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getclusters
- description: Envoy Proxy Dump Current Configuration
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getconfigdump
- description: Envoy Proxy Dump Initialization Configuration
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getinitdump
- description: Envoy Proxy List Listeners
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getlisteners
- description: Envoy Proxy List TLS Certificates
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcerts
- description: Envoy Proxy Get Runtime Settings
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getruntime
- description: Envoy Proxy Modify Runtime Settings
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: postruntimemodify
- description: Envoy Proxy View or Modify Log Levels
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: postlogging
- description: Envoy Proxy Get Memory Usage
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getmemory
- description: Envoy Proxy Get Hot Restart Version
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gethotrestartversion
- description: Envoy Proxy Reset Counters
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: postresetcounters
- description: Envoy Proxy Drain Listeners
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: postdrainlisteners
- description: Envoy Proxy Fail Health Checks
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: posthealthcheckfail
- description: Envoy Proxy Resume Health Checks
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: posthealthcheckok
- description: Envoy Proxy Shutdown Server
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: postquitquitquit
- description: Envoy Proxy Enable or Disable CPU Profiler
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: postcpuprofiler
- description: Envoy Proxy Enable or Disable Heap Profiler
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: postheapprofiler
- description: Envoy Proxy Tap Traffic
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: posttap
- description: Envoy Proxy Get Mutex Contention Stats
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcontention
---
