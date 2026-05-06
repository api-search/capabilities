---
categories: []
consumed_apis: []
description: Revenue intelligence workflow combining calls, conversations, signals, and opportunities to provide pipeline visibility and AI-driven coaching insights. Used by sales managers and revenue leaders to monitor deal health and rep performance.
layout: capability
name: Salesloft Revenue Intelligence
operations:
- description: List all calls
  method: GET
  name: list-calls
  path: /v1/calls
- description: List all opportunities
  method: GET
  name: list-opportunities
  path: /v1/opportunities
- description: Get opportunity by ID
  method: GET
  name: fetch-opportunity
  path: /v1/opportunities/{id}
- description: Submit a buyer signal to Rhythm
  method: POST
  name: create-signal
  path: /v1/signals
- description: List all emails
  method: GET
  name: list-emails
  path: /v1/emails
- description: List all tasks
  method: GET
  name: list-tasks
  path: /v1/tasks
- description: Create a follow-up task
  method: POST
  name: create-task
  path: /v1/tasks
- description: List all users
  method: GET
  name: list-users
  path: /v1/users
personas: []
provider_name: Salesloft
provider_slug: salesloft
search_terms:
- list sales team members in salesloft
- sales
- fetch opportunity
- create webhook subscription
- salesloft
- sales opportunities and pipeline
- list pending sales tasks and follow-ups
- list webhook subscriptions for salesloft event notifications
- signals
- call recordings and outcomes
- analytics
- list tasks
- submit a buyer intent signal to salesloft rhythm to prioritize follow-up
- list emails sent through salesloft for activity tracking
- single opportunity
- create signal
- list all users
- list all emails
- ai
- list all opportunities
- submit a buyer signal to rhythm
- create a follow-up task
- automation
- list webhook subscriptions
- revenue intelligence
- conversations
- buyer intent signals for rhythm
- crm
- list all calls
- create a follow-up task for a sales rep
- get details for a specific opportunity
- submit buyer signal
- sales team users
- list emails
- list call recordings and outcomes from salesloft
- list sales opportunities and pipeline in salesloft
- list calls
- tasks and follow-ups
- get opportunity by id
- list users
- list opportunities
- list all tasks
- create a webhook subscription to receive salesloft events
- email activity tracking
- create task
- revenue
- opportunities
slug: revenue-intelligence
source_filename: revenue-intelligence.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Salesloft Revenue Intelligence\n  description: Revenue intelligence workflow combining calls, conversations, signals, and opportunities to provide pipeline\n    visibility and AI-driven coaching insights. Used by sales managers and revenue leaders to monitor deal health and rep\n    performance.\n  tags:\n  - Revenue Intelligence\n  - Conversations\n  - Opportunities\n  - Signals\n  - Analytics\n  - Salesloft\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SALESLOFT_API_KEY: SALESLOFT_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: salesloft\n    baseUri: https://api.salesloft.com/v2\n    description: Salesloft Revenue Orchestration Platform REST API\n    authentication:\n      type: bearer\n      token: '{{SALESLOFT_API_KEY}}'\n    resources:\n    - name: me\n      path: /me\n      description: Current authenticated user\n      operations:\n      - name: get-current-user\n \
  \       method: GET\n        description: Retrieve the current authenticated user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: team\n      path: /team\n      description: Current team settings\n      operations:\n      - name: get-current-team\n        method: GET\n        description: Retrieve the current team\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounts\n      path: /accounts\n      description: Company accounts in Salesloft\n      operations:\n      - name: list-accounts\n        method: GET\n        description: List all accounts\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number\n        - name: per_page\n          in: query\n          type: integer\n          required: false\n   \
  \       description: Results per page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-account\n        method: POST\n        description: Create a new account\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            domain: '{{tools.domain}}'\n            phone: '{{tools.phone}}'\n            website: '{{tools.website}}'\n            industry: '{{tools.industry}}'\n            owner_id: '{{tools.owner_id}}'\n    - name: accounts-by-id\n      path: /accounts/{id}\n      description: Single account by ID\n      operations:\n      - name: fetch-account\n        method: GET\n        description: Fetch a single account by ID\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n      \
  \    required: true\n          description: Account ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-account\n        method: PUT\n        description: Update an existing account\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Account ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            domain: '{{tools.domain}}'\n      - name: delete-account\n        method: DELETE\n        description: Delete an account\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Account ID\n        outputRawFormat: json\n        outputParameters:\n     \
  \   - name: result\n          type: object\n          value: $.\n    - name: people\n      path: /people\n      description: Prospects and contacts in Salesloft\n      operations:\n      - name: list-people\n        method: GET\n        description: List all people\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number\n        - name: per_page\n          in: query\n          type: integer\n          required: false\n          description: Results per page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-person\n        method: POST\n        description: Create a new person\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            email_address: '{{tools.email_address}}'\n\
  \            first_name: '{{tools.first_name}}'\n            last_name: '{{tools.last_name}}'\n            title: '{{tools.title}}'\n            account_id: '{{tools.account_id}}'\n            owner_id: '{{tools.owner_id}}'\n    - name: people-by-id\n      path: /people/{id}\n      description: Single person by ID\n      operations:\n      - name: fetch-person\n        method: GET\n        description: Fetch a single person by ID\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Person ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-person\n        method: PUT\n        description: Update a person\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Person ID\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            first_name: '{{tools.first_name}}'\n            last_name: '{{tools.last_name}}'\n            title: '{{tools.title}}'\n      - name: delete-person\n        method: DELETE\n        description: Delete a person\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Person ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cadences\n      path: /cadences\n      description: Sales cadences (structured outreach sequences)\n      operations:\n      - name: list-cadences\n        method: GET\n        description: List all cadences\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cadences-by-id\n      path: /cadences/{id}\n      description: Single cadence by ID\n      operations:\n      - name: fetch-cadence\n        method: GET\n        description: Fetch a cadence by ID\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Cadence ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cadence-memberships\n      path: /cadence_memberships\n      description: Person-cadence enrollment associations\n      operations:\n      - name: list-cadence-memberships\n        method: GET\n        description: List cadence memberships\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n   \
  \   - name: create-cadence-membership\n        method: POST\n        description: Enroll a person in a cadence\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            person_id: '{{tools.person_id}}'\n            cadence_id: '{{tools.cadence_id}}'\n            user_id: '{{tools.user_id}}'\n    - name: calls\n      path: /calls\n      description: Phone calls made through Salesloft\n      operations:\n      - name: list-calls\n        method: GET\n        description: List all calls\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: emails\n      path: /emails\n      description: Emails sent via Salesloft\n  \
  \    operations:\n      - name: list-emails\n        method: GET\n        description: List all emails\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tasks\n      path: /tasks\n      description: Sales tasks and to-dos\n      operations:\n      - name: list-tasks\n        method: GET\n        description: List all tasks\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-task\n        method: POST\n        description: Create a task\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            subject: '{{tools.subject}}'\n\
  \            person_id: '{{tools.person_id}}'\n            due_on: '{{tools.due_on}}'\n    - name: opportunities\n      path: /opportunities\n      description: Sales opportunities\n      operations:\n      - name: list-opportunities\n        method: GET\n        description: List all opportunities\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: opportunities-by-id\n      path: /opportunities/{id}\n      description: Single opportunity by ID\n      operations:\n      - name: fetch-opportunity\n        method: GET\n        description: Fetch an opportunity by ID\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Opportunity ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: signals\n      path: /signals\n      description:\
  \ Buyer intent signals for Rhythm\n      operations:\n      - name: create-signal\n        method: POST\n        description: Submit a buyer intent signal to Rhythm\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            person_id: '{{tools.person_id}}'\n    - name: users\n      path: /users\n      description: Salesloft platform users\n      operations:\n      - name: list-users\n        method: GET\n        description: List all users\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: webhook-subscriptions\n      path: /webhook_subscriptions\n      description: Webhook subscriptions for event notifications\n      operations:\n      - name: list-webhook-subscriptions\n        method: GET\n        description: List webhook subscriptions\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-webhook-subscription\n        method: POST\n        description: Create a webhook subscription\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            url: '{{tools.url}}'\n            event_type: '{{tools.event_type}}'\n  exposes:\n  - type: rest\n    port: 8081\n    namespace: revenue-intelligence-api\n    description: Unified REST API for Salesloft revenue intelligence and pipeline management.\n    resources:\n    - path: /v1/calls\n      name: calls\n      description: Call recordings and outcomes\n      operations:\n      - method: GET\n        name: list-calls\n        description: List all calls\n        call: salesloft.list-calls\n        with:\n          page: rest.page\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /v1/opportunities\n      name: opportunities\n      description: Sales opportunities and pipeline\n      operations:\n      - method: GET\n        name: list-opportunities\n        description: List all opportunities\n        call: salesloft.list-opportunities\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/opportunities/{id}\n      name: opportunity-by-id\n      description: Single opportunity\n      operations:\n      - method: GET\n        name: fetch-opportunity\n        description: Get opportunity by ID\n        call: salesloft.fetch-opportunity\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/signals\n      name: signals\n      description: Buyer intent signals for Rhythm\n      operations:\n      - method: POST\n        name: create-signal\n        description: Submit a buyer signal to Rhythm\n   \
  \     call: salesloft.create-signal\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/emails\n      name: emails\n      description: Email activity tracking\n      operations:\n      - method: GET\n        name: list-emails\n        description: List all emails\n        call: salesloft.list-emails\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/tasks\n      name: tasks\n      description: Tasks and follow-ups\n      operations:\n      - method: GET\n        name: list-tasks\n        description: List all tasks\n        call: salesloft.list-tasks\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-task\n        description: Create a follow-up task\n        call: salesloft.create-task\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/users\n      name: users\n      description: Sales team users\n   \
  \   operations:\n      - method: GET\n        name: list-users\n        description: List all users\n        call: salesloft.list-users\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9081\n    namespace: revenue-intelligence-mcp\n    transport: http\n    description: MCP server for AI-assisted revenue intelligence and pipeline management.\n    tools:\n    - name: list-calls\n      description: List call recordings and outcomes from Salesloft\n      hints:\n        readOnly: true\n        idempotent: true\n      call: salesloft.list-calls\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-opportunities\n      description: List sales opportunities and pipeline in Salesloft\n      hints:\n        readOnly: true\n        idempotent: true\n      call: salesloft.list-opportunities\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: fetch-opportunity\n      description: Get details\
  \ for a specific opportunity\n      hints:\n        readOnly: true\n        idempotent: true\n      call: salesloft.fetch-opportunity\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: submit-buyer-signal\n      description: Submit a buyer intent signal to Salesloft Rhythm to prioritize follow-up\n      hints:\n        readOnly: false\n      call: salesloft.create-signal\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-emails\n      description: List emails sent through Salesloft for activity tracking\n      hints:\n        readOnly: true\n        idempotent: true\n      call: salesloft.list-emails\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-tasks\n      description: List pending sales tasks and follow-ups\n      hints:\n        readOnly: true\n        idempotent: true\n      call: salesloft.list-tasks\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n    - name: create-task\n      description: Create a follow-up task for a sales rep\n      hints:\n        readOnly: false\n      call: salesloft.create-task\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-users\n      description: List sales team members in Salesloft\n      hints:\n        readOnly: true\n        idempotent: true\n      call: salesloft.list-users\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-webhook-subscriptions\n      description: List webhook subscriptions for Salesloft event notifications\n      hints:\n        readOnly: true\n        idempotent: true\n      call: salesloft.list-webhook-subscriptions\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-webhook-subscription\n      description: Create a webhook subscription to receive Salesloft events\n      hints:\n        readOnly: false\n      call: salesloft.create-webhook-subscription\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/salesloft/refs/heads/main/capabilities/revenue-intelligence.yaml
tags:
- Revenue Intelligence
- Conversations
- Opportunities
- Signals
- Analytics
- Salesloft
tools:
- description: List call recordings and outcomes from Salesloft
  hints:
    idempotent: true
    readOnly: true
  name: list-calls
- description: List sales opportunities and pipeline in Salesloft
  hints:
    idempotent: true
    readOnly: true
  name: list-opportunities
- description: Get details for a specific opportunity
  hints:
    idempotent: true
    readOnly: true
  name: fetch-opportunity
- description: Submit a buyer intent signal to Salesloft Rhythm to prioritize follow-up
  hints:
    readOnly: false
  name: submit-buyer-signal
- description: List emails sent through Salesloft for activity tracking
  hints:
    idempotent: true
    readOnly: true
  name: list-emails
- description: List pending sales tasks and follow-ups
  hints:
    idempotent: true
    readOnly: true
  name: list-tasks
- description: Create a follow-up task for a sales rep
  hints:
    readOnly: false
  name: create-task
- description: List sales team members in Salesloft
  hints:
    idempotent: true
    readOnly: true
  name: list-users
- description: List webhook subscriptions for Salesloft event notifications
  hints:
    idempotent: true
    readOnly: true
  name: list-webhook-subscriptions
- description: Create a webhook subscription to receive Salesloft events
  hints:
    readOnly: false
  name: create-webhook-subscription
---
