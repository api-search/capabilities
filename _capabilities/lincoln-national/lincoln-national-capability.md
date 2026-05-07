---
categories: []
consumed_apis: []
description: Lincoln Financial provides LincSmart APIs for benefits administration integration. The platform includes Enrollment, EOI (Evidence of Insurability), and Plan Design APIs that enable real-time data sync between Lincoln Financial and benefits administration platforms such as ADP, Workday, Businessolver, bswift, and Benefitfocus.
layout: capability
name: Lincoln Financial LincSmart APIs
operations:
- description: Sync Enrollment Data
  method: POST
  name: syncenrollment
  path: /enrollment
- description: Submit Evidence of Insurability
  method: POST
  name: submiteoi
  path: /eoi
- description: Get Plan Design Information
  method: GET
  name: getplandesign
  path: /plan-design
personas: []
provider_name: Lincoln National
provider_slug: lincoln-national
search_terms:
- submit evidence of insurability
- submiteoi
- getplandesign
- annuities
- get plan design information
- lincoln
- insurance
- syncenrollment
- sync enrollment data
- api
- enrollment
- hr
- retirement
- benefits
- national
slug: lincoln-national-capability
source_filename: lincoln-national-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Lincoln Financial LincSmart APIs\n  description: Lincoln Financial provides LincSmart APIs for benefits administration integration. The platform includes Enrollment,\n    EOI (Evidence of Insurability), and Plan Design APIs that enable real-time data sync between Lincoln Financial and benefits\n    administration platforms such as ADP, Workday, Businessolver, bswift, and Benefitfocus.\n  tags:\n  - Lincoln\n  - National\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: lincoln-national\n    baseUri: https://www.lincolnfinancial.com\n    description: Lincoln Financial LincSmart APIs HTTP API.\n    resources:\n    - name: enrollment\n      path: /enrollment\n      operations:\n      - name: syncenrollment\n        method: POST\n        description: Sync Enrollment Data\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n    - name: eoi\n      path: /eoi\n      operations:\n      - name: submiteoi\n        method: POST\n        description: Submit Evidence of Insurability\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: plan-design\n      path: /plan-design\n      operations:\n      - name: getplandesign\n        method: GET\n        description: Get Plan Design Information\n        inputParameters:\n        - name: planId\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: lincoln-national-rest\n    description: REST adapter for Lincoln Financial LincSmart APIs.\n    resources:\n    - path: /enrollment\n      name: syncenrollment\n      operations:\n      - method: POST\n        name: syncenrollment\n\
  \        description: Sync Enrollment Data\n        call: lincoln-national.syncenrollment\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /eoi\n      name: submiteoi\n      operations:\n      - method: POST\n        name: submiteoi\n        description: Submit Evidence of Insurability\n        call: lincoln-national.submiteoi\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /plan-design\n      name: getplandesign\n      operations:\n      - method: GET\n        name: getplandesign\n        description: Get Plan Design Information\n        call: lincoln-national.getplandesign\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: lincoln-national-mcp\n    transport: http\n    description: MCP adapter for Lincoln Financial LincSmart APIs for AI agent use.\n    tools:\n    - name: syncenrollment\n      description: Sync Enrollment Data\n      hints:\n\
  \        readOnly: false\n        destructive: false\n        idempotent: false\n      call: lincoln-national.syncenrollment\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: submiteoi\n      description: Submit Evidence of Insurability\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: lincoln-national.submiteoi\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getplandesign\n      description: Get Plan Design Information\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: lincoln-national.getplandesign\n      with:\n        planId: tools.planId\n      inputParameters:\n      - name: planId\n        type: string\n        description: planId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/lincoln-national/refs/heads/main/capabilities/lincoln-national-capability.yaml
tags:
- Lincoln
- National
- API
tools:
- description: Sync Enrollment Data
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: syncenrollment
- description: Submit Evidence of Insurability
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: submiteoi
- description: Get Plan Design Information
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getplandesign
---
