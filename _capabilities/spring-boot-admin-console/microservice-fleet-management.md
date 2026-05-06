---
categories: []
consumed_apis: []
description: Workflow capability for managing and monitoring a fleet of Spring Boot microservices via Spring Boot Admin. Provides unified visibility into application health, instance lifecycle, real-time metrics, logger management, and environment inspection across all registered services. Designed for platform engineers and SREs managing Spring Boot microservice deployments.
layout: capability
name: Spring Boot Admin Microservice Fleet Management
operations:
- description: List all registered applications with instance counts and status
  method: GET
  name: list-applications
  path: /v1/applications
- description: Get all instances for a named application
  method: GET
  name: get-application
  path: /v1/applications/{name}
- description: Deregister all instances of an application
  method: DELETE
  name: deregister-application
  path: /v1/applications/{name}
- description: List all registered instances with optional app filter
  method: GET
  name: list-instances
  path: /v1/instances
- description: Get full instance details
  method: GET
  name: get-instance
  path: /v1/instances/{id}
- description: Deregister an instance
  method: DELETE
  name: deregister-instance
  path: /v1/instances/{id}
- description: Get health status from instance Actuator
  method: GET
  name: get-instance-health
  path: /v1/instances/{id}/health
- description: Get available metrics for an instance
  method: GET
  name: get-instance-metrics
  path: /v1/instances/{id}/metrics
- description: Get environment properties for an instance
  method: GET
  name: get-instance-environment
  path: /v1/instances/{id}/env
- description: Get logger configuration for an instance
  method: GET
  name: get-instance-loggers
  path: /v1/instances/{id}/loggers
- description: Set logger level for an instance at runtime
  method: POST
  name: set-instance-logger-level
  path: /v1/instances/{id}/loggers
personas: []
provider_name: Spring Boot Admin Console
provider_slug: spring-boot-admin-console
search_terms:
- registered application fleet overview
- instance micrometer metrics
- get current logger levels for a specific microservice instance to diagnose logging issues
- get instance loggers
- deregister application
- deregister an instance
- instance environment configuration
- list all registered applications with instance counts and status
- java
- get comprehensive details for a specific microservice instance by its admin id
- get available micrometer metrics for a specific microservice instance
- deregister instance
- inspect instance environment
- instance logger management
- individual application instances
- check instance health
- inspect all environment properties and configuration for a specific microservice instance
- deregister and remove a specific microservice instance from the admin server
- get health status from instance actuator
- get all instances for a named application
- actuator
- monitoring
- get logger configuration for an instance
- fleet management
- get details and all running instances for a specific application by name
- list instances
- spring boot admin
- get full instance details
- list all spring boot applications registered with the admin server, including their health status and instance count
- spring boot
- instance health status
- observability
- list all registered instances with optional app filter
- get build version, git commit, and runtime info for a specific microservice instance
- set instance logger level
- check the live health status of a specific microservice instance by proxying its actuator health endpoint
- administration
- get instance environment
- set logger level for an instance at runtime
- get instance metrics
- get instance health
- get available metrics for an instance
- deregister all instances of an application
- change the log level for a logger on a specific instance at runtime without restart (e.g., set debug for a troublesome service)
- get instance info
- single instance management
- specific application details
- get application
- get environment properties for an instance
- sre
- list applications
- microservices
- get instance
- list all registered microservice instances, optionally filtered by application name
slug: microservice-fleet-management
source_filename: microservice-fleet-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Spring Boot Admin Microservice Fleet Management\n  description: Workflow capability for managing and monitoring a fleet of Spring Boot microservices via Spring Boot Admin.\n    Provides unified visibility into application health, instance lifecycle, real-time metrics, logger management, and environment\n    inspection across all registered services. Designed for platform engineers and SREs managing Spring Boot microservice\n    deployments.\n  tags:\n  - Spring Boot Admin\n  - Fleet Management\n  - Microservices\n  - SRE\n  - Observability\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SPRING_BOOT_ADMIN_URL: SPRING_BOOT_ADMIN_URL\ncapability:\n  consumes:\n  - type: http\n    namespace: spring-boot-admin\n    baseUri: '{{env.SPRING_BOOT_ADMIN_URL}}'\n    description: Spring Boot Admin server REST API\n    resources:\n    - name: applications\n      path: /applications\n      description: Application\
  \ registration and management\n      operations:\n      - name: list-applications\n        method: GET\n        description: List all registered applications with their instances\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: register-application\n        method: POST\n        description: Register a new Spring Boot application\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            managementUrl: '{{tools.managementUrl}}'\n            healthUrl: '{{tools.healthUrl}}'\n            serviceUrl: '{{tools.serviceUrl}}'\n      - name: get-application\n        method: GET\n        description: Get all instances for a specific application\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n\
  \          required: true\n          description: Application name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deregister-application\n        method: DELETE\n        description: Deregister all instances of an application\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: Application name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: instances\n      path: /instances\n      description: Application instance monitoring and management\n      operations:\n      - name: list-instances\n        method: GET\n        description: List all registered instances\n        inputParameters:\n        - name: application\n          in: query\n          type: string\n          required: false\n          description: Filter\
  \ by application name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-instance\n        method: GET\n        description: Get details for a specific instance\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Instance ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deregister-instance\n        method: DELETE\n        description: Deregister a specific instance\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Instance ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-instance-actuator-endpoints\n        method: GET\n    \
  \    description: Get available Actuator endpoints for an instance\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Instance ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-instance-health\n        method: GET\n        description: Get health status of a specific instance\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Instance ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-instance-info\n        method: GET\n        description: Get application info for a specific instance\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description:\
  \ Instance ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-instance-metrics\n        method: GET\n        description: Get available metrics for a specific instance\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Instance ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-instance-environment\n        method: GET\n        description: Get environment properties for a specific instance\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Instance ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-instance-loggers\n    \
  \    method: GET\n        description: Get logger configuration for a specific instance\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Instance ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: set-instance-logger-level\n        method: POST\n        description: Set logger level for a specific instance at runtime\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Instance ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            configuredLevel: '{{tools.level}}'\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: fleet-management-api\n    description: Unified REST API\
  \ for Spring Boot microservice fleet management via Spring Boot Admin.\n    resources:\n    - path: /v1/applications\n      name: applications\n      description: Registered application fleet overview\n      operations:\n      - method: GET\n        name: list-applications\n        description: List all registered applications with instance counts and status\n        call: spring-boot-admin.list-applications\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/applications/{name}\n      name: application-detail\n      description: Specific application details\n      operations:\n      - method: GET\n        name: get-application\n        description: Get all instances for a named application\n        call: spring-boot-admin.get-application\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: deregister-application\n        description: Deregister all\
  \ instances of an application\n        call: spring-boot-admin.deregister-application\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/instances\n      name: instances\n      description: Individual application instances\n      operations:\n      - method: GET\n        name: list-instances\n        description: List all registered instances with optional app filter\n        call: spring-boot-admin.list-instances\n        with:\n          application: rest.application\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/instances/{id}\n      name: instance-detail\n      description: Single instance management\n      operations:\n      - method: GET\n        name: get-instance\n        description: Get full instance details\n        call: spring-boot-admin.get-instance\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n         \
  \ mapping: $.\n      - method: DELETE\n        name: deregister-instance\n        description: Deregister an instance\n        call: spring-boot-admin.deregister-instance\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/instances/{id}/health\n      name: instance-health\n      description: Instance health status\n      operations:\n      - method: GET\n        name: get-instance-health\n        description: Get health status from instance Actuator\n        call: spring-boot-admin.get-instance-health\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/instances/{id}/metrics\n      name: instance-metrics\n      description: Instance Micrometer metrics\n      operations:\n      - method: GET\n        name: get-instance-metrics\n        description: Get available metrics for an instance\n        call: spring-boot-admin.get-instance-metrics\n\
  \        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/instances/{id}/env\n      name: instance-environment\n      description: Instance environment configuration\n      operations:\n      - method: GET\n        name: get-instance-environment\n        description: Get environment properties for an instance\n        call: spring-boot-admin.get-instance-environment\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/instances/{id}/loggers\n      name: instance-loggers\n      description: Instance logger management\n      operations:\n      - method: GET\n        name: get-instance-loggers\n        description: Get logger configuration for an instance\n        call: spring-boot-admin.get-instance-loggers\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n  \
  \      name: set-instance-logger-level\n        description: Set logger level for an instance at runtime\n        call: spring-boot-admin.set-instance-logger-level\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: fleet-management-mcp\n    transport: http\n    description: MCP server for AI-assisted Spring Boot microservice fleet management.\n    tools:\n    - name: list-applications\n      description: List all Spring Boot applications registered with the Admin server, including their health status and instance\n        count\n      hints:\n        readOnly: true\n        openWorld: true\n      call: spring-boot-admin.list-applications\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-application\n      description: Get details and all running instances for a specific application by name\n      hints:\n        readOnly: true\n        openWorld:\
  \ true\n      call: spring-boot-admin.get-application\n      with:\n        name: tools.name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-instances\n      description: List all registered microservice instances, optionally filtered by application name\n      hints:\n        readOnly: true\n        openWorld: true\n      call: spring-boot-admin.list-instances\n      with:\n        application: tools.application\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-instance\n      description: Get comprehensive details for a specific microservice instance by its Admin ID\n      hints:\n        readOnly: true\n        openWorld: true\n      call: spring-boot-admin.get-instance\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: check-instance-health\n      description: Check the live health status of a specific microservice instance by proxying its Actuator\
  \ health endpoint\n      hints:\n        readOnly: true\n        openWorld: true\n      call: spring-boot-admin.get-instance-health\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-instance-info\n      description: Get build version, git commit, and runtime info for a specific microservice instance\n      hints:\n        readOnly: true\n        openWorld: true\n      call: spring-boot-admin.get-instance-info\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-instance-metrics\n      description: Get available Micrometer metrics for a specific microservice instance\n      hints:\n        readOnly: true\n        openWorld: true\n      call: spring-boot-admin.get-instance-metrics\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: inspect-instance-environment\n      description: Inspect all\
  \ environment properties and configuration for a specific microservice instance\n      hints:\n        readOnly: true\n        openWorld: true\n      call: spring-boot-admin.get-instance-environment\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-instance-loggers\n      description: Get current logger levels for a specific microservice instance to diagnose logging issues\n      hints:\n        readOnly: true\n        openWorld: true\n      call: spring-boot-admin.get-instance-loggers\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: set-instance-logger-level\n      description: Change the log level for a logger on a specific instance at runtime without restart (e.g., set DEBUG for\n        a troublesome service)\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: spring-boot-admin.set-instance-logger-level\n\
  \      with:\n        id: tools.id\n        level: tools.level\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deregister-instance\n      description: Deregister and remove a specific microservice instance from the Admin server\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: spring-boot-admin.deregister-instance\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/spring-boot-admin-console/refs/heads/main/capabilities/microservice-fleet-management.yaml
tags:
- Spring Boot Admin
- Fleet Management
- Microservices
- SRE
- Observability
tools:
- description: List all Spring Boot applications registered with the Admin server, including their health status and instance count
  hints:
    openWorld: true
    readOnly: true
  name: list-applications
- description: Get details and all running instances for a specific application by name
  hints:
    openWorld: true
    readOnly: true
  name: get-application
- description: List all registered microservice instances, optionally filtered by application name
  hints:
    openWorld: true
    readOnly: true
  name: list-instances
- description: Get comprehensive details for a specific microservice instance by its Admin ID
  hints:
    openWorld: true
    readOnly: true
  name: get-instance
- description: Check the live health status of a specific microservice instance by proxying its Actuator health endpoint
  hints:
    openWorld: true
    readOnly: true
  name: check-instance-health
- description: Get build version, git commit, and runtime info for a specific microservice instance
  hints:
    openWorld: true
    readOnly: true
  name: get-instance-info
- description: Get available Micrometer metrics for a specific microservice instance
  hints:
    openWorld: true
    readOnly: true
  name: get-instance-metrics
- description: Inspect all environment properties and configuration for a specific microservice instance
  hints:
    openWorld: true
    readOnly: true
  name: inspect-instance-environment
- description: Get current logger levels for a specific microservice instance to diagnose logging issues
  hints:
    openWorld: true
    readOnly: true
  name: get-instance-loggers
- description: Change the log level for a logger on a specific instance at runtime without restart (e.g., set DEBUG for a troublesome service)
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: set-instance-logger-level
- description: Deregister and remove a specific microservice instance from the Admin server
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deregister-instance
---
