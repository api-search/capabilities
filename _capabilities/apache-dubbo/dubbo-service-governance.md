---
categories: []
consumed_apis:
- dubbo-admin
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
- SRE
- create traffic rule
- rpc
- platform engineering
- list condition routing rules
- list all services registered in the dubbo cluster
- apache dubbo
- sres monitoring cluster health and responding to service incidents
- java
- list condition routes
- list all applications registered in the dubbo cluster
- manage dubbo services
- create a new condition routing rule for traffic management
- apache
- create a new condition routing rule
- list all condition routing rules in the cluster
- cluster monitoring metrics
- service mesh
- open source
- get cluster metrics
- create condition route
- get dubbo cluster health metrics
- traffic management
- cluster metrics, flow metrics, and observability
- microservices
- list all registered dubbo applications
- list services
- service discovery
- list applications
- manage dubbo applications
- list traffic rules
- Platform Engineer
- list dubbo applications
- list dubbo services
- go
- get health and performance metrics for the dubbo cluster
- manage services, applications, traffic rules, and cluster monitoring
- manage traffic routing rules
- discovery, registration, and lifecycle of dubbo services and applications
- routing rules, load balancing, gray releases, and traffic shaping
- service governance
- engineers managing the dubbo cluster infrastructure and governance policies
- list all registered dubbo services
slug: dubbo-service-governance
source_filename: dubbo-service-governance.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Apache Dubbo Service Governance\"\n  description: \"Unified capability for governing Apache Dubbo microservices — managing services, applications, traffic rules, routing policies, and monitoring cluster health. Designed for platform engineers and SREs managing Dubbo clusters.\"\n  tags:\n    - Apache Dubbo\n    - Service Governance\n    - Microservices\n    - Traffic Management\n    - Platform Engineering\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      DUBBO_ADMIN_BASE_URL: DUBBO_ADMIN_BASE_URL\n\ncapability:\n  consumes:\n    - import: dubbo-admin\n      location: ./shared/dubbo-admin.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: dubbo-governance-api\n      description: \"Unified REST API for Apache Dubbo service governance.\"\n      resources:\n        - path: /v1/applications\n          name: applications\n          description: Manage Dubbo applications\n\
  \          operations:\n            - method: GET\n              name: list-applications\n              description: List all registered Dubbo applications\n              call: \"dubbo-admin.list-applications\"\n              with:\n                env: \"rest.env\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/services\n          name: services\n          description: Manage Dubbo services\n          operations:\n            - method: GET\n              name: list-services\n              description: List all registered Dubbo services\n              call: \"dubbo-admin.list-services\"\n              with:\n                env: \"rest.env\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/traffic-rules\n          name: traffic-rules\n          description: Manage traffic routing rules\n          operations:\n            - method: GET\n \
  \             name: list-condition-routes\n              description: List condition routing rules\n              call: \"dubbo-admin.list-condition-routes\"\n              with:\n                env: \"rest.env\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-condition-route\n              description: Create a new condition routing rule\n              call: \"dubbo-admin.create-condition-route\"\n              with:\n                env: \"rest.env\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/metrics\n          name: metrics\n          description: Cluster monitoring metrics\n          operations:\n            - method: GET\n              name: get-cluster-metrics\n              description: Get Dubbo cluster health metrics\n              call: \"dubbo-admin.get-cluster-metrics\"\n              with:\n\
  \                env: \"rest.env\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: dubbo-governance-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Apache Dubbo service governance.\"\n      tools:\n        - name: list-dubbo-applications\n          description: List all applications registered in the Dubbo cluster\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"dubbo-admin.list-applications\"\n          with:\n            env: \"tools.env\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-dubbo-services\n          description: List all services registered in the Dubbo cluster\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"dubbo-admin.list-services\"\n          with:\n            env: \"tools.env\"\n\
  \          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-traffic-rules\n          description: List all condition routing rules in the cluster\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"dubbo-admin.list-condition-routes\"\n          with:\n            env: \"tools.env\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-traffic-rule\n          description: Create a new condition routing rule for traffic management\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"dubbo-admin.create-condition-route\"\n          with:\n            env: \"tools.env\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-cluster-metrics\n          description: Get health and performance metrics for the Dubbo\
  \ cluster\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"dubbo-admin.get-cluster-metrics\"\n          with:\n            env: \"tools.env\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
