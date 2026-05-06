---
categories: []
consumed_apis: []
description: 'Workflow capability for email marketing and campaign management using Silverpop (Acoustic Campaign). Covers the full campaign lifecycle: contact management, campaign creation and scheduling, transactional messaging, engagement reporting, and marketing automation programs.'
layout: capability
name: Silverpop Email Marketing
operations:
- description: List all contact databases.
  method: GET
  name: list-databases
  path: /v1/databases
- description: List contacts in a database.
  method: GET
  name: list-contacts
  path: /v1/databases/{id}/contacts
- description: Add a new contact to a database.
  method: POST
  name: add-contact
  path: /v1/databases/{id}/contacts
- description: Get a contact's details.
  method: GET
  name: get-contact
  path: /v1/databases/{db_id}/contacts/{contact_id}
- description: Update a contact's attributes.
  method: PUT
  name: update-contact
  path: /v1/databases/{db_id}/contacts/{contact_id}
- description: Remove a contact from a database.
  method: DELETE
  name: remove-contact
  path: /v1/databases/{db_id}/contacts/{contact_id}
- description: List all email campaigns.
  method: GET
  name: list-campaigns
  path: /v1/campaigns
- description: Create a new email campaign.
  method: POST
  name: create-campaign
  path: /v1/campaigns
- description: Get campaign details.
  method: GET
  name: get-campaign
  path: /v1/campaigns/{id}
- description: Schedule a campaign for delivery.
  method: POST
  name: schedule-campaign
  path: /v1/campaigns/{id}/schedule
- description: Get campaign aggregate performance metrics.
  method: GET
  name: get-campaign-summary
  path: /v1/campaigns/{id}/reports/summary
- description: Get campaign open event data.
  method: GET
  name: get-campaign-opens
  path: /v1/campaigns/{id}/reports/opens
- description: Get campaign click event data.
  method: GET
  name: get-campaign-clicks
  path: /v1/campaigns/{id}/reports/clicks
- description: List all marketing automation programs.
  method: GET
  name: list-programs
  path: /v1/programs
- description: Get program details and status.
  method: GET
  name: get-program
  path: /v1/programs/{id}
personas: []
provider_name: Silverpop
provider_slug: silverpop
search_terms:
- schedule campaign
- list all marketing automation programs.
- list all contact databases.
- list contacts in a specific database with pagination.
- get contact
- single program operations.
- add a new contact to a silverpop database.
- get a contact's details.
- update a contact's attributes and custom fields.
- digital marketing
- single contact operations.
- campaign scheduling.
- reporting
- get details of a specific email campaign.
- email campaign management.
- update contact
- campaign open events.
- get program details and status.
- remove (opt-out) a contact from a database.
- add contact
- add a new contact to a database.
- list programs
- get campaign summary
- remove a contact from a database.
- get campaign
- list campaigns
- get detailed click-through event records for a campaign.
- get campaign opens
- get campaign clicks
- create a new email campaign mailing.
- marketing automation
- list all email campaigns.
- email marketing
- get details and status of a specific marketing automation program.
- get campaign click event data.
- get campaign aggregate performance metrics.
- get a specific contact's profile and custom fields.
- list all email campaigns with optional status filtering.
- get aggregate performance metrics for a sent campaign (opens, clicks, unsubscribes, bounces).
- get detailed open event records for a campaign.
- contact management within a database.
- update a contact's attributes.
- schedule a campaign for delivery at a specific date and time.
- list all contact databases (lists) in the silverpop account.
- list databases
- contact database management.
- contact management
- get campaign open event data.
- campaign performance summary.
- list contacts in a database.
- single campaign operations.
- create campaign
- create a new email campaign.
- schedule a campaign for delivery.
- list contacts
- get campaign details.
- campaign management
- remove contact
- marketing automation programs.
- get program
- campaign click events.
slug: email-marketing
source_filename: email-marketing.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Silverpop Email Marketing\n  description: 'Workflow capability for email marketing and campaign management using Silverpop (Acoustic Campaign). Covers\n    the full campaign lifecycle: contact management, campaign creation and scheduling, transactional messaging, engagement\n    reporting, and marketing automation programs.'\n  tags:\n  - Email Marketing\n  - Campaign Management\n  - Marketing Automation\n  - Contact Management\n  - Reporting\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SILVERPOP_ACCESS_TOKEN: SILVERPOP_ACCESS_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: silverpop\n    baseUri: https://api-campaign-us-1.goacoustic.com\n    description: Silverpop Engage (Acoustic Campaign) REST API.\n    authentication:\n      type: bearer\n      token: '{{SILVERPOP_ACCESS_TOKEN}}'\n    resources:\n    - name: databases\n      path: /rest/databases\n      description: Contact\
  \ database (list) management.\n      operations:\n      - name: list-databases\n        method: GET\n        description: List all contact databases in the account.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: contacts\n      path: /rest/databases/{database_id}/contacts\n      description: Contact management within a database.\n      operations:\n      - name: list-contacts\n        method: GET\n        description: List contacts from a specific database.\n        inputParameters:\n        - name: database_id\n          in: path\n          type: string\n          required: true\n          description: Contact database identifier.\n        - name: count\n          in: query\n          type: integer\n          required: false\n          description: Number of contacts to return.\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description:\
  \ Pagination offset.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: add-contact\n        method: POST\n        description: Add a new contact to a database.\n        inputParameters:\n        - name: database_id\n          in: path\n          type: string\n          required: true\n          description: Contact database identifier.\n        body:\n          type: json\n          data:\n            email: '{{tools.email}}'\n            first_name: '{{tools.first_name}}'\n            last_name: '{{tools.last_name}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: contact\n      path: /rest/databases/{database_id}/contacts/{contact_id}\n      description: Single contact operations.\n      operations:\n      - name: get-contact\n        method: GET\n        description: Retrieve a specific contact's details.\n\
  \        inputParameters:\n        - name: database_id\n          in: path\n          type: string\n          required: true\n        - name: contact_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-contact\n        method: PUT\n        description: Update a contact's attributes.\n        inputParameters:\n        - name: database_id\n          in: path\n          type: string\n          required: true\n        - name: contact_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: remove-contact\n        method: DELETE\n        description: Remove a contact from a database.\n        inputParameters:\n        - name: database_id\n          in: path\n         \
  \ type: string\n          required: true\n        - name: contact_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: campaigns\n      path: /rest/mailings\n      description: Email campaign management.\n      operations:\n      - name: list-campaigns\n        method: GET\n        description: List all email campaigns.\n        inputParameters:\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Filter by campaign status.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-campaign\n        method: POST\n        description: Create a new email campaign.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            subject: '{{tools.subject}}'\n\
  \            database_id: '{{tools.database_id}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: campaign\n      path: /rest/mailings/{mailing_id}\n      description: Single campaign operations.\n      operations:\n      - name: get-campaign\n        method: GET\n        description: Retrieve details of a specific campaign.\n        inputParameters:\n        - name: mailing_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: campaign-schedule\n      path: /rest/mailings/{mailing_id}/schedule\n      description: Campaign scheduling.\n      operations:\n      - name: schedule-campaign\n        method: POST\n        description: Schedule a campaign for delivery.\n        inputParameters:\n        - name: mailing_id\n          in: path\n  \
  \        type: string\n          required: true\n        body:\n          type: json\n          data:\n            schedule_date: '{{tools.schedule_date}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: campaign-report\n      path: /rest/reports/mailings/{mailing_id}/summary\n      description: Campaign performance reporting.\n      operations:\n      - name: get-campaign-summary\n        method: GET\n        description: Retrieve aggregate performance metrics for a campaign.\n        inputParameters:\n        - name: mailing_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: campaign-opens\n      path: /rest/reports/mailings/{mailing_id}/opens\n      description: Campaign open event reporting.\n      operations:\n      - name: get-campaign-opens\n\
  \        method: GET\n        description: Retrieve open event data for a campaign.\n        inputParameters:\n        - name: mailing_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: campaign-clicks\n      path: /rest/reports/mailings/{mailing_id}/clicks\n      description: Campaign click event reporting.\n      operations:\n      - name: get-campaign-clicks\n        method: GET\n        description: Retrieve click event data for a campaign.\n        inputParameters:\n        - name: mailing_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: programs\n      path: /rest/programs\n      description: Marketing automation program management.\n      operations:\n      -\
  \ name: list-programs\n        method: GET\n        description: List all marketing automation programs.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: program\n      path: /rest/programs/{program_id}\n      description: Single program operations.\n      operations:\n      - name: get-program\n        method: GET\n        description: Retrieve details of a specific program.\n        inputParameters:\n        - name: program_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: email-marketing-api\n    description: Unified REST API for email marketing and campaign management via Silverpop/Acoustic.\n    resources:\n    - path: /v1/databases\n      name: databases\n      description: Contact database\
  \ management.\n      operations:\n      - method: GET\n        name: list-databases\n        description: List all contact databases.\n        call: silverpop.list-databases\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/databases/{id}/contacts\n      name: contacts\n      description: Contact management within a database.\n      operations:\n      - method: GET\n        name: list-contacts\n        description: List contacts in a database.\n        call: silverpop.list-contacts\n        with:\n          database_id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: add-contact\n        description: Add a new contact to a database.\n        call: silverpop.add-contact\n        with:\n          database_id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/databases/{db_id}/contacts/{contact_id}\n      name: contact\n      description:\
  \ Single contact operations.\n      operations:\n      - method: GET\n        name: get-contact\n        description: Get a contact's details.\n        call: silverpop.get-contact\n        with:\n          database_id: rest.db_id\n          contact_id: rest.contact_id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PUT\n        name: update-contact\n        description: Update a contact's attributes.\n        call: silverpop.update-contact\n        with:\n          database_id: rest.db_id\n          contact_id: rest.contact_id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: remove-contact\n        description: Remove a contact from a database.\n        call: silverpop.remove-contact\n        with:\n          database_id: rest.db_id\n          contact_id: rest.contact_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/campaigns\n      name:\
  \ campaigns\n      description: Email campaign management.\n      operations:\n      - method: GET\n        name: list-campaigns\n        description: List all email campaigns.\n        call: silverpop.list-campaigns\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-campaign\n        description: Create a new email campaign.\n        call: silverpop.create-campaign\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/campaigns/{id}\n      name: campaign\n      description: Single campaign operations.\n      operations:\n      - method: GET\n        name: get-campaign\n        description: Get campaign details.\n        call: silverpop.get-campaign\n        with:\n          mailing_id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/campaigns/{id}/schedule\n      name: campaign-schedule\n      description: Campaign scheduling.\n   \
  \   operations:\n      - method: POST\n        name: schedule-campaign\n        description: Schedule a campaign for delivery.\n        call: silverpop.schedule-campaign\n        with:\n          mailing_id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/campaigns/{id}/reports/summary\n      name: campaign-summary\n      description: Campaign performance summary.\n      operations:\n      - method: GET\n        name: get-campaign-summary\n        description: Get campaign aggregate performance metrics.\n        call: silverpop.get-campaign-summary\n        with:\n          mailing_id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/campaigns/{id}/reports/opens\n      name: campaign-opens\n      description: Campaign open events.\n      operations:\n      - method: GET\n        name: get-campaign-opens\n        description: Get campaign open event data.\n        call: silverpop.get-campaign-opens\n\
  \        with:\n          mailing_id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/campaigns/{id}/reports/clicks\n      name: campaign-clicks\n      description: Campaign click events.\n      operations:\n      - method: GET\n        name: get-campaign-clicks\n        description: Get campaign click event data.\n        call: silverpop.get-campaign-clicks\n        with:\n          mailing_id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/programs\n      name: programs\n      description: Marketing automation programs.\n      operations:\n      - method: GET\n        name: list-programs\n        description: List all marketing automation programs.\n        call: silverpop.list-programs\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/programs/{id}\n      name: program\n      description: Single program operations.\n      operations:\n     \
  \ - method: GET\n        name: get-program\n        description: Get program details and status.\n        call: silverpop.get-program\n        with:\n          program_id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: email-marketing-mcp\n    transport: http\n    description: MCP server for AI-assisted email marketing and campaign management.\n    tools:\n    - name: list-databases\n      description: List all contact databases (lists) in the Silverpop account.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: silverpop.list-databases\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-contacts\n      description: List contacts in a specific database with pagination.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: silverpop.list-contacts\n      with:\n        database_id: tools.database_id\n      outputParameters:\n \
  \     - type: object\n        mapping: $.\n    - name: add-contact\n      description: Add a new contact to a Silverpop database.\n      hints:\n        readOnly: false\n      call: silverpop.add-contact\n      with:\n        database_id: tools.database_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-contact\n      description: Get a specific contact's profile and custom fields.\n      hints:\n        readOnly: true\n      call: silverpop.get-contact\n      with:\n        database_id: tools.database_id\n        contact_id: tools.contact_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-contact\n      description: Update a contact's attributes and custom fields.\n      hints:\n        readOnly: false\n        idempotent: true\n      call: silverpop.update-contact\n      with:\n        database_id: tools.database_id\n        contact_id: tools.contact_id\n      outputParameters:\n      - type: object\n      \
  \  mapping: $.\n    - name: remove-contact\n      description: Remove (opt-out) a contact from a database.\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: silverpop.remove-contact\n      with:\n        database_id: tools.database_id\n        contact_id: tools.contact_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-campaigns\n      description: List all email campaigns with optional status filtering.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: silverpop.list-campaigns\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-campaign\n      description: Create a new email campaign mailing.\n      hints:\n        readOnly: false\n      call: silverpop.create-campaign\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-campaign\n      description: Get details of a specific email campaign.\n      hints:\n\
  \        readOnly: true\n      call: silverpop.get-campaign\n      with:\n        mailing_id: tools.mailing_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: schedule-campaign\n      description: Schedule a campaign for delivery at a specific date and time.\n      hints:\n        readOnly: false\n      call: silverpop.schedule-campaign\n      with:\n        mailing_id: tools.mailing_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-campaign-summary\n      description: Get aggregate performance metrics for a sent campaign (opens, clicks, unsubscribes, bounces).\n      hints:\n        readOnly: true\n      call: silverpop.get-campaign-summary\n      with:\n        mailing_id: tools.mailing_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-campaign-opens\n      description: Get detailed open event records for a campaign.\n      hints:\n        readOnly: true\n        openWorld: true\n\
  \      call: silverpop.get-campaign-opens\n      with:\n        mailing_id: tools.mailing_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-campaign-clicks\n      description: Get detailed click-through event records for a campaign.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: silverpop.get-campaign-clicks\n      with:\n        mailing_id: tools.mailing_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-programs\n      description: List all marketing automation programs.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: silverpop.list-programs\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-program\n      description: Get details and status of a specific marketing automation program.\n      hints:\n        readOnly: true\n      call: silverpop.get-program\n      with:\n        program_id: tools.program_id\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/silverpop/refs/heads/main/capabilities/email-marketing.yaml
tags:
- Email Marketing
- Campaign Management
- Marketing Automation
- Contact Management
- Reporting
tools:
- description: List all contact databases (lists) in the Silverpop account.
  hints:
    openWorld: true
    readOnly: true
  name: list-databases
- description: List contacts in a specific database with pagination.
  hints:
    openWorld: true
    readOnly: true
  name: list-contacts
- description: Add a new contact to a Silverpop database.
  hints:
    readOnly: false
  name: add-contact
- description: Get a specific contact's profile and custom fields.
  hints:
    readOnly: true
  name: get-contact
- description: Update a contact's attributes and custom fields.
  hints:
    idempotent: true
    readOnly: false
  name: update-contact
- description: Remove (opt-out) a contact from a database.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: remove-contact
- description: List all email campaigns with optional status filtering.
  hints:
    openWorld: true
    readOnly: true
  name: list-campaigns
- description: Create a new email campaign mailing.
  hints:
    readOnly: false
  name: create-campaign
- description: Get details of a specific email campaign.
  hints:
    readOnly: true
  name: get-campaign
- description: Schedule a campaign for delivery at a specific date and time.
  hints:
    readOnly: false
  name: schedule-campaign
- description: Get aggregate performance metrics for a sent campaign (opens, clicks, unsubscribes, bounces).
  hints:
    readOnly: true
  name: get-campaign-summary
- description: Get detailed open event records for a campaign.
  hints:
    openWorld: true
    readOnly: true
  name: get-campaign-opens
- description: Get detailed click-through event records for a campaign.
  hints:
    openWorld: true
    readOnly: true
  name: get-campaign-clicks
- description: List all marketing automation programs.
  hints:
    openWorld: true
    readOnly: true
  name: list-programs
- description: Get details and status of a specific marketing automation program.
  hints:
    readOnly: true
  name: get-program
---
