---
categories: []
consumed_apis: []
description: The ADP Payroll API provides programmatic access to payroll processing, payroll output data, and compensation management. REST APIs support payroll runs, payroll output retrieval (including CSV-formatted bulk data), and headcount and compensation analysis across ADP payroll platforms.
layout: capability
name: ADP Payroll API
operations:
- description: List Payroll Outputs
  method: GET
  name: listpayrolloutputs
  path: /payroll/v1/payroll-outputs
- description: Get Payroll Output Details
  method: GET
  name: getpayrolloutput
  path: /payroll/v1/payroll-outputs/{payrollOutputID}
- description: Get Worker-level Payroll Outputs
  method: GET
  name: getpayrollworkeroutputs
  path: /payroll/v1/payroll-outputs/{payrollOutputID}/worker-outputs
- description: List Payroll Instructions
  method: GET
  name: listpayrollinstructions
  path: /payroll/v1/payroll-instructions
- description: Create Payroll Instruction
  method: POST
  name: createpayrollinstruction
  path: /payroll/v1/payroll-instructions
personas: []
provider_name: ADP
provider_slug: adp
search_terms:
- adp
- list payroll instructions
- listpayrollinstructions
- hcm
- getpayrolloutput
- getpayrollworkeroutputs
- get worker-level payroll outputs
- createpayrollinstruction
- list payroll outputs
- get payroll output details
- payroll
- workforce
- hr
- api
- benefits
- listpayrolloutputs
- create payroll instruction
slug: adp-capability
source_filename: adp-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: ADP Payroll API\n  description: The ADP Payroll API provides programmatic access to payroll processing, payroll output data, and compensation\n    management. REST APIs support payroll runs, payroll output retrieval (including CSV-formatted bulk data), and headcount\n    and compensation analysis across ADP payroll platforms.\n  tags:\n  - Adp\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: adp\n    baseUri: https://api.adp.com\n    description: ADP Payroll API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{ADP_TOKEN}}'\n    resources:\n    - name: payroll-v1-payroll-outputs\n      path: /payroll/v1/payroll-outputs\n      operations:\n      - name: listpayrolloutputs\n        method: GET\n        description: List Payroll Outputs\n        inputParameters:\n        - name: $filter\n          in: query\n          type: string\n          description:\
  \ OData filter expression\n        - name: $top\n          in: query\n          type: integer\n        - name: $skip\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: payroll-v1-payroll-outputs-payrolloutputid\n      path: /payroll/v1/payroll-outputs/{payrollOutputID}\n      operations:\n      - name: getpayrolloutput\n        method: GET\n        description: Get Payroll Output Details\n        inputParameters:\n        - name: payrollOutputID\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: payroll-v1-payroll-outputs-payrolloutputid-worke\n      path: /payroll/v1/payroll-outputs/{payrollOutputID}/worker-outputs\n      operations:\n      - name: getpayrollworkeroutputs\n        method: GET\n \
  \       description: Get Worker-level Payroll Outputs\n        inputParameters:\n        - name: payrollOutputID\n          in: path\n          type: string\n          required: true\n        - name: $top\n          in: query\n          type: integer\n        - name: $skip\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: payroll-v1-payroll-instructions\n      path: /payroll/v1/payroll-instructions\n      operations:\n      - name: listpayrollinstructions\n        method: GET\n        description: List Payroll Instructions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createpayrollinstruction\n        method: POST\n        description: Create Payroll Instruction\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: adp-rest\n    description: REST adapter for ADP Payroll API.\n    resources:\n    - path: /payroll/v1/payroll-outputs\n      name: listpayrolloutputs\n      operations:\n      - method: GET\n        name: listpayrolloutputs\n        description: List Payroll Outputs\n        call: adp.listpayrolloutputs\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /payroll/v1/payroll-outputs/{payrollOutputID}\n      name: getpayrolloutput\n      operations:\n      - method: GET\n        name: getpayrolloutput\n        description: Get Payroll Output Details\n        call: adp.getpayrolloutput\n        with:\n          payrollOutputID: rest.payrollOutputID\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /payroll/v1/payroll-outputs/{payrollOutputID}/worker-outputs\n      name: getpayrollworkeroutputs\n      operations:\n      - method:\
  \ GET\n        name: getpayrollworkeroutputs\n        description: Get Worker-level Payroll Outputs\n        call: adp.getpayrollworkeroutputs\n        with:\n          payrollOutputID: rest.payrollOutputID\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /payroll/v1/payroll-instructions\n      name: listpayrollinstructions\n      operations:\n      - method: GET\n        name: listpayrollinstructions\n        description: List Payroll Instructions\n        call: adp.listpayrollinstructions\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /payroll/v1/payroll-instructions\n      name: createpayrollinstruction\n      operations:\n      - method: POST\n        name: createpayrollinstruction\n        description: Create Payroll Instruction\n        call: adp.createpayrollinstruction\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: adp-mcp\n   \
  \ transport: http\n    description: MCP adapter for ADP Payroll API for AI agent use.\n    tools:\n    - name: listpayrolloutputs\n      description: List Payroll Outputs\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: adp.listpayrolloutputs\n      with:\n        $filter: tools.$filter\n        $top: tools.$top\n        $skip: tools.$skip\n      inputParameters:\n      - name: $filter\n        type: string\n        description: OData filter expression\n      - name: $top\n        type: integer\n        description: $top\n      - name: $skip\n        type: integer\n        description: $skip\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getpayrolloutput\n      description: Get Payroll Output Details\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: adp.getpayrolloutput\n      with:\n        payrollOutputID: tools.payrollOutputID\n      inputParameters:\n\
  \      - name: payrollOutputID\n        type: string\n        description: payrollOutputID\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getpayrollworkeroutputs\n      description: Get Worker-level Payroll Outputs\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: adp.getpayrollworkeroutputs\n      with:\n        payrollOutputID: tools.payrollOutputID\n        $top: tools.$top\n        $skip: tools.$skip\n      inputParameters:\n      - name: payrollOutputID\n        type: string\n        description: payrollOutputID\n        required: true\n      - name: $top\n        type: integer\n        description: $top\n      - name: $skip\n        type: integer\n        description: $skip\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listpayrollinstructions\n      description: List Payroll Instructions\n      hints:\n        readOnly: true\n       \
  \ destructive: false\n        idempotent: true\n      call: adp.listpayrollinstructions\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createpayrollinstruction\n      description: Create Payroll Instruction\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: adp.createpayrollinstruction\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    ADP_TOKEN: ADP_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/adp/refs/heads/main/capabilities/adp-capability.yaml
tags:
- Adp
- API
tools:
- description: List Payroll Outputs
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listpayrolloutputs
- description: Get Payroll Output Details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getpayrolloutput
- description: Get Worker-level Payroll Outputs
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getpayrollworkeroutputs
- description: List Payroll Instructions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listpayrollinstructions
- description: Create Payroll Instruction
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createpayrollinstruction
---
