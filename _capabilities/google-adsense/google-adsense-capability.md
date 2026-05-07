---
categories: []
consumed_apis: []
description: The AdSense Management API allows publishers to access their inventory and run earnings and performance reports. It provides programmatic access to ad clients, ad units, custom channels, URL channels, payments, and reports.
layout: capability
name: Google AdSense Management API
operations:
- description: Google AdSense Management List accounts
  method: GET
  name: listaccounts
  path: /v2/accounts
- description: Google AdSense Management List ad clients
  method: GET
  name: listadclients
  path: /v2/{parent}/adclients
- description: Google AdSense Management List ad units
  method: GET
  name: listadunits
  path: /v2/{parent}/adunits
- description: Google AdSense Management Generate report
  method: GET
  name: generatereport
  path: /v2/{account}/reports:generate
- description: Google AdSense Management List payments
  method: GET
  name: listpayments
  path: /v2/{parent}/payments
personas: []
provider_name: Google AdSense Management
provider_slug: google-adsense
search_terms:
- api
- listpayments
- revenue
- google
- google adsense management list ad clients
- ad units
- reports
- adsense
- google adsense management list ad units
- google adsense management list payments
- listadclients
- google adsense management list accounts
- monetization
- generatereport
- listaccounts
- google adsense management generate report
- listadunits
- advertising
- publishers
slug: google-adsense-capability
source_filename: google-adsense-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google AdSense Management API\n  description: The AdSense Management API allows publishers to access their inventory and run earnings and performance reports.\n    It provides programmatic access to ad clients, ad units, custom channels, URL channels, payments, and reports.\n  tags:\n  - Google\n  - Adsense\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: google-adsense\n    baseUri: https://adsense.googleapis.com\n    description: Google AdSense Management API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{GOOGLE_ADSENSE_TOKEN}}'\n    resources:\n    - name: v2-accounts\n      path: /v2/accounts\n      operations:\n      - name: listaccounts\n        method: GET\n        description: Google AdSense Management List accounts\n        inputParameters:\n        - name: pageSize\n          in: query\n          type: integer\n        - name: pageToken\n\
  \          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v2-parent-adclients\n      path: /v2/{parent}/adclients\n      operations:\n      - name: listadclients\n        method: GET\n        description: Google AdSense Management List ad clients\n        inputParameters:\n        - name: parent\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v2-parent-adunits\n      path: /v2/{parent}/adunits\n      operations:\n      - name: listadunits\n        method: GET\n        description: Google AdSense Management List ad units\n        inputParameters:\n        - name: parent\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n     \
  \   - name: result\n          type: object\n          value: $.\n    - name: v2-account-reports-generate\n      path: /v2/{account}/reports:generate\n      operations:\n      - name: generatereport\n        method: GET\n        description: Google AdSense Management Generate report\n        inputParameters:\n        - name: account\n          in: path\n          type: string\n          required: true\n        - name: dateRange\n          in: query\n          type: string\n        - name: metrics\n          in: query\n          type: array\n        - name: dimensions\n          in: query\n          type: array\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v2-parent-payments\n      path: /v2/{parent}/payments\n      operations:\n      - name: listpayments\n        method: GET\n        description: Google AdSense Management List payments\n        inputParameters:\n        - name: parent\n       \
  \   in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: google-adsense-rest\n    description: REST adapter for Google AdSense Management API.\n    resources:\n    - path: /v2/accounts\n      name: listaccounts\n      operations:\n      - method: GET\n        name: listaccounts\n        description: Google AdSense Management List accounts\n        call: google-adsense.listaccounts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/{parent}/adclients\n      name: listadclients\n      operations:\n      - method: GET\n        name: listadclients\n        description: Google AdSense Management List ad clients\n        call: google-adsense.listadclients\n        with:\n          parent: rest.parent\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /v2/{parent}/adunits\n      name: listadunits\n      operations:\n      - method: GET\n        name: listadunits\n        description: Google AdSense Management List ad units\n        call: google-adsense.listadunits\n        with:\n          parent: rest.parent\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/{account}/reports:generate\n      name: generatereport\n      operations:\n      - method: GET\n        name: generatereport\n        description: Google AdSense Management Generate report\n        call: google-adsense.generatereport\n        with:\n          account: rest.account\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/{parent}/payments\n      name: listpayments\n      operations:\n      - method: GET\n        name: listpayments\n        description: Google AdSense Management List payments\n        call: google-adsense.listpayments\n        with:\n          parent: rest.parent\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: google-adsense-mcp\n    transport: http\n    description: MCP adapter for Google AdSense Management API for AI agent use.\n    tools:\n    - name: listaccounts\n      description: Google AdSense Management List accounts\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-adsense.listaccounts\n      with:\n        pageSize: tools.pageSize\n        pageToken: tools.pageToken\n      inputParameters:\n      - name: pageSize\n        type: integer\n        description: pageSize\n      - name: pageToken\n        type: string\n        description: pageToken\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listadclients\n      description: Google AdSense Management List ad clients\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call:\
  \ google-adsense.listadclients\n      with:\n        parent: tools.parent\n      inputParameters:\n      - name: parent\n        type: string\n        description: parent\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listadunits\n      description: Google AdSense Management List ad units\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-adsense.listadunits\n      with:\n        parent: tools.parent\n      inputParameters:\n      - name: parent\n        type: string\n        description: parent\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: generatereport\n      description: Google AdSense Management Generate report\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-adsense.generatereport\n      with:\n        account: tools.account\n        dateRange:\
  \ tools.dateRange\n        metrics: tools.metrics\n        dimensions: tools.dimensions\n      inputParameters:\n      - name: account\n        type: string\n        description: account\n        required: true\n      - name: dateRange\n        type: string\n        description: dateRange\n      - name: metrics\n        type: array\n        description: metrics\n      - name: dimensions\n        type: array\n        description: dimensions\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listpayments\n      description: Google AdSense Management List payments\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-adsense.listpayments\n      with:\n        parent: tools.parent\n      inputParameters:\n      - name: parent\n        type: string\n        description: parent\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n\
  \    GOOGLE_ADSENSE_TOKEN: GOOGLE_ADSENSE_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-adsense/refs/heads/main/capabilities/google-adsense-capability.yaml
tags:
- Google
- Adsense
- API
tools:
- description: Google AdSense Management List accounts
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listaccounts
- description: Google AdSense Management List ad clients
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listadclients
- description: Google AdSense Management List ad units
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listadunits
- description: Google AdSense Management Generate report
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: generatereport
- description: Google AdSense Management List payments
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listpayments
---
