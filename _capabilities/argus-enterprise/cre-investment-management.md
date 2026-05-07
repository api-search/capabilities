---
categories: []
consumed_apis: []
description: Unified capability for commercial real estate investment management using ARGUS Enterprise. Combines property valuation, cash flow modeling, lease management, portfolio analytics, and reporting for Asset Managers and Portfolio Managers.
layout: capability
name: ARGUS Enterprise CRE Investment Management
operations:
- description: List all commercial properties
  method: GET
  name: list-properties
  path: /v1/properties
- description: Get property details and current metrics
  method: GET
  name: get-property
  path: /v1/properties
- description: List all real estate portfolios
  method: GET
  name: list-portfolios
  path: /v1/portfolios
- description: List property valuations
  method: GET
  name: list-valuations
  path: /v1/valuations
- description: List all leases
  method: GET
  name: list-leases
  path: /v1/leases
- description: Get property cash flow projections
  method: GET
  name: get-cashflows
  path: /v1/properties/{id}/cashflows
personas: []
provider_name: ARGUS Enterprise
provider_slug: argus-enterprise
search_terms:
- valuation
- commercial real estate
- portfolio management
- list property valuations
- lease management
- commercial property investment and management
- get cashflows
- cash flow projections
- oversees a portfolio of commercial real estate assets
- property valuations
- Asset Manager
- multi-asset portfolio analytics and reporting
- list lease records with tenant and expiry information
- asset management
- commercial property management
- list commercial real estate properties with current status and metrics
- list all real estate portfolios
- list leases
- get property cashflows
- property valuation and appraisal
- list portfolios
- list valuations
- list properties
- altus group
- list all leases
- list current and historical property valuations
- get property cash flow projections
- argus enterprise
- list real estate portfolios with aggregate performance metrics
- get property details and current metrics
- get cash flow projections for a commercial property
- manages individual commercial real estate assets
- get property
- Portfolio Manager
- list all commercial properties
- investment management
- complete commercial real estate investment management workflow
- get detailed information about a commercial property including valuation and occupancy
- cash flow modeling
slug: cre-investment-management
source_filename: cre-investment-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: ARGUS Enterprise CRE Investment Management\n  description: Unified capability for commercial real estate investment management using ARGUS Enterprise. Combines property\n    valuation, cash flow modeling, lease management, portfolio analytics, and reporting for Asset Managers and Portfolio Managers.\n  tags:\n  - ARGUS Enterprise\n  - Commercial Real Estate\n  - Investment Management\n  - Portfolio Management\n  - Valuation\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    ARGUS_API_KEY: ARGUS_API_KEY\n    ARGUS_BASE_URL: ARGUS_BASE_URL\ncapability:\n  consumes:\n  - type: http\n    namespace: argusenterprise\n    baseUri: '{{env.ARGUS_BASE_URL}}/v1'\n    description: ARGUS Enterprise Core API\n    authentication:\n      type: apikey\n      key: Authorization\n      value: Bearer {{env.ARGUS_API_KEY}}\n      placement: header\n    resources:\n    - name: properties\n      path: /properties\n   \
  \   description: Commercial real estate properties\n      operations:\n      - name: list-properties\n        method: GET\n        description: List all properties\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-property\n        method: GET\n        description: Get property details\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Property ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: portfolios\n      path: /portfolios\n      description: Real estate portfolios\n      operations:\n      - name: list-portfolios\n        method: GET\n        description: List all portfolios\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    -\
  \ name: valuations\n      path: /valuations\n      description: Property valuations\n      operations:\n      - name: list-valuations\n        method: GET\n        description: List valuations\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: leases\n      path: /leases\n      description: Lease records\n      operations:\n      - name: list-leases\n        method: GET\n        description: List leases\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cashflows\n      path: /properties/{id}/cashflows\n      description: Property cash flow projections\n      operations:\n      - name: get-cashflows\n        method: GET\n        description: Get cash flow projections\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Property\
  \ ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8083\n    namespace: cre-investment-api\n    description: Unified REST API for commercial real estate investment management.\n    resources:\n    - path: /v1/properties\n      name: properties\n      description: Commercial property management\n      operations:\n      - method: GET\n        name: list-properties\n        description: List all commercial properties\n        call: argusenterprise.list-properties\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: get-property\n        description: Get property details and current metrics\n        call: argusenterprise.get-property\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/portfolios\n      name: portfolios\n      description:\
  \ Portfolio management\n      operations:\n      - method: GET\n        name: list-portfolios\n        description: List all real estate portfolios\n        call: argusenterprise.list-portfolios\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/valuations\n      name: valuations\n      description: Property valuations\n      operations:\n      - method: GET\n        name: list-valuations\n        description: List property valuations\n        call: argusenterprise.list-valuations\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/leases\n      name: leases\n      description: Lease management\n      operations:\n      - method: GET\n        name: list-leases\n        description: List all leases\n        call: argusenterprise.list-leases\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/properties/{id}/cashflows\n      name: cashflows\n      description: Cash flow projections\n\
  \      operations:\n      - method: GET\n        name: get-cashflows\n        description: Get property cash flow projections\n        call: argusenterprise.get-cashflows\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9093\n    namespace: cre-investment-mcp\n    transport: http\n    description: MCP server for AI-assisted commercial real estate investment management.\n    tools:\n    - name: list-properties\n      description: List commercial real estate properties with current status and metrics\n      hints:\n        readOnly: true\n        openWorld: true\n      call: argusenterprise.list-properties\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-property\n      description: Get detailed information about a commercial property including valuation and occupancy\n      hints:\n        readOnly: true\n      call: argusenterprise.get-property\n      with:\n   \
  \     id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-portfolios\n      description: List real estate portfolios with aggregate performance metrics\n      hints:\n        readOnly: true\n        openWorld: true\n      call: argusenterprise.list-portfolios\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-valuations\n      description: List current and historical property valuations\n      hints:\n        readOnly: true\n        openWorld: true\n      call: argusenterprise.list-valuations\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-leases\n      description: List lease records with tenant and expiry information\n      hints:\n        readOnly: true\n        openWorld: true\n      call: argusenterprise.list-leases\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-property-cashflows\n      description: Get cash flow projections\
  \ for a commercial property\n      hints:\n        readOnly: true\n      call: argusenterprise.get-cashflows\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/argus-enterprise/refs/heads/main/capabilities/cre-investment-management.yaml
tags:
- ARGUS Enterprise
- Commercial Real Estate
- Investment Management
- Portfolio Management
- Valuation
tools:
- description: List commercial real estate properties with current status and metrics
  hints:
    openWorld: true
    readOnly: true
  name: list-properties
- description: Get detailed information about a commercial property including valuation and occupancy
  hints:
    readOnly: true
  name: get-property
- description: List real estate portfolios with aggregate performance metrics
  hints:
    openWorld: true
    readOnly: true
  name: list-portfolios
- description: List current and historical property valuations
  hints:
    openWorld: true
    readOnly: true
  name: list-valuations
- description: List lease records with tenant and expiry information
  hints:
    openWorld: true
    readOnly: true
  name: list-leases
- description: Get cash flow projections for a commercial property
  hints:
    readOnly: true
  name: get-property-cashflows
---
