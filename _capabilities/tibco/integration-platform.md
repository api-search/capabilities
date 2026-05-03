---
categories: []
consumed_apis:
- tibco-tci
- tibco-mashery
description: Unified capability for integration engineers and platform administrators to manage TIBCO Cloud Integration applications and Mashery API management services. Combines app lifecycle, connection management, deployments, and API gateway configuration in a single workflow.
layout: capability
name: TIBCO Integration Platform
operations:
- description: List all TCI integration applications
  method: GET
  name: list-integration-apps
  path: /v1/integration-apps
- description: Get TCI integration app details
  method: GET
  name: get-integration-app
  path: /v1/integration-apps/{appId}
- description: List TCI connections
  method: GET
  name: list-connections
  path: /v1/connections
- description: List TCI deployments
  method: GET
  name: list-deployments
  path: /v1/deployments
- description: List Mashery API services
  method: GET
  name: list-api-services
  path: /v1/api-services
- description: Get Mashery API service details
  method: GET
  name: get-api-service
  path: /v1/api-services/{serviceId}
- description: List Mashery API packages
  method: GET
  name: list-api-packages
  path: /v1/api-packages
personas: []
provider_name: TIBCO
provider_slug: tibco
search_terms:
- tci list deployments
- list api packages
- list mashery api packages and plans
- get details for a specific tibco cloud integration app
- get tci integration app details
- list connections
- analytics
- list all tci integration applications
- list tci connections
- api management
- list integration apps
- individual mashery api service
- connector connections
- list tibco cloud integration connector connections
- tci get app
- integration
- list tibco cloud integration applications (flogo and business studio)
- get api service
- tci list apps
- enterprise software
- mashery list packages
- cloud
- list mashery api services
- messaging
- get details for a specific mashery api service including endpoints
- list api services
- list mashery api packages
- tibco cloud integration applications
- list mashery managed api services
- tibco
- mashery get api service
- list tibco cloud integration running deployments
- list tci deployments
- mashery api packages
- get integration app
- app deployments
- flogo
- list deployments
- ipaas
- mashery managed api services
- individual integration app
- get mashery api service details
- mashery list api services
- tci list connections
- real-time data
- cloud integration
slug: integration-platform
source_filename: integration-platform.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: TIBCO Integration Platform\n  description: >-\n    Unified capability for integration engineers and platform administrators to\n    manage TIBCO Cloud Integration applications and Mashery API management\n    services. Combines app lifecycle, connection management, deployments, and\n    API gateway configuration in a single workflow.\n  tags:\n    - TIBCO\n    - API Management\n    - Cloud Integration\n    - Flogo\n    - Integration\n    - iPaaS\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      TIBCO_CLOUD_TOKEN: TIBCO_CLOUD_TOKEN\n      TIBCO_MASHERY_TOKEN: TIBCO_MASHERY_TOKEN\n\ncapability:\n  consumes:\n    - import: tibco-tci\n      location: ./shared/cloud-integration.yaml\n    - import: tibco-mashery\n      location: ./shared/mashery.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: tibco-integration-api\n      description: >-\n        Unified REST API\
  \ for managing TIBCO integration apps and API management\n        services.\n      resources:\n        - path: /v1/integration-apps\n          name: integration-apps\n          description: TIBCO Cloud Integration applications\n          operations:\n            - method: GET\n              name: list-integration-apps\n              description: List all TCI integration applications\n              call: \"tibco-tci.list-apps\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/integration-apps/{appId}\n          name: integration-app-detail\n          description: Individual integration app\n          operations:\n            - method: GET\n              name: get-integration-app\n              description: Get TCI integration app details\n              call: \"tibco-tci.get-app\"\n              with:\n                appId: \"rest.appId\"\n              outputParameters:\n                - type: object\n         \
  \         mapping: \"$.\"\n\n        - path: /v1/connections\n          name: connections\n          description: Connector connections\n          operations:\n            - method: GET\n              name: list-connections\n              description: List TCI connections\n              call: \"tibco-tci.list-connections\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/deployments\n          name: deployments\n          description: App deployments\n          operations:\n            - method: GET\n              name: list-deployments\n              description: List TCI deployments\n              call: \"tibco-tci.list-deployments\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/api-services\n          name: api-services\n          description: Mashery managed API services\n          operations:\n            - method: GET\n           \
  \   name: list-api-services\n              description: List Mashery API services\n              call: \"tibco-mashery.list-services\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/api-services/{serviceId}\n          name: api-service-detail\n          description: Individual Mashery API service\n          operations:\n            - method: GET\n              name: get-api-service\n              description: Get Mashery API service details\n              call: \"tibco-mashery.get-service\"\n              with:\n                serviceId: \"rest.serviceId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/api-packages\n          name: api-packages\n          description: Mashery API packages\n          operations:\n            - method: GET\n              name: list-api-packages\n              description: List Mashery API packages\n    \
  \          call: \"tibco-mashery.list-packages\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: tibco-integration-mcp\n      transport: http\n      description: >-\n        MCP server for AI-assisted TIBCO integration platform management\n        including app lifecycle and API gateway operations.\n      tools:\n        - name: tci-list-apps\n          description: List TIBCO Cloud Integration applications (Flogo and Business Studio)\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"tibco-tci.list-apps\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: tci-get-app\n          description: Get details for a specific TIBCO Cloud Integration app\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"tibco-tci.get-app\"\n          with:\n     \
  \       appId: \"tools.appId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: tci-list-connections\n          description: List TIBCO Cloud Integration connector connections\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"tibco-tci.list-connections\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: tci-list-deployments\n          description: List TIBCO Cloud Integration running deployments\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"tibco-tci.list-deployments\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: mashery-list-api-services\n          description: List Mashery managed API services\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"tibco-mashery.list-services\"\n\
  \          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: mashery-get-api-service\n          description: Get details for a specific Mashery API service including endpoints\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"tibco-mashery.get-service\"\n          with:\n            serviceId: \"tools.serviceId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: mashery-list-packages\n          description: List Mashery API packages and plans\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"tibco-mashery.list-packages\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/tibco/refs/heads/main/capabilities/integration-platform.yaml
tags:
- TIBCO
- API Management
- Cloud Integration
- Flogo
- Integration
- iPaaS
tools:
- description: List TIBCO Cloud Integration applications (Flogo and Business Studio)
  hints:
    openWorld: false
    readOnly: true
  name: tci-list-apps
- description: Get details for a specific TIBCO Cloud Integration app
  hints:
    openWorld: false
    readOnly: true
  name: tci-get-app
- description: List TIBCO Cloud Integration connector connections
  hints:
    openWorld: false
    readOnly: true
  name: tci-list-connections
- description: List TIBCO Cloud Integration running deployments
  hints:
    openWorld: false
    readOnly: true
  name: tci-list-deployments
- description: List Mashery managed API services
  hints:
    openWorld: false
    readOnly: true
  name: mashery-list-api-services
- description: Get details for a specific Mashery API service including endpoints
  hints:
    openWorld: false
    readOnly: true
  name: mashery-get-api-service
- description: List Mashery API packages and plans
  hints:
    openWorld: false
    readOnly: true
  name: mashery-list-packages
---
