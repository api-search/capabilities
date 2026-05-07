---
categories: []
consumed_apis: []
description: Workflow capability for monitoring NGINX instances combining Plus HTTP API detailed statistics with Stub Status basic metrics. Provides comprehensive observability across connections, HTTP requests, server zones, location zones, caches, rate limiting, and upstream health.
layout: capability
name: NGINX Monitoring And Observability
operations:
- description: Get basic NGINX status metrics
  method: GET
  name: get-stub-status
  path: /v1/stub-status
- description: Get NGINX Plus instance status and version
  method: GET
  name: get-nginx-info
  path: /v1/nginx-info
- description: Get client connection statistics
  method: GET
  name: get-connections
  path: /v1/connections
- description: Get HTTP request statistics
  method: GET
  name: get-http-requests
  path: /v1/http-requests
- description: Get all HTTP server zone statistics
  method: GET
  name: get-http-server-zones
  path: /v1/http-server-zones
- description: Get statistics for a specific HTTP server zone
  method: GET
  name: get-http-server-zone
  path: /v1/http-server-zones/{httpServerZoneName}
- description: Get all HTTP location zone statistics
  method: GET
  name: get-http-location-zones
  path: /v1/http-location-zones
- description: Get all HTTP cache zone statistics
  method: GET
  name: get-http-caches
  path: /v1/http-caches
- description: Get all HTTP connection limit zone statistics
  method: GET
  name: get-http-limit-conn-zones
  path: /v1/http-limit-conns
- description: Get all HTTP request rate limit zone statistics
  method: GET
  name: get-http-limit-req-zones
  path: /v1/http-limit-reqs
- description: Get health and statistics for all HTTP upstream groups
  method: GET
  name: get-http-upstreams
  path: /v1/http-upstreams
- description: Get all stream server zone statistics
  method: GET
  name: get-stream-server-zones
  path: /v1/stream-server-zones
- description: Get health and statistics for all stream upstream groups
  method: GET
  name: get-stream-upstreams
  path: /v1/stream-upstreams
- description: Get cluster zone synchronization status
  method: GET
  name: get-stream-zone-sync
  path: /v1/stream-zone-sync
personas: []
provider_name: NGINX
provider_slug: nginx
search_terms:
- get stream server zones
- get nginx info
- get basic nginx status metrics including active connections and request counters from stub_status
- get health status and traffic statistics for all stream upstream groups
- stream upstream health and statistics
- get http limit req zones
- health checks
- get cluster zone synchronization status
- basic nginx status metrics from stub_status module
- get cache hit/miss/bypass statistics for all http cache zones
- get all http server zone statistics
- get statistics for all http location zones
- get all http request rate limit zone statistics
- get nginx plus instance status and version
- get detailed client connection statistics including active, idle, accepted, and dropped counts
- get cluster zone synchronization status including pending records and sync traffic
- get all http cache zone statistics
- get http request processing statistics including total and current request counts
- cloud native
- monitoring
- reverse proxy
- open source
- http upstream health and statistics
- get health and statistics for all http upstream groups
- get http server zones
- cluster zone synchronization status
- get connection limiting statistics for all http limit_conn zones
- nginx plus instance information
- http request rate limit zone statistics
- get http upstreams
- observability
- get all stream server zone statistics
- get http server zone
- get all http connection limit zone statistics
- http location zone statistics
- get http requests
- get detailed statistics for a specific http server zone
- api gateway
- http server zone statistics
- individual http server zone statistics
- http request processing statistics
- get statistics for all stream (tcp/udp) server zones
- web server
- stream server zone statistics
- get basic nginx status metrics
- get http limit conn zones
- get stream upstreams
- nginx
- get statistics for a specific http server zone
- get statistics for all http server zones including requests, responses, and traffic volume
- get http request statistics
- metrics
- get connections
- get stub status
- get nginx plus instance status including version, build name, and process information
- get http caches
- get stream zone sync
- get request rate limiting statistics for all http limit_req zones
- http cache zone statistics
- caching
- get http location zones
- get health status and traffic statistics for all http upstream server groups
- load balancer
- get health and statistics for all stream upstream groups
- http connection limit zone statistics
- get client connection statistics
- client connection statistics
- get all http location zone statistics
slug: monitoring-and-observability
source_filename: monitoring-and-observability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: NGINX Monitoring And Observability\n  description: Workflow capability for monitoring NGINX instances combining Plus HTTP API detailed statistics with Stub Status\n    basic metrics. Provides comprehensive observability across connections, HTTP requests, server zones, location zones, caches,\n    rate limiting, and upstream health.\n  tags:\n  - NGINX\n  - Monitoring\n  - Observability\n  - Metrics\n  - Health Checks\n  created: '2026-04-21'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: nginx-plus-api\n    baseUri: http://localhost/api/9\n    description: NGINX Plus REST API v9 for dynamic configuration and monitoring.\n    resources:\n    - name: general\n      path: /\n      description: General instance information and root endpoints\n      operations:\n      - name: get-api-endpoints\n        method: GET\n        description: Return list of root API endpoints\n        outputRawFormat: json\n  \
  \      outputParameters:\n        - name: result\n          type: array\n          value: $.\n    - name: nginx-info\n      path: /nginx\n      description: NGINX instance status and version information\n      operations:\n      - name: get-nginx-info\n        method: GET\n        description: Return status of the running NGINX instance including version, build, and process IDs\n        inputParameters:\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Comma-separated list of fields to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: processes\n      path: /processes\n      description: Child process statistics\n      operations:\n      - name: get-processes\n        method: GET\n        description: Return number of abnormally terminated and respawned child processes\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: reset-processes\n        method: DELETE\n        description: Reset counters of abnormally terminated and respawned child processes\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: connections\n      path: /connections\n      description: Client connection statistics\n      operations:\n      - name: get-connections\n        method: GET\n        description: Return client connections statistics\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: reset-connections\n        method: DELETE\n        description: Reset client connections statistics\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: slabs\n      path: /slabs\n      description:\
  \ Shared memory slab allocator statistics\n      operations:\n      - name: get-slabs\n        method: GET\n        description: Return status of all shared memory slab zones\n        inputParameters:\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Comma-separated list of fields to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: slab-zone\n      path: /slabs/{slabZoneName}\n      description: Individual slab zone statistics\n      operations:\n      - name: get-slab-zone\n        method: GET\n        description: Return status of a specific slab zone\n        inputParameters:\n        - name: slabZoneName\n          in: path\n          type: string\n          required: true\n          description: Name of the slab zone\n        - name: fields\n          in: query\n          type: string\n          required: false\n  \
  \        description: Comma-separated list of fields to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: reset-slab-zone\n        method: DELETE\n        description: Reset statistics for a slab zone\n        inputParameters:\n        - name: slabZoneName\n          in: path\n          type: string\n          required: true\n          description: Name of the slab zone\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: http\n      path: /http\n      description: HTTP subsystem endpoints\n      operations:\n      - name: get-http-endpoints\n        method: GET\n        description: Return list of HTTP-related endpoints\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n    - name: http-requests\n      path: /http/requests\n  \
  \    description: HTTP request statistics\n      operations:\n      - name: get-http-requests\n        method: GET\n        description: Return HTTP request statistics\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: reset-http-requests\n        method: DELETE\n        description: Reset HTTP request statistics\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: http-server-zones\n      path: /http/server_zones\n      description: HTTP server zone statistics\n      operations:\n      - name: get-http-server-zones\n        method: GET\n        description: Return status of all HTTP server zones\n        inputParameters:\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Comma-separated list of fields to return\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: http-server-zone\n      path: /http/server_zones/{httpServerZoneName}\n      description: Individual HTTP server zone statistics\n      operations:\n      - name: get-http-server-zone\n        method: GET\n        description: Return status of a specific HTTP server zone\n        inputParameters:\n        - name: httpServerZoneName\n          in: path\n          type: string\n          required: true\n          description: Name of the HTTP server zone\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Comma-separated list of fields to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: reset-http-server-zone\n        method: DELETE\n        description: Reset statistics for an HTTP server zone\n        inputParameters:\n\
  \        - name: httpServerZoneName\n          in: path\n          type: string\n          required: true\n          description: Name of the HTTP server zone\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: http-location-zones\n      path: /http/location_zones\n      description: HTTP location zone statistics\n      operations:\n      - name: get-http-location-zones\n        method: GET\n        description: Return status of all HTTP location zones\n        inputParameters:\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Comma-separated list of fields to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: http-location-zone\n      path: /http/location_zones/{httpLocationZoneName}\n      description: Individual HTTP location zone statistics\n\
  \      operations:\n      - name: get-http-location-zone\n        method: GET\n        description: Return status of a specific HTTP location zone\n        inputParameters:\n        - name: httpLocationZoneName\n          in: path\n          type: string\n          required: true\n          description: Name of the HTTP location zone\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Comma-separated list of fields to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: reset-http-location-zone\n        method: DELETE\n        description: Reset statistics for an HTTP location zone\n        inputParameters:\n        - name: httpLocationZoneName\n          in: path\n          type: string\n          required: true\n          description: Name of the HTTP location zone\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: http-caches\n      path: /http/caches\n      description: HTTP cache zone statistics\n      operations:\n      - name: get-http-caches\n        method: GET\n        description: Return status of all HTTP cache zones\n        inputParameters:\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Comma-separated list of fields to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: http-cache-zone\n      path: /http/caches/{httpCacheZoneName}\n      description: Individual HTTP cache zone statistics\n      operations:\n      - name: get-http-cache-zone\n        method: GET\n        description: Return status of a specific HTTP cache zone\n        inputParameters:\n        - name: httpCacheZoneName\n          in: path\n          type: string\n       \
  \   required: true\n          description: Name of the HTTP cache zone\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Comma-separated list of fields to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: reset-http-cache-zone\n        method: DELETE\n        description: Reset statistics for an HTTP cache zone\n        inputParameters:\n        - name: httpCacheZoneName\n          in: path\n          type: string\n          required: true\n          description: Name of the HTTP cache zone\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: http-limit-conns\n      path: /http/limit_conns\n      description: HTTP connection limit zone statistics\n      operations:\n      - name: get-http-limit-conn-zones\n        method: GET\n      \
  \  description: Return status of all HTTP limit_conn zones\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: http-limit-conn-zone\n      path: /http/limit_conns/{httpLimitConnZoneName}\n      description: Individual HTTP connection limit zone statistics\n      operations:\n      - name: get-http-limit-conn-zone\n        method: GET\n        description: Return status of a specific HTTP limit_conn zone\n        inputParameters:\n        - name: httpLimitConnZoneName\n          in: path\n          type: string\n          required: true\n          description: Name of the HTTP limit_conn zone\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: reset-http-limit-conn-zone\n        method: DELETE\n        description: Reset statistics for an HTTP limit_conn zone\n        inputParameters:\n        - name: httpLimitConnZoneName\n\
  \          in: path\n          type: string\n          required: true\n          description: Name of the HTTP limit_conn zone\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: http-limit-reqs\n      path: /http/limit_reqs\n      description: HTTP request rate limit zone statistics\n      operations:\n      - name: get-http-limit-req-zones\n        method: GET\n        description: Return status of all HTTP limit_req zones\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: http-limit-req-zone\n      path: /http/limit_reqs/{httpLimitReqZoneName}\n      description: Individual HTTP request rate limit zone statistics\n      operations:\n      - name: get-http-limit-req-zone\n        method: GET\n        description: Return status of a specific HTTP limit_req zone\n        inputParameters:\n        - name: httpLimitReqZoneName\n\
  \          in: path\n          type: string\n          required: true\n          description: Name of the HTTP limit_req zone\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: reset-http-limit-req-zone\n        method: DELETE\n        description: Reset statistics for an HTTP limit_req zone\n        inputParameters:\n        - name: httpLimitReqZoneName\n          in: path\n          type: string\n          required: true\n          description: Name of the HTTP limit_req zone\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: http-upstreams\n      path: /http/upstreams\n      description: HTTP upstream server group statistics\n      operations:\n      - name: get-http-upstreams\n        method: GET\n        description: Return status of all HTTP upstream server groups\n        inputParameters:\n        - name:\
  \ fields\n          in: query\n          type: string\n          required: false\n          description: Comma-separated list of fields to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: http-upstream\n      path: /http/upstreams/{httpUpstreamName}\n      description: Individual HTTP upstream server group\n      operations:\n      - name: get-http-upstream\n        method: GET\n        description: Return status of a specific HTTP upstream server group\n        inputParameters:\n        - name: httpUpstreamName\n          in: path\n          type: string\n          required: true\n          description: Name of the upstream server group\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Comma-separated list of fields to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n      - name: reset-http-upstream\n        method: DELETE\n        description: Reset statistics of an HTTP upstream server group\n        inputParameters:\n        - name: httpUpstreamName\n          in: path\n          type: string\n          required: true\n          description: Name of the upstream server group\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: http-upstream-servers\n      path: /http/upstreams/{httpUpstreamName}/servers\n      description: Servers within an HTTP upstream group\n      operations:\n      - name: get-http-upstream-servers\n        method: GET\n        description: Return configuration of all servers in an HTTP upstream server group\n        inputParameters:\n        - name: httpUpstreamName\n          in: path\n          type: string\n          required: true\n          description: Name of the upstream server group\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n      - name: add-http-upstream-server\n        method: POST\n        description: Add a server to an HTTP upstream server group\n        inputParameters:\n        - name: httpUpstreamName\n          in: path\n          type: string\n          required: true\n          description: Name of the upstream server group\n        - name: body\n          in: body\n          type: object\n          required: true\n          description: Server configuration object\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: http-upstream-server\n      path: /http/upstreams/{httpUpstreamName}/servers/{httpUpstreamServerId}\n      description: Individual server within an HTTP upstream group\n      operations:\n      - name: get-http-upstream-server\n        method: GET\n        description: Return configuration of a\
  \ specific server in an HTTP upstream server group\n        inputParameters:\n        - name: httpUpstreamName\n          in: path\n          type: string\n          required: true\n          description: Name of the upstream server group\n        - name: httpUpstreamServerId\n          in: path\n          type: string\n          required: true\n          description: ID of the server\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: modify-http-upstream-server\n        method: PATCH\n        description: Modify a server in an HTTP upstream server group\n        inputParameters:\n        - name: httpUpstreamName\n          in: path\n          type: string\n          required: true\n          description: Name of the upstream server group\n        - name: httpUpstreamServerId\n          in: path\n          type: string\n          required: true\n          description: ID of the server\n        -\
  \ name: body\n          in: body\n          type: object\n          required: true\n          description: Server configuration fields to update\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: remove-http-upstream-server\n        method: DELETE\n        description: Remove a server from an HTTP upstream server group\n        inputParameters:\n        - name: httpUpstreamName\n          in: path\n          type: string\n          required: true\n          description: Name of the upstream server group\n        - name: httpUpstreamServerId\n          in: path\n          type: string\n          required: true\n          description: ID of the server\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: http-keyvals\n      path: /http/keyvals\n      description: HTTP key-value store zones\n      operations:\n   \
  \   - name: get-http-keyval-zones\n        method: GET\n        description: Return key-value pairs from all HTTP keyval zones\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: http-keyval-zone\n      path: /http/keyvals/{httpKeyvalZoneName}\n      description: Individual HTTP key-value store zone\n      operations:\n      - name: get-http-keyval-zone\n        method: GET\n        description: Return key-value pairs from a specific HTTP keyval zone\n        inputParameters:\n        - name: httpKeyvalZoneName\n          in: path\n          type: string\n          required: true\n          description: Name of the HTTP keyval zone\n        - name: key\n          in: query\n          type: string\n          required: false\n          description: Key to look up in the zone\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n\
  \      - name: add-http-keyval\n        method: POST\n        description: Add a key-value pair to an HTTP keyval zone\n        inputParameters:\n        - name: httpKeyvalZoneName\n          in: path\n          type: string\n          required: true\n          description: Name of the HTTP keyval zone\n        - name: body\n          in: body\n          type: object\n          required: true\n          description: Key-value pair to add\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: modify-http-keyval\n        method: PATCH\n        description: Modify a key-value pair or delete a key in an HTTP keyval zone\n        inputParameters:\n        - name: httpKeyvalZoneName\n          in: path\n          type: string\n          required: true\n          description: Name of the HTTP keyval zone\n        - name: body\n          in: body\n          type: object\n          required: true\n          description:\
  \ Key-value updates (set value to null to delete)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: empty-http-keyval-zone\n        method: DELETE\n        description: Empty all key-value pairs from an HTTP keyval zone\n        inputParameters:\n        - name: httpKeyvalZoneName\n          in: path\n          type: string\n          required: true\n          description: Name of the HTTP keyval zone\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: stream\n      path: /stream\n      description: Stream (TCP/UDP) subsystem endpoints\n      operations:\n      - name: get-stream-endpoints\n        method: GET\n        description: Return list of stream-related endpoints\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n    - name: stream-server-zones\n\
  \      path: /stream/server_zones\n      description: Stream server zone statistics\n      operations:\n      - name: get-stream-server-zones\n        method: GET\n        description: Return status of all stream server zones\n        inputParameters:\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Comma-separated list of fields to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: stream-server-zone\n      path: /stream/server_zones/{streamServerZoneName}\n      description: Individual stream server zone statistics\n      operations:\n      - name: get-stream-server-zone\n        method: GET\n        description: Return status of a specific stream server zone\n        inputParameters:\n        - name: streamServerZoneName\n          in: path\n          type: string\n          required: true\n          description: Name\
  \ of the stream server zone\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Comma-separated list of fields to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: reset-stream-server-zone\n        method: DELETE\n        description: Reset statistics for a stream server zone\n        inputParameters:\n        - name: streamServerZoneName\n          in: path\n          type: string\n          required: true\n          description: Name of the stream server zone\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: stream-limit-conns\n      path: /stream/limit_conns\n      description: Stream connection limit zone statistics\n      operations:\n      - name: get-stream-limit-conn-zones\n        method: GET\n        description: Return status\
  \ of all stream limit_conn zones\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: stream-limit-conn-zone\n      path: /stream/limit_conns/{streamLimitConnZoneName}\n      description: Individual stream connection limit zone statistics\n      operations:\n      - name: get-stream-limit-conn-zone\n        method: GET\n        description: Return status of a specific stream limit_conn zone\n        inputParameters:\n        - name: streamLimitConnZoneName\n          in: path\n          type: string\n          required: true\n          description: Name of the stream limit_conn zone\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: reset-stream-limit-conn-zone\n        method: DELETE\n        description: Reset statistics for a stream limit_conn zone\n        inputParameters:\n        - name: streamLimitConnZoneName\n\
  \          in: path\n          type: string\n          required: true\n          description: Name of the stream limit_conn zone\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: stream-upstreams\n      path: /stream/upstreams\n      description: Stream upstream server group statistics\n      operations:\n      - name: get-stream-upstreams\n        method: GET\n        description: Return status of all stream upstream server groups\n        inputParameters:\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Comma-separated list of fields to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: stream-upstream\n      path: /stream/upstreams/{streamUpstreamName}\n      description: Individual stream upstream server group\n      operations:\n\
  \      - name: get-stream-upstream\n        method: GET\n        description: Return status of a specific stream upstream server group\n        inputParameters:\n        - name: streamUpstreamName\n          in: path\n          type: string\n          required: true\n          description: Name of the stream upstream server group\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Comma-separated list of fields to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: reset-stream-upstream\n        method: DELETE\n        description: Reset statistics of a stream upstream server group\n        inputParameters:\n        - name: streamUpstreamName\n          in: path\n          type: string\n          required: true\n          description: Name of the stream upstream server group\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: stream-upstream-servers\n      path: /stream/upstreams/{streamUpstreamName}/servers\n      description: Servers within a stream upstream group\n      operations:\n      - name: get-stream-upstream-servers\n        method: GET\n        description: Return configuration of all servers in a stream upstream server group\n        inputParameters:\n        - name: streamUpstreamName\n          in: path\n          type: string\n          required: true\n          description: Name of the stream upstream server group\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n      - name: add-stream-upstream-server\n        method: POST\n        description: Add a server to a stream upstream server group\n        inputParameters:\n        - name: streamUpstreamName\n          in: path\n          type: string\n          required: true\n          description:\
  \ Name of the stream upstream server group\n        - name: body\n          in: body\n          type: object\n          required: true\n          description: Server configuration object\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: stream-upstream-server\n      path: /stream/upstreams/{streamUpstreamName}/servers/{streamUpstreamServerId}\n      description: Individual server within a stream upstream group\n      operations:\n      - name: get-stream-upstream-server\n        method: GET\n        description: Return configuration of a specific server in a stream upstream server group\n        inputParameters:\n        - name: streamUpstreamName\n          in: path\n          type: string\n          required: true\n          description: Name of the stream upstream server group\n        - name: streamUpstreamServerId\n          in: path\n          type: string\n          required: true\n       \
  \   description: ID of the server\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: modify-stream-upstream-server\n        method: PATCH\n        description: Modify a server in a stream upstream server group\n        inputParameters:\n        - name: streamUpstreamName\n          in: path\n          type: string\n          required: true\n          description: Name of the stream upstream server group\n        - name: streamUpstreamServerId\n          in: path\n          type: string\n          required: true\n          description: ID of the server\n        - name: body\n          in: body\n          type: object\n          required: true\n          description: Server configuration fields to update\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: remove-stream-upstream-server\n        method: DELETE\n\
  \        description: Remove a server from a stream upstream server group\n        inputParameters:\n        - name: streamUpstreamName\n          in: path\n          type: string\n          required: true\n          description: Name of the stream upstream server group\n        - name: streamUpstreamServerId\n          in: path\n          type: string\n          required: true\n          description: ID of the server\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: stream-keyvals\n      path: /stream/keyvals\n      description: Stream key-value store zones\n      operations:\n      - name: get-stream-keyval-zones\n        method: GET\n        description: Return key-value pairs from all stream keyval zones\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: stream-keyval-zone\n      path: /stream/keyvals/{streamKeyvalZoneName}\n\
  \      description: Individual stream key-value store zone\n      operations:\n      - name: get-stream-keyval-zone\n        method: GET\n        description: Return key-value pairs from a specific stream keyval zone\n        inputParameters:\n        - name: streamKeyvalZoneName\n          in: path\n          type: string\n          required: true\n          description: Name of the stream keyval zone\n        - name: key\n          in: query\n          type: string\n          required: false\n          description: Key to look up in the zone\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: add-stream-keyval\n        method: POST\n        description: Add a key-value pair to a stream keyval zone\n        inputParameters:\n        - name: streamKeyvalZoneName\n          in: path\n          type: string\n          required: true\n          description: Name of the stream keyval zone\n        - name:\
  \ body\n          in: body\n          type: object\n          required: true\n          description: Key-value pair to add\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: modify-stream-keyval\n        method: PATCH\n        description: Modify a key-value pair or delete a key in a stream keyval zone\n        inputParameters:\n        - name: streamKeyvalZoneName\n          in: path\n          type: string\n          required: true\n          description: Name of the stream keyval zone\n        - name: body\n          in: body\n          type: object\n          required: true\n          description: Key-value updates (set value to null to delete)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: empty-stream-keyval-zone\n        method: DELETE\n        description: Empty all key-value pairs from a stream\
  \ keyval zone\n        inputParameters:\n        - name: streamKeyvalZoneName\n          in: path\n          type: string\n          required: true\n          description: Name of the stream keyval zone\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: stream-zone-sync\n      path: /stream/zone_sync\n      description: Cluster zone synchronization status\n      operations:\n      - name: get-stream-zone-sync\n        method: GET\n        description: Return synchronization status of a cluster node\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          \n\n# --- truncated at 32 KB (42 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/nginx/refs/heads/main/capabilities/monitoring-and-observability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/nginx/refs/heads/main/capabilities/monitoring-and-observability.yaml
tags:
- NGINX
- Monitoring
- Observability
- Metrics
- Health Checks
tools:
- description: Get basic NGINX status metrics including active connections and request counters from stub_status
  hints:
    openWorld: false
    readOnly: true
  name: get-stub-status
- description: Get NGINX Plus instance status including version, build name, and process information
  hints:
    openWorld: false
    readOnly: true
  name: get-nginx-info
- description: Get detailed client connection statistics including active, idle, accepted, and dropped counts
  hints:
    openWorld: false
    readOnly: true
  name: get-connections
- description: Get HTTP request processing statistics including total and current request counts
  hints:
    openWorld: false
    readOnly: true
  name: get-http-requests
- description: Get statistics for all HTTP server zones including requests, responses, and traffic volume
  hints:
    openWorld: false
    readOnly: true
  name: get-http-server-zones
- description: Get detailed statistics for a specific HTTP server zone
  hints:
    openWorld: false
    readOnly: true
  name: get-http-server-zone
- description: Get statistics for all HTTP location zones
  hints:
    openWorld: false
    readOnly: true
  name: get-http-location-zones
- description: Get cache hit/miss/bypass statistics for all HTTP cache zones
  hints:
    openWorld: false
    readOnly: true
  name: get-http-caches
- description: Get connection limiting statistics for all HTTP limit_conn zones
  hints:
    openWorld: false
    readOnly: true
  name: get-http-limit-conn-zones
- description: Get request rate limiting statistics for all HTTP limit_req zones
  hints:
    openWorld: false
    readOnly: true
  name: get-http-limit-req-zones
- description: Get health status and traffic statistics for all HTTP upstream server groups
  hints:
    openWorld: false
    readOnly: true
  name: get-http-upstreams
- description: Get statistics for all stream (TCP/UDP) server zones
  hints:
    openWorld: false
    readOnly: true
  name: get-stream-server-zones
- description: Get health status and traffic statistics for all stream upstream groups
  hints:
    openWorld: false
    readOnly: true
  name: get-stream-upstreams
- description: Get cluster zone synchronization status including pending records and sync traffic
  hints:
    openWorld: false
    readOnly: true
  name: get-stream-zone-sync
---
