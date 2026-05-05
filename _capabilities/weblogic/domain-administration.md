---
categories: []
consumed_apis:
- weblogic-management
- weblogic-monitoring
description: Unified capability for Oracle WebLogic Server domain administration combining domain configuration management, server lifecycle control, and monitoring. Used by WebLogic administrators to manage entire domains, start/stop servers, configure clusters, and manage data sources and JMS resources.
layout: capability
name: Oracle WebLogic Domain Administration
operations:
- description: List all server configurations in the domain
  method: GET
  name: list-servers
  path: /v1/servers
- description: Create a new managed server configuration
  method: POST
  name: create-server
  path: /v1/servers
- description: Get server configuration
  method: GET
  name: get-server
  path: /v1/servers/{serverName}
- description: Delete a server configuration
  method: DELETE
  name: delete-server
  path: /v1/servers/{serverName}
- description: Start a managed server
  method: POST
  name: start-server
  path: /v1/servers/{serverName}/start
- description: Shut down a managed server
  method: POST
  name: stop-server
  path: /v1/servers/{serverName}/stop
- description: Get server health status
  method: GET
  name: get-server-health
  path: /v1/servers/{serverName}/health
- description: Get server JVM and thread pool metrics
  method: GET
  name: get-server-metrics
  path: /v1/servers/{serverName}/metrics
- description: List all cluster configurations
  method: GET
  name: list-clusters
  path: /v1/clusters
- description: Create a new cluster configuration
  method: POST
  name: create-cluster
  path: /v1/clusters
- description: List all JDBC data source metrics
  method: GET
  name: list-data-sources
  path: /v1/data-sources
- description: Test a JDBC data source connection
  method: POST
  name: test-data-source
  path: /v1/data-sources/{dsName}/test
- description: Start a configuration edit session
  method: POST
  name: start-edit
  path: /v1/edit/start
- description: Activate pending configuration changes
  method: POST
  name: activate-changes
  path: /v1/edit/activate
- description: Cancel the current edit session
  method: POST
  name: cancel-edit
  path: /v1/edit/cancel
personas: []
provider_name: Oracle WebLogic Server APIs
provider_slug: weblogic
search_terms:
- create a new managed server configuration
- start server
- get server health status
- start a managed server in the weblogic domain
- cancel edit session
- start edit
- get server jvm metrics
- list all server configurations in the domain
- create server
- enterprise
- jms
- gracefully shut down a managed server
- application server
- start edit session
- server lifecycle
- cluster management
- delete a managed server configuration from the domain
- oracle
- shut down a managed server
- list all jdbc data source metrics
- list data sources
- test connectivity for a jdbc data source
- jdbc
- start a managed server
- get server metrics
- activate pending configuration changes
- get jvm heap and garbage collection metrics for a server
- list all cluster configurations
- cancel the current edit session
- query diagnostics
- middleware
- shutdown server
- query weblogic diagnostic data using wldf
- list all managed servers in the weblogic domain
- suspend a managed server (pause new requests)
- stop server
- delete server
- create a new managed server configuration in the domain
- cancel the current edit session and discard changes
- get server jvm and thread pool metrics
- get server
- start a configuration edit session
- list all jdbc data source configurations and metrics
- create cluster
- get configuration for a specific weblogic managed server
- test data source
- delete a server configuration
- get server configuration
- resume a suspended managed server
- get health status of a weblogic server
- get thread pool throughput and queue metrics for a server
- cluster configuration management
- activate pending configuration changes across the domain
- create a new cluster configuration
- activate changes
- weblogic
- list servers
- list clusters
- resume server
- jdbc data source management and monitoring
- start a configuration edit session to make domain changes
- cancel edit
- domain administration
- java ee
- get server thread pool
- test a jdbc data source connection
- suspend server
- get server health
- managed server configuration and lifecycle
- list all clusters in the weblogic domain
slug: domain-administration
source_filename: domain-administration.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Oracle WebLogic Domain Administration\"\n  description: >-\n    Unified capability for Oracle WebLogic Server domain administration combining\n    domain configuration management, server lifecycle control, and monitoring.\n    Used by WebLogic administrators to manage entire domains, start/stop servers,\n    configure clusters, and manage data sources and JMS resources.\n  tags:\n    - Oracle\n    - WebLogic\n    - Domain Administration\n    - Server Lifecycle\n    - Cluster Management\n    - JDBC\n    - JMS\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      WEBLOGIC_ADMIN_USER: WEBLOGIC_ADMIN_USER\n      WEBLOGIC_ADMIN_PASSWORD: WEBLOGIC_ADMIN_PASSWORD\n\ncapability:\n  consumes:\n    - import: weblogic-management\n      location: ./shared/weblogic-management.yaml\n    - import: weblogic-monitoring\n      location: ./shared/weblogic-monitoring.yaml\n\n  exposes:\n    - type:\
  \ rest\n      port: 8080\n      namespace: weblogic-domain-api\n      description: \"Unified REST API for Oracle WebLogic domain administration.\"\n      resources:\n        - path: /v1/servers\n          name: servers\n          description: \"Managed server configuration and lifecycle\"\n          operations:\n            - method: GET\n              name: list-servers\n              description: \"List all server configurations in the domain\"\n              call: \"weblogic-management.list-edit-servers\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-server\n              description: \"Create a new managed server configuration\"\n              call: \"weblogic-management.create-edit-server\"\n              with:\n                name: \"rest.name\"\n                listenAddress: \"rest.listenAddress\"\n                listenPort: \"rest.listenPort\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/servers/{serverName}\n          name: server\n          operations:\n            - method: GET\n              name: get-server\n              description: \"Get server configuration\"\n              call: \"weblogic-management.get-edit-server\"\n              with:\n                serverName: \"rest.serverName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-server\n              description: \"Delete a server configuration\"\n              call: \"weblogic-management.delete-edit-server\"\n              with:\n                serverName: \"rest.serverName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/servers/{serverName}/start\n          name: server-start\n          operations:\n            - method: POST\n \
  \             name: start-server\n              description: \"Start a managed server\"\n              call: \"weblogic-management.start-server\"\n              with:\n                serverName: \"rest.serverName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/servers/{serverName}/stop\n          name: server-stop\n          operations:\n            - method: POST\n              name: stop-server\n              description: \"Shut down a managed server\"\n              call: \"weblogic-management.shutdown-server\"\n              with:\n                serverName: \"rest.serverName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/servers/{serverName}/health\n          name: server-health\n          operations:\n            - method: GET\n              name: get-server-health\n              description: \"Get server health status\"\n  \
  \            call: \"weblogic-monitoring.get-server-health\"\n              with:\n                serverName: \"rest.serverName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/servers/{serverName}/metrics\n          name: server-metrics\n          operations:\n            - method: GET\n              name: get-server-metrics\n              description: \"Get server JVM and thread pool metrics\"\n              call: \"weblogic-monitoring.get-server-jvm\"\n              with:\n                serverName: \"rest.serverName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/clusters\n          name: clusters\n          description: \"Cluster configuration management\"\n          operations:\n            - method: GET\n              name: list-clusters\n              description: \"List all cluster configurations\"\n              call: \"weblogic-management.list-edit-clusters\"\
  \n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-cluster\n              description: \"Create a new cluster configuration\"\n              call: \"weblogic-management.create-edit-cluster\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/data-sources\n          name: data-sources\n          description: \"JDBC data source management and monitoring\"\n          operations:\n            - method: GET\n              name: list-data-sources\n              description: \"List all JDBC data source metrics\"\n              call: \"weblogic-monitoring.list-data-sources\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/data-sources/{dsName}/test\n          name: data-source-test\n          operations:\n            - method: POST\n           \
  \   name: test-data-source\n              description: \"Test a JDBC data source connection\"\n              call: \"weblogic-monitoring.test-data-source\"\n              with:\n                dsName: \"rest.dsName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/edit/start\n          name: edit-start\n          operations:\n            - method: POST\n              name: start-edit\n              description: \"Start a configuration edit session\"\n              call: \"weblogic-management.start-edit\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/edit/activate\n          name: edit-activate\n          operations:\n            - method: POST\n              name: activate-changes\n              description: \"Activate pending configuration changes\"\n              call: \"weblogic-management.activate\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/edit/cancel\n          name: edit-cancel\n          operations:\n            - method: POST\n              name: cancel-edit\n              description: \"Cancel the current edit session\"\n              call: \"weblogic-management.cancel-edit\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: weblogic-domain-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Oracle WebLogic domain administration.\"\n      tools:\n        - name: list-servers\n          description: \"List all managed servers in the WebLogic domain\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"weblogic-management.list-edit-servers\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-server\n  \
  \        description: \"Get configuration for a specific WebLogic managed server\"\n          hints:\n            readOnly: true\n          call: \"weblogic-management.get-edit-server\"\n          with:\n            serverName: \"tools.serverName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-server\n          description: \"Create a new managed server configuration in the domain\"\n          hints:\n            readOnly: false\n          call: \"weblogic-management.create-edit-server\"\n          with:\n            name: \"tools.name\"\n            listenAddress: \"tools.listenAddress\"\n            listenPort: \"tools.listenPort\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: delete-server\n          description: \"Delete a managed server configuration from the domain\"\n          hints:\n            destructive: true\n            idempotent: true\n      \
  \    call: \"weblogic-management.delete-edit-server\"\n          with:\n            serverName: \"tools.serverName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: start-server\n          description: \"Start a managed server in the WebLogic domain\"\n          hints:\n            readOnly: false\n          call: \"weblogic-management.start-server\"\n          with:\n            serverName: \"tools.serverName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: shutdown-server\n          description: \"Gracefully shut down a managed server\"\n          hints:\n            destructive: true\n          call: \"weblogic-management.shutdown-server\"\n          with:\n            serverName: \"tools.serverName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: suspend-server\n          description: \"Suspend a managed server\
  \ (pause new requests)\"\n          hints:\n            destructive: false\n          call: \"weblogic-management.suspend-server\"\n          with:\n            serverName: \"tools.serverName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: resume-server\n          description: \"Resume a suspended managed server\"\n          hints:\n            readOnly: false\n          call: \"weblogic-management.resume-server\"\n          with:\n            serverName: \"tools.serverName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-server-health\n          description: \"Get health status of a WebLogic server\"\n          hints:\n            readOnly: true\n          call: \"weblogic-monitoring.get-server-health\"\n          with:\n            serverName: \"tools.serverName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n      \
  \  - name: get-server-jvm-metrics\n          description: \"Get JVM heap and garbage collection metrics for a server\"\n          hints:\n            readOnly: true\n          call: \"weblogic-monitoring.get-server-jvm\"\n          with:\n            serverName: \"tools.serverName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-server-thread-pool\n          description: \"Get thread pool throughput and queue metrics for a server\"\n          hints:\n            readOnly: true\n          call: \"weblogic-monitoring.get-server-thread-pool\"\n          with:\n            serverName: \"tools.serverName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-clusters\n          description: \"List all clusters in the WebLogic domain\"\n          hints:\n            readOnly: true\n          call: \"weblogic-management.list-edit-clusters\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n\n        - name: list-data-sources\n          description: \"List all JDBC data source configurations and metrics\"\n          hints:\n            readOnly: true\n          call: \"weblogic-monitoring.list-data-sources\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: test-data-source\n          description: \"Test connectivity for a JDBC data source\"\n          hints:\n            readOnly: false\n          call: \"weblogic-monitoring.test-data-source\"\n          with:\n            dsName: \"tools.dsName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: start-edit-session\n          description: \"Start a configuration edit session to make domain changes\"\n          hints:\n            readOnly: false\n          call: \"weblogic-management.start-edit\"\n          outputParameters:\n            - type: object\n\
  \              mapping: \"$.\"\n\n        - name: activate-changes\n          description: \"Activate pending configuration changes across the domain\"\n          hints:\n            readOnly: false\n          call: \"weblogic-management.activate\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: cancel-edit-session\n          description: \"Cancel the current edit session and discard changes\"\n          hints:\n            destructive: true\n          call: \"weblogic-management.cancel-edit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: query-diagnostics\n          description: \"Query WebLogic diagnostic data using WLDF\"\n          hints:\n            readOnly: true\n          call: \"weblogic-monitoring.query-diagnostic-data\"\n          with:\n            query: \"tools.query\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\
  \n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/weblogic/refs/heads/main/capabilities/domain-administration.yaml
tags:
- Oracle
- WebLogic
- Domain Administration
- Server Lifecycle
- Cluster Management
- JDBC
- JMS
tools:
- description: List all managed servers in the WebLogic domain
  hints:
    openWorld: true
    readOnly: true
  name: list-servers
- description: Get configuration for a specific WebLogic managed server
  hints:
    readOnly: true
  name: get-server
- description: Create a new managed server configuration in the domain
  hints:
    readOnly: false
  name: create-server
- description: Delete a managed server configuration from the domain
  hints:
    destructive: true
    idempotent: true
  name: delete-server
- description: Start a managed server in the WebLogic domain
  hints:
    readOnly: false
  name: start-server
- description: Gracefully shut down a managed server
  hints:
    destructive: true
  name: shutdown-server
- description: Suspend a managed server (pause new requests)
  hints:
    destructive: false
  name: suspend-server
- description: Resume a suspended managed server
  hints:
    readOnly: false
  name: resume-server
- description: Get health status of a WebLogic server
  hints:
    readOnly: true
  name: get-server-health
- description: Get JVM heap and garbage collection metrics for a server
  hints:
    readOnly: true
  name: get-server-jvm-metrics
- description: Get thread pool throughput and queue metrics for a server
  hints:
    readOnly: true
  name: get-server-thread-pool
- description: List all clusters in the WebLogic domain
  hints:
    readOnly: true
  name: list-clusters
- description: List all JDBC data source configurations and metrics
  hints:
    readOnly: true
  name: list-data-sources
- description: Test connectivity for a JDBC data source
  hints:
    readOnly: false
  name: test-data-source
- description: Start a configuration edit session to make domain changes
  hints:
    readOnly: false
  name: start-edit-session
- description: Activate pending configuration changes across the domain
  hints:
    readOnly: false
  name: activate-changes
- description: Cancel the current edit session and discard changes
  hints:
    destructive: true
  name: cancel-edit-session
- description: Query WebLogic diagnostic data using WLDF
  hints:
    readOnly: true
  name: query-diagnostics
---
