---
categories: []
consumed_apis: []
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
- server lifecycle
- get server thread pool
- delete server
- jdbc data source management and monitoring
- start a configuration edit session to make domain changes
- domain administration
- get server health
- jms
- start a managed server
- get configuration for a specific weblogic managed server
- query diagnostics
- activate pending configuration changes across the domain
- cluster configuration management
- delete a server configuration
- get health status of a weblogic server
- middleware
- resume a suspended managed server
- get thread pool throughput and queue metrics for a server
- start edit
- query weblogic diagnostic data using wldf
- stop server
- list all cluster configurations
- shutdown server
- get server jvm metrics
- start server
- cancel the current edit session and discard changes
- list all managed servers in the weblogic domain
- list clusters
- list servers
- weblogic
- get server health status
- activate pending configuration changes
- cancel edit
- cancel the current edit session
- resume server
- list all jdbc data source configurations and metrics
- start edit session
- list all clusters in the weblogic domain
- get jvm heap and garbage collection metrics for a server
- cluster management
- get server
- create a new cluster configuration
- create a new managed server configuration in the domain
- jdbc
- enterprise
- start a configuration edit session
- test connectivity for a jdbc data source
- get server configuration
- gracefully shut down a managed server
- test data source
- test a jdbc data source connection
- java ee
- list all jdbc data source metrics
- create cluster
- start a managed server in the weblogic domain
- create a new managed server configuration
- delete a managed server configuration from the domain
- suspend a managed server (pause new requests)
- cancel edit session
- managed server configuration and lifecycle
- get server jvm and thread pool metrics
- application server
- list data sources
- create server
- list all server configurations in the domain
- shut down a managed server
- activate changes
- suspend server
- oracle
- get server metrics
slug: domain-administration
source_filename: domain-administration.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Oracle WebLogic Domain Administration\n  description: Unified capability for Oracle WebLogic Server domain administration combining domain configuration management,\n    server lifecycle control, and monitoring. Used by WebLogic administrators to manage entire domains, start/stop servers,\n    configure clusters, and manage data sources and JMS resources.\n  tags:\n  - Oracle\n  - WebLogic\n  - Domain Administration\n  - Server Lifecycle\n  - Cluster Management\n  - JDBC\n  - JMS\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    WEBLOGIC_ADMIN_USER: WEBLOGIC_ADMIN_USER\n    WEBLOGIC_ADMIN_PASSWORD: WEBLOGIC_ADMIN_PASSWORD\ncapability:\n  consumes:\n  - type: http\n    namespace: weblogic-management\n    baseUri: https://{host}:7001/management/weblogic/latest\n    description: WebLogic Server RESTful Management API\n    authentication:\n      type: basic\n      username: '{{WEBLOGIC_ADMIN_USER}}'\n\
  \      password: '{{WEBLOGIC_ADMIN_PASSWORD}}'\n    resources:\n    - name: edit-session\n      path: /edit/changeManager\n      description: Configuration edit session management\n      operations:\n      - name: start-edit\n        method: POST\n        description: Start an edit session\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: activate\n        method: POST\n        description: Activate pending configuration changes\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: cancel-edit\n        method: POST\n        description: Cancel the current edit session\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: edit-servers\n      path: /edit/servers\n      description: Server configuration management\n      operations:\n\
  \      - name: list-edit-servers\n        method: GET\n        description: List all server configurations\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-edit-server\n        method: POST\n        description: Create a new server configuration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            listenAddress: '{{tools.listenAddress}}'\n            listenPort: '{{tools.listenPort}}'\n      - name: get-edit-server\n        method: GET\n        description: Get a server configuration\n        inputParameters:\n        - name: serverName\n          in: path\n          type: string\n          required: true\n          description: Name of the server\n        outputRawFormat: json\n        outputParameters:\n       \
  \ - name: result\n          type: object\n          value: $.\n      - name: update-edit-server\n        method: POST\n        description: Update a server configuration\n        inputParameters:\n        - name: serverName\n          in: path\n          type: string\n          required: true\n          description: Name of the server\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-edit-server\n        method: DELETE\n        description: Delete a server configuration\n        inputParameters:\n        - name: serverName\n          in: path\n          type: string\n          required: true\n          description: Name of the server\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: edit-clusters\n      path: /edit/clusters\n      description: Cluster configuration management\n      operations:\n   \
  \   - name: list-edit-clusters\n        method: GET\n        description: List all cluster configurations\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-edit-cluster\n        method: POST\n        description: Create a new cluster configuration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: domain-config\n      path: /domainConfig\n      description: Read-only domain configuration\n      operations:\n      - name: get-domain-config\n        method: GET\n        description: Get domain configuration tree root\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-domain-servers\n        method: GET\n        description: List all server configurations (read-only)\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: server-lifecycle\n      path: /domainRuntime/serverLifeCycleRuntimes\n      description: Server lifecycle operations\n      operations:\n      - name: list-server-lifecycle\n        method: GET\n        description: List all server lifecycle runtimes\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: start-server\n        method: POST\n        description: Start a managed server\n        inputParameters:\n        - name: serverName\n          in: path\n          type: string\n          required: true\n          description: Name of the managed server\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: shutdown-server\n        method: POST\n        description: Shut down a managed server\n        inputParameters:\n        - name:\
  \ serverName\n          in: path\n          type: string\n          required: true\n          description: Name of the managed server\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: suspend-server\n        method: POST\n        description: Suspend a managed server\n        inputParameters:\n        - name: serverName\n          in: path\n          type: string\n          required: true\n          description: Name of the managed server\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: resume-server\n        method: POST\n        description: Resume a suspended managed server\n        inputParameters:\n        - name: serverName\n          in: path\n          type: string\n          required: true\n          description: Name of the managed server\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: weblogic-monitoring\n    baseUri: https://{host}:7001/management/wls/latest\n    description: WebLogic Server Monitoring and Diagnostics API\n    authentication:\n      type: basic\n      username: '{{WEBLOGIC_ADMIN_USER}}'\n      password: '{{WEBLOGIC_ADMIN_PASSWORD}}'\n    resources:\n    - name: servers\n      path: /servers\n      description: Server monitoring information\n      operations:\n      - name: list-servers\n        method: GET\n        description: List all monitored servers\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-server\n        method: GET\n        description: Get server monitoring information\n        inputParameters:\n        - name: serverName\n          in: path\n          type: string\n          required: true\n          description: Name of the server\n   \
  \     outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-server-health\n        method: GET\n        description: Get server health status\n        inputParameters:\n        - name: serverName\n          in: path\n          type: string\n          required: true\n          description: Name of the server\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-server-jvm\n        method: GET\n        description: Get server JVM metrics\n        inputParameters:\n        - name: serverName\n          in: path\n          type: string\n          required: true\n          description: Name of the server\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-server-thread-pool\n        method: GET\n        description: Get server\
  \ thread pool metrics\n        inputParameters:\n        - name: serverName\n          in: path\n          type: string\n          required: true\n          description: Name of the server\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: data-sources\n      path: /datasources\n      description: JDBC data source monitoring\n      operations:\n      - name: list-data-sources\n        method: GET\n        description: List all data source metrics\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-data-source\n        method: GET\n        description: Get data source metrics\n        inputParameters:\n        - name: dsName\n          in: path\n          type: string\n          required: true\n          description: Data source name\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n      - name: test-data-source\n        method: POST\n        description: Test a data source connection\n        inputParameters:\n        - name: dsName\n          in: path\n          type: string\n          required: true\n          description: Data source name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: diagnostics\n      path: /diagnostics\n      description: WebLogic Diagnostic Framework resources\n      operations:\n      - name: list-wldf-resources\n        method: GET\n        description: List WLDF system resources\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: query-diagnostic-data\n        method: POST\n        description: Query diagnostic data\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n   \
  \       type: object\n          value: $.\n        body:\n          type: json\n          data:\n            query: '{{tools.query}}'\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: weblogic-domain-api\n    description: Unified REST API for Oracle WebLogic domain administration.\n    resources:\n    - path: /v1/servers\n      name: servers\n      description: Managed server configuration and lifecycle\n      operations:\n      - method: GET\n        name: list-servers\n        description: List all server configurations in the domain\n        call: weblogic-management.list-edit-servers\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-server\n        description: Create a new managed server configuration\n        call: weblogic-management.create-edit-server\n        with:\n          name: rest.name\n          listenAddress: rest.listenAddress\n          listenPort: rest.listenPort\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /v1/servers/{serverName}\n      name: server\n      operations:\n      - method: GET\n        name: get-server\n        description: Get server configuration\n        call: weblogic-management.get-edit-server\n        with:\n          serverName: rest.serverName\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-server\n        description: Delete a server configuration\n        call: weblogic-management.delete-edit-server\n        with:\n          serverName: rest.serverName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/servers/{serverName}/start\n      name: server-start\n      operations:\n      - method: POST\n        name: start-server\n        description: Start a managed server\n        call: weblogic-management.start-server\n        with:\n          serverName: rest.serverName\n        outputParameters:\n \
  \       - type: object\n          mapping: $.\n    - path: /v1/servers/{serverName}/stop\n      name: server-stop\n      operations:\n      - method: POST\n        name: stop-server\n        description: Shut down a managed server\n        call: weblogic-management.shutdown-server\n        with:\n          serverName: rest.serverName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/servers/{serverName}/health\n      name: server-health\n      operations:\n      - method: GET\n        name: get-server-health\n        description: Get server health status\n        call: weblogic-monitoring.get-server-health\n        with:\n          serverName: rest.serverName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/servers/{serverName}/metrics\n      name: server-metrics\n      operations:\n      - method: GET\n        name: get-server-metrics\n        description: Get server JVM and thread pool metrics\n      \
  \  call: weblogic-monitoring.get-server-jvm\n        with:\n          serverName: rest.serverName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/clusters\n      name: clusters\n      description: Cluster configuration management\n      operations:\n      - method: GET\n        name: list-clusters\n        description: List all cluster configurations\n        call: weblogic-management.list-edit-clusters\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-cluster\n        description: Create a new cluster configuration\n        call: weblogic-management.create-edit-cluster\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/data-sources\n      name: data-sources\n      description: JDBC data source management and monitoring\n      operations:\n      - method: GET\n        name: list-data-sources\n        description: List all JDBC data source\
  \ metrics\n        call: weblogic-monitoring.list-data-sources\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/data-sources/{dsName}/test\n      name: data-source-test\n      operations:\n      - method: POST\n        name: test-data-source\n        description: Test a JDBC data source connection\n        call: weblogic-monitoring.test-data-source\n        with:\n          dsName: rest.dsName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/edit/start\n      name: edit-start\n      operations:\n      - method: POST\n        name: start-edit\n        description: Start a configuration edit session\n        call: weblogic-management.start-edit\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/edit/activate\n      name: edit-activate\n      operations:\n      - method: POST\n        name: activate-changes\n        description: Activate pending configuration changes\n\
  \        call: weblogic-management.activate\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/edit/cancel\n      name: edit-cancel\n      operations:\n      - method: POST\n        name: cancel-edit\n        description: Cancel the current edit session\n        call: weblogic-management.cancel-edit\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: weblogic-domain-mcp\n    transport: http\n    description: MCP server for AI-assisted Oracle WebLogic domain administration.\n    tools:\n    - name: list-servers\n      description: List all managed servers in the WebLogic domain\n      hints:\n        readOnly: true\n        openWorld: true\n      call: weblogic-management.list-edit-servers\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-server\n      description: Get configuration for a specific WebLogic managed server\n      hints:\n        readOnly:\
  \ true\n      call: weblogic-management.get-edit-server\n      with:\n        serverName: tools.serverName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-server\n      description: Create a new managed server configuration in the domain\n      hints:\n        readOnly: false\n      call: weblogic-management.create-edit-server\n      with:\n        name: tools.name\n        listenAddress: tools.listenAddress\n        listenPort: tools.listenPort\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-server\n      description: Delete a managed server configuration from the domain\n      hints:\n        destructive: true\n        idempotent: true\n      call: weblogic-management.delete-edit-server\n      with:\n        serverName: tools.serverName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: start-server\n      description: Start a managed server in the WebLogic domain\n      hints:\n\
  \        readOnly: false\n      call: weblogic-management.start-server\n      with:\n        serverName: tools.serverName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: shutdown-server\n      description: Gracefully shut down a managed server\n      hints:\n        destructive: true\n      call: weblogic-management.shutdown-server\n      with:\n        serverName: tools.serverName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: suspend-server\n      description: Suspend a managed server (pause new requests)\n      hints:\n        destructive: false\n      call: weblogic-management.suspend-server\n      with:\n        serverName: tools.serverName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: resume-server\n      description: Resume a suspended managed server\n      hints:\n        readOnly: false\n      call: weblogic-management.resume-server\n      with:\n        serverName: tools.serverName\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-server-health\n      description: Get health status of a WebLogic server\n      hints:\n        readOnly: true\n      call: weblogic-monitoring.get-server-health\n      with:\n        serverName: tools.serverName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-server-jvm-metrics\n      description: Get JVM heap and garbage collection metrics for a server\n      hints:\n        readOnly: true\n      call: weblogic-monitoring.get-server-jvm\n      with:\n        serverName: tools.serverName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-server-thread-pool\n      description: Get thread pool throughput and queue metrics for a server\n      hints:\n        readOnly: true\n      call: weblogic-monitoring.get-server-thread-pool\n      with:\n        serverName: tools.serverName\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: list-clusters\n      description: List all clusters in the WebLogic domain\n      hints:\n        readOnly: true\n      call: weblogic-management.list-edit-clusters\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-data-sources\n      description: List all JDBC data source configurations and metrics\n      hints:\n        readOnly: true\n      call: weblogic-monitoring.list-data-sources\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: test-data-source\n      description: Test connectivity for a JDBC data source\n      hints:\n        readOnly: false\n      call: weblogic-monitoring.test-data-source\n      with:\n        dsName: tools.dsName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: start-edit-session\n      description: Start a configuration edit session to make domain changes\n      hints:\n        readOnly: false\n      call: weblogic-management.start-edit\n  \
  \    outputParameters:\n      - type: object\n        mapping: $.\n    - name: activate-changes\n      description: Activate pending configuration changes across the domain\n      hints:\n        readOnly: false\n      call: weblogic-management.activate\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: cancel-edit-session\n      description: Cancel the current edit session and discard changes\n      hints:\n        destructive: true\n      call: weblogic-management.cancel-edit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: query-diagnostics\n      description: Query WebLogic diagnostic data using WLDF\n      hints:\n        readOnly: true\n      call: weblogic-monitoring.query-diagnostic-data\n      with:\n        query: tools.query\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
