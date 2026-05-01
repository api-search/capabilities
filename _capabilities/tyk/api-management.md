---
categories:
- api-management
consumed_apis:
- tyk-gateway
- tyk-dashboard
description: Unified API management workflow combining Gateway and Dashboard APIs for API developers and platform engineers to manage API definitions, keys, policies, and portal configurations.
layout: capability
name: Tyk API Management
operations:
- description: List all API definitions from Dashboard
  method: GET
  name: list-apis
  path: /v1/apis
- description: Get a specific API definition
  method: GET
  name: get-api
  path: /v1/apis
- description: Create a new API definition
  method: POST
  name: create-api
  path: /v1/apis
- description: List all API keys
  method: GET
  name: list-keys
  path: /v1/keys
- description: List all policies
  method: GET
  name: list-policies
  path: /v1/policies
- description: List all dashboard users
  method: GET
  name: list-users
  path: /v1/users
- description: Check gateway health
  method: GET
  name: check-health
  path: /v1/health
- description: Get portal catalogue
  method: GET
  name: get-catalogue
  path: /v1/catalogue
personas: []
provider_name: Tyk
provider_slug: tyk
search_terms:
- get api
- dashboard update api
- graphql
- create a new api key
- dashboard get api
- dashboard list policies
- get a specific api definition from the dashboard
- list apis
- get the developer portal catalogue
- dashboard users
- create api
- dashboard create policy
- check gateway health
- list keys
- update an api definition in the dashboard
- dashboard create key
- check the gateway health status
- tyk
- dashboard list users
- security policies
- gateway
- dashboard list apis
- dashboard get policy
- gateway list apis
- check health
- list all certificates on the gateway
- gateway health
- get a specific policy
- gateway list certificates
- dashboard delete api
- hot reload the gateway configuration
- list all api definitions from dashboard
- api management
- get catalogue
- get portal catalogue
- delete an api definition from the dashboard
- create a new security policy
- dashboard get catalogue
- open source
- api keys
- dashboard list keys
- list users
- list all api definitions from the tyk dashboard
- list all api definitions directly from the gateway
- list all policies
- dashboard create api
- list all dashboard users
- create a new api definition in the dashboard
- gateway hot reload
- api definitions
- gateway check health
- list policies
- list all security policies
- get a specific api definition
- list all api keys
- api gateway
- portal catalogue
- create a new api definition
slug: api-management
source_filename: api-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Tyk API Management\"\n  description: \"Unified API management workflow combining Gateway and Dashboard APIs for API developers and platform engineers to manage API definitions, keys, policies, and portal configurations.\"\n  tags:\n    - API Management\n    - Gateway\n    - Tyk\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      TYK_GATEWAY_SECRET: TYK_GATEWAY_SECRET\n      TYK_DASHBOARD_API_KEY: TYK_DASHBOARD_API_KEY\n\ncapability:\n  consumes:\n    - import: tyk-gateway\n      location: ./shared/gateway.yaml\n    - import: tyk-dashboard\n      location: ./shared/dashboard.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: tyk-api-management-api\n      description: \"Unified REST API for Tyk API management operations.\"\n      resources:\n        - path: /v1/apis\n          name: apis\n          description: \"API definitions\"\n          operations:\n  \
  \          - method: GET\n              name: list-apis\n              description: \"List all API definitions from Dashboard\"\n              call: \"tyk-dashboard.list-apis\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: GET\n              name: get-api\n              description: \"Get a specific API definition\"\n              call: \"tyk-dashboard.get-api\"\n              with:\n                apiID: \"rest.apiID\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-api\n              description: \"Create a new API definition\"\n              call: \"tyk-dashboard.create-api\"\n              with:\n                api_definition: \"rest.api_definition\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/keys\n          name: keys\n\
  \          description: \"API keys\"\n          operations:\n            - method: GET\n              name: list-keys\n              description: \"List all API keys\"\n              call: \"tyk-dashboard.list-keys\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/policies\n          name: policies\n          description: \"Security policies\"\n          operations:\n            - method: GET\n              name: list-policies\n              description: \"List all policies\"\n              call: \"tyk-dashboard.list-policies\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/users\n          name: users\n          description: \"Dashboard users\"\n          operations:\n            - method: GET\n              name: list-users\n              description: \"List all dashboard users\"\n              call: \"tyk-dashboard.list-users\"\n        \
  \      outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/health\n          name: health\n          description: \"Gateway health\"\n          operations:\n            - method: GET\n              name: check-health\n              description: \"Check gateway health\"\n              call: \"tyk-gateway.check-health\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/catalogue\n          name: catalogue\n          description: \"Portal catalogue\"\n          operations:\n            - method: GET\n              name: get-catalogue\n              description: \"Get portal catalogue\"\n              call: \"tyk-dashboard.get-catalogue\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: tyk-api-management-mcp\n      transport: http\n      description: \"MCP server\
  \ for AI-assisted Tyk API management.\"\n      tools:\n        - name: dashboard-list-apis\n          description: \"List all API definitions from the Tyk Dashboard\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"tyk-dashboard.list-apis\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: dashboard-get-api\n          description: \"Get a specific API definition from the Dashboard\"\n          hints:\n            readOnly: true\n          call: \"tyk-dashboard.get-api\"\n          with:\n            apiID: \"tools.apiID\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: dashboard-create-api\n          description: \"Create a new API definition in the Dashboard\"\n          hints:\n            readOnly: false\n          call: \"tyk-dashboard.create-api\"\n          with:\n            api_definition: \"tools.api_definition\"\n      \
  \    outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: dashboard-update-api\n          description: \"Update an API definition in the Dashboard\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"tyk-dashboard.update-api\"\n          with:\n            apiID: \"tools.apiID\"\n            api_definition: \"tools.api_definition\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: dashboard-delete-api\n          description: \"Delete an API definition from the Dashboard\"\n          hints:\n            destructive: true\n            idempotent: true\n          call: \"tyk-dashboard.delete-api\"\n          with:\n            apiID: \"tools.apiID\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: dashboard-list-policies\n          description: \"List all security policies\"\n          hints:\n\
  \            readOnly: true\n          call: \"tyk-dashboard.list-policies\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: dashboard-get-policy\n          description: \"Get a specific policy\"\n          hints:\n            readOnly: true\n          call: \"tyk-dashboard.get-policy\"\n          with:\n            polID: \"tools.polID\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: dashboard-create-policy\n          description: \"Create a new security policy\"\n          hints:\n            readOnly: false\n          call: \"tyk-dashboard.create-policy\"\n          with:\n            policy: \"tools.policy\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: dashboard-list-keys\n          description: \"List all API keys\"\n          hints:\n            readOnly: true\n          call: \"tyk-dashboard.list-keys\"\n \
  \         outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: dashboard-create-key\n          description: \"Create a new API key\"\n          hints:\n            readOnly: false\n          call: \"tyk-dashboard.create-key\"\n          with:\n            key: \"tools.key\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: dashboard-list-users\n          description: \"List all dashboard users\"\n          hints:\n            readOnly: true\n          call: \"tyk-dashboard.list-users\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: dashboard-get-catalogue\n          description: \"Get the developer portal catalogue\"\n          hints:\n            readOnly: true\n          call: \"tyk-dashboard.get-catalogue\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: gateway-list-apis\n \
  \         description: \"List all API definitions directly from the Gateway\"\n          hints:\n            readOnly: true\n          call: \"tyk-gateway.list-apis\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: gateway-check-health\n          description: \"Check the gateway health status\"\n          hints:\n            readOnly: true\n          call: \"tyk-gateway.check-health\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: gateway-hot-reload\n          description: \"Hot reload the gateway configuration\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"tyk-gateway.hot-reload\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: gateway-list-certificates\n          description: \"List all certificates on the gateway\"\n          hints:\n            readOnly: true\n \
  \         call: \"tyk-gateway.list-certificates\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/tyk/refs/heads/main/capabilities/api-management.yaml
tags:
- API Management
- Gateway
- Tyk
tools:
- description: List all API definitions from the Tyk Dashboard
  hints:
    openWorld: true
    readOnly: true
  name: dashboard-list-apis
- description: Get a specific API definition from the Dashboard
  hints:
    readOnly: true
  name: dashboard-get-api
- description: Create a new API definition in the Dashboard
  hints:
    readOnly: false
  name: dashboard-create-api
- description: Update an API definition in the Dashboard
  hints:
    idempotent: true
    readOnly: false
  name: dashboard-update-api
- description: Delete an API definition from the Dashboard
  hints:
    destructive: true
    idempotent: true
  name: dashboard-delete-api
- description: List all security policies
  hints:
    readOnly: true
  name: dashboard-list-policies
- description: Get a specific policy
  hints:
    readOnly: true
  name: dashboard-get-policy
- description: Create a new security policy
  hints:
    readOnly: false
  name: dashboard-create-policy
- description: List all API keys
  hints:
    readOnly: true
  name: dashboard-list-keys
- description: Create a new API key
  hints:
    readOnly: false
  name: dashboard-create-key
- description: List all dashboard users
  hints:
    readOnly: true
  name: dashboard-list-users
- description: Get the developer portal catalogue
  hints:
    readOnly: true
  name: dashboard-get-catalogue
- description: List all API definitions directly from the Gateway
  hints:
    readOnly: true
  name: gateway-list-apis
- description: Check the gateway health status
  hints:
    readOnly: true
  name: gateway-check-health
- description: Hot reload the gateway configuration
  hints:
    idempotent: true
    readOnly: false
  name: gateway-hot-reload
- description: List all certificates on the gateway
  hints:
    readOnly: true
  name: gateway-list-certificates
---
