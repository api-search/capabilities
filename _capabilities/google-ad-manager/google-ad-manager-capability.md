---
categories: []
consumed_apis: []
description: The Google Ad Manager API provides programmatic access to manage Ad Manager data including networks, ad units, companies, orders, placements, line items, creatives, reports, and targeting configurations.
layout: capability
name: Google Ad Manager API
operations:
- description: Google Ad Manager List networks
  method: GET
  name: listnetworks
  path: /v1/networks
- description: Google Ad Manager List ad units
  method: GET
  name: listadunits
  path: /v1/{parent}/adUnits
- description: Google Ad Manager List orders
  method: GET
  name: listorders
  path: /v1/{parent}/orders
- description: Google Ad Manager List companies
  method: GET
  name: listcompanies
  path: /v1/{parent}/companies
- description: Google Ad Manager Run a report
  method: POST
  name: runreport
  path: /v1/{parent}/reports:run
personas: []
provider_name: Google Ad Manager
provider_slug: google-ad-manager
search_terms:
- google ad manager list networks
- google ad manager list orders
- runreport
- manager
- ad manager
- google ad manager list ad units
- google
- listadunits
- ad
- listorders
- line items
- api
- creatives
- ad serving
- google ad manager list companies
- publishers
- google ad manager run a report
- listnetworks
- ad operations
- listcompanies
- orders
- targeting
slug: google-ad-manager-capability
source_filename: google-ad-manager-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google Ad Manager API\n  description: The Google Ad Manager API provides programmatic access to manage Ad Manager data including networks, ad units,\n    companies, orders, placements, line items, creatives, reports, and targeting configurations.\n  tags:\n  - Google\n  - Ad\n  - Manager\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: google-ad-manager\n    baseUri: https://admanager.googleapis.com\n    description: Google Ad Manager API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{GOOGLE_AD_MANAGER_TOKEN}}'\n    resources:\n    - name: v1-networks\n      path: /v1/networks\n      operations:\n      - name: listnetworks\n        method: GET\n        description: Google Ad Manager List networks\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-parent-adunits\n\
  \      path: /v1/{parent}/adUnits\n      operations:\n      - name: listadunits\n        method: GET\n        description: Google Ad Manager List ad units\n        inputParameters:\n        - name: parent\n          in: path\n          type: string\n          required: true\n        - name: pageSize\n          in: query\n          type: integer\n        - name: pageToken\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-parent-orders\n      path: /v1/{parent}/orders\n      operations:\n      - name: listorders\n        method: GET\n        description: Google Ad Manager List orders\n        inputParameters:\n        - name: parent\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-parent-companies\n\
  \      path: /v1/{parent}/companies\n      operations:\n      - name: listcompanies\n        method: GET\n        description: Google Ad Manager List companies\n        inputParameters:\n        - name: parent\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-parent-reports-run\n      path: /v1/{parent}/reports:run\n      operations:\n      - name: runreport\n        method: POST\n        description: Google Ad Manager Run a report\n        inputParameters:\n        - name: parent\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: google-ad-manager-rest\n    description: REST adapter for Google Ad Manager API.\n    resources:\n\
  \    - path: /v1/networks\n      name: listnetworks\n      operations:\n      - method: GET\n        name: listnetworks\n        description: Google Ad Manager List networks\n        call: google-ad-manager.listnetworks\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/{parent}/adUnits\n      name: listadunits\n      operations:\n      - method: GET\n        name: listadunits\n        description: Google Ad Manager List ad units\n        call: google-ad-manager.listadunits\n        with:\n          parent: rest.parent\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/{parent}/orders\n      name: listorders\n      operations:\n      - method: GET\n        name: listorders\n        description: Google Ad Manager List orders\n        call: google-ad-manager.listorders\n        with:\n          parent: rest.parent\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/{parent}/companies\n\
  \      name: listcompanies\n      operations:\n      - method: GET\n        name: listcompanies\n        description: Google Ad Manager List companies\n        call: google-ad-manager.listcompanies\n        with:\n          parent: rest.parent\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/{parent}/reports:run\n      name: runreport\n      operations:\n      - method: POST\n        name: runreport\n        description: Google Ad Manager Run a report\n        call: google-ad-manager.runreport\n        with:\n          parent: rest.parent\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: google-ad-manager-mcp\n    transport: http\n    description: MCP adapter for Google Ad Manager API for AI agent use.\n    tools:\n    - name: listnetworks\n      description: Google Ad Manager List networks\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent:\
  \ true\n      call: google-ad-manager.listnetworks\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listadunits\n      description: Google Ad Manager List ad units\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-ad-manager.listadunits\n      with:\n        parent: tools.parent\n        pageSize: tools.pageSize\n        pageToken: tools.pageToken\n      inputParameters:\n      - name: parent\n        type: string\n        description: parent\n        required: true\n      - name: pageSize\n        type: integer\n        description: pageSize\n      - name: pageToken\n        type: string\n        description: pageToken\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listorders\n      description: Google Ad Manager List orders\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-ad-manager.listorders\n\
  \      with:\n        parent: tools.parent\n      inputParameters:\n      - name: parent\n        type: string\n        description: parent\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listcompanies\n      description: Google Ad Manager List companies\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-ad-manager.listcompanies\n      with:\n        parent: tools.parent\n      inputParameters:\n      - name: parent\n        type: string\n        description: parent\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: runreport\n      description: Google Ad Manager Run a report\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-ad-manager.runreport\n      with:\n        parent: tools.parent\n      inputParameters:\n      - name: parent\n        type: string\n\
  \        description: parent\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    GOOGLE_AD_MANAGER_TOKEN: GOOGLE_AD_MANAGER_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-ad-manager/refs/heads/main/capabilities/google-ad-manager-capability.yaml
tags:
- Google
- Ad
- Manager
- API
tools:
- description: Google Ad Manager List networks
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listnetworks
- description: Google Ad Manager List ad units
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listadunits
- description: Google Ad Manager List orders
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listorders
- description: Google Ad Manager List companies
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcompanies
- description: Google Ad Manager Run a report
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: runreport
---
