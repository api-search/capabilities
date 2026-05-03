---
categories: []
consumed_apis:
- nginx-plus-api
- nginx-stub-status
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
- nginx
- get all stream server zone statistics
- observability
- nginx plus instance information
- get connections
- get http request statistics
- http server zone statistics
- get nginx plus instance status and version
- basic nginx status metrics from stub_status module
- get basic nginx status metrics
- health checks
- api gateway
- http upstream health and statistics
- get basic nginx status metrics including active connections and request counters from stub_status
- individual http server zone statistics
- open source
- reverse proxy
- get detailed client connection statistics including active, idle, accepted, and dropped counts
- http cache zone statistics
- get stream server zones
- get http requests
- get statistics for all stream (tcp/udp) server zones
- get health status and traffic statistics for all stream upstream groups
- http request rate limit zone statistics
- get http upstreams
- get cluster zone synchronization status
- get health status and traffic statistics for all http upstream server groups
- client connection statistics
- get http limit req zones
- get detailed statistics for a specific http server zone
- get health and statistics for all http upstream groups
- load balancer
- get all http location zone statistics
- monitoring
- get http server zone
- stream upstream health and statistics
- get stream upstreams
- get all http server zone statistics
- get client connection statistics
- get http request processing statistics including total and current request counts
- cloud native
- get nginx info
- get cache hit/miss/bypass statistics for all http cache zones
- web server
- get stream zone sync
- get statistics for a specific http server zone
- get request rate limiting statistics for all http limit_req zones
- get http caches
- caching
- get stub status
- http connection limit zone statistics
- get statistics for all http location zones
- get all http connection limit zone statistics
- get statistics for all http server zones including requests, responses, and traffic volume
- get cluster zone synchronization status including pending records and sync traffic
- get http location zones
- metrics
- get all http request rate limit zone statistics
- get http server zones
- get nginx plus instance status including version, build name, and process information
- get http limit conn zones
- http location zone statistics
- get all http cache zone statistics
- stream server zone statistics
- get connection limiting statistics for all http limit_conn zones
- cluster zone synchronization status
- http request processing statistics
- get health and statistics for all stream upstream groups
slug: monitoring-and-observability
source_filename: monitoring-and-observability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"NGINX Monitoring And Observability\"\n  description: >-\n    Workflow capability for monitoring NGINX instances combining Plus HTTP API\n    detailed statistics with Stub Status basic metrics. Provides comprehensive\n    observability across connections, HTTP requests, server zones, location\n    zones, caches, rate limiting, and upstream health.\n  tags:\n    - NGINX\n    - Monitoring\n    - Observability\n    - Metrics\n    - Health Checks\n  created: \"2026-04-21\"\n  modified: \"2026-04-21\"\n\ncapability:\n  consumes:\n    - import: nginx-plus-api\n      location: ./shared/plus-http-api.yaml\n    - import: nginx-stub-status\n      location: ./shared/stub-status.yaml\n\n  exposes:\n    - type: rest\n      port: 8201\n      namespace: nginx-monitoring-rest\n      description: \"REST API for NGINX monitoring and observability.\"\n      resources:\n        - path: /v1/stub-status\n          name: stub-status\n          description:\
  \ \"Basic NGINX status metrics from stub_status module\"\n          operations:\n            - method: GET\n              name: get-stub-status\n              description: \"Get basic NGINX status metrics\"\n              call: \"nginx-stub-status.get-stub-status\"\n              outputParameters:\n                - type: string\n                  mapping: \"$.\"\n        - path: /v1/nginx-info\n          name: nginx-info\n          description: \"NGINX Plus instance information\"\n          operations:\n            - method: GET\n              name: get-nginx-info\n              description: \"Get NGINX Plus instance status and version\"\n              call: \"nginx-plus-api.get-nginx-info\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/connections\n          name: connections\n          description: \"Client connection statistics\"\n          operations:\n            - method: GET\n              name: get-connections\n\
  \              description: \"Get client connection statistics\"\n              call: \"nginx-plus-api.get-connections\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/http-requests\n          name: http-requests\n          description: \"HTTP request processing statistics\"\n          operations:\n            - method: GET\n              name: get-http-requests\n              description: \"Get HTTP request statistics\"\n              call: \"nginx-plus-api.get-http-requests\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/http-server-zones\n          name: http-server-zones\n          description: \"HTTP server zone statistics\"\n          operations:\n            - method: GET\n              name: get-http-server-zones\n              description: \"Get all HTTP server zone statistics\"\n              call: \"nginx-plus-api.get-http-server-zones\"\
  \n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/http-server-zones/{httpServerZoneName}\n          name: http-server-zone\n          description: \"Individual HTTP server zone statistics\"\n          operations:\n            - method: GET\n              name: get-http-server-zone\n              description: \"Get statistics for a specific HTTP server zone\"\n              call: \"nginx-plus-api.get-http-server-zone\"\n              with:\n                httpServerZoneName: \"rest.httpServerZoneName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/http-location-zones\n          name: http-location-zones\n          description: \"HTTP location zone statistics\"\n          operations:\n            - method: GET\n              name: get-http-location-zones\n              description: \"Get all HTTP location zone statistics\"\n              call:\
  \ \"nginx-plus-api.get-http-location-zones\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/http-caches\n          name: http-caches\n          description: \"HTTP cache zone statistics\"\n          operations:\n            - method: GET\n              name: get-http-caches\n              description: \"Get all HTTP cache zone statistics\"\n              call: \"nginx-plus-api.get-http-caches\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/http-limit-conns\n          name: http-limit-conns\n          description: \"HTTP connection limit zone statistics\"\n          operations:\n            - method: GET\n              name: get-http-limit-conn-zones\n              description: \"Get all HTTP connection limit zone statistics\"\n              call: \"nginx-plus-api.get-http-limit-conn-zones\"\n              outputParameters:\n              \
  \  - type: object\n                  mapping: \"$.\"\n        - path: /v1/http-limit-reqs\n          name: http-limit-reqs\n          description: \"HTTP request rate limit zone statistics\"\n          operations:\n            - method: GET\n              name: get-http-limit-req-zones\n              description: \"Get all HTTP request rate limit zone statistics\"\n              call: \"nginx-plus-api.get-http-limit-req-zones\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/http-upstreams\n          name: http-upstreams\n          description: \"HTTP upstream health and statistics\"\n          operations:\n            - method: GET\n              name: get-http-upstreams\n              description: \"Get health and statistics for all HTTP upstream groups\"\n              call: \"nginx-plus-api.get-http-upstreams\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\
  \        - path: /v1/stream-server-zones\n          name: stream-server-zones\n          description: \"Stream server zone statistics\"\n          operations:\n            - method: GET\n              name: get-stream-server-zones\n              description: \"Get all stream server zone statistics\"\n              call: \"nginx-plus-api.get-stream-server-zones\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/stream-upstreams\n          name: stream-upstreams\n          description: \"Stream upstream health and statistics\"\n          operations:\n            - method: GET\n              name: get-stream-upstreams\n              description: \"Get health and statistics for all stream upstream groups\"\n              call: \"nginx-plus-api.get-stream-upstreams\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/stream-zone-sync\n          name:\
  \ stream-zone-sync\n          description: \"Cluster zone synchronization status\"\n          operations:\n            - method: GET\n              name: get-stream-zone-sync\n              description: \"Get cluster zone synchronization status\"\n              call: \"nginx-plus-api.get-stream-zone-sync\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9201\n      namespace: nginx-monitoring-mcp\n      transport: http\n      description: \"MCP server for AI-assisted NGINX monitoring and observability.\"\n      tools:\n        - name: get-stub-status\n          description: \"Get basic NGINX status metrics including active connections and request counters from stub_status\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"nginx-stub-status.get-stub-status\"\n          outputParameters:\n            - type: string\n              mapping: \"$.\"\n        - name:\
  \ get-nginx-info\n          description: \"Get NGINX Plus instance status including version, build name, and process information\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"nginx-plus-api.get-nginx-info\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-connections\n          description: \"Get detailed client connection statistics including active, idle, accepted, and dropped counts\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"nginx-plus-api.get-connections\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-http-requests\n          description: \"Get HTTP request processing statistics including total and current request counts\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"nginx-plus-api.get-http-requests\"\n     \
  \     outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-http-server-zones\n          description: \"Get statistics for all HTTP server zones including requests, responses, and traffic volume\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"nginx-plus-api.get-http-server-zones\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-http-server-zone\n          description: \"Get detailed statistics for a specific HTTP server zone\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"nginx-plus-api.get-http-server-zone\"\n          with:\n            httpServerZoneName: \"tools.httpServerZoneName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-http-location-zones\n          description: \"Get statistics for all HTTP location zones\"\n \
  \         hints:\n            readOnly: true\n            openWorld: false\n          call: \"nginx-plus-api.get-http-location-zones\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-http-caches\n          description: \"Get cache hit/miss/bypass statistics for all HTTP cache zones\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"nginx-plus-api.get-http-caches\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-http-limit-conn-zones\n          description: \"Get connection limiting statistics for all HTTP limit_conn zones\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"nginx-plus-api.get-http-limit-conn-zones\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-http-limit-req-zones\n          description: \"Get request\
  \ rate limiting statistics for all HTTP limit_req zones\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"nginx-plus-api.get-http-limit-req-zones\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-http-upstreams\n          description: \"Get health status and traffic statistics for all HTTP upstream server groups\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"nginx-plus-api.get-http-upstreams\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-stream-server-zones\n          description: \"Get statistics for all stream (TCP/UDP) server zones\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"nginx-plus-api.get-stream-server-zones\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        -\
  \ name: get-stream-upstreams\n          description: \"Get health status and traffic statistics for all stream upstream groups\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"nginx-plus-api.get-stream-upstreams\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-stream-zone-sync\n          description: \"Get cluster zone synchronization status including pending records and sync traffic\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"nginx-plus-api.get-stream-zone-sync\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
