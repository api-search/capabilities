---
categories: []
consumed_apis: []
description: The BFE (Beyond Front End) Management API provides internal monitoring, configuration reload, and profiling endpoints for the BFE open-source layer 7 load balancer. This API should only be exposed on internal networks and never publicly accessible.
layout: capability
name: BFE Management API
operations:
- description: BFE List Monitor Categories
  method: GET
  name: listmonitorcategories
  path: /monitor
- description: BFE Get Monitor Metrics
  method: GET
  name: getmonitormetrics
  path: /monitor/{name}
- description: BFE List Reload Entries
  method: GET
  name: listreloadentries
  path: /reload
- description: BFE Reload Configuration
  method: GET
  name: reloadconfiguration
  path: /reload/{name}
- description: BFE Get Pprof Index
  method: GET
  name: getpprofindex
  path: /debug/pprof/
- description: BFE Get Command Line
  method: GET
  name: getcommandline
  path: /debug/cmdline
- description: BFE Get CPU Profile
  method: GET
  name: getcpuprofile
  path: /debug/profile
personas: []
provider_name: BFE
provider_slug: bfe
search_terms:
- networking
- getcommandline
- bfe list monitor categories
- dynamic configuration management and reload
- baidu
- bfe get monitor metrics
- getpprofindex
- bfe get pprof index
- getcpuprofile
- bfe list reload entries
- bfe get cpu profile
- listmonitorcategories
- bfe reload configuration
- open source
- bfe
- api
- bfe get command line
- load balancer
- getmonitormetrics
- listreloadentries
- cncf
- layer 7 load balancing and traffic routing
- engineer managing bfe load balancer deployments and configuration
- metrics, logging, and distributed tracing
- traffic management
- reloadconfiguration
slug: bfe-capability
source_filename: bfe-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: BFE Management API\n  description: The BFE (Beyond Front End) Management API provides internal monitoring, configuration reload, and profiling\n    endpoints for the BFE open-source layer 7 load balancer. This API should only be exposed on internal networks and never\n    publicly accessible.\n  tags:\n  - Bfe\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: bfe\n    baseUri: http://localhost:8421\n    description: BFE Management API HTTP API.\n    resources:\n    - name: monitor\n      path: /monitor\n      operations:\n      - name: listmonitorcategories\n        method: GET\n        description: BFE List Monitor Categories\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: monitor-name\n      path: /monitor/{name}\n      operations:\n      - name: getmonitormetrics\n        method:\
  \ GET\n        description: BFE Get Monitor Metrics\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: The monitor category name (e.g., connections, requests, routing).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: reload\n      path: /reload\n      operations:\n      - name: listreloadentries\n        method: GET\n        description: BFE List Reload Entries\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: reload-name\n      path: /reload/{name}\n      operations:\n      - name: reloadconfiguration\n        method: GET\n        description: BFE Reload Configuration\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: The reload\
  \ entry name to trigger.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: debug-pprof\n      path: /debug/pprof/\n      operations:\n      - name: getpprofindex\n        method: GET\n        description: BFE Get Pprof Index\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: debug-cmdline\n      path: /debug/cmdline\n      operations:\n      - name: getcommandline\n        method: GET\n        description: BFE Get Command Line\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: debug-profile\n      path: /debug/profile\n      operations:\n      - name: getcpuprofile\n        method: GET\n        description: BFE Get CPU Profile\n        inputParameters:\n        - name: seconds\n          in: query\n          type: integer\n\
  \          description: Duration in seconds for CPU profiling.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: bfe-rest\n    description: REST adapter for BFE Management API.\n    resources:\n    - path: /monitor\n      name: listmonitorcategories\n      operations:\n      - method: GET\n        name: listmonitorcategories\n        description: BFE List Monitor Categories\n        call: bfe.listmonitorcategories\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /monitor/{name}\n      name: getmonitormetrics\n      operations:\n      - method: GET\n        name: getmonitormetrics\n        description: BFE Get Monitor Metrics\n        call: bfe.getmonitormetrics\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /reload\n      name: listreloadentries\n\
  \      operations:\n      - method: GET\n        name: listreloadentries\n        description: BFE List Reload Entries\n        call: bfe.listreloadentries\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /reload/{name}\n      name: reloadconfiguration\n      operations:\n      - method: GET\n        name: reloadconfiguration\n        description: BFE Reload Configuration\n        call: bfe.reloadconfiguration\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /debug/pprof/\n      name: getpprofindex\n      operations:\n      - method: GET\n        name: getpprofindex\n        description: BFE Get Pprof Index\n        call: bfe.getpprofindex\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /debug/cmdline\n      name: getcommandline\n      operations:\n      - method: GET\n        name: getcommandline\n        description: BFE Get Command\
  \ Line\n        call: bfe.getcommandline\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /debug/profile\n      name: getcpuprofile\n      operations:\n      - method: GET\n        name: getcpuprofile\n        description: BFE Get CPU Profile\n        call: bfe.getcpuprofile\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: bfe-mcp\n    transport: http\n    description: MCP adapter for BFE Management API for AI agent use.\n    tools:\n    - name: listmonitorcategories\n      description: BFE List Monitor Categories\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: bfe.listmonitorcategories\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getmonitormetrics\n      description: BFE Get Monitor Metrics\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n  \
  \    call: bfe.getmonitormetrics\n      with:\n        name: tools.name\n      inputParameters:\n      - name: name\n        type: string\n        description: The monitor category name (e.g., connections, requests, routing).\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listreloadentries\n      description: BFE List Reload Entries\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: bfe.listreloadentries\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: reloadconfiguration\n      description: BFE Reload Configuration\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: bfe.reloadconfiguration\n      with:\n        name: tools.name\n      inputParameters:\n      - name: name\n        type: string\n        description: The reload entry name to trigger.\n        required: true\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: getpprofindex\n      description: BFE Get Pprof Index\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: bfe.getpprofindex\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcommandline\n      description: BFE Get Command Line\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: bfe.getcommandline\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcpuprofile\n      description: BFE Get CPU Profile\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: bfe.getcpuprofile\n      with:\n        seconds: tools.seconds\n      inputParameters:\n      - name: seconds\n        type: integer\n        description: Duration in seconds for CPU profiling.\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/bfe/refs/heads/main/capabilities/bfe-capability.yaml
tags:
- Bfe
- API
tools:
- description: BFE List Monitor Categories
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listmonitorcategories
- description: BFE Get Monitor Metrics
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getmonitormetrics
- description: BFE List Reload Entries
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listreloadentries
- description: BFE Reload Configuration
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: reloadconfiguration
- description: BFE Get Pprof Index
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getpprofindex
- description: BFE Get Command Line
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcommandline
- description: BFE Get CPU Profile
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcpuprofile
---
