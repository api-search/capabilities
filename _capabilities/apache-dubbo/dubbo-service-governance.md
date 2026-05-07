---
categories: []
consumed_apis: []
description: Unified capability for governing Apache Dubbo microservices — managing services, applications, traffic rules, routing policies, and monitoring cluster health. Designed for platform engineers and SREs managing Dubbo clusters.
layout: capability
name: Apache Dubbo Service Governance
operations:
- description: List all registered Dubbo applications
  method: GET
  name: list-applications
  path: /v1/applications
- description: List all registered Dubbo services
  method: GET
  name: list-services
  path: /v1/services
- description: List condition routing rules
  method: GET
  name: list-condition-routes
  path: /v1/traffic-rules
- description: Create a new condition routing rule
  method: POST
  name: create-condition-route
  path: /v1/traffic-rules
- description: Get Dubbo cluster health metrics
  method: GET
  name: get-cluster-metrics
  path: /v1/metrics
personas: []
provider_name: Apache Dubbo
provider_slug: apache-dubbo
search_terms:
- create traffic rule
- list services
- service governance
- list condition routing rules
- list all registered dubbo applications
- create a new condition routing rule for traffic management
- list dubbo applications
- java
- service mesh
- open source
- get cluster metrics
- apache dubbo
- manage dubbo applications
- Platform Engineer
- list condition routes
- sres monitoring cluster health and responding to service incidents
- list dubbo services
- get health and performance metrics for the dubbo cluster
- list traffic rules
- apache
- list all registered dubbo services
- create a new condition routing rule
- service discovery
- manage services, applications, traffic rules, and cluster monitoring
- go
- SRE
- discovery, registration, and lifecycle of dubbo services and applications
- traffic management
- list applications
- cluster monitoring metrics
- rpc
- create condition route
- list all applications registered in the dubbo cluster
- list all services registered in the dubbo cluster
- engineers managing the dubbo cluster infrastructure and governance policies
- get dubbo cluster health metrics
- cluster metrics, flow metrics, and observability
- manage dubbo services
- list all condition routing rules in the cluster
- microservices
- manage traffic routing rules
- routing rules, load balancing, gray releases, and traffic shaping
- platform engineering
slug: dubbo-service-governance
source_filename: dubbo-service-governance.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Apache Dubbo Service Governance\n  description: Unified capability for governing Apache Dubbo microservices — managing services, applications, traffic rules,\n    routing policies, and monitoring cluster health. Designed for platform engineers and SREs managing Dubbo clusters.\n  tags:\n  - Apache Dubbo\n  - Service Governance\n  - Microservices\n  - Traffic Management\n  - Platform Engineering\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    DUBBO_ADMIN_BASE_URL: DUBBO_ADMIN_BASE_URL\ncapability:\n  consumes:\n  - type: http\n    namespace: dubbo-admin\n    baseUri: http://localhost:38080\n    description: Apache Dubbo Admin REST API for service governance\n    resources:\n    - name: applications\n      path: /api/{env}/applications\n      description: Manage Dubbo applications in the cluster\n      operations:\n      - name: list-applications\n        method: GET\n        description: List all\
  \ applications registered in the Dubbo cluster\n        inputParameters:\n        - name: env\n          in: path\n          type: string\n          required: true\n          description: Environment name (e.g. dev, prod)\n        - name: service\n          in: query\n          type: string\n          required: false\n          description: Filter by service name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: services\n      path: /api/{env}/services\n      description: Manage Dubbo services\n      operations:\n      - name: list-services\n        method: GET\n        description: List all services registered in the Dubbo cluster\n        inputParameters:\n        - name: env\n          in: path\n          type: string\n          required: true\n          description: Environment name\n        - name: app\n          in: query\n          type: string\n          required: false\n          description:\
  \ Filter by application name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: traffic-rules\n      path: /api/{env}/rules\n      description: Manage traffic routing and configuration rules\n      operations:\n      - name: list-condition-routes\n        method: GET\n        description: List all condition routing rules\n        inputParameters:\n        - name: env\n          in: path\n          type: string\n          required: true\n          description: Environment name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-condition-route\n        method: POST\n        description: Create a new condition routing rule\n        inputParameters:\n        - name: env\n          in: path\n          type: string\n          required: true\n          description: Environment name\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            conditions: '{{tools.conditions}}'\n            service: '{{tools.service}}'\n    - name: metrics\n      path: /api/{env}/metrics\n      description: Cluster metrics and monitoring data\n      operations:\n      - name: get-cluster-metrics\n        method: GET\n        description: Get overview metrics for the Dubbo cluster\n        inputParameters:\n        - name: env\n          in: path\n          type: string\n          required: true\n          description: Environment name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: dubbo-governance-api\n    description: Unified REST API for Apache Dubbo service governance.\n    resources:\n    - path: /v1/applications\n      name: applications\n\
  \      description: Manage Dubbo applications\n      operations:\n      - method: GET\n        name: list-applications\n        description: List all registered Dubbo applications\n        call: dubbo-admin.list-applications\n        with:\n          env: rest.env\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/services\n      name: services\n      description: Manage Dubbo services\n      operations:\n      - method: GET\n        name: list-services\n        description: List all registered Dubbo services\n        call: dubbo-admin.list-services\n        with:\n          env: rest.env\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/traffic-rules\n      name: traffic-rules\n      description: Manage traffic routing rules\n      operations:\n      - method: GET\n        name: list-condition-routes\n        description: List condition routing rules\n        call: dubbo-admin.list-condition-routes\n    \
  \    with:\n          env: rest.env\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-condition-route\n        description: Create a new condition routing rule\n        call: dubbo-admin.create-condition-route\n        with:\n          env: rest.env\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/metrics\n      name: metrics\n      description: Cluster monitoring metrics\n      operations:\n      - method: GET\n        name: get-cluster-metrics\n        description: Get Dubbo cluster health metrics\n        call: dubbo-admin.get-cluster-metrics\n        with:\n          env: rest.env\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: dubbo-governance-mcp\n    transport: http\n    description: MCP server for AI-assisted Apache Dubbo service governance.\n    tools:\n    - name: list-dubbo-applications\n      description:\
  \ List all applications registered in the Dubbo cluster\n      hints:\n        readOnly: true\n        openWorld: true\n      call: dubbo-admin.list-applications\n      with:\n        env: tools.env\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-dubbo-services\n      description: List all services registered in the Dubbo cluster\n      hints:\n        readOnly: true\n        openWorld: true\n      call: dubbo-admin.list-services\n      with:\n        env: tools.env\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-traffic-rules\n      description: List all condition routing rules in the cluster\n      hints:\n        readOnly: true\n        openWorld: true\n      call: dubbo-admin.list-condition-routes\n      with:\n        env: tools.env\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-traffic-rule\n      description: Create a new condition routing rule for traffic management\n\
  \      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: dubbo-admin.create-condition-route\n      with:\n        env: tools.env\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-cluster-metrics\n      description: Get health and performance metrics for the Dubbo cluster\n      hints:\n        readOnly: true\n        openWorld: true\n      call: dubbo-admin.get-cluster-metrics\n      with:\n        env: tools.env\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/apache-dubbo/refs/heads/main/capabilities/dubbo-service-governance.yaml
tags:
- Apache Dubbo
- Service Governance
- Microservices
- Traffic Management
- Platform Engineering
tools:
- description: List all applications registered in the Dubbo cluster
  hints:
    openWorld: true
    readOnly: true
  name: list-dubbo-applications
- description: List all services registered in the Dubbo cluster
  hints:
    openWorld: true
    readOnly: true
  name: list-dubbo-services
- description: List all condition routing rules in the cluster
  hints:
    openWorld: true
    readOnly: true
  name: list-traffic-rules
- description: Create a new condition routing rule for traffic management
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-traffic-rule
- description: Get health and performance metrics for the Dubbo cluster
  hints:
    openWorld: true
    readOnly: true
  name: get-cluster-metrics
---
