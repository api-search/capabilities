---
categories: []
consumed_apis: []
description: Workflow capability for monitoring and observing Spring Boot 3 applications using Actuator endpoints. Provides unified access to health status, JVM and application metrics, environment configuration, logger management, and thread diagnostics for platform engineers and SREs.
layout: capability
name: Spring Boot 3 Application Observability
operations:
- description: Get overall application health
  method: GET
  name: get-health
  path: /v1/health
- description: Get health for a specific component
  method: GET
  name: get-component-health
  path: /v1/health/{component}
- description: Get application information
  method: GET
  name: get-info
  path: /v1/info
- description: List all available metric names
  method: GET
  name: list-metrics
  path: /v1/metrics
- description: Get measurements for a named metric
  method: GET
  name: get-metric
  path: /v1/metrics/{metricName}
- description: Get all environment properties
  method: GET
  name: get-environment
  path: /v1/env
- description: List all loggers with their levels
  method: GET
  name: list-loggers
  path: /v1/loggers
- description: Get logger configuration
  method: GET
  name: get-logger
  path: /v1/loggers/{name}
- description: Set logger level at runtime
  method: POST
  name: set-logger-level
  path: /v1/loggers/{name}
- description: Get JVM thread dump
  method: GET
  name: get-thread-dump
  path: /v1/threads
- description: List all scheduled tasks
  method: GET
  name: get-scheduled-tasks
  path: /v1/scheduled-tasks
personas: []
provider_name: Spring Boot 3
provider_slug: spring-boot-3
search_terms:
- check health status for a specific component like db, redis, diskspace, or rabbit
- jvm thread diagnostics
- check the overall health of the spring boot application including database, cache, and infrastructure components
- look up the value and origin of a specific configuration property by key
- application build and git metadata
- rest api
- list all @scheduled tasks with their cron expressions or fixed-rate intervals
- set logger level
- get thread dump
- java
- list loggers
- inspect environment
- platform engineering
- list all available metric names
- list all scheduled tasks
- framework
- get all environment properties
- get scheduled tasks
- check app health
- logger configuration
- monitoring
- enterprise
- list all available micrometer metrics registered in this application
- single metric measurements with tag filtering
- get measurements for a named metric
- get logger configuration
- get component health
- check component health
- scheduled task registry
- micrometer metrics list
- get app info
- inspect all application environment properties and their sources to diagnose configuration issues
- set logger level at runtime
- spring boot
- get application information
- get the current log level configuration for a specific logger class or package
- observability
- lookup property
- get info
- individual logger management
- application environment and configuration
- list metrics
- application and component health status
- get jvm thread dump
- get application build version, git commit hash, and runtime environment information
- get a jvm thread dump to diagnose deadlocks, high cpu usage, or thread starvation
- list all loggers with their configured and effective log levels for debugging
- get logger
- get current measurements for a metric such as jvm.memory.used, http.server.requests, or hikaricp.connections.active
- get metric
- sre
- individual component health
- get overall application health
- get environment
- temporarily set the log level for a logger (trace, debug, info, warn, error) without restarting
- microservices
- get health for a specific component
- get health
- list all loggers with their levels
slug: application-observability
source_filename: application-observability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Spring Boot 3 Application Observability\n  description: Workflow capability for monitoring and observing Spring Boot 3 applications using Actuator endpoints. Provides\n    unified access to health status, JVM and application metrics, environment configuration, logger management, and thread\n    diagnostics for platform engineers and SREs.\n  tags:\n  - Spring Boot\n  - Observability\n  - Monitoring\n  - SRE\n  - Platform Engineering\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SPRING_BOOT_BASE_URL: SPRING_BOOT_BASE_URL\ncapability:\n  consumes:\n  - type: http\n    namespace: spring-boot-actuator\n    baseUri: '{{env.SPRING_BOOT_BASE_URL}}/actuator'\n    description: Spring Boot 3 Actuator management and monitoring endpoints\n    resources:\n    - name: health\n      path: /health\n      description: Application health status aggregated from all health indicators\n      operations:\n      -\
  \ name: get-health\n        method: GET\n        description: Get overall application health status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-health-component\n        method: GET\n        description: Get health status for a specific component\n        inputParameters:\n        - name: component\n          in: path\n          type: string\n          required: true\n          description: Component name (e.g., db, diskSpace, redis)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: info\n      path: /info\n      description: Application metadata from InfoContributors\n      operations:\n      - name: get-info\n        method: GET\n        description: Get application build, git, and environment info\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n    - name: metrics\n      path: /metrics\n      description: Micrometer application metrics\n      operations:\n      - name: list-metrics\n        method: GET\n        description: List all registered metric names\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-metric\n        method: GET\n        description: Get measurements for a specific metric\n        inputParameters:\n        - name: metricName\n          in: path\n          type: string\n          required: true\n          description: Metric name (e.g., jvm.memory.used)\n        - name: tag\n          in: query\n          type: string\n          required: false\n          description: Tag filter in name:value format\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: environment\n      path: /env\n      description:\
  \ Application environment properties\n      operations:\n      - name: get-environment\n        method: GET\n        description: Get all environment properties grouped by source\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-environment-property\n        method: GET\n        description: Get value and origin of a specific property\n        inputParameters:\n        - name: toMatch\n          in: path\n          type: string\n          required: true\n          description: Property key to look up\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: loggers\n      path: /loggers\n      description: Runtime logger level configuration\n      operations:\n      - name: list-loggers\n        method: GET\n        description: List all loggers with their configured and effective levels\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-logger\n        method: GET\n        description: Get the configuration for a specific logger\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: Logger name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: set-logger-level\n        method: POST\n        description: Set the log level for a logger at runtime\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: Logger name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            configuredLevel: '{{tools.level}}'\n\
  \    - name: threaddump\n      path: /threaddump\n      description: JVM thread dump for diagnostics\n      operations:\n      - name: get-thread-dump\n        method: GET\n        description: Get a snapshot of all live JVM threads\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: scheduledtasks\n      path: /scheduledtasks\n      description: Scheduled task registry\n      operations:\n      - name: get-scheduled-tasks\n        method: GET\n        description: List all registered @Scheduled tasks\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: observability-api\n    description: Unified REST API for Spring Boot 3 application observability.\n    resources:\n    - path: /v1/health\n      name: health\n      description: Application and component health status\n\
  \      operations:\n      - method: GET\n        name: get-health\n        description: Get overall application health\n        call: spring-boot-actuator.get-health\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/health/{component}\n      name: component-health\n      description: Individual component health\n      operations:\n      - method: GET\n        name: get-component-health\n        description: Get health for a specific component\n        call: spring-boot-actuator.get-health-component\n        with:\n          component: rest.component\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/info\n      name: info\n      description: Application build and git metadata\n      operations:\n      - method: GET\n        name: get-info\n        description: Get application information\n        call: spring-boot-actuator.get-info\n        outputParameters:\n        - type: object\n          mapping: $.\n\
  \    - path: /v1/metrics\n      name: metrics\n      description: Micrometer metrics list\n      operations:\n      - method: GET\n        name: list-metrics\n        description: List all available metric names\n        call: spring-boot-actuator.list-metrics\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/metrics/{metricName}\n      name: metric-detail\n      description: Single metric measurements with tag filtering\n      operations:\n      - method: GET\n        name: get-metric\n        description: Get measurements for a named metric\n        call: spring-boot-actuator.get-metric\n        with:\n          metricName: rest.metricName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/env\n      name: environment\n      description: Application environment and configuration\n      operations:\n      - method: GET\n        name: get-environment\n        description: Get all environment properties\n \
  \       call: spring-boot-actuator.get-environment\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/loggers\n      name: loggers\n      description: Logger configuration\n      operations:\n      - method: GET\n        name: list-loggers\n        description: List all loggers with their levels\n        call: spring-boot-actuator.list-loggers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/loggers/{name}\n      name: logger-detail\n      description: Individual logger management\n      operations:\n      - method: GET\n        name: get-logger\n        description: Get logger configuration\n        call: spring-boot-actuator.get-logger\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: set-logger-level\n        description: Set logger level at runtime\n        call: spring-boot-actuator.set-logger-level\n\
  \        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/threads\n      name: threads\n      description: JVM thread diagnostics\n      operations:\n      - method: GET\n        name: get-thread-dump\n        description: Get JVM thread dump\n        call: spring-boot-actuator.get-thread-dump\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/scheduled-tasks\n      name: scheduled-tasks\n      description: Scheduled task registry\n      operations:\n      - method: GET\n        name: get-scheduled-tasks\n        description: List all scheduled tasks\n        call: spring-boot-actuator.get-scheduled-tasks\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: observability-mcp\n    transport: http\n    description: MCP server for AI-assisted Spring Boot 3 application observability and diagnostics.\n    tools:\n\
  \    - name: check-app-health\n      description: Check the overall health of the Spring Boot application including database, cache, and infrastructure components\n      hints:\n        readOnly: true\n        openWorld: true\n      call: spring-boot-actuator.get-health\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: check-component-health\n      description: Check health status for a specific component like db, redis, diskSpace, or rabbit\n      hints:\n        readOnly: true\n        openWorld: true\n      call: spring-boot-actuator.get-health-component\n      with:\n        component: tools.component\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-app-info\n      description: Get application build version, git commit hash, and runtime environment information\n      hints:\n        readOnly: true\n        openWorld: true\n      call: spring-boot-actuator.get-info\n      outputParameters:\n      - type: object\n   \
  \     mapping: $.\n    - name: list-metrics\n      description: List all available Micrometer metrics registered in this application\n      hints:\n        readOnly: true\n        openWorld: true\n      call: spring-boot-actuator.list-metrics\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-metric\n      description: Get current measurements for a metric such as jvm.memory.used, http.server.requests, or hikaricp.connections.active\n      hints:\n        readOnly: true\n        openWorld: true\n      call: spring-boot-actuator.get-metric\n      with:\n        metricName: tools.metricName\n        tag: tools.tag\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: inspect-environment\n      description: Inspect all application environment properties and their sources to diagnose configuration issues\n      hints:\n        readOnly: true\n        openWorld: true\n      call: spring-boot-actuator.get-environment\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: lookup-property\n      description: Look up the value and origin of a specific configuration property by key\n      hints:\n        readOnly: true\n        openWorld: true\n      call: spring-boot-actuator.get-environment-property\n      with:\n        toMatch: tools.propertyKey\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-loggers\n      description: List all loggers with their configured and effective log levels for debugging\n      hints:\n        readOnly: true\n        openWorld: true\n      call: spring-boot-actuator.list-loggers\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-logger\n      description: Get the current log level configuration for a specific logger class or package\n      hints:\n        readOnly: true\n        openWorld: true\n      call: spring-boot-actuator.get-logger\n      with:\n        name: tools.loggerName\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: set-logger-level\n      description: Temporarily set the log level for a logger (TRACE, DEBUG, INFO, WARN, ERROR) without restarting\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: spring-boot-actuator.set-logger-level\n      with:\n        name: tools.loggerName\n        level: tools.level\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-thread-dump\n      description: Get a JVM thread dump to diagnose deadlocks, high CPU usage, or thread starvation\n      hints:\n        readOnly: true\n        openWorld: true\n      call: spring-boot-actuator.get-thread-dump\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-scheduled-tasks\n      description: List all @Scheduled tasks with their cron expressions or fixed-rate intervals\n      hints:\n        readOnly: true\n        openWorld: true\n      call: spring-boot-actuator.get-scheduled-tasks\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/spring-boot-3/refs/heads/main/capabilities/application-observability.yaml
tags:
- Spring Boot
- Observability
- Monitoring
- SRE
- Platform Engineering
tools:
- description: Check the overall health of the Spring Boot application including database, cache, and infrastructure components
  hints:
    openWorld: true
    readOnly: true
  name: check-app-health
- description: Check health status for a specific component like db, redis, diskSpace, or rabbit
  hints:
    openWorld: true
    readOnly: true
  name: check-component-health
- description: Get application build version, git commit hash, and runtime environment information
  hints:
    openWorld: true
    readOnly: true
  name: get-app-info
- description: List all available Micrometer metrics registered in this application
  hints:
    openWorld: true
    readOnly: true
  name: list-metrics
- description: Get current measurements for a metric such as jvm.memory.used, http.server.requests, or hikaricp.connections.active
  hints:
    openWorld: true
    readOnly: true
  name: get-metric
- description: Inspect all application environment properties and their sources to diagnose configuration issues
  hints:
    openWorld: true
    readOnly: true
  name: inspect-environment
- description: Look up the value and origin of a specific configuration property by key
  hints:
    openWorld: true
    readOnly: true
  name: lookup-property
- description: List all loggers with their configured and effective log levels for debugging
  hints:
    openWorld: true
    readOnly: true
  name: list-loggers
- description: Get the current log level configuration for a specific logger class or package
  hints:
    openWorld: true
    readOnly: true
  name: get-logger
- description: Temporarily set the log level for a logger (TRACE, DEBUG, INFO, WARN, ERROR) without restarting
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: set-logger-level
- description: Get a JVM thread dump to diagnose deadlocks, high CPU usage, or thread starvation
  hints:
    openWorld: true
    readOnly: true
  name: get-thread-dump
- description: List all @Scheduled tasks with their cron expressions or fixed-rate intervals
  hints:
    openWorld: true
    readOnly: true
  name: get-scheduled-tasks
---
