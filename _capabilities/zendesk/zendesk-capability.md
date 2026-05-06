---
categories: []
consumed_apis: []
description: Needs a description.
layout: capability
name: Zendesk Account
operations:
- description: Zendesk Get Api V2 Account Settings
  method: GET
  name: showaccountsettings
  path: /api/v2/account/settings
- description: Zendesk Put Api V2 Account Settings
  method: PUT
  name: updateaccountsettings
  path: /api/v2/account/settings
- description: Zendesk Post Api V2 Accounts
  method: POST
  name: createtrialaccount
  path: /api/v2/accounts
- description: Zendesk Get Api V2 Accounts Available
  method: GET
  name: verifysubdomainavailability
  path: /api/v2/accounts/available
personas: []
provider_name: Zendesk
provider_slug: zendesk
search_terms:
- createtrialaccount
- help center
- showaccountsettings
- ticketing
- zendesk
- zendesk post api v2 accounts
- verifysubdomainavailability
- zendesk get api v2 accounts available
- zendesk put api v2 account settings
- crm
- updateaccountsettings
- t1
- support
- api
- sell
- chat
- talk
- tickets
- zendesk get api v2 account settings
slug: zendesk-capability
source_filename: zendesk-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Zendesk Account\n  description: Needs a description.\n  tags:\n  - Zendesk\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: zendesk\n    baseUri: https://api.example.com\n    description: Zendesk Account HTTP API.\n    resources:\n    - name: api-v2-account-settings\n      path: /api/v2/account/settings\n      operations:\n      - name: showaccountsettings\n        method: GET\n        description: Zendesk Get Api V2 Account Settings\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateaccountsettings\n        method: PUT\n        description: Zendesk Put Api V2 Account Settings\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v2-accounts\n      path: /api/v2/accounts\n      operations:\n\
  \      - name: createtrialaccount\n        method: POST\n        description: Zendesk Post Api V2 Accounts\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v2-accounts-available\n      path: /api/v2/accounts/available\n      operations:\n      - name: verifysubdomainavailability\n        method: GET\n        description: Zendesk Get Api V2 Accounts Available\n        inputParameters:\n        - name: subdomain\n          in: query\n          type: string\n          required: true\n          description: Specify the name of the subdomain you want to verify. The name can't contain underscores, hyphens,\n            or spaces.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: zendesk-rest\n    description: REST adapter for Zendesk Account.\n    resources:\n   \
  \ - path: /api/v2/account/settings\n      name: showaccountsettings\n      operations:\n      - method: GET\n        name: showaccountsettings\n        description: Zendesk Get Api V2 Account Settings\n        call: zendesk.showaccountsettings\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v2/account/settings\n      name: updateaccountsettings\n      operations:\n      - method: PUT\n        name: updateaccountsettings\n        description: Zendesk Put Api V2 Account Settings\n        call: zendesk.updateaccountsettings\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v2/accounts\n      name: createtrialaccount\n      operations:\n      - method: POST\n        name: createtrialaccount\n        description: Zendesk Post Api V2 Accounts\n        call: zendesk.createtrialaccount\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v2/accounts/available\n      name:\
  \ verifysubdomainavailability\n      operations:\n      - method: GET\n        name: verifysubdomainavailability\n        description: Zendesk Get Api V2 Accounts Available\n        call: zendesk.verifysubdomainavailability\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: zendesk-mcp\n    transport: http\n    description: MCP adapter for Zendesk Account for AI agent use.\n    tools:\n    - name: showaccountsettings\n      description: Zendesk Get Api V2 Account Settings\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: zendesk.showaccountsettings\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateaccountsettings\n      description: Zendesk Put Api V2 Account Settings\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: zendesk.updateaccountsettings\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: createtrialaccount\n      description: Zendesk Post Api V2 Accounts\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: zendesk.createtrialaccount\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: verifysubdomainavailability\n      description: Zendesk Get Api V2 Accounts Available\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: zendesk.verifysubdomainavailability\n      with:\n        subdomain: tools.subdomain\n      inputParameters:\n      - name: subdomain\n        type: string\n        description: Specify the name of the subdomain you want to verify. The name can't contain underscores, hyphens, or\n          spaces.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/zendesk/refs/heads/main/capabilities/zendesk-capability.yaml
tags:
- Zendesk
- API
tools:
- description: Zendesk Get Api V2 Account Settings
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: showaccountsettings
- description: Zendesk Put Api V2 Account Settings
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateaccountsettings
- description: Zendesk Post Api V2 Accounts
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createtrialaccount
- description: Zendesk Get Api V2 Accounts Available
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: verifysubdomainavailability
---
