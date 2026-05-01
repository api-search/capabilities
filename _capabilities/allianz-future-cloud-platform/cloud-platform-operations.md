---
categories:
- monitoring
consumed_apis:
- allianz-platform-services
description: Workflow capability for platform engineering and DevOps teams operating the Allianz Future Cloud Platform, combining service management, deployment automation, observability, and infrastructure provisioning.
layout: capability
name: Allianz Cloud Platform Operations
operations:
- description: List all platform services
  method: GET
  name: list-services
  path: /v1/services
- description: Register a new microservice
  method: POST
  name: register-service
  path: /v1/services
- description: List deployment history
  method: GET
  name: list-deployments
  path: /v1/services/{service_id}/deployments
- description: Trigger a deployment
  method: POST
  name: deploy-service
  path: /v1/services/{service_id}/deployments
- description: Get platform metrics
  method: GET
  name: get-metrics
  path: /v1/observability/metrics
- description: Provision infrastructure resource
  method: POST
  name: provision-resource
  path: /v1/infrastructure/resources
personas: []
provider_name: Allianz Future Cloud Platform
provider_slug: allianz-future-cloud-platform
search_terms:
- trigger a deployment
- list services
- observability
- cloud platform
- infrastructure provisioning
- financial services
- Insurance Product Developer
- get cpu, memory, request rate, error rate, and latency metrics for a service
- list all platform services
- end-to-end platform operations for devops teams
- registration and lifecycle management of insurance microservices
- platform engineering
- deploy service
- kubernetes
- list deployments
- DevOps Engineer
- get platform metrics
- microservice lifecycle management
- trigger a rolling, blue-green, or canary deployment for a microservice
- metrics, monitoring, and alerting for platform health
- provision resource
- engineer deploying and operating insurance microservices on the platform
- register platform service
- provision redis, rds, msk, or s3 resources for insurance microservices
- list platform services
- get details and status of a specific platform service
- platform observability metrics
- cloud resource provisioning for microservice dependencies
- get service metrics
- enterprise
- engineer responsible for maintaining and evolving the allianz future cloud platform
- gitops-based deployment pipelines for microservice updates
- devops
- provision infrastructure resource
- Platform Engineer
- insurance
- get metrics
- get platform service
- deploy platform service
- list deployment history
- list service deployments
- register service
- list kubernetes namespaces and their team ownership on the platform
- register a new microservice
- register a new insurance microservice on the kubernetes platform
- list deployment history for a platform service including version and status
- developer building insurance microservices on the allianz future cloud platform
- list platform namespaces
- list all microservices registered on the allianz future cloud platform
- deployment management for services
slug: cloud-platform-operations
source_filename: cloud-platform-operations.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Allianz Cloud Platform Operations\"\n  description: \"Workflow capability for platform engineering and DevOps teams operating the Allianz Future Cloud Platform, combining service management, deployment automation, observability, and infrastructure provisioning.\"\n  tags:\n    - Cloud Platform\n    - DevOps\n    - Platform Engineering\n    - Kubernetes\n    - Observability\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      ALLIANZ_PLATFORM_CLIENT_ID: ALLIANZ_PLATFORM_CLIENT_ID\n      ALLIANZ_PLATFORM_CLIENT_SECRET: ALLIANZ_PLATFORM_CLIENT_SECRET\n\ncapability:\n  consumes:\n    - import: allianz-platform-services\n      location: ./shared/platform-services.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: allianz-cloud-platform-ops-api\n      description: \"Unified REST API for Allianz Future Cloud Platform operations workflows.\"\n      resources:\n   \
  \     - path: /v1/services\n          name: services\n          description: \"Microservice lifecycle management\"\n          operations:\n            - method: GET\n              name: list-services\n              description: \"List all platform services\"\n              call: \"allianz-platform-services.list-services\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: register-service\n              description: \"Register a new microservice\"\n              call: \"allianz-platform-services.register-service\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/services/{service_id}/deployments\n          name: deployments\n          description: \"Deployment management for services\"\n          operations:\n            - method: GET\n              name: list-deployments\n              description: \"List deployment\
  \ history\"\n              call: \"allianz-platform-services.list-deployments\"\n              with:\n                service_id: \"rest.service_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: deploy-service\n              description: \"Trigger a deployment\"\n              call: \"allianz-platform-services.deploy-service\"\n              with:\n                service_id: \"rest.service_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/observability/metrics\n          name: metrics\n          description: \"Platform observability metrics\"\n          operations:\n            - method: GET\n              name: get-metrics\n              description: \"Get platform metrics\"\n              call: \"allianz-platform-services.get-metrics\"\n              outputParameters:\n                - type: object\n  \
  \                mapping: \"$.\"\n\n        - path: /v1/infrastructure/resources\n          name: infrastructure\n          description: \"Infrastructure provisioning\"\n          operations:\n            - method: POST\n              name: provision-resource\n              description: \"Provision infrastructure resource\"\n              call: \"allianz-platform-services.provision-resource\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: allianz-cloud-platform-ops-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Allianz Future Cloud Platform operations.\"\n      tools:\n        - name: list-platform-services\n          description: \"List all microservices registered on the Allianz Future Cloud Platform\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"allianz-platform-services.list-services\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n\n        - name: register-platform-service\n          description: \"Register a new insurance microservice on the Kubernetes platform\"\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"allianz-platform-services.register-service\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-platform-service\n          description: \"Get details and status of a specific platform service\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"allianz-platform-services.get-service\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-service-deployments\n          description: \"List deployment history for a platform service including version and status\"\n          hints:\n            readOnly: true\n            openWorld: false\n   \
  \       call: \"allianz-platform-services.list-deployments\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: deploy-platform-service\n          description: \"Trigger a rolling, blue-green, or canary deployment for a microservice\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"allianz-platform-services.deploy-service\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-platform-namespaces\n          description: \"List Kubernetes namespaces and their team ownership on the platform\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"allianz-platform-services.list-namespaces\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-service-metrics\n          description: \"Get CPU, memory,\
  \ request rate, error rate, and latency metrics for a service\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"allianz-platform-services.get-metrics\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: provision-infrastructure-resource\n          description: \"Provision Redis, RDS, MSK, or S3 resources for insurance microservices\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"allianz-platform-services.provision-resource\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/allianz-future-cloud-platform/refs/heads/main/capabilities/cloud-platform-operations.yaml
tags:
- Cloud Platform
- DevOps
- Platform Engineering
- Kubernetes
- Observability
tools:
- description: List all microservices registered on the Allianz Future Cloud Platform
  hints:
    openWorld: false
    readOnly: true
  name: list-platform-services
- description: Register a new insurance microservice on the Kubernetes platform
  hints:
    openWorld: false
    readOnly: false
  name: register-platform-service
- description: Get details and status of a specific platform service
  hints:
    openWorld: false
    readOnly: true
  name: get-platform-service
- description: List deployment history for a platform service including version and status
  hints:
    openWorld: false
    readOnly: true
  name: list-service-deployments
- description: Trigger a rolling, blue-green, or canary deployment for a microservice
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: deploy-platform-service
- description: List Kubernetes namespaces and their team ownership on the platform
  hints:
    openWorld: false
    readOnly: true
  name: list-platform-namespaces
- description: Get CPU, memory, request rate, error rate, and latency metrics for a service
  hints:
    openWorld: false
    readOnly: true
  name: get-service-metrics
- description: Provision Redis, RDS, MSK, or S3 resources for insurance microservices
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: provision-infrastructure-resource
---
