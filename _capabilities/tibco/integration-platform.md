---
categories: []
consumed_apis: []
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
- connector connections
- list api services
- flogo
- get details for a specific mashery api service including endpoints
- list mashery api packages and plans
- integration
- get api service
- list tibco cloud integration applications (flogo and business studio)
- mashery list api services
- analytics
- list mashery managed api services
- cloud integration
- get tci integration app details
- cloud
- list deployments
- get details for a specific tibco cloud integration app
- get integration app
- mashery api packages
- list mashery api packages
- mashery list packages
- list api packages
- list tci deployments
- list tibco cloud integration connector connections
- tci list connections
- app deployments
- tci list deployments
- messaging
- list integration apps
- list tibco cloud integration running deployments
- mashery get api service
- list tci connections
- ipaas
- real-time data
- tibco cloud integration applications
- list all tci integration applications
- get mashery api service details
- tci get app
- api management
- individual integration app
- list connections
- individual mashery api service
- list mashery api services
- enterprise software
- tci list apps
- tibco
- mashery managed api services
slug: integration-platform
source_filename: integration-platform.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: TIBCO Integration Platform\n  description: Unified capability for integration engineers and platform administrators to manage TIBCO Cloud Integration\n    applications and Mashery API management services. Combines app lifecycle, connection management, deployments, and API\n    gateway configuration in a single workflow.\n  tags:\n  - TIBCO\n  - API Management\n  - Cloud Integration\n  - Flogo\n  - Integration\n  - iPaaS\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    TIBCO_CLOUD_TOKEN: TIBCO_CLOUD_TOKEN\n    TIBCO_MASHERY_TOKEN: TIBCO_MASHERY_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: tibco-tci\n    baseUri: https://integration.cloud.tibco.com/api/v1\n    description: TIBCO Cloud Integration REST API\n    authentication:\n      type: bearer\n      token: '{{TIBCO_CLOUD_TOKEN}}'\n    resources:\n    - name: apps\n      path: /apps\n      description: Integration application\
  \ management\n      operations:\n      - name: list-apps\n        method: GET\n        description: List all integration applications\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n        - name: offset\n          in: query\n          type: integer\n          required: false\n        - name: filter\n          in: query\n          type: string\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-app\n        method: POST\n        description: Create a new integration application\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            description: '{{tools.description}}'\n            type: '{{tools.type}}'\n      - name:\
  \ get-app\n        method: GET\n        description: Get integration application details\n        inputParameters:\n        - name: appId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-app\n        method: DELETE\n        description: Delete an integration application\n        inputParameters:\n        - name: appId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: connections\n      path: /connections\n      description: Connector connection management\n      operations:\n      - name: list-connections\n        method: GET\n        description: List all connections\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n      - name: create-connection\n        method: POST\n        description: Create a new connection\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            connectorType: '{{tools.connectorType}}'\n            properties: '{{tools.properties}}'\n    - name: deployments\n      path: /deployments\n      description: App deployment management\n      operations:\n      - name: list-deployments\n        method: GET\n        description: List all deployments\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deploy-app\n        method: POST\n        description: Deploy an integration application\n        inputParameters:\n        - name: appId\n          in: path\n          type: string\n          required:\
  \ true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            instances: '{{tools.instances}}'\n            environmentId: '{{tools.environmentId}}'\n  - type: http\n    namespace: tibco-mashery\n    baseUri: https://api.mashery.com/v3/rest\n    description: TIBCO Mashery API Management REST API\n    authentication:\n      type: bearer\n      token: '{{TIBCO_MASHERY_TOKEN}}'\n    resources:\n    - name: services\n      path: /services\n      description: API service management\n      operations:\n      - name: list-services\n        method: GET\n        description: List API services\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-service\n        method: POST\n        description: Create a new API service\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            description: '{{tools.description}}'\n      - name: get-service\n        method: GET\n        description: Get API service details\n        inputParameters:\n        - name: serviceId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: packages\n      path: /packages\n      description: API package management\n      operations:\n      - name: list-packages\n        method: GET\n        description: List API packages\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: keys\n      path: /keys\n      description: API key management\n      operations:\n      - name: list-keys\n \
  \       method: GET\n        description: List API keys\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: tibco-integration-api\n    description: Unified REST API for managing TIBCO integration apps and API management services.\n    resources:\n    - path: /v1/integration-apps\n      name: integration-apps\n      description: TIBCO Cloud Integration applications\n      operations:\n      - method: GET\n        name: list-integration-apps\n        description: List all TCI integration applications\n        call: tibco-tci.list-apps\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/integration-apps/{appId}\n      name: integration-app-detail\n      description: Individual integration app\n      operations:\n      - method: GET\n        name: get-integration-app\n        description: Get TCI integration app details\n\
  \        call: tibco-tci.get-app\n        with:\n          appId: rest.appId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/connections\n      name: connections\n      description: Connector connections\n      operations:\n      - method: GET\n        name: list-connections\n        description: List TCI connections\n        call: tibco-tci.list-connections\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/deployments\n      name: deployments\n      description: App deployments\n      operations:\n      - method: GET\n        name: list-deployments\n        description: List TCI deployments\n        call: tibco-tci.list-deployments\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/api-services\n      name: api-services\n      description: Mashery managed API services\n      operations:\n      - method: GET\n        name: list-api-services\n        description: List\
  \ Mashery API services\n        call: tibco-mashery.list-services\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/api-services/{serviceId}\n      name: api-service-detail\n      description: Individual Mashery API service\n      operations:\n      - method: GET\n        name: get-api-service\n        description: Get Mashery API service details\n        call: tibco-mashery.get-service\n        with:\n          serviceId: rest.serviceId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/api-packages\n      name: api-packages\n      description: Mashery API packages\n      operations:\n      - method: GET\n        name: list-api-packages\n        description: List Mashery API packages\n        call: tibco-mashery.list-packages\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: tibco-integration-mcp\n    transport: http\n    description:\
  \ MCP server for AI-assisted TIBCO integration platform management including app lifecycle and API gateway\n      operations.\n    tools:\n    - name: tci-list-apps\n      description: List TIBCO Cloud Integration applications (Flogo and Business Studio)\n      hints:\n        readOnly: true\n        openWorld: false\n      call: tibco-tci.list-apps\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: tci-get-app\n      description: Get details for a specific TIBCO Cloud Integration app\n      hints:\n        readOnly: true\n        openWorld: false\n      call: tibco-tci.get-app\n      with:\n        appId: tools.appId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: tci-list-connections\n      description: List TIBCO Cloud Integration connector connections\n      hints:\n        readOnly: true\n        openWorld: false\n      call: tibco-tci.list-connections\n      outputParameters:\n      - type: object\n        mapping: $.\n\
  \    - name: tci-list-deployments\n      description: List TIBCO Cloud Integration running deployments\n      hints:\n        readOnly: true\n        openWorld: false\n      call: tibco-tci.list-deployments\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: mashery-list-api-services\n      description: List Mashery managed API services\n      hints:\n        readOnly: true\n        openWorld: false\n      call: tibco-mashery.list-services\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: mashery-get-api-service\n      description: Get details for a specific Mashery API service including endpoints\n      hints:\n        readOnly: true\n        openWorld: false\n      call: tibco-mashery.get-service\n      with:\n        serviceId: tools.serviceId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: mashery-list-packages\n      description: List Mashery API packages and plans\n      hints:\n        readOnly:\
  \ true\n        openWorld: false\n      call: tibco-mashery.list-packages\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
