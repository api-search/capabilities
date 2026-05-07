---
categories: []
consumed_apis: []
description: Fraud-prevention and dispute-management workflows on Shift4. Combines blacklist rules, fraud warnings, and chargeback disputes for risk and operations teams.
layout: capability
name: Shift4 Fraud and Dispute Operations
operations: []
personas: []
provider_name: Shift4 Payments
provider_slug: shift4-payments
search_terms:
- disputes
- list shift4 disputes (chargebacks).
- risk
- operations
- list fraud warnings
- payments
- retrieve a shift4 dispute by id.
- fintech
- get dispute
- shift4
- list shift4 fraud warnings.
- list disputes
- commerce
- checkout
- fraud
slug: fraud-and-disputes
source_filename: fraud-and-disputes.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Shift4 Fraud and Dispute Operations\n  description: Fraud-prevention and dispute-management workflows on Shift4. Combines blacklist rules, fraud warnings, and\n    chargeback disputes for risk and operations teams.\n  tags:\n  - Shift4\n  - Fraud\n  - Disputes\n  - Risk\n  - Operations\n  created: '2026-05-05'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SHIFT4_API_KEY: SHIFT4_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: shift4-disputes\n    baseUri: https://api.shift4.com\n    authentication:\n      type: basic\n      username: '{{SHIFT4_API_KEY}}'\n      password: ''\n    resources:\n    - name: disputes\n      path: /disputes\n      operations:\n      - name: list-disputes\n        method: GET\n        description: List disputes.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: dispute\n      path: /disputes/{dispute}\n\
  \      operations:\n      - name: get-dispute\n        method: GET\n        description: Retrieve a dispute by ID.\n        inputParameters:\n        - name: dispute\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: fraud-warnings\n      path: /fraud-warnings\n      operations:\n      - name: list-fraud-warnings\n        method: GET\n        description: List fraud warnings.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: mcp\n    port: 9082\n    namespace: shift4-fraud-disputes-mcp\n    transport: http\n    description: MCP surface for Shift4 fraud and dispute workflows.\n    tools:\n    - name: list-disputes\n      description: List Shift4 disputes (chargebacks).\n      hints:\n        readOnly: true\n      call: shift4-disputes.list-disputes\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-dispute\n      description: Retrieve a Shift4 dispute by ID.\n      hints:\n        readOnly: true\n      call: shift4-disputes.get-dispute\n      with:\n        dispute: tools.dispute\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-fraud-warnings\n      description: List Shift4 fraud warnings.\n      hints:\n        readOnly: true\n      call: shift4-disputes.list-fraud-warnings\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/shift4-payments/refs/heads/main/capabilities/fraud-and-disputes.yaml
tags:
- Shift4
- Fraud
- Disputes
- Risk
- Operations
tools:
- description: List Shift4 disputes (chargebacks).
  hints:
    readOnly: true
  name: list-disputes
- description: Retrieve a Shift4 dispute by ID.
  hints:
    readOnly: true
  name: get-dispute
- description: List Shift4 fraud warnings.
  hints:
    readOnly: true
  name: list-fraud-warnings
---
