---
categories: []
consumed_apis:
- api-portal
description: Unified capability for managing the full API lifecycle in SAP API Management. Combines the API Portal management API to support end-to-end workflows for API platform engineers, integration architects, and developer experience teams. Enables programmatic API governance, proxy management, product publishing, and developer portal administration.
layout: capability
name: SAP API Lifecycle Management
operations:
- description: List all registered API providers
  method: GET
  name: list-api-providers
  path: /v1/providers
- description: List all API proxies
  method: GET
  name: list-api-proxies
  path: /v1/proxies
- description: Create a new API proxy
  method: POST
  name: create-api-proxy
  path: /v1/proxies
- description: Get API proxy details
  method: GET
  name: get-api-proxy
  path: /v1/proxies/{name}
- description: Delete an API proxy
  method: DELETE
  name: delete-api-proxy
  path: /v1/proxies/{name}
- description: List all API products
  method: GET
  name: list-api-products
  path: /v1/products
- description: Create a new API product
  method: POST
  name: create-api-product
  path: /v1/products
- description: List all developer applications
  method: GET
  name: list-applications
  path: /v1/applications
- description: List all key-value maps
  method: GET
  name: list-key-value-maps
  path: /v1/key-value-maps
- description: Create a new key-value map
  method: POST
  name: create-key-value-map
  path: /v1/key-value-maps
personas: []
provider_name: SAP API Management
provider_slug: sap-api-management
search_terms:
- get api proxy
- list api products
- list all key-value maps
- api proxy lifecycle operations
- delete an api proxy
- sap
- get api proxy details
- api product catalog management
- create key value map
- list api proxies
- list all api products
- create a new key-value map
- enterprise
- list all api proxies
- list all api products in the developer portal
- governance
- api lifecycle
- create a new api proxy
- sap btp
- create a new api proxy in sap api management
- create api product
- delete api proxy
- backend api provider management
- runtime configuration key-value maps
- list api providers
- list key value maps
- create a new api product bundle for the developer portal
- api management
- list all registered api providers
- list all developer applications consuming api products
- single api proxy operations
- list all backend api providers registered in sap api management
- list all developer applications
- create a new api product
- developer application management
- delete an api proxy from sap api management
- create api proxy
- get details for a specific sap api management proxy
- list all key-value maps for policy configuration
- create a new runtime key-value map for api policies
- list all api proxies in sap api management
- list applications
- developer portal
slug: api-lifecycle-management
source_filename: api-lifecycle-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"SAP API Lifecycle Management\"\n  description: >-\n    Unified capability for managing the full API lifecycle in SAP API Management.\n    Combines the API Portal management API to support end-to-end workflows for\n    API platform engineers, integration architects, and developer experience teams.\n    Enables programmatic API governance, proxy management, product publishing,\n    and developer portal administration.\n  tags:\n    - API Lifecycle\n    - API Management\n    - Developer Portal\n    - SAP BTP\n    - Governance\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SAP_APIMGMT_CLIENT_ID: SAP_APIMGMT_CLIENT_ID\n      SAP_APIMGMT_CLIENT_SECRET: SAP_APIMGMT_CLIENT_SECRET\n      SAP_APIMGMT_TENANT_URL: SAP_APIMGMT_TENANT_URL\n\ncapability:\n  consumes:\n    - import: api-portal\n      location: ./shared/api-portal.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n  \
  \    namespace: sap-api-lifecycle-api\n      description: \"Unified REST API for SAP API Management lifecycle operations.\"\n      resources:\n        - path: /v1/providers\n          name: api-providers\n          description: \"Backend API provider management\"\n          operations:\n            - method: GET\n              name: list-api-providers\n              description: \"List all registered API providers\"\n              call: \"api-portal.list-api-providers\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/proxies\n          name: api-proxies\n          description: \"API proxy lifecycle operations\"\n          operations:\n            - method: GET\n              name: list-api-proxies\n              description: \"List all API proxies\"\n              call: \"api-portal.list-api-proxies\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n          \
  \  - method: POST\n              name: create-api-proxy\n              description: \"Create a new API proxy\"\n              call: \"api-portal.create-api-proxy\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/proxies/{name}\n          name: api-proxy\n          description: \"Single API proxy operations\"\n          operations:\n            - method: GET\n              name: get-api-proxy\n              description: \"Get API proxy details\"\n              call: \"api-portal.get-api-proxy\"\n              with:\n                name: \"rest.name\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-api-proxy\n              description: \"Delete an API proxy\"\n              call: \"api-portal.delete-api-proxy\"\n              with:\n                name: \"rest.name\"\n              outputParameters:\n  \
  \              - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/products\n          name: api-products\n          description: \"API product catalog management\"\n          operations:\n            - method: GET\n              name: list-api-products\n              description: \"List all API products\"\n              call: \"api-portal.list-api-products\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-api-product\n              description: \"Create a new API product\"\n              call: \"api-portal.create-api-product\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/applications\n          name: applications\n          description: \"Developer application management\"\n          operations:\n            - method: GET\n              name: list-applications\n              description:\
  \ \"List all developer applications\"\n              call: \"api-portal.list-applications\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/key-value-maps\n          name: key-value-maps\n          description: \"Runtime configuration key-value maps\"\n          operations:\n            - method: GET\n              name: list-key-value-maps\n              description: \"List all key-value maps\"\n              call: \"api-portal.list-key-value-maps\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-key-value-map\n              description: \"Create a new key-value map\"\n              call: \"api-portal.create-key-value-map\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: sap-api-lifecycle-mcp\n     \
  \ transport: http\n      description: \"MCP server for AI-assisted SAP API Management lifecycle operations.\"\n      tools:\n        - name: list-api-providers\n          description: \"List all backend API providers registered in SAP API Management\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"api-portal.list-api-providers\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-api-proxies\n          description: \"List all API proxies in SAP API Management\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"api-portal.list-api-proxies\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-api-proxy\n          description: \"Get details for a specific SAP API Management proxy\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"api-portal.get-api-proxy\"\
  \n          with:\n            name: \"tools.name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-api-proxy\n          description: \"Create a new API proxy in SAP API Management\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"api-portal.create-api-proxy\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: delete-api-proxy\n          description: \"Delete an API proxy from SAP API Management\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"api-portal.delete-api-proxy\"\n          with:\n            name: \"tools.name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-api-products\n          description: \"List all API products in the developer portal\"\n          hints:\n\
  \            readOnly: true\n            openWorld: false\n          call: \"api-portal.list-api-products\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-api-product\n          description: \"Create a new API product bundle for the developer portal\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"api-portal.create-api-product\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-applications\n          description: \"List all developer applications consuming API products\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"api-portal.list-applications\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-key-value-maps\n          description: \"List all key-value maps for policy configuration\"\n          hints:\n\
  \            readOnly: true\n            openWorld: false\n          call: \"api-portal.list-key-value-maps\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-key-value-map\n          description: \"Create a new runtime key-value map for API policies\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"api-portal.create-key-value-map\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/sap-api-management/refs/heads/main/capabilities/api-lifecycle-management.yaml
tags:
- API Lifecycle
- API Management
- Developer Portal
- SAP BTP
- Governance
tools:
- description: List all backend API providers registered in SAP API Management
  hints:
    openWorld: false
    readOnly: true
  name: list-api-providers
- description: List all API proxies in SAP API Management
  hints:
    openWorld: false
    readOnly: true
  name: list-api-proxies
- description: Get details for a specific SAP API Management proxy
  hints:
    openWorld: false
    readOnly: true
  name: get-api-proxy
- description: Create a new API proxy in SAP API Management
  hints:
    destructive: false
    readOnly: false
  name: create-api-proxy
- description: Delete an API proxy from SAP API Management
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-api-proxy
- description: List all API products in the developer portal
  hints:
    openWorld: false
    readOnly: true
  name: list-api-products
- description: Create a new API product bundle for the developer portal
  hints:
    destructive: false
    readOnly: false
  name: create-api-product
- description: List all developer applications consuming API products
  hints:
    openWorld: false
    readOnly: true
  name: list-applications
- description: List all key-value maps for policy configuration
  hints:
    openWorld: false
    readOnly: true
  name: list-key-value-maps
- description: Create a new runtime key-value map for API policies
  hints:
    destructive: false
    readOnly: false
  name: create-key-value-map
---
