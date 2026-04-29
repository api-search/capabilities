---
categories: []
consumed_apis:
- mdes-digital
- mdes-token-connect
- mdes-pre-digitization
- mdes-bulk-tokenization
- token-requestor-id
- issuer-click-to-pay
description: Unified workflow for digital payment teams and issuer technology to manage card tokenization, MDES digital enablement, Click to Pay enrollment, and push provisioning to digital wallets.
layout: capability
name: Mastercard Digital Enablement and Tokenization
operations:
- description: Tokenize a payment card
  method: POST
  name: tokenize-card
  path: /v1/tokens
- description: Check card eligibility for digitization
  method: POST
  name: check-digitization-eligibility
  path: /v1/eligibility
- description: Submit bulk tokenization request
  method: POST
  name: submit-bulk-tokenization
  path: /v1/bulk-tokenization
- description: Push provision a token to a wallet
  method: POST
  name: push-provision
  path: /v1/provisioning
personas: []
provider_name: Mastercard
provider_slug: mastercard
search_terms:
- digital payments
- tokenize a payment card via mdes
- digital identity
- tokenize a payment card
- payments
- click to pay
- check card eligibility for digitization
- check if a card is eligible for digitization
- delete token
- open banking
- enroll an issuer in click to pay
- suspend an active token
- bulk tokenization operations
- delete a token
- check digitization eligibility
- tokenize card
- tokenization
- fraud detection
- submit bulk tokenization
- token lifecycle management
- enroll issuer click to pay
- suspend token
- push provisioning to wallets
- mdes
- register token requestor
- credit cards
- get token details
- register a new token requestor
- submit bulk tokenization request
- financial services
- mastercard
- push provision a token to a digital wallet
- push provision a token to a wallet
- pre-digitization eligibility
- push provision to wallet
- submit a bulk tokenization request for a card portfolio
- push provision
slug: digital-enablement-and-tokenization
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Mastercard Digital Enablement and Tokenization\"\n  description: \"Unified workflow for digital payment teams and issuer technology to manage card tokenization, MDES digital enablement, Click to Pay enrollment, and push provisioning to digital wallets.\"\n  tags:\n    - Mastercard\n    - Tokenization\n    - MDES\n    - Digital Payments\n    - Click to Pay\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      MASTERCARD_CONSUMER_KEY: MASTERCARD_CONSUMER_KEY\n      MASTERCARD_SIGNING_KEY: MASTERCARD_SIGNING_KEY\n\ncapability:\n  consumes:\n    - import: mdes-digital\n      location: ./shared/mdes-digital-enablement.yaml\n    - import: mdes-token-connect\n      location: ./shared/mdes-token-connect.yaml\n    - import: mdes-pre-digitization\n      location: ./shared/mdes-pre-digitization.yaml\n    - import: mdes-bulk-tokenization\n      location: ./shared/mdes-bulk-tokenization.yaml\n\
  \    - import: token-requestor-id\n      location: ./shared/token-requestor-id.yaml\n    - import: issuer-click-to-pay\n      location: ./shared/issuer-enrollment-click-to-pay.yaml\n\n  exposes:\n    - type: rest\n      port: 8088\n      namespace: digital-token-api\n      description: \"Unified REST API for digital enablement and tokenization.\"\n      resources:\n        - path: /v1/tokens\n          name: tokens\n          description: \"Token lifecycle management\"\n          operations:\n            - method: POST\n              name: tokenize-card\n              description: \"Tokenize a payment card\"\n              call: \"mdes-digital.tokenize\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/eligibility\n          name: eligibility\n          description: \"Pre-digitization eligibility\"\n          operations:\n            - method: POST\n              name: check-digitization-eligibility\n             \
  \ description: \"Check card eligibility for digitization\"\n              call: \"mdes-pre-digitization.check-eligibility\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/bulk-tokenization\n          name: bulk-tokenization\n          description: \"Bulk tokenization operations\"\n          operations:\n            - method: POST\n              name: submit-bulk-tokenization\n              description: \"Submit bulk tokenization request\"\n              call: \"mdes-bulk-tokenization.submit-bulk-tokenization\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/provisioning\n          name: provisioning\n          description: \"Push provisioning to wallets\"\n          operations:\n            - method: POST\n              name: push-provision\n              description: \"Push provision a token to a wallet\"\n              call: \"mdes-token-connect.push-provision\"\
  \n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9098\n      namespace: digital-token-mcp\n      transport: http\n      description: \"MCP server for AI-assisted digital enablement and tokenization.\"\n      tools:\n        - name: tokenize-card\n          description: \"Tokenize a payment card via MDES\"\n          hints:\n            readOnly: false\n          call: \"mdes-digital.tokenize\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-token-details\n          description: \"Get token details\"\n          hints:\n            readOnly: true\n          call: \"mdes-digital.get-token\"\n          with:\n            token_id: \"tools.token_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: suspend-token\n          description: \"Suspend an active token\"\n          hints:\n          \
  \  readOnly: false\n          call: \"mdes-digital.suspend-token\"\n          with:\n            token_id: \"tools.token_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-token\n          description: \"Delete a token\"\n          hints:\n            readOnly: false\n            destructive: true\n          call: \"mdes-digital.delete-token\"\n          with:\n            token_id: \"tools.token_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: check-digitization-eligibility\n          description: \"Check if a card is eligible for digitization\"\n          hints:\n            readOnly: true\n          call: \"mdes-pre-digitization.check-eligibility\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: push-provision-to-wallet\n          description: \"Push provision a token to a digital wallet\"\n          hints:\n\
  \            readOnly: false\n          call: \"mdes-token-connect.push-provision\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: submit-bulk-tokenization\n          description: \"Submit a bulk tokenization request for a card portfolio\"\n          hints:\n            readOnly: false\n          call: \"mdes-bulk-tokenization.submit-bulk-tokenization\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: register-token-requestor\n          description: \"Register a new token requestor\"\n          hints:\n            readOnly: false\n          call: \"token-requestor-id.register-requestor\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: enroll-issuer-click-to-pay\n          description: \"Enroll an issuer in Click to Pay\"\n          hints:\n            readOnly: false\n          call: \"issuer-click-to-pay.enroll-issuer\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/mastercard/refs/heads/main/capabilities/digital-enablement-and-tokenization.yaml
tags:
- Mastercard
- Tokenization
- MDES
- Digital Payments
- Click to Pay
tools:
- description: Tokenize a payment card via MDES
  hints:
    readOnly: false
  name: tokenize-card
- description: Get token details
  hints:
    readOnly: true
  name: get-token-details
- description: Suspend an active token
  hints:
    readOnly: false
  name: suspend-token
- description: Delete a token
  hints:
    destructive: true
    readOnly: false
  name: delete-token
- description: Check if a card is eligible for digitization
  hints:
    readOnly: true
  name: check-digitization-eligibility
- description: Push provision a token to a digital wallet
  hints:
    readOnly: false
  name: push-provision-to-wallet
- description: Submit a bulk tokenization request for a card portfolio
  hints:
    readOnly: false
  name: submit-bulk-tokenization
- description: Register a new token requestor
  hints:
    readOnly: false
  name: register-token-requestor
- description: Enroll an issuer in Click to Pay
  hints:
    readOnly: false
  name: enroll-issuer-click-to-pay
---
