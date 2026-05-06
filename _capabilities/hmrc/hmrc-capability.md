---
categories: []
consumed_apis: []
description: The HMRC VAT Making Tax Digital (MTD) API enables VAT-registered businesses and agents to submit VAT returns, view VAT obligations, liabilities, and payments, in compliance with UK Making Tax Digital requirements. Requires OAuth 2.0 authentication and mandatory fraud prevention headers on all requests.
layout: capability
name: HMRC VAT (Making Tax Digital) API
operations:
- description: Retrieve VAT obligations
  method: GET
  name: getvatobligations
  path: /organisations/vat/{vrn}/obligations
- description: Submit a VAT return
  method: POST
  name: submitvatreturn
  path: /organisations/vat/{vrn}/returns
- description: View a submitted VAT return
  method: GET
  name: getvatreturn
  path: /organisations/vat/{vrn}/returns/{periodKey}
- description: Retrieve VAT payments
  method: GET
  name: getvatpayments
  path: /organisations/vat/{vrn}/payments
- description: Retrieve VAT liabilities
  method: GET
  name: getvatliabilities
  path: /organisations/vat/{vrn}/liabilities
personas: []
provider_name: HMRC UK Tax Authority
provider_slug: hmrc
search_terms:
- retrieve vat liabilities
- government
- getvatpayments
- retrieve vat payments
- api
- making tax digital
- view a submitted vat return
- submitvatreturn
- getvatreturn
- tax
- uk
- submit a vat return
- regulatory
- retrieve vat obligations
- hmrc
- getvatliabilities
- getvatobligations
slug: hmrc-capability
source_filename: hmrc-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: HMRC VAT (Making Tax Digital) API\n  description: The HMRC VAT Making Tax Digital (MTD) API enables VAT-registered businesses and agents to submit VAT returns,\n    view VAT obligations, liabilities, and payments, in compliance with UK Making Tax Digital requirements. Requires OAuth\n    2.0 authentication and mandatory fraud prevention headers on all requests.\n  tags:\n  - Hmrc\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: hmrc\n    baseUri: https://api.service.hmrc.gov.uk\n    description: HMRC VAT (Making Tax Digital) API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{HMRC_TOKEN}}'\n    resources:\n    - name: organisations-vat-vrn-obligations\n      path: /organisations/vat/{vrn}/obligations\n      operations:\n      - name: getvatobligations\n        method: GET\n        description: Retrieve VAT obligations\n        inputParameters:\n  \
  \      - name: vrn\n          in: path\n          type: string\n          required: true\n          description: VAT Registration Number (9 digits)\n        - name: from\n          in: query\n          type: string\n          required: true\n          description: Obligation period start date (YYYY-MM-DD), minimum 2017-01-01\n        - name: to\n          in: query\n          type: string\n          required: true\n          description: Obligation period end date (must be within 366 days of 'from')\n        - name: status\n          in: query\n          type: string\n        - name: Authorization\n          in: header\n          type: string\n          required: true\n          description: Bearer token (OAuth 2.0)\n        - name: Gov-Client-Connection-Method\n          in: header\n          type: string\n          required: true\n          description: Fraud prevention header – client connection method\n        - name: Gov-Vendor-Version\n          in: header\n          type: string\n\
  \          required: true\n          description: Fraud prevention header – vendor application version\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organisations-vat-vrn-returns\n      path: /organisations/vat/{vrn}/returns\n      operations:\n      - name: submitvatreturn\n        method: POST\n        description: Submit a VAT return\n        inputParameters:\n        - name: vrn\n          in: path\n          type: string\n          required: true\n        - name: Authorization\n          in: header\n          type: string\n          required: true\n        - name: Gov-Client-Connection-Method\n          in: header\n          type: string\n          required: true\n        - name: Gov-Vendor-Version\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n    - name: organisations-vat-vrn-returns-periodkey\n      path: /organisations/vat/{vrn}/returns/{periodKey}\n      operations:\n      - name: getvatreturn\n        method: GET\n        description: View a submitted VAT return\n        inputParameters:\n        - name: vrn\n          in: path\n          type: string\n          required: true\n        - name: periodKey\n          in: path\n          type: string\n          required: true\n          description: Period key from the obligation (e.g., \"23AA\")\n        - name: Authorization\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organisations-vat-vrn-payments\n      path: /organisations/vat/{vrn}/payments\n      operations:\n      - name: getvatpayments\n        method: GET\n        description: Retrieve VAT payments\n        inputParameters:\n        - name: vrn\n\
  \          in: path\n          type: string\n          required: true\n        - name: from\n          in: query\n          type: string\n          required: true\n        - name: to\n          in: query\n          type: string\n          required: true\n        - name: Authorization\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organisations-vat-vrn-liabilities\n      path: /organisations/vat/{vrn}/liabilities\n      operations:\n      - name: getvatliabilities\n        method: GET\n        description: Retrieve VAT liabilities\n        inputParameters:\n        - name: vrn\n          in: path\n          type: string\n          required: true\n        - name: from\n          in: query\n          type: string\n          required: true\n        - name: to\n          in: query\n          type: string\n          required: true\n\
  \        - name: Authorization\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: hmrc-rest\n    description: REST adapter for HMRC VAT (Making Tax Digital) API.\n    resources:\n    - path: /organisations/vat/{vrn}/obligations\n      name: getvatobligations\n      operations:\n      - method: GET\n        name: getvatobligations\n        description: Retrieve VAT obligations\n        call: hmrc.getvatobligations\n        with:\n          vrn: rest.vrn\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organisations/vat/{vrn}/returns\n      name: submitvatreturn\n      operations:\n      - method: POST\n        name: submitvatreturn\n        description: Submit a VAT return\n        call: hmrc.submitvatreturn\n        with:\n          vrn: rest.vrn\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organisations/vat/{vrn}/returns/{periodKey}\n      name: getvatreturn\n      operations:\n      - method: GET\n        name: getvatreturn\n        description: View a submitted VAT return\n        call: hmrc.getvatreturn\n        with:\n          vrn: rest.vrn\n          periodKey: rest.periodKey\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organisations/vat/{vrn}/payments\n      name: getvatpayments\n      operations:\n      - method: GET\n        name: getvatpayments\n        description: Retrieve VAT payments\n        call: hmrc.getvatpayments\n        with:\n          vrn: rest.vrn\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organisations/vat/{vrn}/liabilities\n      name: getvatliabilities\n      operations:\n      - method: GET\n        name: getvatliabilities\n        description: Retrieve VAT liabilities\n\
  \        call: hmrc.getvatliabilities\n        with:\n          vrn: rest.vrn\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: hmrc-mcp\n    transport: http\n    description: MCP adapter for HMRC VAT (Making Tax Digital) API for AI agent use.\n    tools:\n    - name: getvatobligations\n      description: Retrieve VAT obligations\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: hmrc.getvatobligations\n      with:\n        vrn: tools.vrn\n        from: tools.from\n        to: tools.to\n        status: tools.status\n      inputParameters:\n      - name: vrn\n        type: string\n        description: VAT Registration Number (9 digits)\n        required: true\n      - name: from\n        type: string\n        description: Obligation period start date (YYYY-MM-DD), minimum 2017-01-01\n        required: true\n      - name: to\n        type: string\n        description:\
  \ Obligation period end date (must be within 366 days of 'from')\n        required: true\n      - name: status\n        type: string\n        description: status\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: submitvatreturn\n      description: Submit a VAT return\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: hmrc.submitvatreturn\n      with:\n        vrn: tools.vrn\n      inputParameters:\n      - name: vrn\n        type: string\n        description: vrn\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getvatreturn\n      description: View a submitted VAT return\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: hmrc.getvatreturn\n      with:\n        vrn: tools.vrn\n        periodKey: tools.periodKey\n      inputParameters:\n      - name: vrn\n        type: string\n        description:\
  \ vrn\n        required: true\n      - name: periodKey\n        type: string\n        description: Period key from the obligation (e.g., \"23AA\")\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getvatpayments\n      description: Retrieve VAT payments\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: hmrc.getvatpayments\n      with:\n        vrn: tools.vrn\n        from: tools.from\n        to: tools.to\n      inputParameters:\n      - name: vrn\n        type: string\n        description: vrn\n        required: true\n      - name: from\n        type: string\n        description: from\n        required: true\n      - name: to\n        type: string\n        description: to\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getvatliabilities\n      description: Retrieve VAT liabilities\n      hints:\n        readOnly: true\n\
  \        destructive: false\n        idempotent: true\n      call: hmrc.getvatliabilities\n      with:\n        vrn: tools.vrn\n        from: tools.from\n        to: tools.to\n      inputParameters:\n      - name: vrn\n        type: string\n        description: vrn\n        required: true\n      - name: from\n        type: string\n        description: from\n        required: true\n      - name: to\n        type: string\n        description: to\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    HMRC_TOKEN: HMRC_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/hmrc/refs/heads/main/capabilities/hmrc-capability.yaml
tags:
- Hmrc
- API
tools:
- description: Retrieve VAT obligations
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getvatobligations
- description: Submit a VAT return
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: submitvatreturn
- description: View a submitted VAT return
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getvatreturn
- description: Retrieve VAT payments
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getvatpayments
- description: Retrieve VAT liabilities
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getvatliabilities
---
