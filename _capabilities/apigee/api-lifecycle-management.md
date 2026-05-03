---
categories:
- api-management
consumed_apis:
- api-management
- api-hub
description: Unified workflow for managing the full API lifecycle on Google Apigee - from API proxy creation and deployment to developer portal management, product packaging, and analytics.
layout: capability
name: Apigee API Lifecycle Management
operations:
- description: List API proxies.
  method: GET
  name: list-proxies
  path: /v1/proxies
- description: List API products.
  method: GET
  name: list-products
  path: /v1/products
- description: List developers.
  method: GET
  name: list-developers
  path: /v1/developers
personas: []
provider_name: Apigee
provider_slug: apigee
search_terms:
- list api products
- list api products.
- list all api products packaged for developer consumption.
- list all apis catalogued in apigee api hub for discovery and governance.
- apigee
- architect overseeing api platform strategy and governance across the organization.
- api gateway
- manage api developers.
- api governance
- list api proxies
- list proxies
- list api proxies.
- enterprise
- list all environments (e.g., dev, staging, prod) in the organization.
- manage api proxies.
- list all registered api developers in the organization.
- microservices
- list developers.
- api lifecycle
- Platform Architect
- API Governance Lead
- list environments
- analytics
- monetization
- api management
- list products
- manage api products.
- leader establishing api standards, cataloguing apis, and discovering shadow apis.
- API Platform Engineer
- API Product Manager
- integrations
- google cloud
- engineer managing api proxies, deployments, and policies in apigee.
- list all api proxies in an apigee organization.
- api hub
- list hub apis
- list developers
- hybrid
- manager packaging api products and managing developer relationships.
- developer portal
slug: api-lifecycle-management
source_filename: api-lifecycle-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Apigee API Lifecycle Management\"\n  description: \"Unified workflow for managing the full API lifecycle on Google Apigee - from API proxy creation and deployment to developer portal management, product packaging, and analytics.\"\n  tags:\n    - Apigee\n    - API Management\n    - API Lifecycle\n    - Google Cloud\n    - Developer Portal\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      GOOGLE_ACCESS_TOKEN: GOOGLE_ACCESS_TOKEN\n\ncapability:\n  consumes:\n    - import: api-management\n      location: ./shared/api-management.yaml\n    - import: api-hub\n      location: ./shared/api-hub.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: apigee-lifecycle-api\n      description: \"Unified REST API for Apigee API lifecycle management.\"\n      resources:\n        - path: /v1/proxies\n          name: api-proxies\n          description: \"Manage API proxies.\"\
  \n          operations:\n            - method: GET\n              name: list-proxies\n              description: \"List API proxies.\"\n              call: \"api-management.listApiProxies\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/products\n          name: api-products\n          description: \"Manage API products.\"\n          operations:\n            - method: GET\n              name: list-products\n              description: \"List API products.\"\n              call: \"api-management.listApiProducts\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/developers\n          name: developers\n          description: \"Manage API developers.\"\n          operations:\n            - method: GET\n              name: list-developers\n              description: \"List developers.\"\n              call: \"api-management.listDevelopers\"\n     \
  \         outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: apigee-lifecycle-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Apigee API lifecycle management.\"\n      tools:\n        - name: list-api-proxies\n          description: \"List all API proxies in an Apigee organization.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"api-management.listApiProxies\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-api-products\n          description: \"List all API products packaged for developer consumption.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"api-management.listApiProducts\"\n          outputParameters:\n            - type: object\n           \
  \   mapping: \"$.\"\n        - name: list-developers\n          description: \"List all registered API developers in the organization.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"api-management.listDevelopers\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-environments\n          description: \"List all environments (e.g., dev, staging, prod) in the organization.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"api-management.listEnvironments\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-hub-apis\n          description: \"List all APIs catalogued in Apigee API Hub for discovery and governance.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent:\
  \ true\n          call: \"api-hub.listApis\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/apigee/refs/heads/main/capabilities/api-lifecycle-management.yaml
tags:
- Apigee
- API Management
- API Lifecycle
- Google Cloud
- Developer Portal
tools:
- description: List all API proxies in an Apigee organization.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-api-proxies
- description: List all API products packaged for developer consumption.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-api-products
- description: List all registered API developers in the organization.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-developers
- description: List all environments (e.g., dev, staging, prod) in the organization.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-environments
- description: List all APIs catalogued in Apigee API Hub for discovery and governance.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-hub-apis
---
