---
categories:
- messaging
consumed_apis: []
description: Unified workflow for sending transactional emails, managing domains, configuring webhooks, and monitoring delivery statistics. Used by developers integrating email notifications into applications.
layout: capability
name: AhaSend Email Operations
operations:
- description: List email messages
  method: GET
  name: list-messages
  path: /v1/messages
- description: Send a transactional email
  method: POST
  name: send-message
  path: /v1/messages
- description: List domains
  method: GET
  name: list-domains
  path: /v1/domains
- description: List webhooks
  method: GET
  name: list-webhooks
  path: /v1/webhooks
- description: List suppressed addresses
  method: GET
  name: list-suppressions
  path: /v1/suppressions
- description: Get deliverability statistics
  method: GET
  name: get-deliverability-stats
  path: /v1/statistics/deliverability
personas: []
provider_name: AhaSend
provider_slug: ahasend
search_terms:
- list sent email messages with delivery status
- manage event webhooks
- DevOps Engineer
- get deliverability statistics
- application developer integrating transactional email into their application
- managing email suppression lists
- infrastructure engineer monitoring email delivery health and managing domains
- send emails, manage domains, configure webhooks, and monitor delivery statistics
- webhook and route configuration for email events
- list suppressions
- deliverability
- list domains
- send a transactional email message via ahasend
- get transactional email deliverability statistics and metrics
- configuring and validating sending domains
- send message
- send and retrieve transactional email messages
- manage sending domains
- developer tools
- list configured webhooks for email event notifications
- webhooks
- email
- list webhooks
- list suppressed email addresses (bounces, complaints, unsubscribes)
- list messages
- sending and tracking transactional emails
- list configured sending domains and their dns verification status
- list email messages
- send a transactional email
- email delivery statistics
- Developer
- get deliverability stats
- smtp
- transactional email
- manage email suppressions
- send email
- list suppressed addresses
slug: email-operations
source_filename: email-operations.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: AhaSend Email Operations\n  description: Unified workflow for sending transactional emails, managing domains, configuring webhooks, and monitoring delivery\n    statistics. Used by developers integrating email notifications into applications.\n  tags:\n  - Email\n  - Transactional Email\n  - Developer Tools\n  - Webhooks\n  - Deliverability\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    AHASEND_API_KEY: AHASEND_API_KEY\n    AHASEND_ACCOUNT_ID: AHASEND_ACCOUNT_ID\ncapability:\n  consumes:\n  - type: http\n    namespace: ahasend\n    baseUri: https://api.ahasend.com\n    description: AhaSend transactional email REST API v2\n    authentication:\n      type: bearer\n      token: '{{AHASEND_API_KEY}}'\n    resources:\n    - name: messages\n      path: /v2/accounts/{account_id}/messages\n      description: Send and manage transactional email messages\n      operations:\n      - name: list-messages\n\
  \        method: GET\n        description: List messages for an account\n        inputParameters:\n        - name: account_id\n          in: path\n          type: string\n          required: true\n          description: Account identifier\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of items to return\n        - name: cursor\n          in: query\n          type: string\n          required: false\n          description: Pagination cursor\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: send-message\n        method: POST\n        description: Send a transactional email message\n        inputParameters:\n        - name: account_id\n          in: path\n          type: string\n          required: true\n          description: Account identifier\n        outputRawFormat: json\n        outputParameters:\n        -\
  \ name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            from: '{{tools.from}}'\n            to: '{{tools.to}}'\n            subject: '{{tools.subject}}'\n            html: '{{tools.html}}'\n    - name: domains\n      path: /v2/accounts/{account_id}/domains\n      description: Manage sending domains\n      operations:\n      - name: list-domains\n        method: GET\n        description: List all domains for an account\n        inputParameters:\n        - name: account_id\n          in: path\n          type: string\n          required: true\n          description: Account identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-domain\n        method: POST\n        description: Add a new sending domain\n        inputParameters:\n        - name: account_id\n          in: path\n          type: string\n          required:\
  \ true\n          description: Account identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            domain: '{{tools.domain}}'\n    - name: webhooks\n      path: /v2/accounts/{account_id}/webhooks\n      description: Manage event webhooks\n      operations:\n      - name: list-webhooks\n        method: GET\n        description: List all webhooks for an account\n        inputParameters:\n        - name: account_id\n          in: path\n          type: string\n          required: true\n          description: Account identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-webhook\n        method: POST\n        description: Create a new webhook\n        inputParameters:\n        - name: account_id\n          in: path\n          type: string\n    \
  \      required: true\n          description: Account identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            url: '{{tools.url}}'\n            events: '{{tools.events}}'\n    - name: suppressions\n      path: /v2/accounts/{account_id}/suppressions\n      description: Manage email suppression lists\n      operations:\n      - name: list-suppressions\n        method: GET\n        description: List suppressed email addresses\n        inputParameters:\n        - name: account_id\n          in: path\n          type: string\n          required: true\n          description: Account identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: statistics\n      path: /v2/accounts/{account_id}/statistics/transactional/deliverability\n      description: Email delivery\
  \ statistics and analytics\n      operations:\n      - name: get-deliverability-stats\n        method: GET\n        description: Get transactional email deliverability statistics\n        inputParameters:\n        - name: account_id\n          in: path\n          type: string\n          required: true\n          description: Account identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: ahasend-email-ops-api\n    description: Unified REST API for AhaSend email operations.\n    resources:\n    - path: /v1/messages\n      name: messages\n      description: Send and retrieve transactional email messages\n      operations:\n      - method: GET\n        name: list-messages\n        description: List email messages\n        call: ahasend.list-messages\n        with:\n          account_id: rest.account_id\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n      - method: POST\n        name: send-message\n        description: Send a transactional email\n        call: ahasend.send-message\n        with:\n          account_id: rest.account_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/domains\n      name: domains\n      description: Manage sending domains\n      operations:\n      - method: GET\n        name: list-domains\n        description: List domains\n        call: ahasend.list-domains\n        with:\n          account_id: rest.account_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/webhooks\n      name: webhooks\n      description: Manage event webhooks\n      operations:\n      - method: GET\n        name: list-webhooks\n        description: List webhooks\n        call: ahasend.list-webhooks\n        with:\n          account_id: rest.account_id\n        outputParameters:\n        - type: object\n          mapping: $.\n\
  \    - path: /v1/suppressions\n      name: suppressions\n      description: Manage email suppressions\n      operations:\n      - method: GET\n        name: list-suppressions\n        description: List suppressed addresses\n        call: ahasend.list-suppressions\n        with:\n          account_id: rest.account_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/statistics/deliverability\n      name: statistics\n      description: Email delivery statistics\n      operations:\n      - method: GET\n        name: get-deliverability-stats\n        description: Get deliverability statistics\n        call: ahasend.get-deliverability-stats\n        with:\n          account_id: rest.account_id\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9080\n    namespace: ahasend-email-ops-mcp\n    transport: http\n    description: MCP server for AI-assisted transactional email operations.\n    tools:\n    - name:\
  \ send-email\n      description: Send a transactional email message via AhaSend\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: ahasend.send-message\n      with:\n        account_id: tools.account_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-messages\n      description: List sent email messages with delivery status\n      hints:\n        readOnly: true\n        openWorld: true\n      call: ahasend.list-messages\n      with:\n        account_id: tools.account_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-domains\n      description: List configured sending domains and their DNS verification status\n      hints:\n        readOnly: true\n        openWorld: true\n      call: ahasend.list-domains\n      with:\n        account_id: tools.account_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-webhooks\n      description:\
  \ List configured webhooks for email event notifications\n      hints:\n        readOnly: true\n        openWorld: true\n      call: ahasend.list-webhooks\n      with:\n        account_id: tools.account_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-suppressions\n      description: List suppressed email addresses (bounces, complaints, unsubscribes)\n      hints:\n        readOnly: true\n        openWorld: true\n      call: ahasend.list-suppressions\n      with:\n        account_id: tools.account_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-deliverability-stats\n      description: Get transactional email deliverability statistics and metrics\n      hints:\n        readOnly: true\n        openWorld: true\n      call: ahasend.get-deliverability-stats\n      with:\n        account_id: tools.account_id\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/ahasend/refs/heads/main/capabilities/email-operations.yaml
tags:
- Email
- Transactional Email
- Developer Tools
- Webhooks
- Deliverability
tools:
- description: Send a transactional email message via AhaSend
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: send-email
- description: List sent email messages with delivery status
  hints:
    openWorld: true
    readOnly: true
  name: list-messages
- description: List configured sending domains and their DNS verification status
  hints:
    openWorld: true
    readOnly: true
  name: list-domains
- description: List configured webhooks for email event notifications
  hints:
    openWorld: true
    readOnly: true
  name: list-webhooks
- description: List suppressed email addresses (bounces, complaints, unsubscribes)
  hints:
    openWorld: true
    readOnly: true
  name: list-suppressions
- description: Get transactional email deliverability statistics and metrics
  hints:
    openWorld: true
    readOnly: true
  name: get-deliverability-stats
---
