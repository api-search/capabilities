---
categories: []
consumed_apis: []
description: The Nudge Security REST API enables programmatic access to retrieve data about apps, accounts, OAuth grants, security events, fields, users, user groups, labels, notifications, findings, playbooks, app-to-app integrations, app instances, AI sessions and prompts, and the browser extension. It supports integration with SIEM, SOAR, and ticketing systems and allows management of custom fields and classifications. The API is rate limited to 1200 requests per 5-minute period. API tokens auto-expire after 4 weeks of no use.
layout: capability
name: Nudge Security API
operations:
- description: Search apps
  method: GET
  name: get-apps
  path: /apps
- description: Get app
  method: GET
  name: get-apps-app-id
  path: /apps/{app_id}
- description: Set app category
  method: POST
  name: post-apps-app-category-app-id
  path: /apps/app-category/{app_id}
- description: Search accounts
  method: GET
  name: get-accounts
  path: /accounts
- description: Get account
  method: GET
  name: get-accounts-account-id
  path: /accounts/{account_id}
- description: Search OAuth grants
  method: GET
  name: get-oauth-grants
  path: /oauth-grants
- description: Get OAuth grant
  method: GET
  name: get-oauth-grants-grant-id
  path: /oauth-grants/{grant_id}
- description: Search events
  method: GET
  name: get-events
  path: /events
- description: Get event
  method: GET
  name: get-events-event-id
  path: /events/{event_id}
- description: Search users
  method: GET
  name: get-users
  path: /users
- description: Search user groups
  method: GET
  name: get-user-groups
  path: /user-groups
- description: List user group members
  method: GET
  name: get-user-groups-group-id-members
  path: /user-groups/{group_id}/members
- description: Search notifications
  method: GET
  name: get-notifications
  path: /notifications
- description: Search fields
  method: GET
  name: get-fields
  path: /fields
- description: Create field
  method: POST
  name: post-fields
  path: /fields
- description: Search labels
  method: GET
  name: get-labels
  path: /labels
- description: Create label
  method: POST
  name: post-labels
  path: /labels
- description: Search findings
  method: GET
  name: get-findings
  path: /findings
- description: Search app-to-app integrations
  method: GET
  name: get-app-to-app-integrations
  path: /app-to-app-integrations
personas: []
provider_name: Nudge Security
provider_slug: nudge-security
search_terms:
- get users
- set app category
- get oauth grants
- get user groups
- get fields
- create field
- search user groups
- get event
- create label
- get events
- get apps
- post labels
- search events
- sspm
- saas management
- get user groups group id members
- search apps
- security
- get apps app id
- get events event id
- compliance
- oauth
- search accounts
- search labels
- search fields
- api
- get app to app integrations
- shadow it
- get notifications
- saas security
- search users
- search app-to-app integrations
- get accounts account id
- access management
- get labels
- search findings
- get accounts
- search oauth grants
- list user group members
- ai security
- search notifications
- get oauth grant
- post apps app category app id
- get account
- get app
- get oauth grants grant id
- governance
- nudge
- get findings
- post fields
slug: nudge-security-capability
source_filename: nudge-security-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Nudge Security API\n  description: The Nudge Security REST API enables programmatic access to retrieve data about apps, accounts, OAuth grants,\n    security events, fields, users, user groups, labels, notifications, findings, playbooks, app-to-app integrations, app\n    instances, AI sessions and prompts, and the browser extension. It supports integration with SIEM, SOAR, and ticketing\n    systems and allows management of custom fields and classifications. The API is rate limited to 1200 requests per 5-minute\n    period. API tokens auto-expire after 4 weeks of no use.\n  tags:\n  - Nudge\n  - Security\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: nudge-security\n    baseUri: https://api.nudgesecurity.io/api/1.0\n    description: Nudge Security API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{NUDGE_SECURITY_TOKEN}}'\n    resources:\n    - name:\
  \ apps\n      path: /apps\n      operations:\n      - name: get-apps\n        method: GET\n        description: Search apps\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: apps-app-id\n      path: /apps/{app_id}\n      operations:\n      - name: get-apps-app-id\n        method: GET\n        description: Get app\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: apps-app-category-app-id\n      path: /apps/app-category/{app_id}\n      operations:\n      - name: post-apps-app-category-app-id\n        method: POST\n        description: Set app category\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounts\n      path: /accounts\n      operations:\n      - name: get-accounts\n        method: GET\n        description: Search\
  \ accounts\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounts-account-id\n      path: /accounts/{account_id}\n      operations:\n      - name: get-accounts-account-id\n        method: GET\n        description: Get account\n        inputParameters:\n        - name: account_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: oauth-grants\n      path: /oauth-grants\n      operations:\n      - name: get-oauth-grants\n        method: GET\n        description: Search OAuth grants\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: oauth-grants-grant-id\n      path: /oauth-grants/{grant_id}\n      operations:\n      - name: get-oauth-grants-grant-id\n\
  \        method: GET\n        description: Get OAuth grant\n        inputParameters:\n        - name: grant_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: events\n      path: /events\n      operations:\n      - name: get-events\n        method: GET\n        description: Search events\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: events-event-id\n      path: /events/{event_id}\n      operations:\n      - name: get-events-event-id\n        method: GET\n        description: Get event\n        inputParameters:\n        - name: event_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n   \
  \ - name: users\n      path: /users\n      operations:\n      - name: get-users\n        method: GET\n        description: Search users\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: user-groups\n      path: /user-groups\n      operations:\n      - name: get-user-groups\n        method: GET\n        description: Search user groups\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: user-groups-group-id-members\n      path: /user-groups/{group_id}/members\n      operations:\n      - name: get-user-groups-group-id-members\n        method: GET\n        description: List user group members\n        inputParameters:\n        - name: group_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n    - name: notifications\n      path: /notifications\n      operations:\n      - name: get-notifications\n        method: GET\n        description: Search notifications\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: fields\n      path: /fields\n      operations:\n      - name: get-fields\n        method: GET\n        description: Search fields\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: post-fields\n        method: POST\n        description: Create field\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: labels\n      path: /labels\n      operations:\n      - name: get-labels\n        method: GET\n        description: Search labels\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: post-labels\n        method: POST\n        description: Create label\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: findings\n      path: /findings\n      operations:\n      - name: get-findings\n        method: GET\n        description: Search findings\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: app-to-app-integrations\n      path: /app-to-app-integrations\n      operations:\n      - name: get-app-to-app-integrations\n        method: GET\n        description: Search app-to-app integrations\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: nudge-security-rest\n    description: REST adapter\
  \ for Nudge Security API.\n    resources:\n    - path: /apps\n      name: get-apps\n      operations:\n      - method: GET\n        name: get-apps\n        description: Search apps\n        call: nudge-security.get-apps\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apps/{app_id}\n      name: get-apps-app-id\n      operations:\n      - method: GET\n        name: get-apps-app-id\n        description: Get app\n        call: nudge-security.get-apps-app-id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apps/app-category/{app_id}\n      name: post-apps-app-category-app-id\n      operations:\n      - method: POST\n        name: post-apps-app-category-app-id\n        description: Set app category\n        call: nudge-security.post-apps-app-category-app-id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounts\n      name: get-accounts\n      operations:\n      - method:\
  \ GET\n        name: get-accounts\n        description: Search accounts\n        call: nudge-security.get-accounts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounts/{account_id}\n      name: get-accounts-account-id\n      operations:\n      - method: GET\n        name: get-accounts-account-id\n        description: Get account\n        call: nudge-security.get-accounts-account-id\n        with:\n          account_id: rest.account_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /oauth-grants\n      name: get-oauth-grants\n      operations:\n      - method: GET\n        name: get-oauth-grants\n        description: Search OAuth grants\n        call: nudge-security.get-oauth-grants\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /oauth-grants/{grant_id}\n      name: get-oauth-grants-grant-id\n      operations:\n      - method: GET\n        name: get-oauth-grants-grant-id\n\
  \        description: Get OAuth grant\n        call: nudge-security.get-oauth-grants-grant-id\n        with:\n          grant_id: rest.grant_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /events\n      name: get-events\n      operations:\n      - method: GET\n        name: get-events\n        description: Search events\n        call: nudge-security.get-events\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /events/{event_id}\n      name: get-events-event-id\n      operations:\n      - method: GET\n        name: get-events-event-id\n        description: Get event\n        call: nudge-security.get-events-event-id\n        with:\n          event_id: rest.event_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users\n      name: get-users\n      operations:\n      - method: GET\n        name: get-users\n        description: Search users\n        call: nudge-security.get-users\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /user-groups\n      name: get-user-groups\n      operations:\n      - method: GET\n        name: get-user-groups\n        description: Search user groups\n        call: nudge-security.get-user-groups\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /user-groups/{group_id}/members\n      name: get-user-groups-group-id-members\n      operations:\n      - method: GET\n        name: get-user-groups-group-id-members\n        description: List user group members\n        call: nudge-security.get-user-groups-group-id-members\n        with:\n          group_id: rest.group_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /notifications\n      name: get-notifications\n      operations:\n      - method: GET\n        name: get-notifications\n        description: Search notifications\n        call: nudge-security.get-notifications\n  \
  \      outputParameters:\n        - type: object\n          mapping: $.\n    - path: /fields\n      name: get-fields\n      operations:\n      - method: GET\n        name: get-fields\n        description: Search fields\n        call: nudge-security.get-fields\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /fields\n      name: post-fields\n      operations:\n      - method: POST\n        name: post-fields\n        description: Create field\n        call: nudge-security.post-fields\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /labels\n      name: get-labels\n      operations:\n      - method: GET\n        name: get-labels\n        description: Search labels\n        call: nudge-security.get-labels\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /labels\n      name: post-labels\n      operations:\n      - method: POST\n        name: post-labels\n        description: Create\
  \ label\n        call: nudge-security.post-labels\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /findings\n      name: get-findings\n      operations:\n      - method: GET\n        name: get-findings\n        description: Search findings\n        call: nudge-security.get-findings\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /app-to-app-integrations\n      name: get-app-to-app-integrations\n      operations:\n      - method: GET\n        name: get-app-to-app-integrations\n        description: Search app-to-app integrations\n        call: nudge-security.get-app-to-app-integrations\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: nudge-security-mcp\n    transport: http\n    description: MCP adapter for Nudge Security API for AI agent use.\n    tools:\n    - name: get-apps\n      description: Search apps\n      hints:\n        readOnly:\
  \ true\n        destructive: false\n        idempotent: true\n      call: nudge-security.get-apps\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-apps-app-id\n      description: Get app\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: nudge-security.get-apps-app-id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: post-apps-app-category-app-id\n      description: Set app category\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: nudge-security.post-apps-app-category-app-id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-accounts\n      description: Search accounts\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: nudge-security.get-accounts\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name:\
  \ get-accounts-account-id\n      description: Get account\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: nudge-security.get-accounts-account-id\n      with:\n        account_id: tools.account_id\n      inputParameters:\n      - name: account_id\n        type: string\n        description: account_id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-oauth-grants\n      description: Search OAuth grants\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: nudge-security.get-oauth-grants\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-oauth-grants-grant-id\n      description: Get OAuth grant\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: nudge-security.get-oauth-grants-grant-id\n      with:\n        grant_id: tools.grant_id\n     \
  \ inputParameters:\n      - name: grant_id\n        type: string\n        description: grant_id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-events\n      description: Search events\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: nudge-security.get-events\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-events-event-id\n      description: Get event\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: nudge-security.get-events-event-id\n      with:\n        event_id: tools.event_id\n      inputParameters:\n      - name: event_id\n        type: string\n        description: event_id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-users\n      description: Search users\n      hints:\n        readOnly: true\n        destructive:\
  \ false\n        idempotent: true\n      call: nudge-security.get-users\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-user-groups\n      description: Search user groups\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: nudge-security.get-user-groups\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-user-groups-group-id-members\n      description: List user group members\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: nudge-security.get-user-groups-group-id-members\n      with:\n        group_id: tools.group_id\n      inputParameters:\n      - name: group_id\n        type: string\n        description: group_id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-notifications\n      description: Search notifications\n      hints:\n        readOnly:\
  \ true\n        destructive: false\n        idempotent: true\n      call: nudge-security.get-notifications\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-fields\n      description: Search fields\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: nudge-security.get-fields\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: post-fields\n      description: Create field\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: nudge-security.post-fields\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-labels\n      description: Search labels\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: nudge-security.get-labels\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: post-labels\n      description: Create\
  \ label\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: nudge-security.post-labels\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-findings\n      description: Search findings\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: nudge-security.get-findings\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-app-to-app-integrations\n      description: Search app-to-app integrations\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: nudge-security.get-app-to-app-integrations\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    NUDGE_SECURITY_TOKEN: NUDGE_SECURITY_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/nudge-security/refs/heads/main/capabilities/nudge-security-capability.yaml
tags:
- Nudge
- Security
- API
tools:
- description: Search apps
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-apps
- description: Get app
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-apps-app-id
- description: Set app category
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-apps-app-category-app-id
- description: Search accounts
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-accounts
- description: Get account
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-accounts-account-id
- description: Search OAuth grants
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-oauth-grants
- description: Get OAuth grant
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-oauth-grants-grant-id
- description: Search events
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-events
- description: Get event
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-events-event-id
- description: Search users
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-users
- description: Search user groups
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-user-groups
- description: List user group members
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-user-groups-group-id-members
- description: Search notifications
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-notifications
- description: Search fields
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-fields
- description: Create field
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-fields
- description: Search labels
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-labels
- description: Create label
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-labels
- description: Search findings
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-findings
- description: Search app-to-app integrations
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-app-to-app-integrations
---
