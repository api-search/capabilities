---
categories: []
consumed_apis: []
description: Finch is a unified employment API that lets developers integrate with HRIS, payroll, and benefits systems through a single interface. The API exposes Company, Directory, Individual, Employment, Payment, Pay Statement, and Benefits resources, plus Sandbox endpoints for testing.
layout: capability
name: Finch API
operations:
- description: Create a Finch Connect session
  method: POST
  name: createconnectsession
  path: /connect/sessions
- description: Exchange authorization code for access token
  method: POST
  name: exchangeauthcode
  path: /auth/token
- description: Get connected company information
  method: GET
  name: getcompany
  path: /employer/company
- description: List employees in the company directory
  method: GET
  name: listdirectory
  path: /employer/directory
- description: Get individual records (PII)
  method: POST
  name: getindividuals
  path: /employer/individual
- description: Get employment records
  method: POST
  name: getemployment
  path: /employer/employment
- description: List company payments (pay runs)
  method: GET
  name: listpayments
  path: /employer/payment
- description: Get pay statements for one or more payments
  method: POST
  name: getpaystatements
  path: /employer/pay-statement
- description: List company benefits
  method: GET
  name: listbenefits
  path: /employer/benefits
personas: []
provider_name: Finch
provider_slug: finch
search_terms:
- hris
- listdirectory
- unified api
- get individual records (pii)
- api
- getindividuals
- list company benefits
- get employment records
- finch
- exchangeauthcode
- list company payments (pay runs)
- hr
- getpaystatements
- get connected company information
- payroll
- getemployment
- create a finch connect session
- employment
- exchange authorization code for access token
- benefits
- workforce
- createconnectsession
- list employees in the company directory
- get pay statements for one or more payments
- listbenefits
- listpayments
- getcompany
slug: finch-capability
source_filename: finch-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Finch API\n  description: Finch is a unified employment API that lets developers integrate with HRIS, payroll, and benefits systems through\n    a single interface. The API exposes Company, Directory, Individual, Employment, Payment, Pay Statement, and Benefits resources,\n    plus Sandbox endpoints for testing.\n  tags:\n  - Finch\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: finch\n    baseUri: https://api.tryfinch.com\n    description: Finch API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{FINCH_TOKEN}}'\n    resources:\n    - name: connect-sessions\n      path: /connect/sessions\n      operations:\n      - name: createconnectsession\n        method: POST\n        description: Create a Finch Connect session\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    -\
  \ name: auth-token\n      path: /auth/token\n      operations:\n      - name: exchangeauthcode\n        method: POST\n        description: Exchange authorization code for access token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: employer-company\n      path: /employer/company\n      operations:\n      - name: getcompany\n        method: GET\n        description: Get connected company information\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: employer-directory\n      path: /employer/directory\n      operations:\n      - name: listdirectory\n        method: GET\n        description: List employees in the company directory\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n        - name: offset\n          in: query\n          type: integer\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: employer-individual\n      path: /employer/individual\n      operations:\n      - name: getindividuals\n        method: POST\n        description: Get individual records (PII)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: employer-employment\n      path: /employer/employment\n      operations:\n      - name: getemployment\n        method: POST\n        description: Get employment records\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: employer-payment\n      path: /employer/payment\n      operations:\n      - name: listpayments\n        method: GET\n        description: List company payments (pay runs)\n        inputParameters:\n        - name: start_date\n          in: query\n          type:\
  \ string\n        - name: end_date\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: employer-pay-statement\n      path: /employer/pay-statement\n      operations:\n      - name: getpaystatements\n        method: POST\n        description: Get pay statements for one or more payments\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: employer-benefits\n      path: /employer/benefits\n      operations:\n      - name: listbenefits\n        method: GET\n        description: List company benefits\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: finch-rest\n    description: REST adapter for Finch API.\n    resources:\n    - path: /connect/sessions\n\
  \      name: createconnectsession\n      operations:\n      - method: POST\n        name: createconnectsession\n        description: Create a Finch Connect session\n        call: finch.createconnectsession\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth/token\n      name: exchangeauthcode\n      operations:\n      - method: POST\n        name: exchangeauthcode\n        description: Exchange authorization code for access token\n        call: finch.exchangeauthcode\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /employer/company\n      name: getcompany\n      operations:\n      - method: GET\n        name: getcompany\n        description: Get connected company information\n        call: finch.getcompany\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /employer/directory\n      name: listdirectory\n      operations:\n      - method: GET\n        name: listdirectory\n\
  \        description: List employees in the company directory\n        call: finch.listdirectory\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /employer/individual\n      name: getindividuals\n      operations:\n      - method: POST\n        name: getindividuals\n        description: Get individual records (PII)\n        call: finch.getindividuals\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /employer/employment\n      name: getemployment\n      operations:\n      - method: POST\n        name: getemployment\n        description: Get employment records\n        call: finch.getemployment\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /employer/payment\n      name: listpayments\n      operations:\n      - method: GET\n        name: listpayments\n        description: List company payments (pay runs)\n        call: finch.listpayments\n        outputParameters:\n       \
  \ - type: object\n          mapping: $.\n    - path: /employer/pay-statement\n      name: getpaystatements\n      operations:\n      - method: POST\n        name: getpaystatements\n        description: Get pay statements for one or more payments\n        call: finch.getpaystatements\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /employer/benefits\n      name: listbenefits\n      operations:\n      - method: GET\n        name: listbenefits\n        description: List company benefits\n        call: finch.listbenefits\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: finch-mcp\n    transport: http\n    description: MCP adapter for Finch API for AI agent use.\n    tools:\n    - name: createconnectsession\n      description: Create a Finch Connect session\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: finch.createconnectsession\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: exchangeauthcode\n      description: Exchange authorization code for access token\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: finch.exchangeauthcode\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcompany\n      description: Get connected company information\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: finch.getcompany\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listdirectory\n      description: List employees in the company directory\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: finch.listdirectory\n      with:\n        limit: tools.limit\n        offset: tools.offset\n      inputParameters:\n      - name: limit\n        type: integer\n        description:\
  \ limit\n      - name: offset\n        type: integer\n        description: offset\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getindividuals\n      description: Get individual records (PII)\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: finch.getindividuals\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getemployment\n      description: Get employment records\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: finch.getemployment\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listpayments\n      description: List company payments (pay runs)\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: finch.listpayments\n      with:\n        start_date: tools.start_date\n        end_date: tools.end_date\n      inputParameters:\n\
  \      - name: start_date\n        type: string\n        description: start_date\n      - name: end_date\n        type: string\n        description: end_date\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getpaystatements\n      description: Get pay statements for one or more payments\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: finch.getpaystatements\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listbenefits\n      description: List company benefits\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: finch.listbenefits\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    FINCH_TOKEN: FINCH_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/finch/refs/heads/main/capabilities/finch-capability.yaml
tags:
- Finch
- API
tools:
- description: Create a Finch Connect session
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createconnectsession
- description: Exchange authorization code for access token
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: exchangeauthcode
- description: Get connected company information
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcompany
- description: List employees in the company directory
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listdirectory
- description: Get individual records (PII)
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: getindividuals
- description: Get employment records
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: getemployment
- description: List company payments (pay runs)
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listpayments
- description: Get pay statements for one or more payments
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: getpaystatements
- description: List company benefits
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listbenefits
---
