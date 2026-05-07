---
categories:
- customer-engagement
consumed_apis: []
description: Unified capability for marketing automation workflows combining the Marketing Cloud REST API for contact management, journey orchestration, email and SMS messaging, data extensions, and content asset management. Used by marketing teams and marketing ops to manage campaigns and subscriber engagement.
layout: capability
name: Salesforce Marketing Automation
operations:
- description: List contacts in the Marketing Cloud account.
  method: GET
  name: list-contacts
  path: /v1/contacts
- description: Get a contact by contact key.
  method: GET
  name: get-contact
  path: /v1/contacts/{contactKey}
- description: Delete one or more contacts.
  method: POST
  name: delete-contacts
  path: /v1/contacts/delete
- description: Get rows from a Data Extension.
  method: GET
  name: get-data-extension-rows
  path: /v1/data-extensions/{key}/rows
- description: Insert or upsert rows into a Data Extension.
  method: POST
  name: insert-data-extension-rows
  path: /v1/data-extensions/{key}/rows
- description: Create and initiate a triggered email send.
  method: POST
  name: create-email-send
  path: /v1/emails
- description: Create and initiate an SMS send.
  method: POST
  name: create-sms-send
  path: /v1/sms
- description: Get the delivery status of an email message.
  method: GET
  name: get-message-status
  path: /v1/messages/{messageKey}/status
- description: List Marketing Cloud journeys.
  method: GET
  name: list-journeys
  path: /v1/journeys
- description: Get a journey by ID.
  method: GET
  name: get-journey
  path: /v1/journeys/{interactionId}
- description: Fire a journey entry event to enroll a contact.
  method: POST
  name: fire-journey-event
  path: /v1/journey-events
- description: List content assets.
  method: GET
  name: list-assets
  path: /v1/assets
- description: Create a content asset.
  method: POST
  name: create-asset
  path: /v1/assets
- description: Get a content asset by ID.
  method: GET
  name: get-asset
  path: /v1/assets/{id}
- description: Update a content asset.
  method: PUT
  name: update-asset
  path: /v1/assets/{id}
- description: Delete a content asset.
  method: DELETE
  name: delete-asset
  path: /v1/assets/{id}
personas: []
provider_name: Salesforce
provider_slug: salesforce
search_terms:
- triggered email send operations.
- create and initiate a triggered email send.
- create and initiate an sms send to one or more recipients.
- list content assets.
- analytics
- create sms send
- insert or upsert rows into a marketing cloud data extension.
- get contact
- get data extension rows
- get message status
- get rows from a marketing cloud data extension.
- journeys
- get a content builder asset by id.
- update a content asset.
- insert data extension rows
- delete one or more contacts from marketing cloud.
- create a content asset.
- ai
- sms send operations.
- fire a journey entry event to enroll a contact.
- platform
- create asset
- get the delivery status of a triggered email send.
- fire a journey entry event to enroll a contact in a journey.
- get journey
- update a content builder asset.
- create email send
- individual contact operations.
- delete a content asset.
- get a contact by contact key.
- get the delivery status of an email message.
- insert or upsert rows into a data extension.
- get rows from a data extension.
- list marketing cloud journeys.
- individual journey operations.
- list journeys
- journey entry event operations.
- get a content asset by id.
- create and initiate a triggered email send to one or more recipients.
- list marketing cloud journey builder journeys.
- delete a content builder asset.
- data extension row operations.
- list contacts in the marketing cloud account.
- crm
- get a journey by id.
- journey builder journey management.
- list contacts
- individual asset operations.
- update asset
- get detailed information about a marketing cloud journey.
- marketing cloud
- create a new content asset in content builder.
- message delivery status.
- enterprise
- get a marketing cloud contact by contact key.
- delete contacts
- cloud
- list marketing cloud content builder assets.
- marketing
- sales
- delete one or more contacts.
- contact deletion operations.
- create and initiate an sms send.
- get asset
- fire journey event
- content builder asset management.
- marketing cloud contact management.
- customer service
- marketing automation
- commerce
- list assets
- delete asset
- salesforce
- email marketing
slug: marketing-automation
source_filename: marketing-automation.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Salesforce Marketing Automation\n  description: Unified capability for marketing automation workflows combining the Marketing Cloud REST API for contact management,\n    journey orchestration, email and SMS messaging, data extensions, and content asset management. Used by marketing teams\n    and marketing ops to manage campaigns and subscriber engagement.\n  tags:\n  - Salesforce\n  - Marketing Cloud\n  - Marketing Automation\n  - Email Marketing\n  - Journeys\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SALESFORCE_MC_CLIENT_ID: SALESFORCE_MC_CLIENT_ID\n    SALESFORCE_MC_CLIENT_SECRET: SALESFORCE_MC_CLIENT_SECRET\n    SALESFORCE_MC_ACCESS_TOKEN: SALESFORCE_MC_ACCESS_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: salesforce-mc\n    baseUri: https://{subdomain}.rest.marketingcloudapis.com\n    description: Salesforce Marketing Cloud REST API for contacts, journeys, data extensions,\
  \ messaging, and content assets.\n    authentication:\n      type: bearer\n      token: '{{SALESFORCE_MC_ACCESS_TOKEN}}'\n    resources:\n    - name: authentication\n      path: /v2\n      description: OAuth 2.0 token operations.\n      operations:\n      - name: get-access-token\n        method: POST\n        path: /token\n        description: Obtain an OAuth 2.0 access token.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            grant_type: '{{tools.grant_type}}'\n            client_id: '{{tools.client_id}}'\n            client_secret: '{{tools.client_secret}}'\n    - name: contacts\n      path: /contacts/v1/contacts\n      description: Contact management operations.\n      operations:\n      - name: list-contacts\n        method: GET\n        path: /\n        description: List contacts in the Marketing Cloud account.\n\
  \        inputParameters:\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number to retrieve.\n        - name: pageSize\n          in: query\n          type: integer\n          required: false\n          description: Number of contacts per page.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-contact\n        method: GET\n        path: /{contactKey}\n        description: Get a contact by contact key.\n        inputParameters:\n        - name: contactKey\n          in: path\n          type: string\n          required: true\n          description: The unique contact key.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-contacts\n        method: DELETE\n        path: /\n        description: Delete one or more contacts.\n\
  \        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            contactKeys: '{{tools.contact_keys}}'\n    - name: data-extensions\n      path: /data/v1/async/dataextensions\n      description: Data Extension row operations.\n      operations:\n      - name: get-data-extension-rows\n        method: GET\n        path: /key:{key}/rows\n        description: Get rows from a Data Extension.\n        inputParameters:\n        - name: key\n          in: path\n          type: string\n          required: true\n          description: The Data Extension external key.\n        - name: $pageSize\n          in: query\n          type: integer\n          required: false\n          description: Number of rows per page.\n        - name: $page\n          in: query\n          type: integer\n          required: false\n          description: Page number\
  \ to retrieve.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: insert-data-extension-rows\n        method: POST\n        path: /key:{key}/rows\n        description: Insert rows into a Data Extension.\n        inputParameters:\n        - name: key\n          in: path\n          type: string\n          required: true\n          description: The Data Extension external key.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            items: '{{tools.items}}'\n    - name: messaging\n      path: /messaging/v1\n      description: Email and SMS messaging operations.\n      operations:\n      - name: create-email-send\n        method: POST\n        path: /email/messages\n        description: Create and initiate a triggered email send.\n        inputParameters: []\n     \
  \   outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            definitionKey: '{{tools.definition_key}}'\n            recipients: '{{tools.recipients}}'\n      - name: create-sms-send\n        method: POST\n        path: /sms/messages\n        description: Create and initiate an SMS send.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            definitionKey: '{{tools.definition_key}}'\n            recipients: '{{tools.recipients}}'\n      - name: get-message-status\n        method: GET\n        path: /email/messages/{messageKey}\n        description: Get the status of an email message send.\n        inputParameters:\n        - name: messageKey\n          in: path\n          type: string\n         \
  \ required: true\n          description: The unique message key.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: journeys\n      path: /interaction/v1\n      description: Journey Builder operations.\n      operations:\n      - name: list-journeys\n        method: GET\n        path: /interactions\n        description: List Marketing Cloud journeys.\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number to retrieve.\n        - name: pageSize\n          in: query\n          type: integer\n          required: false\n          description: Number of journeys per page.\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Filter by status.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n      - name: get-journey\n        method: GET\n        path: /interactions/{interactionId}\n        description: Get a journey by ID.\n        inputParameters:\n        - name: interactionId\n          in: path\n          type: string\n          required: true\n          description: The journey interaction ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: fire-journey-event\n        method: POST\n        path: /events\n        description: Fire a journey entry event to enroll a contact.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            ContactKey: '{{tools.contact_key}}'\n            EventDefinitionKey: '{{tools.event_definition_key}}'\n    - name: assets\n      path: /asset/v1/content/assets\n\
  \      description: Content Builder asset operations.\n      operations:\n      - name: list-assets\n        method: GET\n        path: /\n        description: List content assets.\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number.\n        - name: pageSize\n          in: query\n          type: integer\n          required: false\n          description: Assets per page.\n        - name: assetType\n          in: query\n          type: string\n          required: false\n          description: Filter by asset type.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-asset\n        method: POST\n        path: /\n        description: Create a content asset.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            assetType: '{{tools.asset_type}}'\n      - name: get-asset\n        method: GET\n        path: /{id}\n        description: Get a content asset by ID.\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: The asset numeric ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-asset\n        method: PUT\n        path: /{id}\n        description: Update a content asset.\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: The asset numeric ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type:\
  \ json\n          data:\n            name: '{{tools.name}}'\n      - name: delete-asset\n        method: DELETE\n        path: /{id}\n        description: Delete a content asset.\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: The asset numeric ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8081\n    namespace: marketing-automation-api\n    description: Unified REST API for Salesforce marketing automation workflows.\n    resources:\n    - path: /v1/contacts\n      name: contacts\n      description: Marketing Cloud contact management.\n      operations:\n      - method: GET\n        name: list-contacts\n        description: List contacts in the Marketing Cloud account.\n        call: salesforce-mc.list-contacts\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /v1/contacts/{contactKey}\n      name: contact\n      description: Individual contact operations.\n      operations:\n      - method: GET\n        name: get-contact\n        description: Get a contact by contact key.\n        call: salesforce-mc.get-contact\n        with:\n          contactKey: rest.contactKey\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/contacts/delete\n      name: contact-deletion\n      description: Contact deletion operations.\n      operations:\n      - method: POST\n        name: delete-contacts\n        description: Delete one or more contacts.\n        call: salesforce-mc.delete-contacts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/data-extensions/{key}/rows\n      name: data-extension-rows\n      description: Data Extension row operations.\n      operations:\n      - method: GET\n        name: get-data-extension-rows\n        description: Get rows from\
  \ a Data Extension.\n        call: salesforce-mc.get-data-extension-rows\n        with:\n          key: rest.key\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: insert-data-extension-rows\n        description: Insert or upsert rows into a Data Extension.\n        call: salesforce-mc.insert-data-extension-rows\n        with:\n          key: rest.key\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/emails\n      name: email-sends\n      description: Triggered email send operations.\n      operations:\n      - method: POST\n        name: create-email-send\n        description: Create and initiate a triggered email send.\n        call: salesforce-mc.create-email-send\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/sms\n      name: sms-sends\n      description: SMS send operations.\n      operations:\n      - method: POST\n        name: create-sms-send\n\
  \        description: Create and initiate an SMS send.\n        call: salesforce-mc.create-sms-send\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/messages/{messageKey}/status\n      name: message-status\n      description: Message delivery status.\n      operations:\n      - method: GET\n        name: get-message-status\n        description: Get the delivery status of an email message.\n        call: salesforce-mc.get-message-status\n        with:\n          messageKey: rest.messageKey\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/journeys\n      name: journeys\n      description: Journey Builder journey management.\n      operations:\n      - method: GET\n        name: list-journeys\n        description: List Marketing Cloud journeys.\n        call: salesforce-mc.list-journeys\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/journeys/{interactionId}\n   \
  \   name: journey\n      description: Individual journey operations.\n      operations:\n      - method: GET\n        name: get-journey\n        description: Get a journey by ID.\n        call: salesforce-mc.get-journey\n        with:\n          interactionId: rest.interactionId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/journey-events\n      name: journey-events\n      description: Journey entry event operations.\n      operations:\n      - method: POST\n        name: fire-journey-event\n        description: Fire a journey entry event to enroll a contact.\n        call: salesforce-mc.fire-journey-event\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/assets\n      name: assets\n      description: Content Builder asset management.\n      operations:\n      - method: GET\n        name: list-assets\n        description: List content assets.\n        call: salesforce-mc.list-assets\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n      - method: POST\n        name: create-asset\n        description: Create a content asset.\n        call: salesforce-mc.create-asset\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/assets/{id}\n      name: asset\n      description: Individual asset operations.\n      operations:\n      - method: GET\n        name: get-asset\n        description: Get a content asset by ID.\n        call: salesforce-mc.get-asset\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PUT\n        name: update-asset\n        description: Update a content asset.\n        call: salesforce-mc.update-asset\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-asset\n        description: Delete a content asset.\n        call: salesforce-mc.delete-asset\n\
  \        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9091\n    namespace: marketing-automation-mcp\n    transport: http\n    description: MCP server for AI-assisted Salesforce marketing automation.\n    tools:\n    - name: list-contacts\n      description: List contacts in the Marketing Cloud account.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: salesforce-mc.list-contacts\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-contact\n      description: Get a Marketing Cloud contact by contact key.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: salesforce-mc.get-contact\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-contacts\n      description: Delete one or more contacts from Marketing Cloud.\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent:\
  \ false\n      call: salesforce-mc.delete-contacts\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-data-extension-rows\n      description: Get rows from a Marketing Cloud Data Extension.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: salesforce-mc.get-data-extension-rows\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: insert-data-extension-rows\n      description: Insert or upsert rows into a Marketing Cloud Data Extension.\n      hints:\n        readOnly: false\n        idempotent: false\n      call: salesforce-mc.insert-data-extension-rows\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-email-send\n      description: Create and initiate a triggered email send to one or more recipients.\n      hints:\n        readOnly: false\n        idempotent: false\n      call: salesforce-mc.create-email-send\n      outputParameters:\n      - type: object\n   \
  \     mapping: $.\n    - name: create-sms-send\n      description: Create and initiate an SMS send to one or more recipients.\n      hints:\n        readOnly: false\n        idempotent: false\n      call: salesforce-mc.create-sms-send\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-message-status\n      description: Get the delivery status of a triggered email send.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: salesforce-mc.get-message-status\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-journeys\n      description: List Marketing Cloud Journey Builder journeys.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: salesforce-mc.list-journeys\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-journey\n      description: Get detailed information about a Marketing Cloud journey.\n      hints:\n        readOnly: true\n      \
  \  idempotent: true\n      call: salesforce-mc.get-journey\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: fire-journey-event\n      description: Fire a journey entry event to enroll a contact in a journey.\n      hints:\n        readOnly: false\n        idempotent: false\n      call: salesforce-mc.fire-journey-event\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-assets\n      description: List Marketing Cloud Content Builder assets.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: salesforce-mc.list-assets\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-asset\n      description: Create a new content asset in Content Builder.\n      hints:\n        readOnly: false\n        idempotent: false\n      call: salesforce-mc.create-asset\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-asset\n      description: Get a Content\
  \ Builder asset by ID.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: salesforce-mc.get-asset\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-asset\n      description: Update a Content Builder asset.\n      hints:\n        readOnly: false\n        idempotent: true\n      call: salesforce-mc.update-asset\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-asset\n      description: Delete a Content Builder asset.\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: salesforce-mc.delete-asset\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/salesforce/refs/heads/main/capabilities/marketing-automation.yaml
tags:
- Salesforce
- Marketing Cloud
- Marketing Automation
- Email Marketing
- Journeys
tools:
- description: List contacts in the Marketing Cloud account.
  hints:
    idempotent: true
    readOnly: true
  name: list-contacts
- description: Get a Marketing Cloud contact by contact key.
  hints:
    idempotent: true
    readOnly: true
  name: get-contact
- description: Delete one or more contacts from Marketing Cloud.
  hints:
    destructive: true
    idempotent: false
    readOnly: false
  name: delete-contacts
- description: Get rows from a Marketing Cloud Data Extension.
  hints:
    idempotent: true
    readOnly: true
  name: get-data-extension-rows
- description: Insert or upsert rows into a Marketing Cloud Data Extension.
  hints:
    idempotent: false
    readOnly: false
  name: insert-data-extension-rows
- description: Create and initiate a triggered email send to one or more recipients.
  hints:
    idempotent: false
    readOnly: false
  name: create-email-send
- description: Create and initiate an SMS send to one or more recipients.
  hints:
    idempotent: false
    readOnly: false
  name: create-sms-send
- description: Get the delivery status of a triggered email send.
  hints:
    idempotent: true
    readOnly: true
  name: get-message-status
- description: List Marketing Cloud Journey Builder journeys.
  hints:
    idempotent: true
    readOnly: true
  name: list-journeys
- description: Get detailed information about a Marketing Cloud journey.
  hints:
    idempotent: true
    readOnly: true
  name: get-journey
- description: Fire a journey entry event to enroll a contact in a journey.
  hints:
    idempotent: false
    readOnly: false
  name: fire-journey-event
- description: List Marketing Cloud Content Builder assets.
  hints:
    idempotent: true
    readOnly: true
  name: list-assets
- description: Create a new content asset in Content Builder.
  hints:
    idempotent: false
    readOnly: false
  name: create-asset
- description: Get a Content Builder asset by ID.
  hints:
    idempotent: true
    readOnly: true
  name: get-asset
- description: Update a Content Builder asset.
  hints:
    idempotent: true
    readOnly: false
  name: update-asset
- description: Delete a Content Builder asset.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-asset
---
