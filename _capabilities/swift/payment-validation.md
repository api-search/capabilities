---
categories: []
consumed_apis:
- swiftref
description: Unified payment validation capability combining the SWIFT SwiftRef reference data API. Enables payment operations teams and fintech developers to validate BICs, IBANs, LEIs, and routing codes before payment execution to achieve higher straight-through processing rates.
layout: capability
name: SWIFT Payment Validation
operations:
- description: Get BIC Details
  method: GET
  name: get-bic
  path: /v1/bics/{bic}
- description: Validate BIC
  method: GET
  name: validate-bic
  path: /v1/bics/{bic}/validity
- description: Get IBAN Details
  method: GET
  name: get-iban
  path: /v1/ibans/{iban}
- description: Validate IBAN
  method: GET
  name: validate-iban
  path: /v1/ibans/{iban}/validity
- description: Get LEI Details
  method: GET
  name: get-lei
  path: /v1/leis/{lei}
- description: Get National ID Details
  method: GET
  name: get-national-id
  path: /v1/national-ids/{national_id}
personas: []
provider_name: SWIFT
provider_slug: swift
search_terms:
- get national id
- get bic for iban
- gpi
- iso 20022
- get bic
- validate bic
- look up lei details
- validate lei
- get lei
- look up national clearing code or routing number details and associated bics
- validate and look up bic details
- iban validation
- get iban details
- cross-border payments
- look up iban details and bic
- financial services
- look up legal entity identifier details and gleif registration status
- check whether a bic is reachable via sepa ct, dd, or instant schemes
- get bic details
- banking
- resolve the bic routing code for a given iban
- payments
- bic validation
- get iban
- validate a bic
- get bic sepa reachability
- financial messaging
- get lei details
- look up national clearing codes
- validation
- validate an iban
- get national id details
- validate a legal entity identifier is active in gleif
- swift
- validate iban
- look up bic details including institution name, country, and swift connectivity
- validate iban format, check digits, country code, and bban structure
- reference data
- validate a bic is registered and active in the swift network
- look up iban details including associated bic, bank code, and account structure
slug: payment-validation
source_filename: payment-validation.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"SWIFT Payment Validation\"\n  description: >-\n    Unified payment validation capability combining the SWIFT SwiftRef reference\n    data API. Enables payment operations teams and fintech developers to validate\n    BICs, IBANs, LEIs, and routing codes before payment execution to achieve\n    higher straight-through processing rates.\n  tags:\n    - BIC Validation\n    - Financial Services\n    - IBAN Validation\n    - ISO 20022\n    - Payments\n    - Reference Data\n    - SWIFT\n    - Validation\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      SWIFT_CLIENT_ID: SWIFT_CLIENT_ID\n      SWIFT_CLIENT_SECRET: SWIFT_CLIENT_SECRET\n\ncapability:\n  consumes:\n    - import: swiftref\n      location: ./shared/swift-swiftref.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: swift-validation-api\n      description: \"Unified REST API for SWIFT financial identifier\
  \ validation.\"\n      resources:\n        - path: /v1/bics/{bic}\n          name: bics\n          description: \"Validate and look up BIC details\"\n          operations:\n            - method: GET\n              name: get-bic\n              description: \"Get BIC Details\"\n              call: \"swiftref.get-bic\"\n              with:\n                bic: \"rest.bic\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/bics/{bic}/validity\n          name: bic-validity\n          description: \"Validate a BIC\"\n          operations:\n            - method: GET\n              name: validate-bic\n              description: \"Validate BIC\"\n              call: \"swiftref.validate-bic\"\n              with:\n                bic: \"rest.bic\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/ibans/{iban}\n          name: ibans\n          description:\
  \ \"Look up IBAN details and BIC\"\n          operations:\n            - method: GET\n              name: get-iban\n              description: \"Get IBAN Details\"\n              call: \"swiftref.get-iban\"\n              with:\n                iban: \"rest.iban\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/ibans/{iban}/validity\n          name: iban-validity\n          description: \"Validate an IBAN\"\n          operations:\n            - method: GET\n              name: validate-iban\n              description: \"Validate IBAN\"\n              call: \"swiftref.validate-iban\"\n              with:\n                iban: \"rest.iban\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/leis/{lei}\n          name: leis\n          description: \"Look up LEI details\"\n          operations:\n            - method: GET\n              name: get-lei\n\
  \              description: \"Get LEI Details\"\n              call: \"swiftref.get-lei\"\n              with:\n                lei: \"rest.lei\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/national-ids/{national_id}\n          name: national-ids\n          description: \"Look up national clearing codes\"\n          operations:\n            - method: GET\n              name: get-national-id\n              description: \"Get National ID Details\"\n              call: \"swiftref.get-national-id\"\n              with:\n                national_id: \"rest.national_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: swift-validation-mcp\n      transport: http\n      description: \"MCP server for AI-assisted SWIFT payment identifier validation.\"\n      tools:\n        - name: get-bic\n          description:\
  \ \"Look up BIC details including institution name, country, and SWIFT connectivity\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"swiftref.get-bic\"\n          with:\n            bic: \"tools.bic\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: validate-bic\n          description: \"Validate a BIC is registered and active in the SWIFT network\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"swiftref.validate-bic\"\n          with:\n            bic: \"tools.bic\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-bic-sepa-reachability\n          description: \"Check whether a BIC is reachable via SEPA CT, DD, or Instant schemes\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"swiftref.get-bic\"\n          with:\n           \
  \ bic: \"tools.bic\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-iban\n          description: \"Look up IBAN details including associated BIC, bank code, and account structure\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"swiftref.get-iban\"\n          with:\n            iban: \"tools.iban\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: validate-iban\n          description: \"Validate IBAN format, check digits, country code, and BBAN structure\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"swiftref.validate-iban\"\n          with:\n            iban: \"tools.iban\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-bic-for-iban\n          description: \"Resolve the BIC routing code for a given IBAN\"\n\
  \          hints:\n            readOnly: true\n            idempotent: true\n          call: \"swiftref.get-bic-for-iban\"\n          with:\n            iban: \"tools.iban\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-lei\n          description: \"Look up Legal Entity Identifier details and GLEIF registration status\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"swiftref.get-lei\"\n          with:\n            lei: \"tools.lei\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: validate-lei\n          description: \"Validate a Legal Entity Identifier is active in GLEIF\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"swiftref.validate-lei\"\n          with:\n            lei: \"tools.lei\"\n          outputParameters:\n            - type: object\n              mapping:\
  \ \"$.\"\n\n        - name: get-national-id\n          description: \"Look up national clearing code or routing number details and associated BICs\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"swiftref.get-national-id\"\n          with:\n            national_id: \"tools.national_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/swift/refs/heads/main/capabilities/payment-validation.yaml
tags:
- BIC Validation
- Financial Services
- IBAN Validation
- ISO 20022
- Payments
- Reference Data
- SWIFT
- Validation
tools:
- description: Look up BIC details including institution name, country, and SWIFT connectivity
  hints:
    idempotent: true
    readOnly: true
  name: get-bic
- description: Validate a BIC is registered and active in the SWIFT network
  hints:
    idempotent: true
    readOnly: true
  name: validate-bic
- description: Check whether a BIC is reachable via SEPA CT, DD, or Instant schemes
  hints:
    idempotent: true
    readOnly: true
  name: get-bic-sepa-reachability
- description: Look up IBAN details including associated BIC, bank code, and account structure
  hints:
    idempotent: true
    readOnly: true
  name: get-iban
- description: Validate IBAN format, check digits, country code, and BBAN structure
  hints:
    idempotent: true
    readOnly: true
  name: validate-iban
- description: Resolve the BIC routing code for a given IBAN
  hints:
    idempotent: true
    readOnly: true
  name: get-bic-for-iban
- description: Look up Legal Entity Identifier details and GLEIF registration status
  hints:
    idempotent: true
    readOnly: true
  name: get-lei
- description: Validate a Legal Entity Identifier is active in GLEIF
  hints:
    idempotent: true
    readOnly: true
  name: validate-lei
- description: Look up national clearing code or routing number details and associated BICs
  hints:
    idempotent: true
    readOnly: true
  name: get-national-id
---
