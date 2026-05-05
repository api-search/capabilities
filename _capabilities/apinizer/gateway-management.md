---
categories: []
consumed_apis: []
description: Manage gateways, inspect endpoints and policies, and monitor metrics across the Apinizer platform
layout: capability
name: Gateway Management
operations:
- description: ''
  method: GET
  name: ''
  path: /gateways
- description: ''
  method: GET
  name: ''
  path: /gateways/{gatewayId}/endpoints
- description: ''
  method: GET
  name: ''
  path: /gateways/{gatewayId}/policies
- description: ''
  method: GET
  name: ''
  path: /monitoring/metrics
personas: []
provider_name: Apinizer
provider_slug: apinizer
search_terms:
- get metrics
- create a new apinizer api gateway
- policies
- list all configured apinizer api gateways with their status and configuration
- list policies applied to a gateway
- list api endpoints on a gateway
- list endpoints
- list gateways
- retrieve platform monitoring metrics
- api management
- create gateway
- list all configured apinizer gateways
- retrieve monitoring metrics including request counts, latency, and error rates from apinizer
- api monitoring
- api security
- list all api endpoints registered on a specific apinizer gateway
- api gateway
- list policies
- list all security and traffic policies applied to a specific apinizer gateway
slug: gateway-management
source_filename: gateway-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  name: Apinizer Gateway Management\n  description: Manage gateways, inspect endpoints and policies, and monitor metrics across the Apinizer platform\n  version: 1.0.0\n\nimport:\n  - name: apinizer\n    location: shared/gateway.yaml\n\ncapability:\n  exposes:\n    - type: rest\n      port: 8121\n      namespace: apinizer-gateway-rest\n      resources:\n        - path: \"/gateways\"\n          name: gateways\n          label: \"List Gateways\"\n          description: \"List all configured Apinizer gateways\"\n          operations:\n            - method: GET\n              call: apinizer.listGateways\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n                  items:\n                    type: object\n\n        - path: \"/gateways/{gatewayId}/endpoints\"\n          name: endpoints\n          label: \"List Endpoints\"\n          description: \"List API endpoints on a gateway\"\n     \
  \     operations:\n            - method: GET\n              call: apinizer.listEndpoints\n              inputParameters:\n                - name: gatewayId\n                  in: path\n                  type: string\n                  required: true\n                  description: \"Gateway ID\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n                  items:\n                    type: object\n\n        - path: \"/gateways/{gatewayId}/policies\"\n          name: policies\n          label: \"List Policies\"\n          description: \"List policies applied to a gateway\"\n          operations:\n            - method: GET\n              call: apinizer.listPolicies\n              inputParameters:\n                - name: gatewayId\n                  in: path\n                  type: string\n                  required: true\n                  description: \"Gateway ID\"\n              outputParameters:\n                - type: array\n\
  \                  mapping: \"$.\"\n                  items:\n                    type: object\n\n        - path: \"/monitoring/metrics\"\n          name: metrics\n          label: \"Get Metrics\"\n          description: \"Retrieve platform monitoring metrics\"\n          operations:\n            - method: GET\n              call: apinizer.getMetrics\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      address: \"0.0.0.0\"\n      port: 9121\n      namespace: apinizer-management\n      description: \"Apinizer gateway management — inspect gateways, endpoints, policies, and retrieve monitoring metrics\"\n      tools:\n        - name: list-gateways\n          description: \"List all configured Apinizer API gateways with their status and configuration\"\n          hints:\n            readOnly: true\n          call: apinizer.listGateways\n          outputParameters:\n            - type: array\n              mapping: \"\
  $.\"\n              items:\n                type: object\n\n        - name: create-gateway\n          description: \"Create a new Apinizer API gateway\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: apinizer.createGateway\n          inputParameters:\n            - name: body\n              type: object\n              required: true\n              description: \"Gateway configuration including name, type, and connection settings\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-endpoints\n          description: \"List all API endpoints registered on a specific Apinizer gateway\"\n          hints:\n            readOnly: true\n          call: apinizer.listEndpoints\n          inputParameters:\n            - name: gatewayId\n              type: string\n              required: true\n              description: \"Gateway ID\"\n          outputParameters:\n\
  \            - type: array\n              mapping: \"$.\"\n              items:\n                type: object\n\n        - name: list-policies\n          description: \"List all security and traffic policies applied to a specific Apinizer gateway\"\n          hints:\n            readOnly: true\n          call: apinizer.listPolicies\n          inputParameters:\n            - name: gatewayId\n              type: string\n              required: true\n              description: \"Gateway ID\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n              items:\n                type: object\n\n        - name: get-metrics\n          description: \"Retrieve monitoring metrics including request counts, latency, and error rates from Apinizer\"\n          hints:\n            readOnly: true\n          call: apinizer.getMetrics\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/apinizer/refs/heads/main/capabilities/gateway-management.yaml
tags: []
tools:
- description: List all configured Apinizer API gateways with their status and configuration
  hints:
    readOnly: true
  name: list-gateways
- description: Create a new Apinizer API gateway
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-gateway
- description: List all API endpoints registered on a specific Apinizer gateway
  hints:
    readOnly: true
  name: list-endpoints
- description: List all security and traffic policies applied to a specific Apinizer gateway
  hints:
    readOnly: true
  name: list-policies
- description: Retrieve monitoring metrics including request counts, latency, and error rates from Apinizer
  hints:
    readOnly: true
  name: get-metrics
---
