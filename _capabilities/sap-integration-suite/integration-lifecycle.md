---
categories: []
consumed_apis:
- cloud-integration
- api-management
description: Unified capability for managing the complete integration lifecycle on SAP Integration Suite. Combines Cloud Integration artifact management with API Management proxy lifecycle for integration developers and platform administrators. Covers design, deployment, monitoring, and API governance workflows.
layout: capability
name: SAP Integration Suite - Integration Lifecycle
operations:
- description: List all integration packages
  method: GET
  name: list-integration-packages
  path: /v1/integration-packages
- description: Get a specific integration package
  method: GET
  name: get-integration-package
  path: /v1/integration-packages/{id}
- description: List all deployed runtime artifacts
  method: GET
  name: list-runtime-artifacts
  path: /v1/runtime-artifacts
- description: Get runtime artifact status
  method: GET
  name: get-runtime-artifact
  path: /v1/runtime-artifacts/{id}
- description: Undeploy a runtime artifact
  method: DELETE
  name: undeploy-runtime-artifact
  path: /v1/runtime-artifacts/{id}
- description: Deploy an integration flow to runtime
  method: POST
  name: deploy-integration-flow
  path: /v1/deploy
- description: List message processing logs
  method: GET
  name: list-message-processing-logs
  path: /v1/message-processing-logs
- description: Get a specific message log
  method: GET
  name: get-message-processing-log
  path: /v1/message-processing-logs/{messageGuid}
- description: List all service endpoints
  method: GET
  name: list-service-endpoints
  path: /v1/service-endpoints
- description: List all API proxies
  method: GET
  name: list-api-proxies
  path: /v1/api-proxies
- description: Get API proxy details
  method: GET
  name: get-api-proxy
  path: /v1/api-proxies/{name}
- description: Delete an API proxy
  method: DELETE
  name: delete-api-proxy
  path: /v1/api-proxies/{name}
- description: List all API products
  method: GET
  name: list-api-products
  path: /v1/api-products
- description: List all developer applications
  method: GET
  name: list-applications
  path: /v1/applications
- description: List all developers
  method: GET
  name: list-developers
  path: /v1/developers
personas: []
provider_name: SAP Integration Suite
provider_slug: sap-integration-suite
search_terms:
- list api products
- list api proxies
- list all developers
- remove a deployed integration flow from the runtime
- deploy an integration flow to runtime
- list applications
- get api proxy details
- delete an api proxy from sap api management
- undeploy runtime artifact
- list all api products
- get api product
- list all deployed runtime artifacts
- get runtime artifact status
- get a specific message processing log entry by guid
- list all api products in the sap api management developer portal
- api management
- integration flows
- undeploy a runtime artifact
- single api proxy configuration
- get a specific message log
- deployed integration flow runtime artifacts
- get api proxy
- list all service endpoints registered in sap integration suite
- get a specific sap integration package by id
- developer applications and subscriptions
- api products bundling api proxies
- get the deployment status of a specific integration flow
- list all api proxies in the sap api management tenant
- list all developer applications
- deploy integration flow
- list all api proxies
- list all developers registered in the sap api management portal
- enterprise integration
- get a specific api proxy configuration by name
- list runtime artifacts
- integration service endpoints
- get runtime artifact
- sap
- list message processing logs, optionally filtered by status or flow name
- get a specific integration package
- get message processing log
- message processing audit logs
- list all integration packages in the sap cloud integration tenant
- list all developer applications registered in the api portal
- list developers
- get integration package
- single integration package details
- list service endpoints
- deploy an integration flow artifact to the sap integration suite runtime
- sap btp
- ipaas
- list integration packages
- list all integration packages
- developer accounts in api portal
- create api proxy
- delete an api proxy
- get a specific api product by name
- event mesh
- list message processing logs
- sap integration suite
- create a new api proxy in sap api management
- single runtime artifact status
- list and retrieve integration packages
- single message processing log
- list all service endpoints
- devops
- list all deployed runtime integration artifacts and their status
- api management proxy configurations
- trigger integration flow deployment
- delete api proxy
- cloud integration
slug: integration-lifecycle
source_filename: integration-lifecycle.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"SAP Integration Suite - Integration Lifecycle\"\n  description: >-\n    Unified capability for managing the complete integration lifecycle on\n    SAP Integration Suite. Combines Cloud Integration artifact management\n    with API Management proxy lifecycle for integration developers and\n    platform administrators. Covers design, deployment, monitoring, and\n    API governance workflows.\n  tags:\n    - SAP Integration Suite\n    - Cloud Integration\n    - API Management\n    - Integration Flows\n    - DevOps\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SAP_CLOUD_INTEGRATION_OAUTH_TOKEN: SAP_CLOUD_INTEGRATION_OAUTH_TOKEN\n      SAP_CLOUD_INTEGRATION_HOST: SAP_CLOUD_INTEGRATION_HOST\n      SAP_APIM_OAUTH_TOKEN: SAP_APIM_OAUTH_TOKEN\n      SAP_APIM_HOST: SAP_APIM_HOST\n\ncapability:\n  consumes:\n    - import: cloud-integration\n      location: ./shared/cloud-integration.yaml\n\
  \    - import: api-management\n      location: ./shared/api-management.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: integration-lifecycle-api\n      description: \"Unified REST API for SAP Integration Suite lifecycle management.\"\n      resources:\n        - path: /v1/integration-packages\n          name: integration-packages\n          description: List and retrieve integration packages\n          operations:\n            - method: GET\n              name: list-integration-packages\n              description: List all integration packages\n              call: \"cloud-integration.list-integration-packages\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/integration-packages/{id}\n          name: integration-package\n          description: Single integration package details\n          operations:\n            - method: GET\n              name: get-integration-package\n              description:\
  \ Get a specific integration package\n              call: \"cloud-integration.get-integration-package\"\n              with:\n                Id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/runtime-artifacts\n          name: runtime-artifacts\n          description: Deployed integration flow runtime artifacts\n          operations:\n            - method: GET\n              name: list-runtime-artifacts\n              description: List all deployed runtime artifacts\n              call: \"cloud-integration.list-runtime-artifacts\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/runtime-artifacts/{id}\n          name: runtime-artifact\n          description: Single runtime artifact status\n          operations:\n            - method: GET\n              name: get-runtime-artifact\n              description: Get runtime artifact status\n\
  \              call: \"cloud-integration.get-runtime-artifact\"\n              with:\n                Id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: undeploy-runtime-artifact\n              description: Undeploy a runtime artifact\n              call: \"cloud-integration.undeploy-runtime-artifact\"\n              with:\n                Id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/deploy\n          name: deploy\n          description: Trigger integration flow deployment\n          operations:\n            - method: POST\n              name: deploy-integration-flow\n              description: Deploy an integration flow to runtime\n              call: \"cloud-integration.deploy-integration-flow\"\n              with:\n                Id: \"rest.id\"\n                Version: \"rest.version\"\
  \n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/message-processing-logs\n          name: message-processing-logs\n          description: Message processing audit logs\n          operations:\n            - method: GET\n              name: list-message-processing-logs\n              description: List message processing logs\n              call: \"cloud-integration.list-message-processing-logs\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/message-processing-logs/{messageGuid}\n          name: message-processing-log\n          description: Single message processing log\n          operations:\n            - method: GET\n              name: get-message-processing-log\n              description: Get a specific message log\n              call: \"cloud-integration.get-message-processing-log\"\n              with:\n                MessageGuid: \"\
  rest.messageGuid\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/service-endpoints\n          name: service-endpoints\n          description: Integration service endpoints\n          operations:\n            - method: GET\n              name: list-service-endpoints\n              description: List all service endpoints\n              call: \"cloud-integration.list-service-endpoints\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/api-proxies\n          name: api-proxies\n          description: API Management proxy configurations\n          operations:\n            - method: GET\n              name: list-api-proxies\n              description: List all API proxies\n              call: \"api-management.list-api-proxies\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/api-proxies/{name}\n\
  \          name: api-proxy\n          description: Single API proxy configuration\n          operations:\n            - method: GET\n              name: get-api-proxy\n              description: Get API proxy details\n              call: \"api-management.get-api-proxy\"\n              with:\n                name: \"rest.name\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-api-proxy\n              description: Delete an API proxy\n              call: \"api-management.delete-api-proxy\"\n              with:\n                name: \"rest.name\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/api-products\n          name: api-products\n          description: API products bundling API proxies\n          operations:\n            - method: GET\n              name: list-api-products\n              description: List\
  \ all API products\n              call: \"api-management.list-api-products\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/applications\n          name: applications\n          description: Developer applications and subscriptions\n          operations:\n            - method: GET\n              name: list-applications\n              description: List all developer applications\n              call: \"api-management.list-applications\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/developers\n          name: developers\n          description: Developer accounts in API portal\n          operations:\n            - method: GET\n              name: list-developers\n              description: List all developers\n              call: \"api-management.list-developers\"\n              outputParameters:\n                - type: object\n            \
  \      mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: integration-lifecycle-mcp\n      transport: http\n      description: \"MCP server for AI-assisted SAP Integration Suite lifecycle management.\"\n      tools:\n        - name: list-integration-packages\n          description: List all integration packages in the SAP Cloud Integration tenant\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"cloud-integration.list-integration-packages\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-integration-package\n          description: Get a specific SAP integration package by ID\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"cloud-integration.get-integration-package\"\n          with:\n            Id: \"tools.Id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-runtime-artifacts\n\
  \          description: List all deployed runtime integration artifacts and their status\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"cloud-integration.list-runtime-artifacts\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-runtime-artifact\n          description: Get the deployment status of a specific integration flow\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"cloud-integration.get-runtime-artifact\"\n          with:\n            Id: \"tools.Id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: deploy-integration-flow\n          description: Deploy an integration flow artifact to the SAP Integration Suite runtime\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"cloud-integration.deploy-integration-flow\"\
  \n          with:\n            Id: \"tools.Id\"\n            Version: \"tools.Version\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: undeploy-runtime-artifact\n          description: Remove a deployed integration flow from the runtime\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"cloud-integration.undeploy-runtime-artifact\"\n          with:\n            Id: \"tools.Id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-message-processing-logs\n          description: List message processing logs, optionally filtered by status or flow name\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"cloud-integration.list-message-processing-logs\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-message-processing-log\n\
  \          description: Get a specific message processing log entry by GUID\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"cloud-integration.get-message-processing-log\"\n          with:\n            MessageGuid: \"tools.MessageGuid\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-service-endpoints\n          description: List all service endpoints registered in SAP Integration Suite\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"cloud-integration.list-service-endpoints\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-api-proxies\n          description: List all API proxies in the SAP API Management tenant\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"api-management.list-api-proxies\"\n          outputParameters:\n      \
  \      - type: object\n              mapping: \"$.\"\n        - name: get-api-proxy\n          description: Get a specific API proxy configuration by name\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"api-management.get-api-proxy\"\n          with:\n            name: \"tools.name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-api-proxy\n          description: Create a new API proxy in SAP API Management\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"api-management.create-api-proxy\"\n          with:\n            name: \"tools.name\"\n            title: \"tools.title\"\n            targetEndpoint: \"tools.targetEndpoint\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-api-proxy\n          description: Delete an API proxy from SAP\
  \ API Management\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"api-management.delete-api-proxy\"\n          with:\n            name: \"tools.name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-api-products\n          description: List all API products in the SAP API Management developer portal\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"api-management.list-api-products\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-api-product\n          description: Get a specific API product by name\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"api-management.get-api-product\"\n          with:\n            name: \"tools.name\"\n          outputParameters:\n            - type: object\n            \
  \  mapping: \"$.\"\n        - name: list-applications\n          description: List all developer applications registered in the API portal\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"api-management.list-applications\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-developers\n          description: List all developers registered in the SAP API Management portal\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"api-management.list-developers\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/sap-integration-suite/refs/heads/main/capabilities/integration-lifecycle.yaml
tags:
- SAP Integration Suite
- Cloud Integration
- API Management
- Integration Flows
- DevOps
tools:
- description: List all integration packages in the SAP Cloud Integration tenant
  hints:
    openWorld: true
    readOnly: true
  name: list-integration-packages
- description: Get a specific SAP integration package by ID
  hints:
    openWorld: false
    readOnly: true
  name: get-integration-package
- description: List all deployed runtime integration artifacts and their status
  hints:
    openWorld: true
    readOnly: true
  name: list-runtime-artifacts
- description: Get the deployment status of a specific integration flow
  hints:
    openWorld: false
    readOnly: true
  name: get-runtime-artifact
- description: Deploy an integration flow artifact to the SAP Integration Suite runtime
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: deploy-integration-flow
- description: Remove a deployed integration flow from the runtime
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: undeploy-runtime-artifact
- description: List message processing logs, optionally filtered by status or flow name
  hints:
    openWorld: true
    readOnly: true
  name: list-message-processing-logs
- description: Get a specific message processing log entry by GUID
  hints:
    openWorld: false
    readOnly: true
  name: get-message-processing-log
- description: List all service endpoints registered in SAP Integration Suite
  hints:
    openWorld: true
    readOnly: true
  name: list-service-endpoints
- description: List all API proxies in the SAP API Management tenant
  hints:
    openWorld: true
    readOnly: true
  name: list-api-proxies
- description: Get a specific API proxy configuration by name
  hints:
    openWorld: false
    readOnly: true
  name: get-api-proxy
- description: Create a new API proxy in SAP API Management
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-api-proxy
- description: Delete an API proxy from SAP API Management
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-api-proxy
- description: List all API products in the SAP API Management developer portal
  hints:
    openWorld: true
    readOnly: true
  name: list-api-products
- description: Get a specific API product by name
  hints:
    openWorld: false
    readOnly: true
  name: get-api-product
- description: List all developer applications registered in the API portal
  hints:
    openWorld: true
    readOnly: true
  name: list-applications
- description: List all developers registered in the SAP API Management portal
  hints:
    openWorld: true
    readOnly: true
  name: list-developers
---
