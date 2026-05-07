---
categories:
- monitoring
consumed_apis: []
description: Workflow for monitoring WebSphere environments combining health checks, metrics, performance data, logging, and batch job tracking from Open Liberty and traditional WAS APIs for operations teams.
layout: capability
name: WebSphere Monitoring and Observability
operations:
- description: Get Open Liberty overall health
  method: GET
  name: get-liberty-health
  path: /v1/health
- description: Get WAS server health
  method: GET
  name: get-was-health
  path: /v1/health
- description: Get all Open Liberty metrics
  method: GET
  name: get-all-metrics
  path: /v1/metrics
- description: Get Liberty admin metrics
  method: GET
  name: get-liberty-metrics
  path: /v1/metrics
- description: Get WAS performance monitoring data
  method: GET
  name: get-performance-data
  path: /v1/performance
- description: Get Liberty log messages
  method: GET
  name: get-log-messages
  path: /v1/logs
- description: List batch job instances
  method: GET
  name: list-batch-jobs
  path: /v1/batch-jobs
personas: []
provider_name: IBM WebSphere
provider_slug: websphere
search_terms:
- get was health
- get open liberty overall health
- list batch jobs
- get open liberty overall health status
- get liberty log messages
- get liveness
- list batch job instances
- get was performance monitoring data
- middleware
- log management
- get was server health status
- get performance data
- get liberty admin metrics
- get liberty health
- j2ee
- metrics collection
- cloud native
- monitoring
- check if liberty server is alive
- check if liberty server is ready for traffic
- get batch job
- get readiness
- observability
- batch job monitoring
- health check endpoints
- get batch job instance details
- get all open liberty metrics
- performance data
- get liberty metrics
- get all metrics
- get liberty logging configuration
- list jakarta batch job instances
- metrics
- enterprise java
- get recent liberty log messages
- application server
- get log config
- get was server health
- get log messages
- microservices
- ibm websphere
slug: monitoring-and-observability
source_filename: monitoring-and-observability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: WebSphere Monitoring and Observability\n  description: Workflow for monitoring WebSphere environments combining health checks, metrics, performance data, logging,\n    and batch job tracking from Open Liberty and traditional WAS APIs for operations teams.\n  tags:\n  - IBM WebSphere\n  - Monitoring\n  - Observability\n  - Metrics\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    WEBSPHERE_USERNAME: WEBSPHERE_USERNAME\n    WEBSPHERE_PASSWORD: WEBSPHERE_PASSWORD\n    LIBERTY_USERNAME: LIBERTY_USERNAME\n    LIBERTY_PASSWORD: LIBERTY_PASSWORD\ncapability:\n  consumes:\n  - type: http\n    namespace: open-liberty\n    baseUri: https://localhost:9443\n    description: Open Liberty server APIs for health, metrics, batch, and configuration\n    authentication:\n      type: basic\n      username: '{{LIBERTY_USERNAME}}'\n      password: '{{LIBERTY_PASSWORD}}'\n    resources:\n    - name: health\n      path:\
  \ /health\n      description: MicroProfile Health Check API\n      operations:\n      - name: get-overall-health\n        method: GET\n        description: Get overall health status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-readiness\n        method: GET\n        description: Get readiness status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-liveness\n        method: GET\n        description: Get liveness status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-started\n        method: GET\n        description: Get startup status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: metrics\n      path: /metrics\n\
  \      description: MicroProfile Metrics API\n      operations:\n      - name: get-all-metrics\n        method: GET\n        description: Get all metrics\n        inputParameters:\n        - name: scope\n          in: query\n          type: string\n          required: false\n          description: Metrics scope filter\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-base-metrics\n        method: GET\n        description: Get base metrics\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-vendor-metrics\n        method: GET\n        description: Get vendor metrics\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-application-metrics\n        method: GET\n        description: Get application metrics\n   \
  \     outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: batch\n      path: /ibm/api/batch\n      description: Jakarta Batch job management\n      operations:\n      - name: list-batch-job-instances\n        method: GET\n        description: List batch job instances\n        inputParameters:\n        - name: jobName\n          in: query\n          type: string\n          required: false\n          description: Filter by job name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-batch-job-instance\n        method: GET\n        description: Get batch job instance details\n        inputParameters:\n        - name: jobInstanceId\n          in: path\n          type: integer\n          required: true\n          description: Job instance ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n      - name: list-batch-job-executions\n        method: GET\n        description: List job executions for an instance\n        inputParameters:\n        - name: jobInstanceId\n          in: path\n          type: integer\n          required: true\n          description: Job instance ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: stop-batch-job-execution\n        method: PUT\n        description: Stop a running batch job\n        inputParameters:\n        - name: executionId\n          in: path\n          type: integer\n          required: true\n          description: Execution ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: restart-batch-job-execution\n        method: PUT\n        description: Restart a failed batch job\n        inputParameters:\n \
  \       - name: executionId\n          in: path\n          type: integer\n          required: true\n          description: Execution ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: admin-rest\n    baseUri: https://localhost:9443/ibm/api\n    description: REST API for WebSphere Application Server administration\n    authentication:\n      type: basic\n      username: '{{WEBSPHERE_USERNAME}}'\n      password: '{{WEBSPHERE_PASSWORD}}'\n    resources:\n    - name: applications\n      path: /applications\n      description: Application deployment and lifecycle management\n      operations:\n      - name: list-applications\n        method: GET\n        description: List deployed applications\n        inputParameters:\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Filter by application status\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-application\n        method: GET\n        description: Get application details\n        inputParameters:\n        - name: appName\n          in: path\n          type: string\n          required: true\n          description: Application name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deploy-application\n        method: POST\n        description: Deploy a new application\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            contextRoot: '{{tools.contextRoot}}'\n            targetServer: '{{tools.targetServer}}'\n      - name: start-application\n        method: POST\n        description: Start a deployed\
  \ application\n        inputParameters:\n        - name: appName\n          in: path\n          type: string\n          required: true\n          description: Application name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: stop-application\n        method: POST\n        description: Stop a running application\n        inputParameters:\n        - name: appName\n          in: path\n          type: string\n          required: true\n          description: Application name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: uninstall-application\n        method: DELETE\n        description: Uninstall a deployed application\n        inputParameters:\n        - name: appName\n          in: path\n          type: string\n          required: true\n          description: Application name\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: servers\n      path: /servers\n      description: Server configuration and management\n      operations:\n      - name: list-servers\n        method: GET\n        description: List all servers in the cell\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-server\n        method: GET\n        description: Get server details\n        inputParameters:\n        - name: serverName\n          in: path\n          type: string\n          required: true\n          description: Server name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: start-server\n        method: POST\n        description: Start a server\n        inputParameters:\n        - name: serverName\n          in: path\n          type: string\n\
  \          required: true\n          description: Server name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: stop-server\n        method: POST\n        description: Stop a server\n        inputParameters:\n        - name: serverName\n          in: path\n          type: string\n          required: true\n          description: Server name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: clusters\n      path: /clusters\n      description: Cluster management operations\n      operations:\n      - name: list-clusters\n        method: GET\n        description: List all clusters\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-cluster\n        method: GET\n        description: Get cluster details\n        inputParameters:\n\
  \        - name: clusterName\n          in: path\n          type: string\n          required: true\n          description: Cluster name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: start-cluster\n        method: POST\n        description: Start all members of a cluster\n        inputParameters:\n        - name: clusterName\n          in: path\n          type: string\n          required: true\n          description: Cluster name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: stop-cluster\n        method: POST\n        description: Stop all members of a cluster\n        inputParameters:\n        - name: clusterName\n          in: path\n          type: string\n          required: true\n          description: Cluster name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n    - name: monitoring\n      path: /monitoring\n      description: Performance monitoring and health checks\n      operations:\n      - name: get-performance-data\n        method: GET\n        description: Get performance monitoring data\n        inputParameters:\n        - name: module\n          in: query\n          type: string\n          required: false\n          description: Performance module name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-health-status\n        method: GET\n        description: Get server health status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: configuration\n      path: /config\n      description: Server configuration management\n      operations:\n      - name: list-config-resources\n        method: GET\n        description:\
  \ List configuration resource types\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-config-resources\n        method: GET\n        description: List resources of a specific type\n        inputParameters:\n        - name: resourceType\n          in: path\n          type: string\n          required: true\n          description: Configuration resource type\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: liberty-admin\n    baseUri: https://localhost:9443/ibm/api\n    description: Liberty Admin REST API for server configuration and management\n    authentication:\n      type: basic\n      username: '{{LIBERTY_USERNAME}}'\n      password: '{{LIBERTY_PASSWORD}}'\n    resources:\n    - name: server\n      path: /server\n      description: Server runtime management\n      operations:\n   \
  \   - name: get-server-info\n        method: GET\n        description: Get Liberty server information\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-server-dump\n        method: POST\n        description: Create a server dump for diagnostics\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            include: '{{tools.include}}'\n      - name: create-java-dump\n        method: POST\n        description: Create a Java core dump\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: config\n      path: /config\n      description: Server configuration management\n      operations:\n      - name: get-server-config\n        method: GET\n        description: Get server configuration\n\
  \        inputParameters:\n        - name: depth\n          in: query\n          type: integer\n          required: false\n          description: Depth of nested elements\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-server-config\n        method: PUT\n        description: Update server configuration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-config-element\n        method: GET\n        description: Get a specific configuration element\n        inputParameters:\n        - name: elementName\n          in: path\n          type: string\n          required: true\n          description: Configuration element name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-config-element\n        method:\
  \ POST\n        description: Create a configuration element\n        inputParameters:\n        - name: elementName\n          in: path\n          type: string\n          required: true\n          description: Configuration element name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-config-element\n        method: DELETE\n        description: Delete a configuration element\n        inputParameters:\n        - name: elementName\n          in: path\n          type: string\n          required: true\n          description: Configuration element name\n        - name: uid\n          in: path\n          type: string\n          required: true\n          description: Element unique identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: applications\n      path: /applications\n      description: Application\
  \ deployment and lifecycle\n      operations:\n      - name: list-applications\n        method: GET\n        description: List deployed applications\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-application\n        method: GET\n        description: Get application details\n        inputParameters:\n        - name: appName\n          in: path\n          type: string\n          required: true\n          description: Application name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: start-application\n        method: POST\n        description: Start an application\n        inputParameters:\n        - name: appName\n          in: path\n          type: string\n          required: true\n          description: Application name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n      - name: stop-application\n        method: POST\n        description: Stop an application\n        inputParameters:\n        - name: appName\n          in: path\n          type: string\n          required: true\n          description: Application name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: restart-application\n        method: POST\n        description: Restart an application\n        inputParameters:\n        - name: appName\n          in: path\n          type: string\n          required: true\n          description: Application name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: features\n      path: /features\n      description: Liberty feature management\n      operations:\n      - name: list-features\n        method: GET\n        description:\
  \ List installed features\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-feature\n        method: GET\n        description: Get feature details\n        inputParameters:\n        - name: featureName\n          in: path\n          type: string\n          required: true\n          description: Feature symbolic name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: logging\n      path: /logging\n      description: Log access and configuration\n      operations:\n      - name: get-log-config\n        method: GET\n        description: Get logging configuration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-log-config\n        method: PUT\n        description: Update logging configuration\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-log-messages\n        method: GET\n        description: Get recent log messages\n        inputParameters:\n        - name: maxMessages\n          in: query\n          type: integer\n          required: false\n          description: Maximum messages to return\n        - name: level\n          in: query\n          type: string\n          required: false\n          description: Minimum log level\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: monitoring\n      path: /monitoring\n      description: Server monitoring and metrics\n      operations:\n      - name: get-metrics\n        method: GET\n        description: Get MicroProfile Metrics data\n        inputParameters:\n        - name: scope\n          in: query\n          type: string\n          required: false\n          description:\
  \ Metrics scope (base, vendor, application)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-health\n        method: GET\n        description: Get MicroProfile Health check results\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8083\n    namespace: monitoring-api\n    description: Unified REST API for WebSphere monitoring and observability.\n    resources:\n    - path: /v1/health\n      name: health\n      description: Health check endpoints\n      operations:\n      - method: GET\n        name: get-liberty-health\n        description: Get Open Liberty overall health\n        call: open-liberty.get-overall-health\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: get-was-health\n        description: Get WAS server health\n\
  \        call: admin-rest.get-health-status\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/metrics\n      name: metrics\n      description: Metrics collection\n      operations:\n      - method: GET\n        name: get-all-metrics\n        description: Get all Open Liberty metrics\n        call: open-liberty.get-all-metrics\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: get-liberty-metrics\n        description: Get Liberty admin metrics\n        call: liberty-admin.get-metrics\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/performance\n      name: performance\n      description: Performance data\n      operations:\n      - method: GET\n        name: get-performance-data\n        description: Get WAS performance monitoring data\n        call: admin-rest.get-performance-data\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /v1/logs\n      name: logs\n      description: Log management\n      operations:\n      - method: GET\n        name: get-log-messages\n        description: Get Liberty log messages\n        call: liberty-admin.get-log-messages\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/batch-jobs\n      name: batch-jobs\n      description: Batch job monitoring\n      operations:\n      - method: GET\n        name: list-batch-jobs\n        description: List batch job instances\n        call: open-liberty.list-batch-job-instances\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9093\n    namespace: monitoring-mcp\n    transport: http\n    description: MCP server for AI-assisted WebSphere monitoring.\n    tools:\n    - name: get-liberty-health\n      description: Get Open Liberty overall health status\n      hints:\n        readOnly: true\n      call: open-liberty.get-overall-health\n     \
  \ outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-readiness\n      description: Check if Liberty server is ready for traffic\n      hints:\n        readOnly: true\n      call: open-liberty.get-readiness\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-liveness\n      description: Check if Liberty server is alive\n      hints:\n        readOnly: true\n      call: open-liberty.get-liveness\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-was-health\n      description: Get WAS server health status\n      hints:\n        readOnly: true\n      call: admin-rest.get-health-status\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-all-metrics\n      description: Get all Open Liberty metrics\n      hints:\n        readOnly: true\n      call: open-liberty.get-all-metrics\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-performance-data\n\
  \      description: Get WAS performance monitoring data\n      hints:\n        readOnly: true\n      call: admin-rest.get-performance-data\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-log-messages\n      description: Get recent Liberty log messages\n      hints:\n        readOnly: true\n      call: liberty-admin.get-log-messages\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-log-config\n      description: Get Liberty logging configuration\n      hints:\n        readOnly: true\n      call: liberty-admin.get-log-config\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-batch-jobs\n      description: List Jakarta Batch job instances\n      hints:\n        readOnly: true\n      call: open-liberty.list-batch-job-instances\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-batch-job\n      description: Get batch job instance details\n      hints:\n\
  \        readOnly: true\n      call: open-liberty.get-batch-job-instance\n      with:\n        jobInstanceId: tools.jobInstanceId\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/websphere/refs/heads/main/capabilities/monitoring-and-observability.yaml
tags:
- IBM WebSphere
- Monitoring
- Observability
- Metrics
tools:
- description: Get Open Liberty overall health status
  hints:
    readOnly: true
  name: get-liberty-health
- description: Check if Liberty server is ready for traffic
  hints:
    readOnly: true
  name: get-readiness
- description: Check if Liberty server is alive
  hints:
    readOnly: true
  name: get-liveness
- description: Get WAS server health status
  hints:
    readOnly: true
  name: get-was-health
- description: Get all Open Liberty metrics
  hints:
    readOnly: true
  name: get-all-metrics
- description: Get WAS performance monitoring data
  hints:
    readOnly: true
  name: get-performance-data
- description: Get recent Liberty log messages
  hints:
    readOnly: true
  name: get-log-messages
- description: Get Liberty logging configuration
  hints:
    readOnly: true
  name: get-log-config
- description: List Jakarta Batch job instances
  hints:
    readOnly: true
  name: list-batch-jobs
- description: Get batch job instance details
  hints:
    readOnly: true
  name: get-batch-job
---
