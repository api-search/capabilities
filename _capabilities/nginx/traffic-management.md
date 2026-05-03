---
categories: []
consumed_apis:
- nginx-plus-api
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
- nginx
- http key-value store for dynamic routing rules
- load balancing
- add a server to a stream upstream group
- individual stream upstream server
- get http upstream servers
- remove http upstream server
- get http upstream server
- add a key-value pair for dynamic routing
- api gateway
- add a server to an http upstream group
- servers in an http upstream group
- modify http keyval
- remove a server from an http upstream group
- stream upstream server groups
- open source
- list all stream upstream server groups
- reverse proxy
- get stream upstream server
- upstream management
- get http upstreams
- add a key-value pair to an http keyval zone for dynamic traffic routing
- dynamically add a server to a stream (tcp/udp) upstream group
- list all nginx http upstream server groups with health and traffic statistics
- modify or delete a key-value pair in an http keyval zone
- dynamically add a backend server to an nginx http upstream group for load balancing
- list all servers in a specific nginx http upstream group with their configuration
- dynamic configuration
- load balancer
- remove a backend server from an nginx http upstream group
- remove a server from a stream (tcp/udp) upstream group
- modify an http upstream server configuration
- get stream upstreams
- cloud native
- modify a stream upstream server configuration
- individual http upstream server
- modify configuration of an http upstream server (weight, max_conns, backup, down status)
- web server
- list servers in a stream upstream group
- http upstream server groups
- add stream upstream server
- remove a server from a stream upstream group
- list all nginx stream (tcp/udp) upstream server groups with health statistics
- get configuration of a specific upstream server
- caching
- list servers in an http upstream group
- empty http keyval zone
- modify stream upstream server
- list all http upstream server groups with health status
- get key-value pairs from an http keyval zone
- modify a key-value pair for dynamic routing
- remove stream upstream server
- get configuration of a specific stream upstream server
- get http keyval zone
- empty all key-value pairs from an http keyval zone
- traffic management
- add http upstream server
- servers in a stream upstream group
- modify http upstream server
- get stream upstream servers
- get key-value pairs from an http keyval zone used for dynamic routing decisions
- add http keyval
slug: traffic-management
source_filename: traffic-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"NGINX Traffic Management\"\n  description: >-\n    Workflow capability for managing NGINX Plus traffic routing including\n    dynamic upstream server management, load balancing configuration,\n    key-value store operations, and real-time upstream health monitoring\n    for both HTTP and stream (TCP/UDP) protocols.\n  tags:\n    - NGINX\n    - Traffic Management\n    - Load Balancing\n    - Upstream Management\n    - Dynamic Configuration\n  created: \"2026-04-21\"\n  modified: \"2026-04-21\"\n\ncapability:\n  consumes:\n    - import: nginx-plus-api\n      location: ./shared/plus-http-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8200\n      namespace: nginx-traffic-management-rest\n      description: \"REST API for NGINX traffic management and upstream configuration.\"\n      resources:\n        - path: /v1/http-upstreams\n          name: http-upstreams\n          description: \"HTTP upstream server groups\"\n        \
  \  operations:\n            - method: GET\n              name: get-http-upstreams\n              description: \"List all HTTP upstream server groups with health status\"\n              call: \"nginx-plus-api.get-http-upstreams\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/http-upstreams/{httpUpstreamName}/servers\n          name: http-upstream-servers\n          description: \"Servers in an HTTP upstream group\"\n          operations:\n            - method: GET\n              name: get-http-upstream-servers\n              description: \"List servers in an HTTP upstream group\"\n              call: \"nginx-plus-api.get-http-upstream-servers\"\n              with:\n                httpUpstreamName: \"rest.httpUpstreamName\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n            - method: POST\n              name: add-http-upstream-server\n              description:\
  \ \"Add a server to an HTTP upstream group\"\n              call: \"nginx-plus-api.add-http-upstream-server\"\n              with:\n                httpUpstreamName: \"rest.httpUpstreamName\"\n                body: \"rest.body\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/http-upstreams/{httpUpstreamName}/servers/{httpUpstreamServerId}\n          name: http-upstream-server\n          description: \"Individual HTTP upstream server\"\n          operations:\n            - method: GET\n              name: get-http-upstream-server\n              description: \"Get configuration of a specific upstream server\"\n              call: \"nginx-plus-api.get-http-upstream-server\"\n              with:\n                httpUpstreamName: \"rest.httpUpstreamName\"\n                httpUpstreamServerId: \"rest.httpUpstreamServerId\"\n              outputParameters:\n                - type: object\n                  mapping: \"\
  $.\"\n            - method: PATCH\n              name: modify-http-upstream-server\n              description: \"Modify an HTTP upstream server configuration\"\n              call: \"nginx-plus-api.modify-http-upstream-server\"\n              with:\n                httpUpstreamName: \"rest.httpUpstreamName\"\n                httpUpstreamServerId: \"rest.httpUpstreamServerId\"\n                body: \"rest.body\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: remove-http-upstream-server\n              description: \"Remove a server from an HTTP upstream group\"\n              call: \"nginx-plus-api.remove-http-upstream-server\"\n              with:\n                httpUpstreamName: \"rest.httpUpstreamName\"\n                httpUpstreamServerId: \"rest.httpUpstreamServerId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        -\
  \ path: /v1/http-keyvals/{httpKeyvalZoneName}\n          name: http-keyval-zone\n          description: \"HTTP key-value store for dynamic routing rules\"\n          operations:\n            - method: GET\n              name: get-http-keyval-zone\n              description: \"Get key-value pairs from an HTTP keyval zone\"\n              call: \"nginx-plus-api.get-http-keyval-zone\"\n              with:\n                httpKeyvalZoneName: \"rest.httpKeyvalZoneName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: add-http-keyval\n              description: \"Add a key-value pair for dynamic routing\"\n              call: \"nginx-plus-api.add-http-keyval\"\n              with:\n                httpKeyvalZoneName: \"rest.httpKeyvalZoneName\"\n                body: \"rest.body\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n          \
  \  - method: PATCH\n              name: modify-http-keyval\n              description: \"Modify a key-value pair for dynamic routing\"\n              call: \"nginx-plus-api.modify-http-keyval\"\n              with:\n                httpKeyvalZoneName: \"rest.httpKeyvalZoneName\"\n                body: \"rest.body\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: empty-http-keyval-zone\n              description: \"Empty all key-value pairs from an HTTP keyval zone\"\n              call: \"nginx-plus-api.empty-http-keyval-zone\"\n              with:\n                httpKeyvalZoneName: \"rest.httpKeyvalZoneName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/stream-upstreams\n          name: stream-upstreams\n          description: \"Stream upstream server groups\"\n          operations:\n            - method: GET\n\
  \              name: get-stream-upstreams\n              description: \"List all stream upstream server groups\"\n              call: \"nginx-plus-api.get-stream-upstreams\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/stream-upstreams/{streamUpstreamName}/servers\n          name: stream-upstream-servers\n          description: \"Servers in a stream upstream group\"\n          operations:\n            - method: GET\n              name: get-stream-upstream-servers\n              description: \"List servers in a stream upstream group\"\n              call: \"nginx-plus-api.get-stream-upstream-servers\"\n              with:\n                streamUpstreamName: \"rest.streamUpstreamName\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n            - method: POST\n              name: add-stream-upstream-server\n              description: \"Add a server to a stream\
  \ upstream group\"\n              call: \"nginx-plus-api.add-stream-upstream-server\"\n              with:\n                streamUpstreamName: \"rest.streamUpstreamName\"\n                body: \"rest.body\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/stream-upstreams/{streamUpstreamName}/servers/{streamUpstreamServerId}\n          name: stream-upstream-server\n          description: \"Individual stream upstream server\"\n          operations:\n            - method: GET\n              name: get-stream-upstream-server\n              description: \"Get configuration of a specific stream upstream server\"\n              call: \"nginx-plus-api.get-stream-upstream-server\"\n              with:\n                streamUpstreamName: \"rest.streamUpstreamName\"\n                streamUpstreamServerId: \"rest.streamUpstreamServerId\"\n              outputParameters:\n                - type: object\n                  mapping:\
  \ \"$.\"\n            - method: PATCH\n              name: modify-stream-upstream-server\n              description: \"Modify a stream upstream server configuration\"\n              call: \"nginx-plus-api.modify-stream-upstream-server\"\n              with:\n                streamUpstreamName: \"rest.streamUpstreamName\"\n                streamUpstreamServerId: \"rest.streamUpstreamServerId\"\n                body: \"rest.body\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: remove-stream-upstream-server\n              description: \"Remove a server from a stream upstream group\"\n              call: \"nginx-plus-api.remove-stream-upstream-server\"\n              with:\n                streamUpstreamName: \"rest.streamUpstreamName\"\n                streamUpstreamServerId: \"rest.streamUpstreamServerId\"\n              outputParameters:\n                - type: object\n             \
  \     mapping: \"$.\"\n\n    - type: mcp\n      port: 9200\n      namespace: nginx-traffic-management-mcp\n      transport: http\n      description: \"MCP server for AI-assisted NGINX traffic management and upstream configuration.\"\n      tools:\n        - name: get-http-upstreams\n          description: \"List all NGINX HTTP upstream server groups with health and traffic statistics\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"nginx-plus-api.get-http-upstreams\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-http-upstream-servers\n          description: \"List all servers in a specific NGINX HTTP upstream group with their configuration\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"nginx-plus-api.get-http-upstream-servers\"\n          with:\n            httpUpstreamName: \"tools.httpUpstreamName\"\n          outputParameters:\n\
  \            - type: array\n              mapping: \"$.\"\n        - name: add-http-upstream-server\n          description: \"Dynamically add a backend server to an NGINX HTTP upstream group for load balancing\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n            openWorld: false\n          call: \"nginx-plus-api.add-http-upstream-server\"\n          with:\n            httpUpstreamName: \"tools.httpUpstreamName\"\n            body: \"tools.body\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: modify-http-upstream-server\n          description: \"Modify configuration of an HTTP upstream server (weight, max_conns, backup, down status)\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n            openWorld: false\n          call: \"nginx-plus-api.modify-http-upstream-server\"\n          with:\n      \
  \      httpUpstreamName: \"tools.httpUpstreamName\"\n            httpUpstreamServerId: \"tools.httpUpstreamServerId\"\n            body: \"tools.body\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: remove-http-upstream-server\n          description: \"Remove a backend server from an NGINX HTTP upstream group\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n            openWorld: false\n          call: \"nginx-plus-api.remove-http-upstream-server\"\n          with:\n            httpUpstreamName: \"tools.httpUpstreamName\"\n            httpUpstreamServerId: \"tools.httpUpstreamServerId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-http-keyval-zone\n          description: \"Get key-value pairs from an HTTP keyval zone used for dynamic routing decisions\"\n          hints:\n            readOnly: true\n    \
  \        openWorld: false\n          call: \"nginx-plus-api.get-http-keyval-zone\"\n          with:\n            httpKeyvalZoneName: \"tools.httpKeyvalZoneName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: add-http-keyval\n          description: \"Add a key-value pair to an HTTP keyval zone for dynamic traffic routing\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n            openWorld: false\n          call: \"nginx-plus-api.add-http-keyval\"\n          with:\n            httpKeyvalZoneName: \"tools.httpKeyvalZoneName\"\n            body: \"tools.body\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: modify-http-keyval\n          description: \"Modify or delete a key-value pair in an HTTP keyval zone\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent:\
  \ true\n            openWorld: false\n          call: \"nginx-plus-api.modify-http-keyval\"\n          with:\n            httpKeyvalZoneName: \"tools.httpKeyvalZoneName\"\n            body: \"tools.body\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-stream-upstreams\n          description: \"List all NGINX stream (TCP/UDP) upstream server groups with health statistics\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"nginx-plus-api.get-stream-upstreams\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: add-stream-upstream-server\n          description: \"Dynamically add a server to a stream (TCP/UDP) upstream group\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n            openWorld: false\n          call: \"nginx-plus-api.add-stream-upstream-server\"\n   \
  \       with:\n            streamUpstreamName: \"tools.streamUpstreamName\"\n            body: \"tools.body\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: remove-stream-upstream-server\n          description: \"Remove a server from a stream (TCP/UDP) upstream group\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n            openWorld: false\n          call: \"nginx-plus-api.remove-stream-upstream-server\"\n          with:\n            streamUpstreamName: \"tools.streamUpstreamName\"\n            streamUpstreamServerId: \"tools.streamUpstreamServerId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
