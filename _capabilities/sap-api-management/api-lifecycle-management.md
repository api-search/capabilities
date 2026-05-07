---
categories: []
consumed_apis: []
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
- governance
- list all developer applications consuming api products
- delete api proxy
- delete an api proxy
- create a new api proxy
- list all api products
- create api proxy
- list all api proxies
- list api proxies
- api management
- sap btp
- list all backend api providers registered in sap api management
- get details for a specific sap api management proxy
- sap
- list all registered api providers
- list api providers
- list key value maps
- create a new api product
- list all api proxies in sap api management
- developer portal
- create a new runtime key-value map for api policies
- backend api provider management
- create a new api proxy in sap api management
- list all developer applications
- create a new api product bundle for the developer portal
- enterprise
- runtime configuration key-value maps
- create key value map
- delete an api proxy from sap api management
- list applications
- api proxy lifecycle operations
- developer application management
- list all key-value maps
- list api products
- api product catalog management
- create a new key-value map
- api lifecycle
- list all api products in the developer portal
- get api proxy
- get api proxy details
- create api product
- single api proxy operations
- list all key-value maps for policy configuration
slug: api-lifecycle-management
source_filename: api-lifecycle-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: SAP API Lifecycle Management\n  description: Unified capability for managing the full API lifecycle in SAP API Management. Combines the API Portal management\n    API to support end-to-end workflows for API platform engineers, integration architects, and developer experience teams.\n    Enables programmatic API governance, proxy management, product publishing, and developer portal administration.\n  tags:\n  - API Lifecycle\n  - API Management\n  - Developer Portal\n  - SAP BTP\n  - Governance\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SAP_APIMGMT_CLIENT_ID: SAP_APIMGMT_CLIENT_ID\n    SAP_APIMGMT_CLIENT_SECRET: SAP_APIMGMT_CLIENT_SECRET\n    SAP_APIMGMT_TENANT_URL: SAP_APIMGMT_TENANT_URL\ncapability:\n  consumes:\n  - type: http\n    namespace: api-portal\n    baseUri: https://{{SAP_APIMGMT_TENANT_URL}}/apiportal/api/1.0/Management.svc\n    description: SAP API Management OData management\
  \ service for CRUD operations on API entities\n    authentication:\n      type: bearer\n      token: '{{SAP_APIMGMT_ACCESS_TOKEN}}'\n    resources:\n    - name: api-providers\n      path: /APIProviders\n      description: Backend system provider management\n      operations:\n      - name: list-api-providers\n        method: GET\n        description: List all registered API providers\n        inputParameters:\n        - name: $top\n          in: query\n          type: integer\n          required: false\n        - name: $filter\n          in: query\n          type: string\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-api-provider\n        method: POST\n        description: Register a new backend system as an API provider\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n\
  \          type: json\n          data:\n            name: '{{tools.name}}'\n            host: '{{tools.host}}'\n            description: '{{tools.description}}'\n      - name: get-api-provider\n        method: GET\n        description: Get details of a specific API provider\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-api-provider\n        method: DELETE\n        description: Delete a registered API provider\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-proxies\n      path: /APIProxies\n      description: API proxy lifecycle management\n      operations:\n\
  \      - name: list-api-proxies\n        method: GET\n        description: List all API proxies\n        inputParameters:\n        - name: $top\n          in: query\n          type: integer\n          required: false\n        - name: $filter\n          in: query\n          type: string\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-api-proxy\n        method: POST\n        description: Create a new API proxy\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            basepath: '{{tools.basepath}}'\n            title: '{{tools.title}}'\n            description: '{{tools.description}}'\n      - name: get-api-proxy\n        method: GET\n        description: Get details of a specific API proxy\n \
  \       inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-api-proxy\n        method: DELETE\n        description: Delete an API proxy\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-products\n      path: /APIProducts\n      description: API product catalog management\n      operations:\n      - name: list-api-products\n        method: GET\n        description: List all API products\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-api-product\n        method: POST\n        description:\
  \ Create a new API product\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            title: '{{tools.title}}'\n            description: '{{tools.description}}'\n            scope: '{{tools.scope}}'\n      - name: delete-api-product\n        method: DELETE\n        description: Delete an API product\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: applications\n      path: /Applications\n      description: Developer application management\n      operations:\n      - name: list-applications\n        method: GET\n        description: List all registered developer applications\n        outputRawFormat: json\n      \
  \  outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: key-value-maps\n      path: /KeyValueMaps\n      description: Runtime configuration key-value store management\n      operations:\n      - name: list-key-value-maps\n        method: GET\n        description: List all key-value maps\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-key-value-map\n        method: POST\n        description: Create a new key-value map\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            encrypted: '{{tools.encrypted}}'\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: sap-api-lifecycle-api\n    description: Unified REST API for SAP API Management lifecycle operations.\n    resources:\n\
  \    - path: /v1/providers\n      name: api-providers\n      description: Backend API provider management\n      operations:\n      - method: GET\n        name: list-api-providers\n        description: List all registered API providers\n        call: api-portal.list-api-providers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/proxies\n      name: api-proxies\n      description: API proxy lifecycle operations\n      operations:\n      - method: GET\n        name: list-api-proxies\n        description: List all API proxies\n        call: api-portal.list-api-proxies\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-api-proxy\n        description: Create a new API proxy\n        call: api-portal.create-api-proxy\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/proxies/{name}\n      name: api-proxy\n      description: Single API proxy operations\n\
  \      operations:\n      - method: GET\n        name: get-api-proxy\n        description: Get API proxy details\n        call: api-portal.get-api-proxy\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-api-proxy\n        description: Delete an API proxy\n        call: api-portal.delete-api-proxy\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/products\n      name: api-products\n      description: API product catalog management\n      operations:\n      - method: GET\n        name: list-api-products\n        description: List all API products\n        call: api-portal.list-api-products\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-api-product\n        description: Create a new API product\n        call: api-portal.create-api-product\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/applications\n      name: applications\n      description: Developer application management\n      operations:\n      - method: GET\n        name: list-applications\n        description: List all developer applications\n        call: api-portal.list-applications\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/key-value-maps\n      name: key-value-maps\n      description: Runtime configuration key-value maps\n      operations:\n      - method: GET\n        name: list-key-value-maps\n        description: List all key-value maps\n        call: api-portal.list-key-value-maps\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-key-value-map\n        description: Create a new key-value map\n        call: api-portal.create-key-value-map\n        outputParameters:\n        - type: object\n       \
  \   mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: sap-api-lifecycle-mcp\n    transport: http\n    description: MCP server for AI-assisted SAP API Management lifecycle operations.\n    tools:\n    - name: list-api-providers\n      description: List all backend API providers registered in SAP API Management\n      hints:\n        readOnly: true\n        openWorld: false\n      call: api-portal.list-api-providers\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-api-proxies\n      description: List all API proxies in SAP API Management\n      hints:\n        readOnly: true\n        openWorld: false\n      call: api-portal.list-api-proxies\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-api-proxy\n      description: Get details for a specific SAP API Management proxy\n      hints:\n        readOnly: true\n        openWorld: false\n      call: api-portal.get-api-proxy\n      with:\n        name: tools.name\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-api-proxy\n      description: Create a new API proxy in SAP API Management\n      hints:\n        readOnly: false\n        destructive: false\n      call: api-portal.create-api-proxy\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-api-proxy\n      description: Delete an API proxy from SAP API Management\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: api-portal.delete-api-proxy\n      with:\n        name: tools.name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-api-products\n      description: List all API products in the developer portal\n      hints:\n        readOnly: true\n        openWorld: false\n      call: api-portal.list-api-products\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-api-product\n      description: Create\
  \ a new API product bundle for the developer portal\n      hints:\n        readOnly: false\n        destructive: false\n      call: api-portal.create-api-product\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-applications\n      description: List all developer applications consuming API products\n      hints:\n        readOnly: true\n        openWorld: false\n      call: api-portal.list-applications\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-key-value-maps\n      description: List all key-value maps for policy configuration\n      hints:\n        readOnly: true\n        openWorld: false\n      call: api-portal.list-key-value-maps\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-key-value-map\n      description: Create a new runtime key-value map for API policies\n      hints:\n        readOnly: false\n        destructive: false\n      call: api-portal.create-key-value-map\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n"
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
