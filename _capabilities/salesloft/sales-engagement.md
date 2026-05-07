---
categories: []
consumed_apis: []
description: Sales engagement workflow combining account and people management with cadence enrollment. Used by sales reps to discover accounts, add prospects, and enroll them in structured outreach sequences to drive pipeline.
layout: capability
name: Salesloft Sales Engagement
operations:
- description: List all accounts
  method: GET
  name: list-accounts
  path: /v1/accounts
- description: Create a new account
  method: POST
  name: create-account
  path: /v1/accounts
- description: Get account by ID
  method: GET
  name: fetch-account
  path: /v1/accounts/{id}
- description: Update an account
  method: PUT
  name: update-account
  path: /v1/accounts/{id}
- description: Delete an account
  method: DELETE
  name: delete-account
  path: /v1/accounts/{id}
- description: List all people
  method: GET
  name: list-people
  path: /v1/people
- description: Create a new person
  method: POST
  name: create-person
  path: /v1/people
- description: Get person by ID
  method: GET
  name: fetch-person
  path: /v1/people/{id}
- description: Update a person
  method: PUT
  name: update-person
  path: /v1/people/{id}
- description: Delete a person
  method: DELETE
  name: delete-person
  path: /v1/people/{id}
- description: List all cadences
  method: GET
  name: list-cadences
  path: /v1/cadences
- description: Get cadence by ID
  method: GET
  name: fetch-cadence
  path: /v1/cadences/{id}
- description: List cadence enrollments
  method: GET
  name: list-cadence-memberships
  path: /v1/cadence-memberships
- description: Enroll a person in a cadence
  method: POST
  name: enroll-person
  path: /v1/cadence-memberships
personas: []
provider_name: Salesloft
provider_slug: salesloft
search_terms:
- list cadence enrollments
- update person
- list cadence memberships
- update person/contact details
- automation
- manage contacts and prospects
- get account by id
- enroll a person in a cadence
- ai
- delete an account
- list all cadences
- get details for a specific cadence
- list accounts
- single account operations
- delete person
- list all people
- single cadence operations
- engagement
- fetch account
- enroll people in cadences
- get details for a specific person
- revenue
- get details for a specific account
- crm
- create a new account
- sales cadences and outreach sequences
- single person operations
- list current cadence enrollments
- create account
- enroll person in cadence
- update a person
- create a new company account in salesloft
- cadences
- accounts
- create person
- list all accounts
- delete a person
- people
- salesloft
- get person by id
- list salesloft accounts to find target companies
- list people
- update account details in salesloft
- update account
- add a new contact/prospect to salesloft
- sales
- update an account
- delete account
- list cadences
- enroll person
- manage company accounts
- create a new person
- enroll a person in a sales cadence for structured outreach
- fetch cadence
- list contacts and prospects in salesloft
- list available sales cadences/outreach sequences
- fetch person
- get cadence by id
slug: sales-engagement
source_filename: sales-engagement.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Salesloft Sales Engagement\n  description: Sales engagement workflow combining account and people management with cadence enrollment. Used by sales reps\n    to discover accounts, add prospects, and enroll them in structured outreach sequences to drive pipeline.\n  tags:\n  - Sales\n  - Engagement\n  - Cadences\n  - Accounts\n  - People\n  - Salesloft\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SALESLOFT_API_KEY: SALESLOFT_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: salesloft\n    baseUri: https://api.salesloft.com/v2\n    description: Salesloft Revenue Orchestration Platform REST API\n    authentication:\n      type: bearer\n      token: '{{SALESLOFT_API_KEY}}'\n    resources:\n    - name: me\n      path: /me\n      description: Current authenticated user\n      operations:\n      - name: get-current-user\n        method: GET\n        description: Retrieve the current\
  \ authenticated user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: team\n      path: /team\n      description: Current team settings\n      operations:\n      - name: get-current-team\n        method: GET\n        description: Retrieve the current team\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounts\n      path: /accounts\n      description: Company accounts in Salesloft\n      operations:\n      - name: list-accounts\n        method: GET\n        description: List all accounts\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number\n        - name: per_page\n          in: query\n          type: integer\n          required: false\n          description: Results per page\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-account\n        method: POST\n        description: Create a new account\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            domain: '{{tools.domain}}'\n            phone: '{{tools.phone}}'\n            website: '{{tools.website}}'\n            industry: '{{tools.industry}}'\n            owner_id: '{{tools.owner_id}}'\n    - name: accounts-by-id\n      path: /accounts/{id}\n      description: Single account by ID\n      operations:\n      - name: fetch-account\n        method: GET\n        description: Fetch a single account by ID\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Account ID\n       \
  \ outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-account\n        method: PUT\n        description: Update an existing account\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Account ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            domain: '{{tools.domain}}'\n      - name: delete-account\n        method: DELETE\n        description: Delete an account\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Account ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n\
  \    - name: people\n      path: /people\n      description: Prospects and contacts in Salesloft\n      operations:\n      - name: list-people\n        method: GET\n        description: List all people\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number\n        - name: per_page\n          in: query\n          type: integer\n          required: false\n          description: Results per page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-person\n        method: POST\n        description: Create a new person\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            email_address: '{{tools.email_address}}'\n            first_name: '{{tools.first_name}}'\n\
  \            last_name: '{{tools.last_name}}'\n            title: '{{tools.title}}'\n            account_id: '{{tools.account_id}}'\n            owner_id: '{{tools.owner_id}}'\n    - name: people-by-id\n      path: /people/{id}\n      description: Single person by ID\n      operations:\n      - name: fetch-person\n        method: GET\n        description: Fetch a single person by ID\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Person ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-person\n        method: PUT\n        description: Update a person\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Person ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n        body:\n          type: json\n          data:\n            first_name: '{{tools.first_name}}'\n            last_name: '{{tools.last_name}}'\n            title: '{{tools.title}}'\n      - name: delete-person\n        method: DELETE\n        description: Delete a person\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Person ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cadences\n      path: /cadences\n      description: Sales cadences (structured outreach sequences)\n      operations:\n      - name: list-cadences\n        method: GET\n        description: List all cadences\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number\n        outputRawFormat: json\n     \
  \   outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cadences-by-id\n      path: /cadences/{id}\n      description: Single cadence by ID\n      operations:\n      - name: fetch-cadence\n        method: GET\n        description: Fetch a cadence by ID\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Cadence ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cadence-memberships\n      path: /cadence_memberships\n      description: Person-cadence enrollment associations\n      operations:\n      - name: list-cadence-memberships\n        method: GET\n        description: List cadence memberships\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-cadence-membership\n\
  \        method: POST\n        description: Enroll a person in a cadence\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            person_id: '{{tools.person_id}}'\n            cadence_id: '{{tools.cadence_id}}'\n            user_id: '{{tools.user_id}}'\n    - name: calls\n      path: /calls\n      description: Phone calls made through Salesloft\n      operations:\n      - name: list-calls\n        method: GET\n        description: List all calls\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: emails\n      path: /emails\n      description: Emails sent via Salesloft\n      operations:\n      - name: list-emails\n\
  \        method: GET\n        description: List all emails\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tasks\n      path: /tasks\n      description: Sales tasks and to-dos\n      operations:\n      - name: list-tasks\n        method: GET\n        description: List all tasks\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-task\n        method: POST\n        description: Create a task\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            subject: '{{tools.subject}}'\n            person_id: '{{tools.person_id}}'\n\
  \            due_on: '{{tools.due_on}}'\n    - name: opportunities\n      path: /opportunities\n      description: Sales opportunities\n      operations:\n      - name: list-opportunities\n        method: GET\n        description: List all opportunities\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: opportunities-by-id\n      path: /opportunities/{id}\n      description: Single opportunity by ID\n      operations:\n      - name: fetch-opportunity\n        method: GET\n        description: Fetch an opportunity by ID\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Opportunity ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: signals\n      path: /signals\n      description: Buyer intent signals for Rhythm\n      operations:\n\
  \      - name: create-signal\n        method: POST\n        description: Submit a buyer intent signal to Rhythm\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            person_id: '{{tools.person_id}}'\n    - name: users\n      path: /users\n      description: Salesloft platform users\n      operations:\n      - name: list-users\n        method: GET\n        description: List all users\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: webhook-subscriptions\n      path: /webhook_subscriptions\n      description: Webhook subscriptions for event notifications\n      operations:\n      - name: list-webhook-subscriptions\n        method: GET\n        description: List webhook subscriptions\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: create-webhook-subscription\n        method: POST\n        description: Create a webhook subscription\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            url: '{{tools.url}}'\n            event_type: '{{tools.event_type}}'\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: sales-engagement-api\n    description: Unified REST API for Salesloft sales engagement workflows.\n    resources:\n    - path: /v1/accounts\n      name: accounts\n      description: Manage company accounts\n      operations:\n      - method: GET\n        name: list-accounts\n        description: List all accounts\n        call: salesloft.list-accounts\n        with:\n          page: rest.page\n          per_page: rest.per_page\n        outputParameters:\n        - type: object\n       \
  \   mapping: $.\n      - method: POST\n        name: create-account\n        description: Create a new account\n        call: salesloft.create-account\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/accounts/{id}\n      name: account-by-id\n      description: Single account operations\n      operations:\n      - method: GET\n        name: fetch-account\n        description: Get account by ID\n        call: salesloft.fetch-account\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PUT\n        name: update-account\n        description: Update an account\n        call: salesloft.update-account\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-account\n        description: Delete an account\n        call: salesloft.delete-account\n        with:\n          id: rest.id\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/people\n      name: people\n      description: Manage contacts and prospects\n      operations:\n      - method: GET\n        name: list-people\n        description: List all people\n        call: salesloft.list-people\n        with:\n          page: rest.page\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-person\n        description: Create a new person\n        call: salesloft.create-person\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/people/{id}\n      name: person-by-id\n      description: Single person operations\n      operations:\n      - method: GET\n        name: fetch-person\n        description: Get person by ID\n        call: salesloft.fetch-person\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method:\
  \ PUT\n        name: update-person\n        description: Update a person\n        call: salesloft.update-person\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-person\n        description: Delete a person\n        call: salesloft.delete-person\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/cadences\n      name: cadences\n      description: Sales cadences and outreach sequences\n      operations:\n      - method: GET\n        name: list-cadences\n        description: List all cadences\n        call: salesloft.list-cadences\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/cadences/{id}\n      name: cadence-by-id\n      description: Single cadence operations\n      operations:\n      - method: GET\n        name: fetch-cadence\n        description: Get cadence\
  \ by ID\n        call: salesloft.fetch-cadence\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/cadence-memberships\n      name: cadence-memberships\n      description: Enroll people in cadences\n      operations:\n      - method: GET\n        name: list-cadence-memberships\n        description: List cadence enrollments\n        call: salesloft.list-cadence-memberships\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: enroll-person\n        description: Enroll a person in a cadence\n        call: salesloft.create-cadence-membership\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9080\n    namespace: sales-engagement-mcp\n    transport: http\n    description: MCP server for AI-assisted Salesloft sales engagement workflows.\n    tools:\n    - name: list-accounts\n      description: List Salesloft accounts\
  \ to find target companies\n      hints:\n        readOnly: true\n        idempotent: true\n      call: salesloft.list-accounts\n      with:\n        page: tools.page\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-account\n      description: Create a new company account in Salesloft\n      hints:\n        readOnly: false\n      call: salesloft.create-account\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: fetch-account\n      description: Get details for a specific account\n      hints:\n        readOnly: true\n        idempotent: true\n      call: salesloft.fetch-account\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-account\n      description: Update account details in Salesloft\n      hints:\n        readOnly: false\n        idempotent: true\n      call: salesloft.update-account\n      with:\n        id: tools.id\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: list-people\n      description: List contacts and prospects in Salesloft\n      hints:\n        readOnly: true\n        idempotent: true\n      call: salesloft.list-people\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-person\n      description: Add a new contact/prospect to Salesloft\n      hints:\n        readOnly: false\n      call: salesloft.create-person\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: fetch-person\n      description: Get details for a specific person\n      hints:\n        readOnly: true\n        idempotent: true\n      call: salesloft.fetch-person\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-person\n      description: Update person/contact details\n      hints:\n        readOnly: false\n        idempotent: true\n      call: salesloft.update-person\n      with:\n\
  \        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-cadences\n      description: List available sales cadences/outreach sequences\n      hints:\n        readOnly: true\n        idempotent: true\n      call: salesloft.list-cadences\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: fetch-cadence\n      description: Get details for a specific cadence\n      hints:\n        readOnly: true\n        idempotent: true\n      call: salesloft.fetch-cadence\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: enroll-person-in-cadence\n      description: Enroll a person in a sales cadence for structured outreach\n      hints:\n        readOnly: false\n      call: salesloft.create-cadence-membership\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-cadence-memberships\n      description: List current cadence enrollments\n\
  \      hints:\n        readOnly: true\n        idempotent: true\n      call: salesloft.list-cadence-memberships\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/salesloft/refs/heads/main/capabilities/sales-engagement.yaml
tags:
- Sales
- Engagement
- Cadences
- Accounts
- People
- Salesloft
tools:
- description: List Salesloft accounts to find target companies
  hints:
    idempotent: true
    readOnly: true
  name: list-accounts
- description: Create a new company account in Salesloft
  hints:
    readOnly: false
  name: create-account
- description: Get details for a specific account
  hints:
    idempotent: true
    readOnly: true
  name: fetch-account
- description: Update account details in Salesloft
  hints:
    idempotent: true
    readOnly: false
  name: update-account
- description: List contacts and prospects in Salesloft
  hints:
    idempotent: true
    readOnly: true
  name: list-people
- description: Add a new contact/prospect to Salesloft
  hints:
    readOnly: false
  name: create-person
- description: Get details for a specific person
  hints:
    idempotent: true
    readOnly: true
  name: fetch-person
- description: Update person/contact details
  hints:
    idempotent: true
    readOnly: false
  name: update-person
- description: List available sales cadences/outreach sequences
  hints:
    idempotent: true
    readOnly: true
  name: list-cadences
- description: Get details for a specific cadence
  hints:
    idempotent: true
    readOnly: true
  name: fetch-cadence
- description: Enroll a person in a sales cadence for structured outreach
  hints:
    readOnly: false
  name: enroll-person-in-cadence
- description: List current cadence enrollments
  hints:
    idempotent: true
    readOnly: true
  name: list-cadence-memberships
---
