---
categories: []
consumed_apis: []
description: The ACME (Automatic Certificate Management Environment) protocol API used by Let's Encrypt to automate the issuance, renewal, and revocation of TLS certificates. Implements RFC 8555.
layout: capability
name: Let's Encrypt ACME API
operations:
- description: Get ACME directory
  method: GET
  name: getdirectory
  path: /directory
- description: Create or look up an account
  method: POST
  name: newaccount
  path: /acme/new-acct
- description: Update or deactivate account
  method: POST
  name: updateaccount
  path: /acme/acct/{accountId}
- description: Submit a new certificate order
  method: POST
  name: neworder
  path: /acme/new-order
- description: Get order status
  method: POST
  name: getorder
  path: /acme/order/{orderId}
- description: Finalize an order with a CSR
  method: POST
  name: finalizeorder
  path: /acme/finalize/{orderId}
- description: Get authorization status
  method: POST
  name: getauthorization
  path: /acme/authz/{authzId}
- description: Respond to a challenge
  method: POST
  name: respondchallenge
  path: /acme/chall/{challengeId}
- description: Download issued certificate
  method: POST
  name: getcertificate
  path: /acme/cert/{certId}
- description: Revoke a certificate
  method: POST
  name: revokecertificate
  path: /acme/revoke-cert
- description: Rotate account key
  method: POST
  name: keychange
  path: /acme/key-change
personas: []
provider_name: Let's Encrypt
provider_slug: lets-encrypt
search_terms:
- get order status
- neworder
- rotate account key
- lets
- finalizeorder
- getdirectory
- encrypt
- download issued certificate
- update or deactivate account
- pki
- get acme directory
- respond to a challenge
- linux foundation
- getorder
- security
- revokecertificate
- submit a new certificate order
- tls
- getauthorization
- respondchallenge
- revoke a certificate
- create or look up an account
- api
- updateaccount
- newaccount
- keychange
- getcertificate
- acme
- finalize an order with a csr
- certificates
- get authorization status
slug: lets-encrypt-capability
source_filename: lets-encrypt-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Let's Encrypt ACME API\n  description: The ACME (Automatic Certificate Management Environment) protocol API used by Let's Encrypt to automate the\n    issuance, renewal, and revocation of TLS certificates. Implements RFC 8555.\n  tags:\n  - Lets\n  - Encrypt\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: lets-encrypt\n    baseUri: https://acme-v02.api.letsencrypt.org\n    description: Let's Encrypt ACME API HTTP API.\n    resources:\n    - name: directory\n      path: /directory\n      operations:\n      - name: getdirectory\n        method: GET\n        description: Get ACME directory\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: acme-new-acct\n      path: /acme/new-acct\n      operations:\n      - name: newaccount\n        method: POST\n        description: Create or look\
  \ up an account\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: acme-acct-accountid\n      path: /acme/acct/{accountId}\n      operations:\n      - name: updateaccount\n        method: POST\n        description: Update or deactivate account\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: acme-new-order\n      path: /acme/new-order\n      operations:\n      - name: neworder\n        method: POST\n        description: Submit a new certificate order\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: acme-order-orderid\n      path: /acme/order/{orderId}\n      operations:\n      - name: getorder\n   \
  \     method: POST\n        description: Get order status\n        inputParameters:\n        - name: orderId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: acme-finalize-orderid\n      path: /acme/finalize/{orderId}\n      operations:\n      - name: finalizeorder\n        method: POST\n        description: Finalize an order with a CSR\n        inputParameters:\n        - name: orderId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: acme-authz-authzid\n      path: /acme/authz/{authzId}\n      operations:\n      - name: getauthorization\n        method: POST\n        description: Get authorization status\n        inputParameters:\n        - name: authzId\n          in:\
  \ path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: acme-chall-challengeid\n      path: /acme/chall/{challengeId}\n      operations:\n      - name: respondchallenge\n        method: POST\n        description: Respond to a challenge\n        inputParameters:\n        - name: challengeId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: acme-cert-certid\n      path: /acme/cert/{certId}\n      operations:\n      - name: getcertificate\n        method: POST\n        description: Download issued certificate\n        inputParameters:\n        - name: certId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n       \
  \ - name: result\n          type: object\n          value: $.\n    - name: acme-revoke-cert\n      path: /acme/revoke-cert\n      operations:\n      - name: revokecertificate\n        method: POST\n        description: Revoke a certificate\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: acme-key-change\n      path: /acme/key-change\n      operations:\n      - name: keychange\n        method: POST\n        description: Rotate account key\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: lets-encrypt-rest\n    description: REST adapter for Let's Encrypt ACME API.\n    resources:\n    - path: /directory\n      name: getdirectory\n      operations:\n      - method: GET\n        name: getdirectory\n        description: Get ACME directory\n        call: lets-encrypt.getdirectory\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /acme/new-acct\n      name: newaccount\n      operations:\n      - method: POST\n        name: newaccount\n        description: Create or look up an account\n        call: lets-encrypt.newaccount\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /acme/acct/{accountId}\n      name: updateaccount\n      operations:\n      - method: POST\n        name: updateaccount\n        description: Update or deactivate account\n        call: lets-encrypt.updateaccount\n        with:\n          accountId: rest.accountId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /acme/new-order\n      name: neworder\n      operations:\n      - method: POST\n        name: neworder\n        description: Submit a new certificate order\n        call: lets-encrypt.neworder\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path:\
  \ /acme/order/{orderId}\n      name: getorder\n      operations:\n      - method: POST\n        name: getorder\n        description: Get order status\n        call: lets-encrypt.getorder\n        with:\n          orderId: rest.orderId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /acme/finalize/{orderId}\n      name: finalizeorder\n      operations:\n      - method: POST\n        name: finalizeorder\n        description: Finalize an order with a CSR\n        call: lets-encrypt.finalizeorder\n        with:\n          orderId: rest.orderId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /acme/authz/{authzId}\n      name: getauthorization\n      operations:\n      - method: POST\n        name: getauthorization\n        description: Get authorization status\n        call: lets-encrypt.getauthorization\n        with:\n          authzId: rest.authzId\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /acme/chall/{challengeId}\n      name: respondchallenge\n      operations:\n      - method: POST\n        name: respondchallenge\n        description: Respond to a challenge\n        call: lets-encrypt.respondchallenge\n        with:\n          challengeId: rest.challengeId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /acme/cert/{certId}\n      name: getcertificate\n      operations:\n      - method: POST\n        name: getcertificate\n        description: Download issued certificate\n        call: lets-encrypt.getcertificate\n        with:\n          certId: rest.certId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /acme/revoke-cert\n      name: revokecertificate\n      operations:\n      - method: POST\n        name: revokecertificate\n        description: Revoke a certificate\n        call: lets-encrypt.revokecertificate\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /acme/key-change\n      name: keychange\n      operations:\n      - method: POST\n        name: keychange\n        description: Rotate account key\n        call: lets-encrypt.keychange\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: lets-encrypt-mcp\n    transport: http\n    description: MCP adapter for Let's Encrypt ACME API for AI agent use.\n    tools:\n    - name: getdirectory\n      description: Get ACME directory\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: lets-encrypt.getdirectory\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: newaccount\n      description: Create or look up an account\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: lets-encrypt.newaccount\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateaccount\n\
  \      description: Update or deactivate account\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: lets-encrypt.updateaccount\n      with:\n        accountId: tools.accountId\n      inputParameters:\n      - name: accountId\n        type: string\n        description: accountId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: neworder\n      description: Submit a new certificate order\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: lets-encrypt.neworder\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getorder\n      description: Get order status\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: lets-encrypt.getorder\n      with:\n        orderId: tools.orderId\n      inputParameters:\n      - name: orderId\n        type: string\n\
  \        description: orderId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: finalizeorder\n      description: Finalize an order with a CSR\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: lets-encrypt.finalizeorder\n      with:\n        orderId: tools.orderId\n      inputParameters:\n      - name: orderId\n        type: string\n        description: orderId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getauthorization\n      description: Get authorization status\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: lets-encrypt.getauthorization\n      with:\n        authzId: tools.authzId\n      inputParameters:\n      - name: authzId\n        type: string\n        description: authzId\n        required: true\n      outputParameters:\n      - type: object\n   \
  \     mapping: $.\n    - name: respondchallenge\n      description: Respond to a challenge\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: lets-encrypt.respondchallenge\n      with:\n        challengeId: tools.challengeId\n      inputParameters:\n      - name: challengeId\n        type: string\n        description: challengeId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcertificate\n      description: Download issued certificate\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: lets-encrypt.getcertificate\n      with:\n        certId: tools.certId\n      inputParameters:\n      - name: certId\n        type: string\n        description: certId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: revokecertificate\n      description: Revoke a certificate\n   \
  \   hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: lets-encrypt.revokecertificate\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: keychange\n      description: Rotate account key\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: lets-encrypt.keychange\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/lets-encrypt/refs/heads/main/capabilities/lets-encrypt-capability.yaml
tags:
- Lets
- Encrypt
- API
tools:
- description: Get ACME directory
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdirectory
- description: Create or look up an account
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: newaccount
- description: Update or deactivate account
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateaccount
- description: Submit a new certificate order
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: neworder
- description: Get order status
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: getorder
- description: Finalize an order with a CSR
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: finalizeorder
- description: Get authorization status
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: getauthorization
- description: Respond to a challenge
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: respondchallenge
- description: Download issued certificate
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: getcertificate
- description: Revoke a certificate
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: revokecertificate
- description: Rotate account key
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: keychange
---
