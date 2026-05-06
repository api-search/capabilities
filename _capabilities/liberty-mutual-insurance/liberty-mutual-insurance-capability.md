---
categories: []
consumed_apis: []
description: The Liberty Mutual Renters Insurance API enables partners to offer affordable renters insurance with an easy quote and bind experience.
layout: capability
name: Liberty Mutual Renters Insurance API
operations:
- description: Create Quote
  method: POST
  name: createquote
  path: /quotes
- description: Get Quote
  method: GET
  name: getquote
  path: /quotes/{quoteId}
- description: Bind Policy
  method: POST
  name: bindpolicy
  path: /policies
personas: []
provider_name: Liberty Mutual Insurance
provider_slug: liberty-mutual-insurance
search_terms:
- insurance
- personal lines
- bindpolicy
- create quote
- bind policy
- liberty
- property
- api
- casualty
- getquote
- commercial lines
- renters
- createquote
- get quote
- safety data
- mutual
slug: liberty-mutual-insurance-capability
source_filename: liberty-mutual-insurance-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Liberty Mutual Renters Insurance API\n  description: The Liberty Mutual Renters Insurance API enables partners to offer affordable renters insurance with an easy\n    quote and bind experience.\n  tags:\n  - Liberty\n  - Mutual\n  - Insurance\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: liberty-mutual-insurance\n    baseUri: https://api.libertymutual.com\n    description: Liberty Mutual Renters Insurance API HTTP API.\n    resources:\n    - name: quotes\n      path: /quotes\n      operations:\n      - name: createquote\n        method: POST\n        description: Create Quote\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: quotes-quoteid\n      path: /quotes/{quoteId}\n      operations:\n      - name: getquote\n        method: GET\n        description: Get Quote\n        inputParameters:\n\
  \        - name: quoteId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: policies\n      path: /policies\n      operations:\n      - name: bindpolicy\n        method: POST\n        description: Bind Policy\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: liberty-mutual-insurance-rest\n    description: REST adapter for Liberty Mutual Renters Insurance API.\n    resources:\n    - path: /quotes\n      name: createquote\n      operations:\n      - method: POST\n        name: createquote\n        description: Create Quote\n        call: liberty-mutual-insurance.createquote\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /quotes/{quoteId}\n      name: getquote\n\
  \      operations:\n      - method: GET\n        name: getquote\n        description: Get Quote\n        call: liberty-mutual-insurance.getquote\n        with:\n          quoteId: rest.quoteId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /policies\n      name: bindpolicy\n      operations:\n      - method: POST\n        name: bindpolicy\n        description: Bind Policy\n        call: liberty-mutual-insurance.bindpolicy\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: liberty-mutual-insurance-mcp\n    transport: http\n    description: MCP adapter for Liberty Mutual Renters Insurance API for AI agent use.\n    tools:\n    - name: createquote\n      description: Create Quote\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: liberty-mutual-insurance.createquote\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: getquote\n      description: Get Quote\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: liberty-mutual-insurance.getquote\n      with:\n        quoteId: tools.quoteId\n      inputParameters:\n      - name: quoteId\n        type: string\n        description: quoteId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: bindpolicy\n      description: Bind Policy\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: liberty-mutual-insurance.bindpolicy\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/liberty-mutual-insurance/refs/heads/main/capabilities/liberty-mutual-insurance-capability.yaml
tags:
- Liberty
- Mutual
- Insurance
- API
tools:
- description: Create Quote
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createquote
- description: Get Quote
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getquote
- description: Bind Policy
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: bindpolicy
---
