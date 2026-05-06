---
categories: []
consumed_apis: []
description: Unified workflow for development organizations and financial inclusion teams to manage digital identities, process payments, and deliver services through the Community Pass ecosystem in underserved communities.
layout: capability
name: Mastercard Community Pass and Financial Inclusion
operations:
- description: Create a digital identity
  method: POST
  name: create-identity
  path: /v1/identities
- description: Process a Community Pass payment
  method: POST
  name: process-payment
  path: /v1/payments
personas: []
provider_name: Mastercard
provider_slug: mastercard
search_terms:
- fraud detection
- digital identity management
- process a community pass payment
- process community payment
- financial services
- financial inclusion
- community pass payments
- create digital identity
- create a digital identity in the community pass ecosystem
- credit cards
- create identity
- digital identity
- open banking
- process payment
- community pass
- verify digital identity
- mastercard
- payments
- create a digital identity
- process a payment in the community pass ecosystem
- verify a digital identity
slug: community-pass-and-inclusion
source_filename: community-pass-and-inclusion.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Mastercard Community Pass and Financial Inclusion\n  description: Unified workflow for development organizations and financial inclusion teams to manage digital identities,\n    process payments, and deliver services through the Community Pass ecosystem in underserved communities.\n  tags:\n  - Mastercard\n  - Community Pass\n  - Financial Inclusion\n  - Digital Identity\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    MASTERCARD_CONSUMER_KEY: MASTERCARD_CONSUMER_KEY\n    MASTERCARD_SIGNING_KEY: MASTERCARD_SIGNING_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: community-pass-identity\n    baseUri: https://api.mastercard.com/community-pass/identity\n    description: Mastercard Community Pass Digital Identity API\n    authentication:\n      type: oauth1\n      consumerKey: '{{MASTERCARD_CONSUMER_KEY}}'\n      signingKey: '{{MASTERCARD_SIGNING_KEY}}'\n    resources:\n    - name: identities\n\
  \      path: /identities\n      description: Digital identity management\n      operations:\n      - name: create-identity\n        method: POST\n        description: Create a digital identity\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            identity: '{{tools.identity}}'\n      - name: verify-identity\n        method: POST\n        description: Verify a digital identity\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            verification: '{{tools.verification}}'\n  - type: http\n    namespace: community-pass-payments\n    baseUri: https://api.mastercard.com/community-pass/payments\n    description: Mastercard Community Pass Payment APIs\n    authentication:\n      type: oauth1\n      consumerKey: '{{MASTERCARD_CONSUMER_KEY}}'\n\
  \      signingKey: '{{MASTERCARD_SIGNING_KEY}}'\n    resources:\n    - name: payments\n      path: /payments\n      description: Community Pass payment operations\n      operations:\n      - name: process-payment\n        method: POST\n        description: Process a Community Pass payment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            payment: '{{tools.payment}}'\n  exposes:\n  - type: rest\n    port: 8089\n    namespace: community-pass-api\n    description: Unified REST API for Community Pass and financial inclusion.\n    resources:\n    - path: /v1/identities\n      name: identities\n      description: Digital identity management\n      operations:\n      - method: POST\n        name: create-identity\n        description: Create a digital identity\n        call: community-pass-identity.create-identity\n        outputParameters:\n        -\
  \ type: object\n          mapping: $.\n    - path: /v1/payments\n      name: payments\n      description: Community Pass payments\n      operations:\n      - method: POST\n        name: process-payment\n        description: Process a Community Pass payment\n        call: community-pass-payments.process-payment\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9099\n    namespace: community-pass-mcp\n    transport: http\n    description: MCP server for AI-assisted Community Pass operations.\n    tools:\n    - name: create-digital-identity\n      description: Create a digital identity in the Community Pass ecosystem\n      hints:\n        readOnly: false\n      call: community-pass-identity.create-identity\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: verify-digital-identity\n      description: Verify a digital identity\n      hints:\n        readOnly: true\n      call: community-pass-identity.verify-identity\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: process-community-payment\n      description: Process a payment in the Community Pass ecosystem\n      hints:\n        readOnly: false\n      call: community-pass-payments.process-payment\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/mastercard/refs/heads/main/capabilities/community-pass-and-inclusion.yaml
tags:
- Mastercard
- Community Pass
- Financial Inclusion
- Digital Identity
tools:
- description: Create a digital identity in the Community Pass ecosystem
  hints:
    readOnly: false
  name: create-digital-identity
- description: Verify a digital identity
  hints:
    readOnly: true
  name: verify-digital-identity
- description: Process a payment in the Community Pass ecosystem
  hints:
    readOnly: false
  name: process-community-payment
---
