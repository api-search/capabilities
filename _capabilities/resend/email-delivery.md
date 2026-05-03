---
api_specs:
- filename: resend-openapi.yml
  format: yaml
  label: resend
  slug: resend
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/resend/refs/heads/main/openapi/resend-openapi.yml
categories: []
consumed_apis:
- resend
description: Workflow capability for sending and managing transactional emails, batch email campaigns, scheduled emails, domain configuration, and audience-based broadcast campaigns using the Resend email API.
layout: capability
name: Resend Email Delivery
operations:
- description: Send a transactional email
  method: POST
  name: send-email
  path: /v1/emails
- description: Retrieve a single sent email
  method: GET
  name: get-email
  path: /v1/emails/{id}
- description: Update a scheduled email
  method: PATCH
  name: update-email
  path: /v1/emails/{id}
- description: Cancel a scheduled email
  method: POST
  name: cancel-email
  path: /v1/emails/{id}/cancel
- description: Send up to 100 emails in a single batch
  method: POST
  name: send-batch-emails
  path: /v1/emails/batch
- description: List all configured sending domains
  method: GET
  name: list-domains
  path: /v1/domains
- description: Add a new sending domain
  method: POST
  name: create-domain
  path: /v1/domains
- description: Get details for a domain
  method: GET
  name: get-domain
  path: /v1/domains/{id}
- description: Update domain tracking settings
  method: PATCH
  name: update-domain
  path: /v1/domains/{id}
- description: Remove a sending domain
  method: DELETE
  name: delete-domain
  path: /v1/domains/{id}
- description: List all audiences
  method: GET
  name: list-audiences
  path: /v1/audiences
- description: Create a new audience
  method: POST
  name: create-audience
  path: /v1/audiences
- description: List contacts in an audience
  method: GET
  name: list-contacts
  path: /v1/audiences/{audience_id}/contacts
- description: Add a contact to an audience
  method: POST
  name: create-contact
  path: /v1/audiences/{audience_id}/contacts
- description: List all broadcast campaigns
  method: GET
  name: list-broadcasts
  path: /v1/broadcasts
- description: Create a new broadcast campaign
  method: POST
  name: create-broadcast
  path: /v1/broadcasts
- description: Send or schedule a broadcast campaign
  method: POST
  name: send-broadcast
  path: /v1/broadcasts/{id}/send
personas: []
provider_name: Resend
provider_slug: resend
search_terms:
- update email
- transactional email sending
- list contacts in a specific audience
- audiences
- send a transactional email to one or more recipients
- list domains
- list sending domains
- create a new contact audience
- create a new broadcast email campaign
- remove a sending domain
- create a new broadcast campaign
- create broadcast
- list all contact audiences
- add contact to audience
- list contacts
- list all configured sending domains
- create contact
- developer tools
- send up to 100 emails in a single batch operation
- send broadcast
- send batch emails
- get email
- add a contact to an audience for marketing emails
- list broadcasts
- marketing email
- get the status and details of a sent email by id
- list all audiences
- email
- list all broadcast campaigns
- list all configured email sending domains
- add a new sending domain
- contact audiences for marketing emails
- list api keys
- list contacts in an audience
- send a transactional email
- create a new audience
- broadcasts
- create domain
- single domain management
- list audiences
- get domain
- cancel a scheduled email before it is sent
- add a new email sending domain
- retrieve a single sent email
- email domain configuration
- verify dns records for a sending domain
- email broadcast campaigns
- send or schedule a broadcast campaign to an audience
- create sending domain
- update domain
- single email management
- transactional email
- send email
- delete domain
- cancel scheduled email
- get details for a domain
- create audience
- audience contacts
- send transactional email
- send up to 100 emails in a single batch
- verify domain
- list all api keys for the account
- batch email sending
- update domain tracking settings
- send broadcast campaign
- send or schedule a broadcast
- update a scheduled email
- add a contact to an audience
- send or schedule a broadcast campaign
- cancel a scheduled email
- get email status
- cancel email
- list all email broadcast campaigns
slug: email-delivery
source_filename: email-delivery.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Resend Email Delivery\"\n  description: >-\n    Workflow capability for sending and managing transactional emails, batch\n    email campaigns, scheduled emails, domain configuration, and audience-based\n    broadcast campaigns using the Resend email API.\n  tags:\n    - Email\n    - Transactional Email\n    - Marketing Email\n    - Developer Tools\n    - Broadcasts\n    - Audiences\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      RESEND_API_KEY: RESEND_API_KEY\n\ncapability:\n  consumes:\n    - import: resend\n      location: ./shared/resend.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: email-delivery-api\n      description: \"Unified REST API for email delivery, domain management, and audience campaigns.\"\n      resources:\n        - path: /v1/emails\n          name: emails\n          description: \"Transactional email sending\"\n          operations:\n\
  \            - method: POST\n              name: send-email\n              description: \"Send a transactional email\"\n              call: \"resend.send-email\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/emails/{id}\n          name: email\n          description: \"Single email management\"\n          operations:\n            - method: GET\n              name: get-email\n              description: \"Retrieve a single sent email\"\n              call: \"resend.get-email\"\n              with:\n                email_id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PATCH\n              name: update-email\n              description: \"Update a scheduled email\"\n              call: \"resend.update-email\"\n              with:\n                email_id: \"rest.id\"\n              outputParameters:\n                - type: object\n\
  \                  mapping: \"$.\"\n        - path: /v1/emails/{id}/cancel\n          name: email-cancel\n          description: \"Cancel scheduled email\"\n          operations:\n            - method: POST\n              name: cancel-email\n              description: \"Cancel a scheduled email\"\n              call: \"resend.cancel-email\"\n              with:\n                email_id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/emails/batch\n          name: email-batch\n          description: \"Batch email sending\"\n          operations:\n            - method: POST\n              name: send-batch-emails\n              description: \"Send up to 100 emails in a single batch\"\n              call: \"resend.send-batch-emails\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/domains\n          name: domains\n          description:\
  \ \"Email domain configuration\"\n          operations:\n            - method: GET\n              name: list-domains\n              description: \"List all configured sending domains\"\n              call: \"resend.list-domains\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-domain\n              description: \"Add a new sending domain\"\n              call: \"resend.create-domain\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/domains/{id}\n          name: domain\n          description: \"Single domain management\"\n          operations:\n            - method: GET\n              name: get-domain\n              description: \"Get details for a domain\"\n              call: \"resend.get-domain\"\n              with:\n                domain_id: \"rest.id\"\n              outputParameters:\n               \
  \ - type: object\n                  mapping: \"$.\"\n            - method: PATCH\n              name: update-domain\n              description: \"Update domain tracking settings\"\n              call: \"resend.update-domain\"\n              with:\n                domain_id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-domain\n              description: \"Remove a sending domain\"\n              call: \"resend.delete-domain\"\n              with:\n                domain_id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/audiences\n          name: audiences\n          description: \"Contact audiences for marketing emails\"\n          operations:\n            - method: GET\n              name: list-audiences\n              description: \"List all audiences\"\n              call: \"\
  resend.list-audiences\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-audience\n              description: \"Create a new audience\"\n              call: \"resend.create-audience\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/audiences/{audience_id}/contacts\n          name: contacts\n          description: \"Audience contacts\"\n          operations:\n            - method: GET\n              name: list-contacts\n              description: \"List contacts in an audience\"\n              call: \"resend.list-contacts\"\n              with:\n                audience_id: \"rest.audience_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-contact\n              description: \"Add a contact to an audience\"\
  \n              call: \"resend.create-contact\"\n              with:\n                audience_id: \"rest.audience_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/broadcasts\n          name: broadcasts\n          description: \"Email broadcast campaigns\"\n          operations:\n            - method: GET\n              name: list-broadcasts\n              description: \"List all broadcast campaigns\"\n              call: \"resend.list-broadcasts\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-broadcast\n              description: \"Create a new broadcast campaign\"\n              call: \"resend.create-broadcast\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/broadcasts/{id}/send\n          name: broadcast-send\n          description:\
  \ \"Send or schedule a broadcast\"\n          operations:\n            - method: POST\n              name: send-broadcast\n              description: \"Send or schedule a broadcast campaign\"\n              call: \"resend.send-broadcast\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: email-delivery-mcp\n      transport: http\n      description: \"MCP server for AI-assisted email delivery, campaign management, and domain configuration.\"\n      tools:\n        - name: send-transactional-email\n          description: \"Send a transactional email to one or more recipients\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"resend.send-email\"\n          with:\n            from: \"tools.from\"\n            to: \"tools.to\"\n            subject: \"tools.subject\"\
  \n            html: \"tools.html\"\n            text: \"tools.text\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-email-status\n          description: \"Get the status and details of a sent email by ID\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"resend.get-email\"\n          with:\n            email_id: \"tools.email_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: send-batch-emails\n          description: \"Send up to 100 emails in a single batch operation\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"resend.send-batch-emails\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: cancel-scheduled-email\n          description: \"Cancel a scheduled email before it is sent\"\n  \
  \        hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"resend.cancel-email\"\n          with:\n            email_id: \"tools.email_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-sending-domains\n          description: \"List all configured email sending domains\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"resend.list-domains\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-sending-domain\n          description: \"Add a new email sending domain\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"resend.create-domain\"\n          with:\n            name: \"tools.name\"\n            region: \"tools.region\"\n          outputParameters:\n            - type: object\n\
  \              mapping: \"$.\"\n        - name: verify-domain\n          description: \"Verify DNS records for a sending domain\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"resend.verify-domain\"\n          with:\n            domain_id: \"tools.domain_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-audiences\n          description: \"List all contact audiences\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"resend.list-audiences\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-audience\n          description: \"Create a new contact audience\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"resend.create-audience\"\n          with:\n            name:\
  \ \"tools.name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-contacts\n          description: \"List contacts in a specific audience\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"resend.list-contacts\"\n          with:\n            audience_id: \"tools.audience_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: add-contact-to-audience\n          description: \"Add a contact to an audience for marketing emails\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"resend.create-contact\"\n          with:\n            audience_id: \"tools.audience_id\"\n            email: \"tools.email\"\n            first_name: \"tools.first_name\"\n            last_name: \"tools.last_name\"\n          outputParameters:\n            - type: object\n       \
  \       mapping: \"$.\"\n        - name: list-broadcasts\n          description: \"List all email broadcast campaigns\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"resend.list-broadcasts\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-broadcast\n          description: \"Create a new broadcast email campaign\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"resend.create-broadcast\"\n          with:\n            name: \"tools.name\"\n            audience_id: \"tools.audience_id\"\n            from: \"tools.from\"\n            subject: \"tools.subject\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: send-broadcast-campaign\n          description: \"Send or schedule a broadcast campaign to an audience\"\n          hints:\n            readOnly:\
  \ false\n            destructive: false\n            idempotent: false\n          call: \"resend.send-broadcast\"\n          with:\n            id: \"tools.id\"\n            scheduled_at: \"tools.scheduled_at\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-api-keys\n          description: \"List all API keys for the account\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"resend.list-api-keys\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/resend/refs/heads/main/capabilities/email-delivery.yaml
tags:
- Email
- Transactional Email
- Marketing Email
- Developer Tools
- Broadcasts
- Audiences
tools:
- description: Send a transactional email to one or more recipients
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: send-transactional-email
- description: Get the status and details of a sent email by ID
  hints:
    openWorld: true
    readOnly: true
  name: get-email-status
- description: Send up to 100 emails in a single batch operation
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: send-batch-emails
- description: Cancel a scheduled email before it is sent
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: cancel-scheduled-email
- description: List all configured email sending domains
  hints:
    openWorld: true
    readOnly: true
  name: list-sending-domains
- description: Add a new email sending domain
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-sending-domain
- description: Verify DNS records for a sending domain
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: verify-domain
- description: List all contact audiences
  hints:
    openWorld: true
    readOnly: true
  name: list-audiences
- description: Create a new contact audience
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-audience
- description: List contacts in a specific audience
  hints:
    openWorld: true
    readOnly: true
  name: list-contacts
- description: Add a contact to an audience for marketing emails
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: add-contact-to-audience
- description: List all email broadcast campaigns
  hints:
    openWorld: true
    readOnly: true
  name: list-broadcasts
- description: Create a new broadcast email campaign
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-broadcast
- description: Send or schedule a broadcast campaign to an audience
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: send-broadcast-campaign
- description: List all API keys for the account
  hints:
    openWorld: true
    readOnly: true
  name: list-api-keys
---
