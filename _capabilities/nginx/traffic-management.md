---
categories: []
consumed_apis: []
description: Workflow capability for managing NGINX Plus traffic routing including dynamic upstream server management, load balancing configuration, key-value store operations, and real-time upstream health monitoring for both HTTP and stream (TCP/UDP) protocols.
layout: capability
name: NGINX Traffic Management
operations:
- description: List all HTTP upstream server groups with health status
  method: GET
  name: get-http-upstreams
  path: /v1/http-upstreams
- description: List servers in an HTTP upstream group
  method: GET
  name: get-http-upstream-servers
  path: /v1/http-upstreams/{httpUpstreamName}/servers
- description: Add a server to an HTTP upstream group
  method: POST
  name: add-http-upstream-server
  path: /v1/http-upstreams/{httpUpstreamName}/servers
- description: Get configuration of a specific upstream server
  method: GET
  name: get-http-upstream-server
  path: /v1/http-upstreams/{httpUpstreamName}/servers/{httpUpstreamServerId}
- description: Modify an HTTP upstream server configuration
  method: PATCH
  name: modify-http-upstream-server
  path: /v1/http-upstreams/{httpUpstreamName}/servers/{httpUpstreamServerId}
- description: Remove a server from an HTTP upstream group
  method: DELETE
  name: remove-http-upstream-server
  path: /v1/http-upstreams/{httpUpstreamName}/servers/{httpUpstreamServerId}
- description: Get key-value pairs from an HTTP keyval zone
  method: GET
  name: get-http-keyval-zone
  path: /v1/http-keyvals/{httpKeyvalZoneName}
- description: Add a key-value pair for dynamic routing
  method: POST
  name: add-http-keyval
  path: /v1/http-keyvals/{httpKeyvalZoneName}
- description: Modify a key-value pair for dynamic routing
  method: PATCH
  name: modify-http-keyval
  path: /v1/http-keyvals/{httpKeyvalZoneName}
- description: Empty all key-value pairs from an HTTP keyval zone
  method: DELETE
  name: empty-http-keyval-zone
  path: /v1/http-keyvals/{httpKeyvalZoneName}
- description: List all stream upstream server groups
  method: GET
  name: get-stream-upstreams
  path: /v1/stream-upstreams
- description: List servers in a stream upstream group
  method: GET
  name: get-stream-upstream-servers
  path: /v1/stream-upstreams/{streamUpstreamName}/servers
- description: Add a server to a stream upstream group
  method: POST
  name: add-stream-upstream-server
  path: /v1/stream-upstreams/{streamUpstreamName}/servers
- description: Get configuration of a specific stream upstream server
  method: GET
  name: get-stream-upstream-server
  path: /v1/stream-upstreams/{streamUpstreamName}/servers/{streamUpstreamServerId}
- description: Modify a stream upstream server configuration
  method: PATCH
  name: modify-stream-upstream-server
  path: /v1/stream-upstreams/{streamUpstreamName}/servers/{streamUpstreamServerId}
- description: Remove a server from a stream upstream group
  method: DELETE
  name: remove-stream-upstream-server
  path: /v1/stream-upstreams/{streamUpstreamName}/servers/{streamUpstreamServerId}
personas: []
provider_name: NGINX
provider_slug: nginx
search_terms:
- reverse proxy
- get configuration of a specific upstream server
- add stream upstream server
- servers in an http upstream group
- list servers in a stream upstream group
- list all http upstream server groups with health status
- get key-value pairs from an http keyval zone
- remove a server from a stream (tcp/udp) upstream group
- get http upstream server
- individual stream upstream server
- get stream upstream server
- dynamically add a server to a stream (tcp/udp) upstream group
- dynamically add a backend server to an nginx http upstream group for load balancing
- upstream management
- list all nginx http upstream server groups with health and traffic statistics
- http upstream server groups
- servers in a stream upstream group
- remove a backend server from an nginx http upstream group
- list all nginx stream (tcp/udp) upstream server groups with health statistics
- get http upstreams
- get configuration of a specific stream upstream server
- add a server to a stream upstream group
- empty all key-value pairs from an http keyval zone
- modify a stream upstream server configuration
- get http upstream servers
- list all stream upstream server groups
- cloud native
- http key-value store for dynamic routing rules
- individual http upstream server
- open source
- list all servers in a specific nginx http upstream group with their configuration
- list servers in an http upstream group
- add a key-value pair to an http keyval zone for dynamic traffic routing
- modify http upstream server
- dynamic configuration
- get stream upstream servers
- modify http keyval
- remove a server from a stream upstream group
- caching
- load balancer
- add a key-value pair for dynamic routing
- web server
- add http upstream server
- stream upstream server groups
- api gateway
- modify an http upstream server configuration
- remove http upstream server
- get stream upstreams
- modify or delete a key-value pair in an http keyval zone
- empty http keyval zone
- traffic management
- add a server to an http upstream group
- remove a server from an http upstream group
- get http keyval zone
- add http keyval
- modify stream upstream server
- remove stream upstream server
- get key-value pairs from an http keyval zone used for dynamic routing decisions
- load balancing
- nginx
- modify configuration of an http upstream server (weight, max_conns, backup, down status)
- modify a key-value pair for dynamic routing
slug: traffic-management
source_filename: traffic-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: NGINX Traffic Management\n  description: Workflow capability for managing NGINX Plus traffic routing including dynamic upstream server management, load\n    balancing configuration, key-value store operations, and real-time upstream health monitoring for both HTTP and stream\n    (TCP/UDP) protocols.\n  tags:\n  - NGINX\n  - Traffic Management\n  - Load Balancing\n  - Upstream Management\n  - Dynamic Configuration\n  created: '2026-04-21'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: nginx-plus-api\n    baseUri: http://localhost/api/9\n    description: NGINX Plus REST API v9 for dynamic configuration and monitoring.\n    resources:\n    - name: general\n      path: /\n      description: General instance information and root endpoints\n      operations:\n      - name: get-api-endpoints\n        method: GET\n        description: Return list of root API endpoints\n        outputRawFormat: json\n     \
  \   outputParameters:\n        - name: result\n          type: array\n          value: $.\n    - name: nginx-info\n      path: /nginx\n      description: NGINX instance status and version information\n      operations:\n      - name: get-nginx-info\n        method: GET\n        description: Return status of the running NGINX instance including version, build, and process IDs\n        inputParameters:\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Comma-separated list of fields to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: processes\n      path: /processes\n      description: Child process statistics\n      operations:\n      - name: get-processes\n        method: GET\n        description: Return number of abnormally terminated and respawned child processes\n        outputRawFormat: json\n        outputParameters:\n\
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
  \ keyval zone\n        inputParameters:\n        - name: streamKeyvalZoneName\n          in: path\n          type: string\n          required: true\n          description: Name of the stream keyval zone\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: stream-zone-sync\n      path: /stream/zone_sync\n      description: Cluster zone synchronization status\n      operations:\n      - name: get-stream-zone-sync\n        method: GET\n        description: Return synchronization status of a cluster node\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          val\n\n# --- truncated at 32 KB (43 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/nginx/refs/heads/main/capabilities/traffic-management.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/nginx/refs/heads/main/capabilities/traffic-management.yaml
tags:
- NGINX
- Traffic Management
- Load Balancing
- Upstream Management
- Dynamic Configuration
tools:
- description: List all NGINX HTTP upstream server groups with health and traffic statistics
  hints:
    openWorld: false
    readOnly: true
  name: get-http-upstreams
- description: List all servers in a specific NGINX HTTP upstream group with their configuration
  hints:
    openWorld: false
    readOnly: true
  name: get-http-upstream-servers
- description: Dynamically add a backend server to an NGINX HTTP upstream group for load balancing
  hints:
    destructive: false
    idempotent: false
    openWorld: false
    readOnly: false
  name: add-http-upstream-server
- description: Modify configuration of an HTTP upstream server (weight, max_conns, backup, down status)
  hints:
    destructive: false
    idempotent: true
    openWorld: false
    readOnly: false
  name: modify-http-upstream-server
- description: Remove a backend server from an NGINX HTTP upstream group
  hints:
    destructive: true
    idempotent: true
    openWorld: false
    readOnly: false
  name: remove-http-upstream-server
- description: Get key-value pairs from an HTTP keyval zone used for dynamic routing decisions
  hints:
    openWorld: false
    readOnly: true
  name: get-http-keyval-zone
- description: Add a key-value pair to an HTTP keyval zone for dynamic traffic routing
  hints:
    destructive: false
    idempotent: false
    openWorld: false
    readOnly: false
  name: add-http-keyval
- description: Modify or delete a key-value pair in an HTTP keyval zone
  hints:
    destructive: false
    idempotent: true
    openWorld: false
    readOnly: false
  name: modify-http-keyval
- description: List all NGINX stream (TCP/UDP) upstream server groups with health statistics
  hints:
    openWorld: false
    readOnly: true
  name: get-stream-upstreams
- description: Dynamically add a server to a stream (TCP/UDP) upstream group
  hints:
    destructive: false
    idempotent: false
    openWorld: false
    readOnly: false
  name: add-stream-upstream-server
- description: Remove a server from a stream (TCP/UDP) upstream group
  hints:
    destructive: true
    idempotent: true
    openWorld: false
    readOnly: false
  name: remove-stream-upstream-server
---
