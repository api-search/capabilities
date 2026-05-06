---
categories: []
consumed_apis: []
description: The Twilio SendGrid Account Provisioning API provides a platform for Twilio SendGrid resellers to manage their customer accounts. This API is for companies that have a formal reseller partnership with Twilio SendGrid. You can access Twilio SendGrid sub-account functionality without becoming a reseller. If you require sub-account functionality, see the Twilio [SendGrid Subusers](https://docs.sendgrid.com/ui/account-and-settings/subusers) feature, which is available with [Pro and Premier plans](https://sendgrid.com/pricing/).
layout: capability
name: Twilio SendGrid Account Provisioning API
operations:
- description: Get all accounts
  method: GET
  name: listaccount
  path: /v3/partners/accounts
- description: Create an account
  method: POST
  name: createaccount
  path: /v3/partners/accounts
- description: Delete an account
  method: DELETE
  name: deleteaccount
  path: /v3/partners/accounts/{accountID}
- description: Get account offerings
  method: GET
  name: listaccountoffering
  path: /v3/partners/accounts/{accountID}/offerings
- description: Update account offerings
  method: PUT
  name: updateaccountoffering
  path: /v3/partners/accounts/{accountID}/offerings
- description: Authenticate an account with single sign on
  method: POST
  name: authenticateaccount
  path: /v3/partners/accounts/{accountID}/sso
- description: Get an account's state
  method: GET
  name: getaccountstate
  path: /v3/partners/accounts/{accountID}/state
- description: Update an account's state
  method: PUT
  name: updateaccountstate
  path: /v3/partners/accounts/{accountID}/state
- description: Get all available offerings
  method: GET
  name: listoffering
  path: /v3/partners/offerings
personas: []
provider_name: SendGrid
provider_slug: sendgrid
search_terms:
- get account offerings
- createaccount
- marketing email
- deleteaccount
- get all available offerings
- smtp
- listoffering
- getaccountstate
- create an account
- get an account's state
- updateaccountoffering
- update account offerings
- t1
- email api
- api
- listaccountoffering
- update an account's state
- transactional email
- listaccount
- authenticateaccount
- delete an account
- email
- get all accounts
- authenticate an account with single sign on
- updateaccountstate
- sendgrid
slug: sendgrid-capability
source_filename: sendgrid-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Twilio SendGrid Account Provisioning API\n  description: The Twilio SendGrid Account Provisioning API provides a platform for Twilio SendGrid resellers to manage their\n    customer accounts. This API is for companies that have a formal reseller partnership with Twilio SendGrid. You can access\n    Twilio SendGrid sub-account functionality without becoming a reseller. If you require sub-account functionality, see the\n    Twilio [SendGrid Subusers](https://docs.sendgrid.com/ui/account-and-settings/subusers) feature, which is available with\n    [Pro and Premier plans](https://sendgrid.com/pricing/).\n  tags:\n  - Sendgrid\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: sendgrid\n    baseUri: https://api.sendgrid.com\n    description: Twilio SendGrid Account Provisioning API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{SENDGRID_TOKEN}}'\n    resources:\n\
  \    - name: v3-partners-accounts\n      path: /v3/partners/accounts\n      operations:\n      - name: listaccount\n        method: GET\n        description: Get all accounts\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createaccount\n        method: POST\n        description: Create an account\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v3-partners-accounts-accountid\n      path: /v3/partners/accounts/{accountID}\n      operations:\n      - name: deleteaccount\n        method: DELETE\n        description: Delete an account\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v3-partners-accounts-accountid-offerings\n      path: /v3/partners/accounts/{accountID}/offerings\n      operations:\n      - name: listaccountoffering\n\
  \        method: GET\n        description: Get account offerings\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateaccountoffering\n        method: PUT\n        description: Update account offerings\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v3-partners-accounts-accountid-sso\n      path: /v3/partners/accounts/{accountID}/sso\n      operations:\n      - name: authenticateaccount\n        method: POST\n        description: Authenticate an account with single sign on\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v3-partners-accounts-accountid-state\n      path: /v3/partners/accounts/{accountID}/state\n      operations:\n      - name: getaccountstate\n        method: GET\n        description: Get an account's\
  \ state\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateaccountstate\n        method: PUT\n        description: Update an account's state\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v3-partners-offerings\n      path: /v3/partners/offerings\n      operations:\n      - name: listoffering\n        method: GET\n        description: Get all available offerings\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: sendgrid-rest\n    description: REST adapter for Twilio SendGrid Account Provisioning API.\n    resources:\n    - path: /v3/partners/accounts\n      name: listaccount\n      operations:\n      - method: GET\n        name: listaccount\n        description: Get\
  \ all accounts\n        call: sendgrid.listaccount\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v3/partners/accounts\n      name: createaccount\n      operations:\n      - method: POST\n        name: createaccount\n        description: Create an account\n        call: sendgrid.createaccount\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v3/partners/accounts/{accountID}\n      name: deleteaccount\n      operations:\n      - method: DELETE\n        name: deleteaccount\n        description: Delete an account\n        call: sendgrid.deleteaccount\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v3/partners/accounts/{accountID}/offerings\n      name: listaccountoffering\n      operations:\n      - method: GET\n        name: listaccountoffering\n        description: Get account offerings\n        call: sendgrid.listaccountoffering\n        outputParameters:\n        - type:\
  \ object\n          mapping: $.\n    - path: /v3/partners/accounts/{accountID}/offerings\n      name: updateaccountoffering\n      operations:\n      - method: PUT\n        name: updateaccountoffering\n        description: Update account offerings\n        call: sendgrid.updateaccountoffering\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v3/partners/accounts/{accountID}/sso\n      name: authenticateaccount\n      operations:\n      - method: POST\n        name: authenticateaccount\n        description: Authenticate an account with single sign on\n        call: sendgrid.authenticateaccount\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v3/partners/accounts/{accountID}/state\n      name: getaccountstate\n      operations:\n      - method: GET\n        name: getaccountstate\n        description: Get an account's state\n        call: sendgrid.getaccountstate\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n    - path: /v3/partners/accounts/{accountID}/state\n      name: updateaccountstate\n      operations:\n      - method: PUT\n        name: updateaccountstate\n        description: Update an account's state\n        call: sendgrid.updateaccountstate\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v3/partners/offerings\n      name: listoffering\n      operations:\n      - method: GET\n        name: listoffering\n        description: Get all available offerings\n        call: sendgrid.listoffering\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: sendgrid-mcp\n    transport: http\n    description: MCP adapter for Twilio SendGrid Account Provisioning API for AI agent use.\n    tools:\n    - name: listaccount\n      description: Get all accounts\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: sendgrid.listaccount\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createaccount\n      description: Create an account\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: sendgrid.createaccount\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteaccount\n      description: Delete an account\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: sendgrid.deleteaccount\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listaccountoffering\n      description: Get account offerings\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: sendgrid.listaccountoffering\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateaccountoffering\n      description: Update account offerings\n      hints:\n        readOnly: false\n        destructive:\
  \ false\n        idempotent: true\n      call: sendgrid.updateaccountoffering\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: authenticateaccount\n      description: Authenticate an account with single sign on\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: sendgrid.authenticateaccount\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getaccountstate\n      description: Get an account's state\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: sendgrid.getaccountstate\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateaccountstate\n      description: Update an account's state\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: sendgrid.updateaccountstate\n      outputParameters:\n      - type: object\n        mapping: $.\n \
  \   - name: listoffering\n      description: Get all available offerings\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: sendgrid.listoffering\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    SENDGRID_TOKEN: SENDGRID_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/sendgrid/refs/heads/main/capabilities/sendgrid-capability.yaml
tags:
- Sendgrid
- API
tools:
- description: Get all accounts
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listaccount
- description: Create an account
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createaccount
- description: Delete an account
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteaccount
- description: Get account offerings
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listaccountoffering
- description: Update account offerings
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateaccountoffering
- description: Authenticate an account with single sign on
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: authenticateaccount
- description: Get an account's state
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getaccountstate
- description: Update an account's state
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateaccountstate
- description: Get all available offerings
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listoffering
---
