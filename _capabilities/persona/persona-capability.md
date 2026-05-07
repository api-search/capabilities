---
categories: []
consumed_apis: []
description: The Persona API enables identity verification, fraud prevention, and Know Your Customer (KYC) workflows. Use the API to create and manage inquiries, accounts, verifications, reports, transactions, lists, and webhooks for verifying users via document checks, selfie checks, and database lookups.
layout: capability
name: Persona API
operations:
- description: List all Accounts
  method: GET
  name: listaccounts
  path: /accounts
- description: Create an Account
  method: POST
  name: createaccount
  path: /accounts
- description: Retrieve an Account
  method: GET
  name: retrieveaccount
  path: /accounts/{id}
- description: Update an Account
  method: PATCH
  name: updateaccount
  path: /accounts/{id}
- description: Redact an Account
  method: POST
  name: redactaccount
  path: /accounts/{id}/redact
- description: Add tag to an Account
  method: POST
  name: addaccounttag
  path: /accounts/{id}/tags
- description: Remove tag from an Account
  method: DELETE
  name: removeaccounttag
  path: /accounts/{id}/tags
- description: Get all relations for an Account
  method: GET
  name: listaccountrelations
  path: /accounts/{id}/relations
- description: Consolidate Accounts
  method: POST
  name: consolidateaccounts
  path: /accounts/consolidate
- description: Search Accounts
  method: POST
  name: searchaccounts
  path: /accounts/search
- description: List all Inquiries
  method: GET
  name: listinquiries
  path: /inquiries
- description: Create an Inquiry
  method: POST
  name: createinquiry
  path: /inquiries
- description: Retrieve an Inquiry
  method: GET
  name: retrieveinquiry
  path: /inquiries/{id}
- description: Update an Inquiry
  method: PATCH
  name: updateinquiry
  path: /inquiries/{id}
- description: Redact an Inquiry
  method: POST
  name: redactinquiry
  path: /inquiries/{id}/redact
- description: Approve an Inquiry
  method: POST
  name: approveinquiry
  path: /inquiries/{id}/approve
- description: Decline an Inquiry
  method: POST
  name: declineinquiry
  path: /inquiries/{id}/decline
- description: Expire an Inquiry
  method: POST
  name: expireinquiry
  path: /inquiries/{id}/expire
- description: Retrieve a Verification
  method: POST
  name: retrieveverification
  path: /verifications/{id}
- description: List all Reports
  method: GET
  name: listreports
  path: /reports
- description: Create a Report
  method: POST
  name: createreport
  path: /reports
- description: Retrieve a Report
  method: GET
  name: retrievereport
  path: /reports/{id}
- description: List all Lists
  method: GET
  name: listlists
  path: /lists
- description: Create a List
  method: POST
  name: createlist
  path: /lists
- description: List all Transactions
  method: GET
  name: listtransactions
  path: /transactions
- description: Create a Transaction
  method: POST
  name: createtransaction
  path: /transactions
- description: List all Webhooks
  method: GET
  name: listwebhooks
  path: /webhooks
- description: Create a Webhook
  method: POST
  name: createwebhook
  path: /webhooks
personas: []
provider_name: Persona
provider_slug: persona
search_terms:
- list all transactions
- searchaccounts
- update an inquiry
- create an account
- remove tag from an account
- redact an inquiry
- kyc
- create a report
- identity verification
- retrieve an inquiry
- redactinquiry
- updateaccount
- retrieveaccount
- declineinquiry
- api
- retrieveverification
- retrieve a report
- retrieve an account
- decline an inquiry
- expire an inquiry
- redact an account
- add tag to an account
- listaccountrelations
- create a transaction
- search accounts
- persona
- create a list
- createwebhook
- expireinquiry
- approveinquiry
- retrievereport
- createinquiry
- retrieve a verification
- listtransactions
- listinquiries
- retrieveinquiry
- fraud prevention
- list all accounts
- createreport
- list all lists
- list all webhooks
- listreports
- listlists
- createtransaction
- create a webhook
- redactaccount
- update an account
- listaccounts
- consolidateaccounts
- removeaccounttag
- get all relations for an account
- updateinquiry
- approve an inquiry
- createaccount
- listwebhooks
- consolidate accounts
- list all reports
- addaccounttag
- list all inquiries
- create an inquiry
- createlist
slug: persona-capability
source_filename: persona-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Persona API\n  description: The Persona API enables identity verification, fraud prevention, and Know Your Customer (KYC) workflows. Use\n    the API to create and manage inquiries, accounts, verifications, reports, transactions, lists, and webhooks for verifying\n    users via document checks, selfie checks, and database lookups.\n  tags:\n  - Persona\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: persona\n    baseUri: https://withpersona.com/api/v1\n    description: Persona API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{PERSONA_TOKEN}}'\n    resources:\n    - name: accounts\n      path: /accounts\n      operations:\n      - name: listaccounts\n        method: GET\n        description: List all Accounts\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name:\
  \ createaccount\n        method: POST\n        description: Create an Account\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounts-id\n      path: /accounts/{id}\n      operations:\n      - name: retrieveaccount\n        method: GET\n        description: Retrieve an Account\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateaccount\n        method: PATCH\n        description: Update an Account\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounts-id-redact\n      path: /accounts/{id}/redact\n      operations:\n      - name: redactaccount\n        method: POST\n        description: Redact an Account\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required:\
  \ true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounts-id-tags\n      path: /accounts/{id}/tags\n      operations:\n      - name: addaccounttag\n        method: POST\n        description: Add tag to an Account\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: removeaccounttag\n        method: DELETE\n        description: Remove tag from an Account\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounts-id-relations\n      path: /accounts/{id}/relations\n      operations:\n      - name: listaccountrelations\n        method: GET\n        description: Get all relations for an Account\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounts-consolidate\n      path: /accounts/consolidate\n      operations:\n      - name: consolidateaccounts\n        method: POST\n        description: Consolidate Accounts\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounts-search\n      path: /accounts/search\n      operations:\n      - name: searchaccounts\n        method: POST\n        description: Search Accounts\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: inquiries\n      path: /inquiries\n      operations:\n      - name: listinquiries\n        method: GET\n        description: List all Inquiries\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n \
  \     - name: createinquiry\n        method: POST\n        description: Create an Inquiry\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: inquiries-id\n      path: /inquiries/{id}\n      operations:\n      - name: retrieveinquiry\n        method: GET\n        description: Retrieve an Inquiry\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateinquiry\n        method: PATCH\n        description: Update an Inquiry\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: inquiries-id-redact\n      path: /inquiries/{id}/redact\n      operations:\n      - name: redactinquiry\n        method: POST\n        description: Redact an Inquiry\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n\
  \          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: inquiries-id-approve\n      path: /inquiries/{id}/approve\n      operations:\n      - name: approveinquiry\n        method: POST\n        description: Approve an Inquiry\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: inquiries-id-decline\n      path: /inquiries/{id}/decline\n      operations:\n      - name: declineinquiry\n        method: POST\n        description: Decline an Inquiry\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n    - name: inquiries-id-expire\n      path: /inquiries/{id}/expire\n      operations:\n      - name: expireinquiry\n        method: POST\n        description: Expire an Inquiry\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: verifications-id\n      path: /verifications/{id}\n      operations:\n      - name: retrieveverification\n        method: POST\n        description: Retrieve a Verification\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: reports\n      path: /reports\n      operations:\n      - name: listreports\n        method: GET\n        description: List all Reports\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createreport\n        method: POST\n        description: Create a Report\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: reports-id\n      path: /reports/{id}\n      operations:\n      - name: retrievereport\n        method: GET\n        description: Retrieve a Report\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: lists\n      path: /lists\n      operations:\n      - name: listlists\n        method: GET\n        description: List all Lists\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n     \
  \     value: $.\n      - name: createlist\n        method: POST\n        description: Create a List\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: transactions\n      path: /transactions\n      operations:\n      - name: listtransactions\n        method: GET\n        description: List all Transactions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createtransaction\n        method: POST\n        description: Create a Transaction\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: webhooks\n      path: /webhooks\n      operations:\n      - name: listwebhooks\n        method: GET\n        description: List all Webhooks\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n      - name: createwebhook\n        method: POST\n        description: Create a Webhook\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: persona-rest\n    description: REST adapter for Persona API.\n    resources:\n    - path: /accounts\n      name: listaccounts\n      operations:\n      - method: GET\n        name: listaccounts\n        description: List all Accounts\n        call: persona.listaccounts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounts\n      name: createaccount\n      operations:\n      - method: POST\n        name: createaccount\n        description: Create an Account\n        call: persona.createaccount\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounts/{id}\n      name: retrieveaccount\n      operations:\n\
  \      - method: GET\n        name: retrieveaccount\n        description: Retrieve an Account\n        call: persona.retrieveaccount\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounts/{id}\n      name: updateaccount\n      operations:\n      - method: PATCH\n        name: updateaccount\n        description: Update an Account\n        call: persona.updateaccount\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounts/{id}/redact\n      name: redactaccount\n      operations:\n      - method: POST\n        name: redactaccount\n        description: Redact an Account\n        call: persona.redactaccount\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounts/{id}/tags\n      name: addaccounttag\n      operations:\n      - method: POST\n        name: addaccounttag\n        description: Add tag to an Account\n        call: persona.addaccounttag\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounts/{id}/tags\n      name: removeaccounttag\n      operations:\n      - method: DELETE\n        name: removeaccounttag\n        description: Remove tag from an Account\n        call: persona.removeaccounttag\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounts/{id}/relations\n      name: listaccountrelations\n      operations:\n      - method: GET\n        name: listaccountrelations\n        description: Get all relations for an Account\n        call: persona.listaccountrelations\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounts/consolidate\n      name: consolidateaccounts\n      operations:\n      - method: POST\n        name: consolidateaccounts\n        description: Consolidate Accounts\n        call: persona.consolidateaccounts\n        outputParameters:\n       \
  \ - type: object\n          mapping: $.\n    - path: /accounts/search\n      name: searchaccounts\n      operations:\n      - method: POST\n        name: searchaccounts\n        description: Search Accounts\n        call: persona.searchaccounts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /inquiries\n      name: listinquiries\n      operations:\n      - method: GET\n        name: listinquiries\n        description: List all Inquiries\n        call: persona.listinquiries\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /inquiries\n      name: createinquiry\n      operations:\n      - method: POST\n        name: createinquiry\n        description: Create an Inquiry\n        call: persona.createinquiry\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /inquiries/{id}\n      name: retrieveinquiry\n      operations:\n      - method: GET\n        name: retrieveinquiry\n      \
  \  description: Retrieve an Inquiry\n        call: persona.retrieveinquiry\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /inquiries/{id}\n      name: updateinquiry\n      operations:\n      - method: PATCH\n        name: updateinquiry\n        description: Update an Inquiry\n        call: persona.updateinquiry\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /inquiries/{id}/redact\n      name: redactinquiry\n      operations:\n      - method: POST\n        name: redactinquiry\n        description: Redact an Inquiry\n        call: persona.redactinquiry\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /inquiries/{id}/approve\n      name: approveinquiry\n      operations:\n      - method: POST\n        name: approveinquiry\n        description: Approve an Inquiry\n        call: persona.approveinquiry\n        with:\n          id: rest.id\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /inquiries/{id}/decline\n      name: declineinquiry\n      operations:\n      - method: POST\n        name: declineinquiry\n        description: Decline an Inquiry\n        call: persona.declineinquiry\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /inquiries/{id}/expire\n      name: expireinquiry\n      operations:\n      - method: POST\n        name: expireinquiry\n        description: Expire an Inquiry\n        call: persona.expireinquiry\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /verifications/{id}\n      name: retrieveverification\n      operations:\n      - method: POST\n        name: retrieveverification\n        description: Retrieve a Verification\n        call: persona.retrieveverification\n        with:\n          id: rest.id\n   \
  \     outputParameters:\n        - type: object\n          mapping: $.\n    - path: /reports\n      name: listreports\n      operations:\n      - method: GET\n        name: listreports\n        description: List all Reports\n        call: persona.listreports\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /reports\n      name: createreport\n      operations:\n      - method: POST\n        name: createreport\n        description: Create a Report\n        call: persona.createreport\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /reports/{id}\n      name: retrievereport\n      operations:\n      - method: GET\n        name: retrievereport\n        description: Retrieve a Report\n        call: persona.retrievereport\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /lists\n      name: listlists\n      operations:\n      - method: GET\n  \
  \      name: listlists\n        description: List all Lists\n        call: persona.listlists\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /lists\n      name: createlist\n      operations:\n      - method: POST\n        name: createlist\n        description: Create a List\n        call: persona.createlist\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /transactions\n      name: listtransactions\n      operations:\n      - method: GET\n        name: listtransactions\n        description: List all Transactions\n        call: persona.listtransactions\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /transactions\n      name: createtransaction\n      operations:\n      - method: POST\n        name: createtransaction\n        description: Create a Transaction\n        call: persona.createtransaction\n        outputParameters:\n        - type: object\n          mapping: $.\n\
  \    - path: /webhooks\n      name: listwebhooks\n      operations:\n      - method: GET\n        name: listwebhooks\n        description: List all Webhooks\n        call: persona.listwebhooks\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /webhooks\n      name: createwebhook\n      operations:\n      - method: POST\n        name: createwebhook\n        description: Create a Webhook\n        call: persona.createwebhook\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: persona-mcp\n    transport: http\n    description: MCP adapter for Persona API for AI agent use.\n    tools:\n    - name: listaccounts\n      description: List all Accounts\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: persona.listaccounts\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createaccount\n      description: Create\
  \ an Account\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: persona.createaccount\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: retrieveaccount\n      description: Retrieve an Account\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: persona.retrieveaccount\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateaccount\n      description: Update an Account\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: persona.updateaccount\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: redactaccount\n      description: Redact an Account\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: persona.redactaccount\n      with:\n        id: tools.id\n      inputParameters:\n      -\
  \ name: id\n        type: string\n        description: id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: addaccounttag\n      description: Add tag to an Account\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: persona.addaccounttag\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: removeaccounttag\n      description: Remove tag from an Account\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: persona.removeaccounttag\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listaccountrelations\n      description: Get all relations for an Account\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: persona.listaccountrelations\n      with:\n        id: tools.id\n      inputParameters:\n      - name: id\n        type:\
  \ string\n        description: id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: consolidateaccounts\n      description: Consolidate Accounts\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: persona.consolidateaccounts\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: searchaccounts\n      description: Search Accounts\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: persona.searchaccounts\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listinquiries\n      description: List all Inquiries\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: persona.listinquiries\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createinquiry\n      description: Create an Inquiry\n      hints:\n\
  \        readOnly: false\n        destructive: false\n        idempotent: false\n      call: persona.createinquiry\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: retrieveinquiry\n      description: Retrieve an Inquiry\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: persona.retrieveinquiry\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateinquiry\n      description: Update an Inquiry\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: persona.updateinquiry\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: redactinquiry\n      description: Redact an Inquiry\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: persona.redactinquiry\n      with:\n        id: tools.id\n      inputParameters:\n      - name: id\n        type: string\n\
  \        description: id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: approveinquiry\n      description: Approve an Inquiry\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: persona.approveinquiry\n      with:\n        id: tools.id\n      inputParameters:\n      - name: id\n        type: string\n        description: id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: declineinquiry\n      description: Decline an Inquiry\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: persona.declineinquiry\n      with:\n        id: tools.id\n      inputParameters:\n      - name: id\n        type: string\n        description: id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: expireinquiry\n      description: Expire an\
  \ Inquiry\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: persona.expireinquiry\n      with:\n        id: tools.id\n      inputParameters:\n      - name: id\n        type: string\n        description: id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: retrieveverification\n      description: Retrieve a Verification\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: persona.retrieveverification\n      with:\n        id: tools.id\n      inputParameters:\n      - name: id\n        type: string\n        description: id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listreports\n      description: List all Reports\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: persona.listreports\n      outputParameters:\n \
  \     - type: object\n        mapping: $.\n    - name: createreport\n      description: Create a Report\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: persona.createreport\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: retrievereport\n      description: Retrieve a Report\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: persona.retrievereport\n      with:\n        id: tools.id\n      inputParameters:\n      - name: id\n        type: string\n        description: id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listlists\n      description: List all Lists\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: persona.listlists\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createlist\n      description:\
  \ Create a List\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: persona.createlist\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listtransactions\n      description: List all Transactions\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: persona.listtransactions\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createtransaction\n      description: Create a Transaction\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: persona.createtransaction\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listwebhooks\n      description: List all Webhooks\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: persona.listwebhooks\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: createwebhook\n      description: Create a Webhook\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: persona.createwebhook\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    PERSONA_TOKEN: PERSONA_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/persona/refs/heads/main/capabilities/persona-capability.yaml
tags:
- Persona
- API
tools:
- description: List all Accounts
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listaccounts
- description: Create an Account
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createaccount
- description: Retrieve an Account
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: retrieveaccount
- description: Update an Account
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateaccount
- description: Redact an Account
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: redactaccount
- description: Add tag to an Account
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: addaccounttag
- description: Remove tag from an Account
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: removeaccounttag
- description: Get all relations for an Account
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listaccountrelations
- description: Consolidate Accounts
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: consolidateaccounts
- description: Search Accounts
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: searchaccounts
- description: List all Inquiries
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listinquiries
- description: Create an Inquiry
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createinquiry
- description: Retrieve an Inquiry
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: retrieveinquiry
- description: Update an Inquiry
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateinquiry
- description: Redact an Inquiry
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: redactinquiry
- description: Approve an Inquiry
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: approveinquiry
- description: Decline an Inquiry
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: declineinquiry
- description: Expire an Inquiry
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: expireinquiry
- description: Retrieve a Verification
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: retrieveverification
- description: List all Reports
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listreports
- description: Create a Report
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createreport
- description: Retrieve a Report
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: retrievereport
- description: List all Lists
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listlists
- description: Create a List
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createlist
- description: List all Transactions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listtransactions
- description: Create a Transaction
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createtransaction
- description: List all Webhooks
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listwebhooks
- description: Create a Webhook
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createwebhook
---
