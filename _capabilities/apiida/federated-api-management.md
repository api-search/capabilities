---
categories:
- api-management
consumed_apis: []
description: Unified workflow for federated API management across multiple API gateways using APIIDA - validating specs, deploying APIs, monitoring gateways, and managing API lifecycle from a central control plane.
layout: capability
name: APIIDA Federated API Management
operations:
- description: List all managed APIs.
  method: GET
  name: list-apis
  path: /v1/apis
- description: List all managed gateways.
  method: GET
  name: list-gateways
  path: /v1/gateways
personas: []
provider_name: APIIDA
provider_slug: apiida
search_terms:
- API Platform Engineer
- get gateway metrics
- list all managed apis.
- list all managed gateways.
- gateway
- architect overseeing multi-gateway api strategy and governance.
- engineer managing apis across multiple gateways using apiida's federated control plane.
- layer7
- enterprise
- Enterprise Architect
- get monitoring and performance metrics for a specific gateway.
- apiida
- list gateways
- validate an openapi proxy specification before deployment.
- validate api specification
- federated api management
- federated
- deploy a validated api to one or more gateway environments.
- api management
- api gateway
- list apis
- list all apis managed across the apiida federated control plane.
- list managed gateways
- governance
- list all broadcom layer7 gateways registered in the gateway manager.
- list managed apis
- deploy api to gateways
slug: federated-api-management
source_filename: federated-api-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: APIIDA Federated API Management\n  description: Unified workflow for federated API management across multiple API gateways using APIIDA - validating specs,\n    deploying APIs, monitoring gateways, and managing API lifecycle from a central control plane.\n  tags:\n  - APIIDA\n  - API Management\n  - Federated\n  - Gateway\n  - Enterprise\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    APIIDA_API_KEY: APIIDA_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: apiida-control-plane\n    baseUri: https://api.apiida.com/control-plane\n    description: APIIDA API Control Plane REST API.\n    authentication:\n      type: bearer\n      token: '{{APIIDA_API_KEY}}'\n    resources:\n    - name: apis\n      path: /apis\n      description: Manage APIs across gateways.\n      operations:\n      - name: list-apis\n        method: GET\n        description: List all APIs.\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-api-version\n        method: POST\n        description: Create a new API version.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: validate-spec\n        method: POST\n        description: Validate an OpenAPI proxy specification.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deploy-api\n        method: POST\n        description: Deploy API to gateways.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: apiida-gateway-manager\n    baseUri: https://api.apiida.com/gateway-manager\n    description: APIIDA API Gateway Manager REST API.\n    authentication:\n      type: bearer\n\
  \      token: '{{APIIDA_API_KEY}}'\n    resources:\n    - name: gateways\n      path: /gateways\n      description: Manage Layer7 gateways.\n      operations:\n      - name: list-gateways\n        method: GET\n        description: List all managed gateways.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: register-gateway\n        method: POST\n        description: Register a new gateway.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-gateway-metrics\n        method: GET\n        description: Get monitoring metrics for a gateway.\n        inputParameters:\n        - name: gatewayId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type:\
  \ rest\n    port: 8080\n    namespace: apiida-federated-api\n    description: Unified REST API for APIIDA federated API management.\n    resources:\n    - path: /v1/apis\n      operations:\n      - method: GET\n        name: list-apis\n        description: List all managed APIs.\n        call: apiida-control-plane.list-apis\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/gateways\n      operations:\n      - method: GET\n        name: list-gateways\n        description: List all managed gateways.\n        call: apiida-gateway-manager.list-gateways\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: apiida-federated-mcp\n    transport: http\n    description: MCP server for AI-assisted APIIDA federated API management.\n    tools:\n    - name: list-managed-apis\n      description: List all APIs managed across the APIIDA federated control plane.\n      hints:\n        readOnly: true\n\
  \        destructive: false\n        idempotent: true\n      call: apiida-control-plane.list-apis\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: validate-api-specification\n      description: Validate an OpenAPI proxy specification before deployment.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: apiida-control-plane.validate-spec\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deploy-api-to-gateways\n      description: Deploy a validated API to one or more gateway environments.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: apiida-control-plane.deploy-api\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-managed-gateways\n      description: List all Broadcom Layer7 gateways registered in the gateway manager.\n      hints:\n        readOnly: true\n        destructive:\
  \ false\n        idempotent: true\n      call: apiida-gateway-manager.list-gateways\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-gateway-metrics\n      description: Get monitoring and performance metrics for a specific gateway.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: apiida-gateway-manager.get-gateway-metrics\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/apiida/refs/heads/main/capabilities/federated-api-management.yaml
tags:
- APIIDA
- API Management
- Federated
- Gateway
- Enterprise
tools:
- description: List all APIs managed across the APIIDA federated control plane.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-managed-apis
- description: Validate an OpenAPI proxy specification before deployment.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: validate-api-specification
- description: Deploy a validated API to one or more gateway environments.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: deploy-api-to-gateways
- description: List all Broadcom Layer7 gateways registered in the gateway manager.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-managed-gateways
- description: Get monitoring and performance metrics for a specific gateway.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-gateway-metrics
---
