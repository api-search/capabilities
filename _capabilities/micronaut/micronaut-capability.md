---
categories: []
consumed_apis: []
description: Micronaut Management provides built-in endpoints for monitoring and managing Micronaut applications. Endpoints include health checks, application info, beans introspection, loggers management, metrics, routes, environment, and thread dumps.
layout: capability
name: Micronaut Management Endpoints API
operations:
- description: Micronaut Application health
  method: GET
  name: gethealth
  path: /health
- description: Micronaut Application info
  method: GET
  name: getinfo
  path: /info
- description: Micronaut List application beans
  method: GET
  name: getbeans
  path: /beans
- description: Micronaut List all loggers
  method: GET
  name: getloggers
  path: /loggers
- description: Micronaut Get logger level
  method: GET
  name: getlogger
  path: /loggers/{name}
- description: Micronaut Set logger level
  method: POST
  name: setloggerlevel
  path: /loggers/{name}
- description: Micronaut List available metrics
  method: GET
  name: listmetrics
  path: /metrics
- description: Micronaut Get metric details
  method: GET
  name: getmetric
  path: /metrics/{name}
- description: Micronaut List application routes
  method: GET
  name: getroutes
  path: /routes
- description: Micronaut Environment properties
  method: GET
  name: getenvironment
  path: /env
- description: Micronaut Thread dump
  method: GET
  name: getthreaddump
  path: /threaddump
- description: Micronaut Refresh application configuration
  method: POST
  name: refresh
  path: /refresh
- description: Micronaut Stop the application
  method: POST
  name: stop
  path: /stop
personas: []
provider_name: Micronaut
provider_slug: micronaut
search_terms:
- micronaut set logger level
- getloggers
- micronaut list all loggers
- getlogger
- api
- getenvironment
- cloud native
- java
- jvm
- refresh
- serverless
- micronaut application info
- micronaut get logger level
- micronaut list application beans
- getthreaddump
- gethealth
- micronaut application health
- frameworks
- micronaut thread dump
- getmetric
- micronaut get metric details
- micronaut list available metrics
- getinfo
- micronaut environment properties
- listmetrics
- micronaut list application routes
- getroutes
- setloggerlevel
- stop
- micronaut refresh application configuration
- microservices
- getbeans
- micronaut
- micronaut stop the application
slug: micronaut-capability
source_filename: micronaut-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Micronaut Management Endpoints API\n  description: Micronaut Management provides built-in endpoints for monitoring and managing Micronaut applications. Endpoints\n    include health checks, application info, beans introspection, loggers management, metrics, routes, environment, and thread\n    dumps.\n  tags:\n  - Micronaut\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: micronaut\n    baseUri: http://localhost:8080\n    description: Micronaut Management Endpoints API HTTP API.\n    resources:\n    - name: health\n      path: /health\n      operations:\n      - name: gethealth\n        method: GET\n        description: Micronaut Application health\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: info\n      path: /info\n      operations:\n      - name: getinfo\n        method:\
  \ GET\n        description: Micronaut Application info\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: beans\n      path: /beans\n      operations:\n      - name: getbeans\n        method: GET\n        description: Micronaut List application beans\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: loggers\n      path: /loggers\n      operations:\n      - name: getloggers\n        method: GET\n        description: Micronaut List all loggers\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: loggers-name\n      path: /loggers/{name}\n      operations:\n      - name: getlogger\n        method: GET\n        description: Micronaut Get logger level\n        inputParameters:\n        - name: name\n          in: path\n         \
  \ type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: setloggerlevel\n        method: POST\n        description: Micronaut Set logger level\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: metrics\n      path: /metrics\n      operations:\n      - name: listmetrics\n        method: GET\n        description: Micronaut List available metrics\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: metrics-name\n      path: /metrics/{name}\n      operations:\n      - name: getmetric\n        method: GET\n        description: Micronaut Get metric details\n        inputParameters:\n\
  \        - name: name\n          in: path\n          type: string\n          required: true\n        - name: tag\n          in: query\n          type: array\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: routes\n      path: /routes\n      operations:\n      - name: getroutes\n        method: GET\n        description: Micronaut List application routes\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: env\n      path: /env\n      operations:\n      - name: getenvironment\n        method: GET\n        description: Micronaut Environment properties\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: threaddump\n      path: /threaddump\n      operations:\n      - name: getthreaddump\n        method: GET\n        description:\
  \ Micronaut Thread dump\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: refresh\n      path: /refresh\n      operations:\n      - name: refresh\n        method: POST\n        description: Micronaut Refresh application configuration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: stop\n      path: /stop\n      operations:\n      - name: stop\n        method: POST\n        description: Micronaut Stop the application\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: micronaut-rest\n    description: REST adapter for Micronaut Management Endpoints API.\n    resources:\n    - path: /health\n      name: gethealth\n      operations:\n      - method: GET\n        name: gethealth\n\
  \        description: Micronaut Application health\n        call: micronaut.gethealth\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /info\n      name: getinfo\n      operations:\n      - method: GET\n        name: getinfo\n        description: Micronaut Application info\n        call: micronaut.getinfo\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /beans\n      name: getbeans\n      operations:\n      - method: GET\n        name: getbeans\n        description: Micronaut List application beans\n        call: micronaut.getbeans\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /loggers\n      name: getloggers\n      operations:\n      - method: GET\n        name: getloggers\n        description: Micronaut List all loggers\n        call: micronaut.getloggers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /loggers/{name}\n      name:\
  \ getlogger\n      operations:\n      - method: GET\n        name: getlogger\n        description: Micronaut Get logger level\n        call: micronaut.getlogger\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /loggers/{name}\n      name: setloggerlevel\n      operations:\n      - method: POST\n        name: setloggerlevel\n        description: Micronaut Set logger level\n        call: micronaut.setloggerlevel\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /metrics\n      name: listmetrics\n      operations:\n      - method: GET\n        name: listmetrics\n        description: Micronaut List available metrics\n        call: micronaut.listmetrics\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /metrics/{name}\n      name: getmetric\n      operations:\n      - method: GET\n        name: getmetric\n\
  \        description: Micronaut Get metric details\n        call: micronaut.getmetric\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /routes\n      name: getroutes\n      operations:\n      - method: GET\n        name: getroutes\n        description: Micronaut List application routes\n        call: micronaut.getroutes\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /env\n      name: getenvironment\n      operations:\n      - method: GET\n        name: getenvironment\n        description: Micronaut Environment properties\n        call: micronaut.getenvironment\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /threaddump\n      name: getthreaddump\n      operations:\n      - method: GET\n        name: getthreaddump\n        description: Micronaut Thread dump\n        call: micronaut.getthreaddump\n        outputParameters:\n      \
  \  - type: object\n          mapping: $.\n    - path: /refresh\n      name: refresh\n      operations:\n      - method: POST\n        name: refresh\n        description: Micronaut Refresh application configuration\n        call: micronaut.refresh\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /stop\n      name: stop\n      operations:\n      - method: POST\n        name: stop\n        description: Micronaut Stop the application\n        call: micronaut.stop\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: micronaut-mcp\n    transport: http\n    description: MCP adapter for Micronaut Management Endpoints API for AI agent use.\n    tools:\n    - name: gethealth\n      description: Micronaut Application health\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: micronaut.gethealth\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n    - name: getinfo\n      description: Micronaut Application info\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: micronaut.getinfo\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getbeans\n      description: Micronaut List application beans\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: micronaut.getbeans\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getloggers\n      description: Micronaut List all loggers\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: micronaut.getloggers\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getlogger\n      description: Micronaut Get logger level\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: micronaut.getlogger\n\
  \      with:\n        name: tools.name\n      inputParameters:\n      - name: name\n        type: string\n        description: name\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: setloggerlevel\n      description: Micronaut Set logger level\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: micronaut.setloggerlevel\n      with:\n        name: tools.name\n      inputParameters:\n      - name: name\n        type: string\n        description: name\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listmetrics\n      description: Micronaut List available metrics\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: micronaut.listmetrics\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getmetric\n      description: Micronaut Get metric details\n\
  \      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: micronaut.getmetric\n      with:\n        name: tools.name\n        tag: tools.tag\n      inputParameters:\n      - name: name\n        type: string\n        description: name\n        required: true\n      - name: tag\n        type: array\n        description: tag\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getroutes\n      description: Micronaut List application routes\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: micronaut.getroutes\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getenvironment\n      description: Micronaut Environment properties\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: micronaut.getenvironment\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name:\
  \ getthreaddump\n      description: Micronaut Thread dump\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: micronaut.getthreaddump\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: refresh\n      description: Micronaut Refresh application configuration\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: micronaut.refresh\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: stop\n      description: Micronaut Stop the application\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: micronaut.stop\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/micronaut/refs/heads/main/capabilities/micronaut-capability.yaml
tags:
- Micronaut
- API
tools:
- description: Micronaut Application health
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gethealth
- description: Micronaut Application info
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getinfo
- description: Micronaut List application beans
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getbeans
- description: Micronaut List all loggers
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getloggers
- description: Micronaut Get logger level
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getlogger
- description: Micronaut Set logger level
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: setloggerlevel
- description: Micronaut List available metrics
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listmetrics
- description: Micronaut Get metric details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getmetric
- description: Micronaut List application routes
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getroutes
- description: Micronaut Environment properties
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getenvironment
- description: Micronaut Thread dump
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getthreaddump
- description: Micronaut Refresh application configuration
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: refresh
- description: Micronaut Stop the application
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: stop
---
