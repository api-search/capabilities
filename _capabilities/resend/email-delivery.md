---
categories: []
consumed_apis: []
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
- list all configured sending domains
- contact audiences for marketing emails
- remove a sending domain
- list broadcasts
- send or schedule a broadcast
- verify domain
- list all contact audiences
- email domain configuration
- create audience
- marketing email
- transactional email sending
- send broadcast campaign
- email broadcast campaigns
- add a contact to an audience for marketing emails
- cancel scheduled email
- send batch emails
- broadcasts
- create contact
- get email
- create domain
- list audiences
- update domain tracking settings
- create a new broadcast email campaign
- list domains
- audiences
- list sending domains
- send broadcast
- list all email broadcast campaigns
- verify dns records for a sending domain
- update email
- list all broadcast campaigns
- send a transactional email to one or more recipients
- create broadcast
- get the status and details of a sent email by id
- delete domain
- list all configured email sending domains
- add a new email sending domain
- create sending domain
- single domain management
- developer tools
- send up to 100 emails in a single batch
- single email management
- email
- get domain
- list contacts
- send up to 100 emails in a single batch operation
- retrieve a single sent email
- send a transactional email
- list api keys
- add contact to audience
- add a contact to an audience
- list all api keys for the account
- create a new audience
- audience contacts
- list contacts in an audience
- send transactional email
- create a new contact audience
- add a new sending domain
- cancel a scheduled email
- send or schedule a broadcast campaign
- update domain
- list all audiences
- create a new broadcast campaign
- cancel a scheduled email before it is sent
- list contacts in a specific audience
- cancel email
- send or schedule a broadcast campaign to an audience
- transactional email
- get email status
- get details for a domain
- send email
- batch email sending
- update a scheduled email
slug: email-delivery
source_filename: email-delivery.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Resend Email Delivery\n  description: Workflow capability for sending and managing transactional emails, batch email campaigns, scheduled emails,\n    domain configuration, and audience-based broadcast campaigns using the Resend email API.\n  tags:\n  - Email\n  - Transactional Email\n  - Marketing Email\n  - Developer Tools\n  - Broadcasts\n  - Audiences\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    RESEND_API_KEY: RESEND_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: resend\n    baseUri: https://api.resend.com\n    description: Resend email API for developers\n    authentication:\n      type: bearer\n      token: '{{RESEND_API_KEY}}'\n    resources:\n    - name: emails\n      path: /emails\n      description: Email sending and management\n      operations:\n      - name: send-email\n        method: POST\n        description: Send an email\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            from: '{{tools.from}}'\n            to: '{{tools.to}}'\n            subject: '{{tools.subject}}'\n            html: '{{tools.html}}'\n            text: '{{tools.text}}'\n      - name: get-email\n        method: GET\n        description: Retrieve a single email by ID\n        inputParameters:\n        - name: email_id\n          in: path\n          type: string\n          required: true\n          description: The ID of the email\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-email\n        method: PATCH\n        description: Update a scheduled email\n        inputParameters:\n        - name: email_id\n          in: path\n          type: string\n          required: true\n          description: The ID of the email\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            scheduled_at: '{{tools.scheduled_at}}'\n      - name: cancel-email\n        method: POST\n        description: Cancel the schedule of an email\n        inputParameters:\n        - name: email_id\n          in: path\n          type: string\n          required: true\n          description: The ID of the email\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: send-batch-emails\n        method: POST\n        description: Trigger up to 100 batch emails at once\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            emails: '{{tools.emails}}'\n    - name: domains\n      path: /domains\n      description:\
  \ Email domain management\n      operations:\n      - name: create-domain\n        method: POST\n        description: Create a new domain\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            region: '{{tools.region}}'\n      - name: list-domains\n        method: GET\n        description: Retrieve a list of domains\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-domain\n        method: GET\n        description: Retrieve a single domain\n        inputParameters:\n        - name: domain_id\n          in: path\n          type: string\n          required: true\n          description: The ID of the domain\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n      - name: update-domain\n        method: PATCH\n        description: Update an existing domain\n        inputParameters:\n        - name: domain_id\n          in: path\n          type: string\n          required: true\n          description: The ID of the domain\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            open_tracking: '{{tools.open_tracking}}'\n            click_tracking: '{{tools.click_tracking}}'\n      - name: delete-domain\n        method: DELETE\n        description: Remove an existing domain\n        inputParameters:\n        - name: domain_id\n          in: path\n          type: string\n          required: true\n          description: The ID of the domain\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: verify-domain\n        method:\
  \ POST\n        description: Verify an existing domain\n        inputParameters:\n        - name: domain_id\n          in: path\n          type: string\n          required: true\n          description: The ID of the domain\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-keys\n      path: /api-keys\n      description: API key management\n      operations:\n      - name: create-api-key\n        method: POST\n        description: Create a new API key\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            permission: '{{tools.permission}}'\n      - name: list-api-keys\n        method: GET\n        description: Retrieve a list of API keys\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n   \
  \       type: object\n          value: $.\n      - name: delete-api-key\n        method: DELETE\n        description: Remove an existing API key\n        inputParameters:\n        - name: api_key_id\n          in: path\n          type: string\n          required: true\n          description: The API key ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: audiences\n      path: /audiences\n      description: Audience and contact management\n      operations:\n      - name: create-audience\n        method: POST\n        description: Create a list of contacts (audience)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n      - name: list-audiences\n        method: GET\n        description: Retrieve a list of audiences\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-audience\n        method: GET\n        description: Retrieve a single audience\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The Audience ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-audience\n        method: DELETE\n        description: Remove an existing audience\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The Audience ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: contacts\n      path: /audiences/{audience_id}/contacts\n      description: Audience contact management\n      operations:\n\
  \      - name: create-contact\n        method: POST\n        description: Create a new contact in an audience\n        inputParameters:\n        - name: audience_id\n          in: path\n          type: string\n          required: true\n          description: The Audience ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            email: '{{tools.email}}'\n            first_name: '{{tools.first_name}}'\n            last_name: '{{tools.last_name}}'\n      - name: list-contacts\n        method: GET\n        description: Retrieve a list of contacts in an audience\n        inputParameters:\n        - name: audience_id\n          in: path\n          type: string\n          required: true\n          description: The Audience ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n   \
  \   - name: get-contact\n        method: GET\n        description: Retrieve a single contact\n        inputParameters:\n        - name: audience_id\n          in: path\n          type: string\n          required: true\n          description: The Audience ID\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The Contact ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-contact\n        method: PATCH\n        description: Update a single contact\n        inputParameters:\n        - name: audience_id\n          in: path\n          type: string\n          required: true\n          description: The Audience ID\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The Contact ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n         \
  \ type: object\n          value: $.\n        body:\n          type: json\n          data:\n            unsubscribed: '{{tools.unsubscribed}}'\n      - name: delete-contact\n        method: DELETE\n        description: Remove an existing contact by ID\n        inputParameters:\n        - name: audience_id\n          in: path\n          type: string\n          required: true\n          description: The Audience ID\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The Contact ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: broadcasts\n      path: /broadcasts\n      description: Broadcast email campaign management\n      operations:\n      - name: create-broadcast\n        method: POST\n        description: Create a broadcast email campaign\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            audience_id: '{{tools.audience_id}}'\n            from: '{{tools.from}}'\n            subject: '{{tools.subject}}'\n      - name: list-broadcasts\n        method: GET\n        description: Retrieve a list of broadcasts\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-broadcast\n        method: GET\n        description: Retrieve a single broadcast\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The Broadcast ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: send-broadcast\n        method: POST\n        description: Send or schedule a broadcast\n        inputParameters:\n      \
  \  - name: id\n          in: path\n          type: string\n          required: true\n          description: The Broadcast ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            scheduled_at: '{{tools.scheduled_at}}'\n      - name: delete-broadcast\n        method: DELETE\n        description: Remove an existing broadcast in draft status\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The Broadcast ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: email-delivery-api\n    description: Unified REST API for email delivery, domain management, and audience campaigns.\n    resources:\n    - path: /v1/emails\n      name: emails\n\
  \      description: Transactional email sending\n      operations:\n      - method: POST\n        name: send-email\n        description: Send a transactional email\n        call: resend.send-email\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/emails/{id}\n      name: email\n      description: Single email management\n      operations:\n      - method: GET\n        name: get-email\n        description: Retrieve a single sent email\n        call: resend.get-email\n        with:\n          email_id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PATCH\n        name: update-email\n        description: Update a scheduled email\n        call: resend.update-email\n        with:\n          email_id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/emails/{id}/cancel\n      name: email-cancel\n      description: Cancel scheduled email\n      operations:\n\
  \      - method: POST\n        name: cancel-email\n        description: Cancel a scheduled email\n        call: resend.cancel-email\n        with:\n          email_id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/emails/batch\n      name: email-batch\n      description: Batch email sending\n      operations:\n      - method: POST\n        name: send-batch-emails\n        description: Send up to 100 emails in a single batch\n        call: resend.send-batch-emails\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/domains\n      name: domains\n      description: Email domain configuration\n      operations:\n      - method: GET\n        name: list-domains\n        description: List all configured sending domains\n        call: resend.list-domains\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-domain\n        description: Add\
  \ a new sending domain\n        call: resend.create-domain\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/domains/{id}\n      name: domain\n      description: Single domain management\n      operations:\n      - method: GET\n        name: get-domain\n        description: Get details for a domain\n        call: resend.get-domain\n        with:\n          domain_id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PATCH\n        name: update-domain\n        description: Update domain tracking settings\n        call: resend.update-domain\n        with:\n          domain_id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-domain\n        description: Remove a sending domain\n        call: resend.delete-domain\n        with:\n          domain_id: rest.id\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /v1/audiences\n      name: audiences\n      description: Contact audiences for marketing emails\n      operations:\n      - method: GET\n        name: list-audiences\n        description: List all audiences\n        call: resend.list-audiences\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-audience\n        description: Create a new audience\n        call: resend.create-audience\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/audiences/{audience_id}/contacts\n      name: contacts\n      description: Audience contacts\n      operations:\n      - method: GET\n        name: list-contacts\n        description: List contacts in an audience\n        call: resend.list-contacts\n        with:\n          audience_id: rest.audience_id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-contact\n     \
  \   description: Add a contact to an audience\n        call: resend.create-contact\n        with:\n          audience_id: rest.audience_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/broadcasts\n      name: broadcasts\n      description: Email broadcast campaigns\n      operations:\n      - method: GET\n        name: list-broadcasts\n        description: List all broadcast campaigns\n        call: resend.list-broadcasts\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-broadcast\n        description: Create a new broadcast campaign\n        call: resend.create-broadcast\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/broadcasts/{id}/send\n      name: broadcast-send\n      description: Send or schedule a broadcast\n      operations:\n      - method: POST\n        name: send-broadcast\n        description: Send or schedule a broadcast\
  \ campaign\n        call: resend.send-broadcast\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: email-delivery-mcp\n    transport: http\n    description: MCP server for AI-assisted email delivery, campaign management, and domain configuration.\n    tools:\n    - name: send-transactional-email\n      description: Send a transactional email to one or more recipients\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: resend.send-email\n      with:\n        from: tools.from\n        to: tools.to\n        subject: tools.subject\n        html: tools.html\n        text: tools.text\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-email-status\n      description: Get the status and details of a sent email by ID\n      hints:\n        readOnly: true\n        openWorld: true\n      call: resend.get-email\n\
  \      with:\n        email_id: tools.email_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: send-batch-emails\n      description: Send up to 100 emails in a single batch operation\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: resend.send-batch-emails\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: cancel-scheduled-email\n      description: Cancel a scheduled email before it is sent\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: resend.cancel-email\n      with:\n        email_id: tools.email_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-sending-domains\n      description: List all configured email sending domains\n      hints:\n        readOnly: true\n        openWorld: true\n      call: resend.list-domains\n      outputParameters:\n      - type: object\n    \
  \    mapping: $.\n    - name: create-sending-domain\n      description: Add a new email sending domain\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: resend.create-domain\n      with:\n        name: tools.name\n        region: tools.region\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: verify-domain\n      description: Verify DNS records for a sending domain\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: resend.verify-domain\n      with:\n        domain_id: tools.domain_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-audiences\n      description: List all contact audiences\n      hints:\n        readOnly: true\n        openWorld: true\n      call: resend.list-audiences\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-audience\n      description: Create a new\
  \ contact audience\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: resend.create-audience\n      with:\n        name: tools.name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-contacts\n      description: List contacts in a specific audience\n      hints:\n        readOnly: true\n        openWorld: true\n      call: resend.list-contacts\n      with:\n        audience_id: tools.audience_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: add-contact-to-audience\n      description: Add a contact to an audience for marketing emails\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: resend.create-contact\n      with:\n        audience_id: tools.audience_id\n        email: tools.email\n        first_name: tools.first_name\n        last_name: tools.last_name\n      outputParameters:\n      - type: object\n  \
  \      mapping: $.\n    - name: list-broadcasts\n      description: List all email broadcast campaigns\n      hints:\n        readOnly: true\n        openWorld: true\n      call: resend.list-broadcasts\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-broadcast\n      description: Create a new broadcast email campaign\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: resend.create-broadcast\n      with:\n        name: tools.name\n        audience_id: tools.audience_id\n        from: tools.from\n        subject: tools.subject\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: send-broadcast-campaign\n      description: Send or schedule a broadcast campaign to an audience\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: resend.send-broadcast\n      with:\n        id: tools.id\n        scheduled_at: tools.scheduled_at\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-api-keys\n      description: List all API keys for the account\n      hints:\n        readOnly: true\n        openWorld: true\n      call: resend.list-api-keys\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
