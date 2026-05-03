---
api_specs:
- filename: salesloft-openapi.yml
  format: yaml
  label: salesloft
  slug: salesloft
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/salesloft/refs/heads/main/openapi/salesloft-openapi.yml
categories: []
consumed_apis:
- salesloft
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
- delete person
- list cadence memberships
- people
- cadences
- list all people
- single person operations
- list all accounts
- update account
- enroll people in cadences
- list contacts and prospects in salesloft
- automation
- get account by id
- sales
- get cadence by id
- create a new account
- enroll a person in a cadence
- get details for a specific person
- enroll a person in a sales cadence for structured outreach
- delete a person
- update person
- list available sales cadences/outreach sequences
- engagement
- create a new company account in salesloft
- create person
- list all cadences
- list current cadence enrollments
- single account operations
- crm
- manage contacts and prospects
- delete an account
- accounts
- enroll person
- ai
- manage company accounts
- get details for a specific cadence
- enroll person in cadence
- revenue
- list accounts
- fetch account
- sales cadences and outreach sequences
- get details for a specific account
- update an account
- list cadence enrollments
- salesloft
- list cadences
- create account
- fetch person
- get person by id
- add a new contact/prospect to salesloft
- delete account
- update account details in salesloft
- single cadence operations
- list people
- create a new person
- fetch cadence
- update a person
- list salesloft accounts to find target companies
- update person/contact details
slug: sales-engagement
source_filename: sales-engagement.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Salesloft Sales Engagement\"\n  description: >-\n    Sales engagement workflow combining account and people management with cadence\n    enrollment. Used by sales reps to discover accounts, add prospects, and enroll\n    them in structured outreach sequences to drive pipeline.\n  tags:\n    - Sales\n    - Engagement\n    - Cadences\n    - Accounts\n    - People\n    - Salesloft\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SALESLOFT_API_KEY: SALESLOFT_API_KEY\n\ncapability:\n  consumes:\n    - import: salesloft\n      location: ./shared/salesloft.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: sales-engagement-api\n      description: \"Unified REST API for Salesloft sales engagement workflows.\"\n      resources:\n        - path: /v1/accounts\n          name: accounts\n          description: \"Manage company accounts\"\n          operations:\n   \
  \         - method: GET\n              name: list-accounts\n              description: \"List all accounts\"\n              call: \"salesloft.list-accounts\"\n              with:\n                page: \"rest.page\"\n                per_page: \"rest.per_page\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-account\n              description: \"Create a new account\"\n              call: \"salesloft.create-account\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/accounts/{id}\n          name: account-by-id\n          description: \"Single account operations\"\n          operations:\n            - method: GET\n              name: fetch-account\n              description: \"Get account by ID\"\n              call: \"salesloft.fetch-account\"\n              with:\n                id: \"rest.id\"\n          \
  \    outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: update-account\n              description: \"Update an account\"\n              call: \"salesloft.update-account\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-account\n              description: \"Delete an account\"\n              call: \"salesloft.delete-account\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/people\n          name: people\n          description: \"Manage contacts and prospects\"\n          operations:\n            - method: GET\n              name: list-people\n              description: \"List all people\"\n              call: \"salesloft.list-people\"\
  \n              with:\n                page: \"rest.page\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-person\n              description: \"Create a new person\"\n              call: \"salesloft.create-person\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/people/{id}\n          name: person-by-id\n          description: \"Single person operations\"\n          operations:\n            - method: GET\n              name: fetch-person\n              description: \"Get person by ID\"\n              call: \"salesloft.fetch-person\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: update-person\n              description: \"Update a person\"\n            \
  \  call: \"salesloft.update-person\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-person\n              description: \"Delete a person\"\n              call: \"salesloft.delete-person\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/cadences\n          name: cadences\n          description: \"Sales cadences and outreach sequences\"\n          operations:\n            - method: GET\n              name: list-cadences\n              description: \"List all cadences\"\n              call: \"salesloft.list-cadences\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/cadences/{id}\n          name: cadence-by-id\n          description:\
  \ \"Single cadence operations\"\n          operations:\n            - method: GET\n              name: fetch-cadence\n              description: \"Get cadence by ID\"\n              call: \"salesloft.fetch-cadence\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/cadence-memberships\n          name: cadence-memberships\n          description: \"Enroll people in cadences\"\n          operations:\n            - method: GET\n              name: list-cadence-memberships\n              description: \"List cadence enrollments\"\n              call: \"salesloft.list-cadence-memberships\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: enroll-person\n              description: \"Enroll a person in a cadence\"\n              call: \"salesloft.create-cadence-membership\"\
  \n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9080\n      namespace: sales-engagement-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Salesloft sales engagement workflows.\"\n      tools:\n        - name: list-accounts\n          description: \"List Salesloft accounts to find target companies\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"salesloft.list-accounts\"\n          with:\n            page: \"tools.page\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-account\n          description: \"Create a new company account in Salesloft\"\n          hints:\n            readOnly: false\n          call: \"salesloft.create-account\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: fetch-account\n         \
  \ description: \"Get details for a specific account\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"salesloft.fetch-account\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: update-account\n          description: \"Update account details in Salesloft\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"salesloft.update-account\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-people\n          description: \"List contacts and prospects in Salesloft\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"salesloft.list-people\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-person\n\
  \          description: \"Add a new contact/prospect to Salesloft\"\n          hints:\n            readOnly: false\n          call: \"salesloft.create-person\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: fetch-person\n          description: \"Get details for a specific person\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"salesloft.fetch-person\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: update-person\n          description: \"Update person/contact details\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"salesloft.update-person\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-cadences\n          description:\
  \ \"List available sales cadences/outreach sequences\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"salesloft.list-cadences\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: fetch-cadence\n          description: \"Get details for a specific cadence\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"salesloft.fetch-cadence\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: enroll-person-in-cadence\n          description: \"Enroll a person in a sales cadence for structured outreach\"\n          hints:\n            readOnly: false\n          call: \"salesloft.create-cadence-membership\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-cadence-memberships\n          description:\
  \ \"List current cadence enrollments\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"salesloft.list-cadence-memberships\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
