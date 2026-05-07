---
categories: []
consumed_apis: []
description: The Spring Boot Actuator API provides production-ready endpoints for monitoring and managing Spring Boot applications. It exposes health checks, metrics, environment information, configuration properties, thread dumps, HTTP traces, application info, and shutdown capabilities via RESTful endpoints. The Actuator supports customizable security, endpoint exposure controls, and integration with monitoring systems like Prometheus, Datadog, and CloudWatch. Used by operators and SREs to observe and manage deployed Spring Boot services.
layout: capability
name: Spring Boot Actuator API
operations:
- description: Get Health Status
  method: GET
  name: gethealth
  path: /health
- description: Get Component Health Status
  method: GET
  name: getcomponenthealth
  path: /health/{component}
- description: List Available Metrics
  method: GET
  name: listmetrics
  path: /metrics
- description: Get Metric Value
  method: GET
  name: getmetric
  path: /metrics/{requiredMetricName}
- description: Get Application Info
  method: GET
  name: getinfo
  path: /info
- description: Get Environment Properties
  method: GET
  name: getenvironment
  path: /env
- description: Get Environment Property
  method: GET
  name: getenvironmentproperty
  path: /env/{toMatch}
- description: List Loggers
  method: GET
  name: listloggers
  path: /loggers
- description: Get Logger Configuration
  method: GET
  name: getlogger
  path: /loggers/{name}
- description: Set Logger Level
  method: POST
  name: setloggerlevel
  path: /loggers/{name}
- description: Get Request Mappings
  method: GET
  name: getmappings
  path: /mappings
- description: Get Thread Dump
  method: GET
  name: getthreaddump
  path: /threaddump
- description: Get Application Beans
  method: GET
  name: getbeans
  path: /beans
personas: []
provider_name: Spring Framework
provider_slug: spring
search_terms:
- get component health status
- getlogger
- ai
- api
- getenvironment
- set logger level
- spring boot
- listloggers
- cloud native
- get thread dump
- get application info
- list available metrics
- get application beans
- java
- rest
- open source
- get request mappings
- spring
- getthreaddump
- getmappings
- enterprise
- gethealth
- framework
- getmetric
- get logger configuration
- list loggers
- getinfo
- get metric value
- listmetrics
- getcomponenthealth
- get health status
- setloggerlevel
- get environment properties
- get environment property
- getenvironmentproperty
- microservices
- getbeans
slug: spring-capability
source_filename: spring-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Spring Boot Actuator API\n  description: The Spring Boot Actuator API provides production-ready endpoints for monitoring and managing Spring Boot applications.\n    It exposes health checks, metrics, environment information, configuration properties, thread dumps, HTTP traces, application\n    info, and shutdown capabilities via RESTful endpoints. The Actuator supports customizable security, endpoint exposure\n    controls, and integration with monitoring systems like Prometheus, Datadog, and CloudWatch. Used by operators and SREs\n    to observe and manage deployed Spring Boot services.\n  tags:\n  - Spring\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: spring\n    baseUri: http://localhost:8080/actuator\n    description: Spring Boot Actuator API HTTP API.\n    authentication:\n      type: basic\n      username: '{{SPRING_USERNAME}}'\n      password: '{{SPRING_PASSWORD}}'\n\
  \    resources:\n    - name: health\n      path: /health\n      operations:\n      - name: gethealth\n        method: GET\n        description: Get Health Status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: health-component\n      path: /health/{component}\n      operations:\n      - name: getcomponenthealth\n        method: GET\n        description: Get Component Health Status\n        inputParameters:\n        - name: component\n          in: path\n          type: string\n          required: true\n          description: Health indicator component name (e.g., db, diskSpace, redis)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: metrics\n      path: /metrics\n      operations:\n      - name: listmetrics\n        method: GET\n        description: List Available Metrics\n        outputRawFormat: json\n \
  \       outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: metrics-requiredmetricname\n      path: /metrics/{requiredMetricName}\n      operations:\n      - name: getmetric\n        method: GET\n        description: Get Metric Value\n        inputParameters:\n        - name: requiredMetricName\n          in: path\n          type: string\n          required: true\n          description: Metric name in dot notation\n        - name: tag\n          in: query\n          type: string\n          description: 'Tag filter in KEY:VALUE format (can be repeated for multiple tags). Example: area:heap or area:heap&tag=id:G1+Eden+Space'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: info\n      path: /info\n      operations:\n      - name: getinfo\n        method: GET\n        description: Get Application Info\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: env\n      path: /env\n      operations:\n      - name: getenvironment\n        method: GET\n        description: Get Environment Properties\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: env-tomatch\n      path: /env/{toMatch}\n      operations:\n      - name: getenvironmentproperty\n        method: GET\n        description: Get Environment Property\n        inputParameters:\n        - name: toMatch\n          in: path\n          type: string\n          required: true\n          description: Property key to look up\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: loggers\n      path: /loggers\n      operations:\n      - name: listloggers\n        method: GET\n        description: List Loggers\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: loggers-name\n      path: /loggers/{name}\n      operations:\n      - name: getlogger\n        method: GET\n        description: Get Logger Configuration\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: Logger name (e.g., com.example.MyService, ROOT)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: setloggerlevel\n        method: POST\n        description: Set Logger Level\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: Logger name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: mappings\n      path: /mappings\n \
  \     operations:\n      - name: getmappings\n        method: GET\n        description: Get Request Mappings\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: threaddump\n      path: /threaddump\n      operations:\n      - name: getthreaddump\n        method: GET\n        description: Get Thread Dump\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: beans\n      path: /beans\n      operations:\n      - name: getbeans\n        method: GET\n        description: Get Application Beans\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: spring-rest\n    description: REST adapter for Spring Boot Actuator API.\n    resources:\n    - path: /health\n      name: gethealth\n      operations:\n\
  \      - method: GET\n        name: gethealth\n        description: Get Health Status\n        call: spring.gethealth\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /health/{component}\n      name: getcomponenthealth\n      operations:\n      - method: GET\n        name: getcomponenthealth\n        description: Get Component Health Status\n        call: spring.getcomponenthealth\n        with:\n          component: rest.component\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /metrics\n      name: listmetrics\n      operations:\n      - method: GET\n        name: listmetrics\n        description: List Available Metrics\n        call: spring.listmetrics\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /metrics/{requiredMetricName}\n      name: getmetric\n      operations:\n      - method: GET\n        name: getmetric\n        description: Get Metric Value\n        call:\
  \ spring.getmetric\n        with:\n          requiredMetricName: rest.requiredMetricName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /info\n      name: getinfo\n      operations:\n      - method: GET\n        name: getinfo\n        description: Get Application Info\n        call: spring.getinfo\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /env\n      name: getenvironment\n      operations:\n      - method: GET\n        name: getenvironment\n        description: Get Environment Properties\n        call: spring.getenvironment\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /env/{toMatch}\n      name: getenvironmentproperty\n      operations:\n      - method: GET\n        name: getenvironmentproperty\n        description: Get Environment Property\n        call: spring.getenvironmentproperty\n        with:\n          toMatch: rest.toMatch\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /loggers\n      name: listloggers\n      operations:\n      - method: GET\n        name: listloggers\n        description: List Loggers\n        call: spring.listloggers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /loggers/{name}\n      name: getlogger\n      operations:\n      - method: GET\n        name: getlogger\n        description: Get Logger Configuration\n        call: spring.getlogger\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /loggers/{name}\n      name: setloggerlevel\n      operations:\n      - method: POST\n        name: setloggerlevel\n        description: Set Logger Level\n        call: spring.setloggerlevel\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /mappings\n      name: getmappings\n      operations:\n\
  \      - method: GET\n        name: getmappings\n        description: Get Request Mappings\n        call: spring.getmappings\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /threaddump\n      name: getthreaddump\n      operations:\n      - method: GET\n        name: getthreaddump\n        description: Get Thread Dump\n        call: spring.getthreaddump\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /beans\n      name: getbeans\n      operations:\n      - method: GET\n        name: getbeans\n        description: Get Application Beans\n        call: spring.getbeans\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: spring-mcp\n    transport: http\n    description: MCP adapter for Spring Boot Actuator API for AI agent use.\n    tools:\n    - name: gethealth\n      description: Get Health Status\n      hints:\n        readOnly: true\n        destructive:\
  \ false\n        idempotent: true\n      call: spring.gethealth\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcomponenthealth\n      description: Get Component Health Status\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: spring.getcomponenthealth\n      with:\n        component: tools.component\n      inputParameters:\n      - name: component\n        type: string\n        description: Health indicator component name (e.g., db, diskSpace, redis)\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listmetrics\n      description: List Available Metrics\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: spring.listmetrics\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getmetric\n      description: Get Metric Value\n      hints:\n        readOnly: true\n  \
  \      destructive: false\n        idempotent: true\n      call: spring.getmetric\n      with:\n        requiredMetricName: tools.requiredMetricName\n        tag: tools.tag\n      inputParameters:\n      - name: requiredMetricName\n        type: string\n        description: Metric name in dot notation\n        required: true\n      - name: tag\n        type: string\n        description: 'Tag filter in KEY:VALUE format (can be repeated for multiple tags). Example: area:heap or area:heap&tag=id:G1+Eden+Space'\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getinfo\n      description: Get Application Info\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: spring.getinfo\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getenvironment\n      description: Get Environment Properties\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n\
  \      call: spring.getenvironment\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getenvironmentproperty\n      description: Get Environment Property\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: spring.getenvironmentproperty\n      with:\n        toMatch: tools.toMatch\n      inputParameters:\n      - name: toMatch\n        type: string\n        description: Property key to look up\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listloggers\n      description: List Loggers\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: spring.listloggers\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getlogger\n      description: Get Logger Configuration\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: spring.getlogger\n\
  \      with:\n        name: tools.name\n      inputParameters:\n      - name: name\n        type: string\n        description: Logger name (e.g., com.example.MyService, ROOT)\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: setloggerlevel\n      description: Set Logger Level\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: spring.setloggerlevel\n      with:\n        name: tools.name\n      inputParameters:\n      - name: name\n        type: string\n        description: Logger name\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getmappings\n      description: Get Request Mappings\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: spring.getmappings\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getthreaddump\n      description: Get\
  \ Thread Dump\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: spring.getthreaddump\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getbeans\n      description: Get Application Beans\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: spring.getbeans\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    SPRING_USERNAME: SPRING_USERNAME\n    SPRING_PASSWORD: SPRING_PASSWORD\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/spring/refs/heads/main/capabilities/spring-capability.yaml
tags:
- Spring
- API
tools:
- description: Get Health Status
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gethealth
- description: Get Component Health Status
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcomponenthealth
- description: List Available Metrics
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listmetrics
- description: Get Metric Value
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getmetric
- description: Get Application Info
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getinfo
- description: Get Environment Properties
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getenvironment
- description: Get Environment Property
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getenvironmentproperty
- description: List Loggers
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listloggers
- description: Get Logger Configuration
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getlogger
- description: Set Logger Level
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: setloggerlevel
- description: Get Request Mappings
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getmappings
- description: Get Thread Dump
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getthreaddump
- description: Get Application Beans
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getbeans
---
