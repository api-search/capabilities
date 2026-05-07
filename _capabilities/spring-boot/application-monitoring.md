---
categories: []
consumed_apis: []
description: Unified capability for monitoring and managing Spring Boot applications using Actuator endpoints. Enables health checks, metrics collection, log level management, and cache operations for DevOps and SRE workflows.
layout: capability
name: Spring Boot Application Monitoring
operations:
- description: Get comprehensive application health status
  method: GET
  name: get-health
  path: /v1/health
- description: Get health status for a specific component (db, redis, diskSpace)
  method: GET
  name: get-component-health
  path: /v1/health/{component}
- description: List all available metric names
  method: GET
  name: list-metrics
  path: /v1/metrics
- description: Get measurements for a specific metric
  method: GET
  name: get-metric
  path: /v1/metrics/{metricName}
- description: List all loggers and their levels
  method: GET
  name: list-loggers
  path: /v1/loggers
- description: Get logger level by name
  method: GET
  name: get-logger
  path: /v1/loggers/{name}
- description: Set logger level at runtime
  method: POST
  name: set-logger-level
  path: /v1/loggers/{name}
- description: Get all environment properties
  method: GET
  name: get-environment
  path: /v1/environment
- description: List all application caches
  method: GET
  name: list-caches
  path: /v1/caches
- description: Evict all caches
  method: DELETE
  name: evict-all-caches
  path: /v1/caches
personas: []
provider_name: Spring Boot
provider_slug: spring-boot
search_terms:
- devops
- logger configuration management
- get jvm metrics including memory usage, garbage collection, thread counts, and cpu usage
- web development
- individual logger management
- application metrics overview
- component-level health status
- auto configuration
- check health status for a specific application component (db, redis, diskspace, custom)
- get health
- embedded server
- set logger level at runtime
- application health monitoring
- spring boot
- set logger level
- list all micrometer metric names available on this spring boot instance
- get measurements for a specific metric
- health check
- get health status for a specific component (db, redis, diskspace)
- monitoring
- list available metrics
- get application info
- java
- cache management
- get logger
- dynamically adjust a logger's log level at runtime (trace, debug, info, warn, error, off) without application restart
- adjust log level
- get logger level by name
- observability
- get comprehensive application health status
- sre
- spring
- evict all application caches to force a full cache refresh
- detailed metric measurements
- get application metadata including build version, git commit info, and custom info contributors
- get jvm metrics
- evict all caches
- list all application caches
- get component health
- framework
- list all loggers and their levels
- get environment
- check the overall health of a spring boot application including all health indicator components (database, cache, disk space, custom indicators)
- get all active environment properties including system, application.properties, profile-specific, and command-line overrides
- list loggers
- metrics
- check component health
- rest api
- list metrics
- get all environment properties
- get environment properties
- list caches
- check application health
- microservices
- list all available metric names
- environment properties
- list all registered loggers and their current configured and effective log levels
- get metric
slug: application-monitoring
source_filename: application-monitoring.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Spring Boot Application Monitoring\n  description: Unified capability for monitoring and managing Spring Boot applications using Actuator endpoints. Enables health\n    checks, metrics collection, log level management, and cache operations for DevOps and SRE workflows.\n  tags:\n  - Spring Boot\n  - Monitoring\n  - Observability\n  - DevOps\n  - SRE\n  - Health Check\n  - Metrics\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SPRING_BOOT_ACTUATOR_BASE_URL: SPRING_BOOT_ACTUATOR_BASE_URL\ncapability:\n  consumes:\n  - type: http\n    namespace: spring-boot-actuator\n    baseUri: '{{SPRING_BOOT_ACTUATOR_BASE_URL}}'\n    description: Spring Boot Actuator management endpoints\n    resources:\n    - name: health\n      path: /health\n      description: Application health status\n      operations:\n      - name: get-health\n        method: GET\n        description: Get application health status\n  \
  \      outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-health-component\n        method: GET\n        description: Get health status for a specific component\n        inputParameters:\n        - name: component\n          in: path\n          type: string\n          required: true\n          description: Health component name (e.g., db, diskSpace)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: metrics\n      path: /metrics\n      description: Application metrics\n      operations:\n      - name: list-metrics\n        method: GET\n        description: List available metric names\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-metric\n        method: GET\n        description: Get metric measurements by name\n    \
  \    inputParameters:\n        - name: metricName\n          in: path\n          type: string\n          required: true\n          description: Metric name (e.g., jvm.memory.used)\n        - name: tag\n          in: query\n          type: array\n          required: false\n          description: Tag filter in KEY:VALUE format\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: environment\n      path: /env\n      description: Application environment properties\n      operations:\n      - name: get-environment\n        method: GET\n        description: Get all environment properties\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-environment-property\n        method: GET\n        description: Get specific environment property value\n        inputParameters:\n        - name: property\n          in: path\n\
  \          type: string\n          required: true\n          description: Property key\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: loggers\n      path: /loggers\n      description: Logger configuration management\n      operations:\n      - name: list-loggers\n        method: GET\n        description: List all loggers and their levels\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-logger\n        method: GET\n        description: Get logger level by name\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: Logger name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: set-logger-level\n        method: POST\n        description:\
  \ Set logger level at runtime\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: Logger name\n        body:\n          type: json\n          data:\n            configuredLevel: '{{tools.level}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: info\n      path: /info\n      description: Application information\n      operations:\n      - name: get-info\n        method: GET\n        description: Get application info\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: caches\n      path: /caches\n      description: Application cache management\n      operations:\n      - name: list-caches\n        method: GET\n        description: List application caches\n        outputRawFormat: json\n        outputParameters:\n        -\
  \ name: result\n          type: object\n          value: $.\n      - name: evict-all-caches\n        method: DELETE\n        description: Evict all caches\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: application-monitoring-api\n    description: Unified REST API for Spring Boot application monitoring and management.\n    resources:\n    - path: /v1/health\n      name: health\n      description: Application health monitoring\n      operations:\n      - method: GET\n        name: get-health\n        description: Get comprehensive application health status\n        call: spring-boot-actuator.get-health\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/health/{component}\n      name: component-health\n      description: Component-level health status\n      operations:\n      - method: GET\n        name: get-component-health\n\
  \        description: Get health status for a specific component (db, redis, diskSpace)\n        call: spring-boot-actuator.get-health-component\n        with:\n          component: rest.component\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/metrics\n      name: metrics\n      description: Application metrics overview\n      operations:\n      - method: GET\n        name: list-metrics\n        description: List all available metric names\n        call: spring-boot-actuator.list-metrics\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/metrics/{metricName}\n      name: metric-detail\n      description: Detailed metric measurements\n      operations:\n      - method: GET\n        name: get-metric\n        description: Get measurements for a specific metric\n        call: spring-boot-actuator.get-metric\n        with:\n          metricName: rest.metricName\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n    - path: /v1/loggers\n      name: loggers\n      description: Logger configuration management\n      operations:\n      - method: GET\n        name: list-loggers\n        description: List all loggers and their levels\n        call: spring-boot-actuator.list-loggers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/loggers/{name}\n      name: logger-detail\n      description: Individual logger management\n      operations:\n      - method: GET\n        name: get-logger\n        description: Get logger level by name\n        call: spring-boot-actuator.get-logger\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: set-logger-level\n        description: Set logger level at runtime\n        call: spring-boot-actuator.set-logger-level\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n    - path: /v1/environment\n      name: environment\n      description: Environment properties\n      operations:\n      - method: GET\n        name: get-environment\n        description: Get all environment properties\n        call: spring-boot-actuator.get-environment\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/caches\n      name: caches\n      description: Cache management\n      operations:\n      - method: GET\n        name: list-caches\n        description: List all application caches\n        call: spring-boot-actuator.list-caches\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: evict-all-caches\n        description: Evict all caches\n        call: spring-boot-actuator.evict-all-caches\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9080\n    namespace: application-monitoring-mcp\n    transport:\
  \ http\n    description: MCP server for AI-assisted Spring Boot application monitoring and incident response.\n    tools:\n    - name: check-application-health\n      description: Check the overall health of a Spring Boot application including all health indicator components (database,\n        cache, disk space, custom indicators)\n      hints:\n        readOnly: true\n        openWorld: false\n      call: spring-boot-actuator.get-health\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: check-component-health\n      description: Check health status for a specific application component (db, redis, diskSpace, custom)\n      hints:\n        readOnly: true\n        openWorld: false\n      call: spring-boot-actuator.get-health-component\n      with:\n        component: tools.component\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-jvm-metrics\n      description: Get JVM metrics including memory usage, garbage collection,\
  \ thread counts, and CPU usage\n      hints:\n        readOnly: true\n        openWorld: false\n      call: spring-boot-actuator.get-metric\n      with:\n        metricName: tools.metricName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-available-metrics\n      description: List all Micrometer metric names available on this Spring Boot instance\n      hints:\n        readOnly: true\n        openWorld: false\n      call: spring-boot-actuator.list-metrics\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-environment-properties\n      description: Get all active environment properties including system, application.properties, profile-specific, and command-line\n        overrides\n      hints:\n        readOnly: true\n        openWorld: false\n      call: spring-boot-actuator.get-environment\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: adjust-log-level\n      description: Dynamically\
  \ adjust a logger's log level at runtime (TRACE, DEBUG, INFO, WARN, ERROR, OFF) without application\n        restart\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: spring-boot-actuator.set-logger-level\n      with:\n        name: tools.loggerName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-loggers\n      description: List all registered loggers and their current configured and effective log levels\n      hints:\n        readOnly: true\n        openWorld: false\n      call: spring-boot-actuator.list-loggers\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-application-info\n      description: Get application metadata including build version, git commit info, and custom info contributors\n      hints:\n        readOnly: true\n        openWorld: false\n      call: spring-boot-actuator.get-info\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: evict-all-caches\n      description: Evict all application caches to force a full cache refresh\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: spring-boot-actuator.evict-all-caches\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/spring-boot/refs/heads/main/capabilities/application-monitoring.yaml
tags:
- Spring Boot
- Monitoring
- Observability
- DevOps
- SRE
- Health Check
- Metrics
tools:
- description: Check the overall health of a Spring Boot application including all health indicator components (database, cache, disk space, custom indicators)
  hints:
    openWorld: false
    readOnly: true
  name: check-application-health
- description: Check health status for a specific application component (db, redis, diskSpace, custom)
  hints:
    openWorld: false
    readOnly: true
  name: check-component-health
- description: Get JVM metrics including memory usage, garbage collection, thread counts, and CPU usage
  hints:
    openWorld: false
    readOnly: true
  name: get-jvm-metrics
- description: List all Micrometer metric names available on this Spring Boot instance
  hints:
    openWorld: false
    readOnly: true
  name: list-available-metrics
- description: Get all active environment properties including system, application.properties, profile-specific, and command-line overrides
  hints:
    openWorld: false
    readOnly: true
  name: get-environment-properties
- description: Dynamically adjust a logger's log level at runtime (TRACE, DEBUG, INFO, WARN, ERROR, OFF) without application restart
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: adjust-log-level
- description: List all registered loggers and their current configured and effective log levels
  hints:
    openWorld: false
    readOnly: true
  name: list-loggers
- description: Get application metadata including build version, git commit info, and custom info contributors
  hints:
    openWorld: false
    readOnly: true
  name: get-application-info
- description: Evict all application caches to force a full cache refresh
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: evict-all-caches
---
