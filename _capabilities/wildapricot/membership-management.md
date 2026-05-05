---
api_specs:
- filename: wildapricot-admin-api-openapi.yml
  format: yaml
  label: wildapricot-admin
  slug: wildapricot-admin
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/wildapricot/refs/heads/main/openapi/wildapricot-admin-api-openapi.yml
categories: []
consumed_apis:
- wildapricot-admin
description: Unified capability for managing membership organizations using WildApricot. Covers contact/member lifecycle, event registration, membership levels, invoicing, and payment processing. Intended for association administrators, membership coordinators, and nonprofit operations staff automating member engagement and financial workflows.
layout: capability
name: WildApricot Membership Management
operations:
- description: List all contacts/members
  method: GET
  name: list-contacts
  path: /v1/contacts
- description: Create a new contact/member
  method: POST
  name: create-contact
  path: /v1/contacts
- description: Get a contact by ID
  method: GET
  name: get-contact
  path: /v1/contacts/{contactId}
- description: List all events
  method: GET
  name: list-events
  path: /v1/events
- description: Create a new event
  method: POST
  name: create-event
  path: /v1/events
- description: List event registrations
  method: GET
  name: list-registrations
  path: /v1/event-registrations
- description: List all membership levels
  method: GET
  name: list-membership-levels
  path: /v1/membership-levels
- description: List invoices
  method: GET
  name: list-invoices
  path: /v1/invoices
- description: List payments
  method: GET
  name: list-payments
  path: /v1/payments
- description: List donations
  method: GET
  name: list-donations
  path: /v1/donations
personas: []
provider_name: WildApricot
provider_slug: wildapricot
search_terms:
- create a new contact/member
- membership management
- invoice management
- create a new event
- list donation records for a wildapricot organization.
- list payments
- create event
- retrieve full details for a specific wildapricot member including membership status, level, and contact fields.
- create contact
- list all contacts/members
- list outstanding and paid invoices for a wildapricot organization.
- full membership lifecycle management including members, events, billing, and donations
- retrieve all membership levels with their pricing, renewal terms, and access privileges.
- event planning, registration management, and attendee tracking
- invoicing, payment processing, and donation management
- email campaign drafting, scheduling, and delivery
- list members
- list all events
- list events
- get a contact by id
- membership tiers and pricing
- operations team automating financial and administrative workflows
- list membership levels
- list invoices
- list event registrations for a wildapricot organization to see who registered for which events.
- donation records
- add member
- nonprofit
- member lifecycle from registration through renewal and lapse
- get member
- list event registrations
- event management
- payments
- member and contact management
- wildapricot
- Association Administrator
- associations
- list donations
- list contacts
- list registrations
- Membership Coordinator
- get contact
- retrieve all contacts/members for a wildapricot organization account.
- payment records
- individual contact/member
- events
- Nonprofit Operations
- staff member managing day-to-day association operations
- team member managing member recruitment, renewals, and engagement
- list payment records for a wildapricot organization.
- event registration management
- list all membership levels
- list all events for a wildapricot organization, including upcoming and past events.
- create a new contact/member record in a wildapricot organization.
slug: membership-management
source_filename: membership-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"WildApricot Membership Management\"\n  description: >-\n    Unified capability for managing membership organizations using WildApricot.\n    Covers contact/member lifecycle, event registration, membership levels,\n    invoicing, and payment processing. Intended for association administrators,\n    membership coordinators, and nonprofit operations staff automating\n    member engagement and financial workflows.\n  tags:\n    - WildApricot\n    - Membership Management\n    - Associations\n    - Nonprofit\n    - Events\n    - Payments\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      WILDAPRICOT_API_KEY: WILDAPRICOT_API_KEY\n\ncapability:\n  consumes:\n    - import: wildapricot-admin\n      location: ./shared/wildapricot-admin-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: wildapricot-membership-api\n      description: \"Unified REST API for WildApricot\
  \ membership management workflows.\"\n      resources:\n        - path: /v1/contacts\n          name: contacts\n          description: \"Member and contact management\"\n          operations:\n            - method: GET\n              name: list-contacts\n              description: \"List all contacts/members\"\n              call: \"wildapricot-admin.list-contacts\"\n              with:\n                accountId: \"rest.accountId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n            - method: POST\n              name: create-contact\n              description: \"Create a new contact/member\"\n              call: \"wildapricot-admin.create-contact\"\n              with:\n                accountId: \"rest.accountId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/contacts/{contactId}\n          name: contact\n          description: \"Individual contact/member\"\
  \n          operations:\n            - method: GET\n              name: get-contact\n              description: \"Get a contact by ID\"\n              call: \"wildapricot-admin.get-contact\"\n              with:\n                accountId: \"rest.accountId\"\n                contactId: \"rest.contactId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/events\n          name: events\n          description: \"Event management\"\n          operations:\n            - method: GET\n              name: list-events\n              description: \"List all events\"\n              call: \"wildapricot-admin.list-events\"\n              with:\n                accountId: \"rest.accountId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n            - method: POST\n              name: create-event\n              description: \"Create a new event\"\n              call: \"wildapricot-admin.create-event\"\
  \n              with:\n                accountId: \"rest.accountId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/event-registrations\n          name: event-registrations\n          description: \"Event registration management\"\n          operations:\n            - method: GET\n              name: list-registrations\n              description: \"List event registrations\"\n              call: \"wildapricot-admin.list-registrations\"\n              with:\n                accountId: \"rest.accountId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/membership-levels\n          name: membership-levels\n          description: \"Membership tiers and pricing\"\n          operations:\n            - method: GET\n              name: list-membership-levels\n              description: \"List all membership levels\"\n              call: \"wildapricot-admin.list-membership-levels\"\
  \n              with:\n                accountId: \"rest.accountId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/invoices\n          name: invoices\n          description: \"Invoice management\"\n          operations:\n            - method: GET\n              name: list-invoices\n              description: \"List invoices\"\n              call: \"wildapricot-admin.list-invoices\"\n              with:\n                accountId: \"rest.accountId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/payments\n          name: payments\n          description: \"Payment records\"\n          operations:\n            - method: GET\n              name: list-payments\n              description: \"List payments\"\n              call: \"wildapricot-admin.list-payments\"\n              with:\n                accountId: \"rest.accountId\"\n          \
  \    outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/donations\n          name: donations\n          description: \"Donation records\"\n          operations:\n            - method: GET\n              name: list-donations\n              description: \"List donations\"\n              call: \"wildapricot-admin.list-donations\"\n              with:\n                accountId: \"rest.accountId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: wildapricot-membership-mcp\n      transport: http\n      description: \"MCP server for AI-assisted WildApricot membership management.\"\n      tools:\n        - name: list-members\n          description: \"Retrieve all contacts/members for a WildApricot organization account.\"\n          hints:\n            readOnly: true\n            idempotent: true\n            openWorld: true\n      \
  \    call: \"wildapricot-admin.list-contacts\"\n          with:\n            accountId: \"tools.accountId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-member\n          description: \"Retrieve full details for a specific WildApricot member including membership status, level, and contact fields.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"wildapricot-admin.get-contact\"\n          with:\n            accountId: \"tools.accountId\"\n            contactId: \"tools.contactId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: add-member\n          description: \"Create a new contact/member record in a WildApricot organization.\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"wildapricot-admin.create-contact\"\n          with:\n            accountId: \"tools.accountId\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-events\n          description: \"List all events for a WildApricot organization, including upcoming and past events.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"wildapricot-admin.list-events\"\n          with:\n            accountId: \"tools.accountId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-event-registrations\n          description: \"List event registrations for a WildApricot organization to see who registered for which events.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"wildapricot-admin.list-registrations\"\n          with:\n            accountId: \"tools.accountId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-membership-levels\n\
  \          description: \"Retrieve all membership levels with their pricing, renewal terms, and access privileges.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"wildapricot-admin.list-membership-levels\"\n          with:\n            accountId: \"tools.accountId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-invoices\n          description: \"List outstanding and paid invoices for a WildApricot organization.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"wildapricot-admin.list-invoices\"\n          with:\n            accountId: \"tools.accountId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-payments\n          description: \"List payment records for a WildApricot organization.\"\n          hints:\n            readOnly: true\n            idempotent: true\n\
  \          call: \"wildapricot-admin.list-payments\"\n          with:\n            accountId: \"tools.accountId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-donations\n          description: \"List donation records for a WildApricot organization.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"wildapricot-admin.list-donations\"\n          with:\n            accountId: \"tools.accountId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/wildapricot/refs/heads/main/capabilities/membership-management.yaml
tags:
- WildApricot
- Membership Management
- Associations
- Nonprofit
- Events
- Payments
tools:
- description: Retrieve all contacts/members for a WildApricot organization account.
  hints:
    idempotent: true
    openWorld: true
    readOnly: true
  name: list-members
- description: Retrieve full details for a specific WildApricot member including membership status, level, and contact fields.
  hints:
    idempotent: true
    readOnly: true
  name: get-member
- description: Create a new contact/member record in a WildApricot organization.
  hints:
    destructive: false
    readOnly: false
  name: add-member
- description: List all events for a WildApricot organization, including upcoming and past events.
  hints:
    idempotent: true
    readOnly: true
  name: list-events
- description: List event registrations for a WildApricot organization to see who registered for which events.
  hints:
    idempotent: true
    readOnly: true
  name: list-event-registrations
- description: Retrieve all membership levels with their pricing, renewal terms, and access privileges.
  hints:
    idempotent: true
    readOnly: true
  name: list-membership-levels
- description: List outstanding and paid invoices for a WildApricot organization.
  hints:
    idempotent: true
    readOnly: true
  name: list-invoices
- description: List payment records for a WildApricot organization.
  hints:
    idempotent: true
    readOnly: true
  name: list-payments
- description: List donation records for a WildApricot organization.
  hints:
    idempotent: true
    readOnly: true
  name: list-donations
---
