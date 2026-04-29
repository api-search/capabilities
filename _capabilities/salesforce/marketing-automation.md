---
categories:
- customer-engagement
consumed_apis:
- salesforce-mc
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
- get data extension rows
- create sms send
- journey entry event operations.
- delete a content asset.
- get rows from a marketing cloud data extension.
- delete one or more contacts.
- create asset
- analytics
- create a new content asset in content builder.
- fire a journey entry event to enroll a contact in a journey.
- get a marketing cloud contact by contact key.
- list marketing cloud journey builder journeys.
- get detailed information about a marketing cloud journey.
- update a content builder asset.
- commerce
- list journeys
- fire journey event
- list marketing cloud content builder assets.
- get journey
- message delivery status.
- delete contacts
- create and initiate a triggered email send.
- insert or upsert rows into a marketing cloud data extension.
- get the delivery status of a triggered email send.
- enterprise
- get a content builder asset by id.
- get a content asset by id.
- get message status
- fire a journey entry event to enroll a contact.
- delete asset
- marketing
- cloud
- marketing cloud
- get a journey by id.
- platform
- sms send operations.
- create a content asset.
- individual journey operations.
- marketing cloud contact management.
- list contacts
- get contact
- data extension row operations.
- ai
- individual contact operations.
- customer service
- email marketing
- create and initiate an sms send to one or more recipients.
- crm
- list contacts in the marketing cloud account.
- get the delivery status of an email message.
- contact deletion operations.
- individual asset operations.
- create email send
- list assets
- create and initiate a triggered email send to one or more recipients.
- delete a content builder asset.
- salesforce
- update a content asset.
- journeys
- delete one or more contacts from marketing cloud.
- get a contact by contact key.
- sales
- journey builder journey management.
- marketing automation
- content builder asset management.
- create and initiate an sms send.
- get asset
- update asset
- insert or upsert rows into a data extension.
- insert data extension rows
- list marketing cloud journeys.
- get rows from a data extension.
- list content assets.
slug: marketing-automation
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Salesforce Marketing Automation\"\n  description: \"Unified capability for marketing automation workflows combining the Marketing Cloud REST API for contact management, journey orchestration, email and SMS messaging, data extensions, and content asset management. Used by marketing teams and marketing ops to manage campaigns and subscriber engagement.\"\n  tags:\n    - Salesforce\n    - Marketing Cloud\n    - Marketing Automation\n    - Email Marketing\n    - Journeys\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      SALESFORCE_MC_CLIENT_ID: SALESFORCE_MC_CLIENT_ID\n      SALESFORCE_MC_CLIENT_SECRET: SALESFORCE_MC_CLIENT_SECRET\n      SALESFORCE_MC_ACCESS_TOKEN: SALESFORCE_MC_ACCESS_TOKEN\n\ncapability:\n  consumes:\n    - import: salesforce-mc\n      location: ./shared/marketing-cloud.yaml\n\n  exposes:\n    - type: rest\n      port: 8081\n      namespace: marketing-automation-api\n\
  \      description: \"Unified REST API for Salesforce marketing automation workflows.\"\n      resources:\n        - path: /v1/contacts\n          name: contacts\n          description: \"Marketing Cloud contact management.\"\n          operations:\n            - method: GET\n              name: list-contacts\n              description: \"List contacts in the Marketing Cloud account.\"\n              call: \"salesforce-mc.list-contacts\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/contacts/{contactKey}\n          name: contact\n          description: \"Individual contact operations.\"\n          operations:\n            - method: GET\n              name: get-contact\n              description: \"Get a contact by contact key.\"\n              call: \"salesforce-mc.get-contact\"\n              with:\n                contactKey: \"rest.contactKey\"\n              outputParameters:\n                - type: object\n\
  \                  mapping: \"$.\"\n        - path: /v1/contacts/delete\n          name: contact-deletion\n          description: \"Contact deletion operations.\"\n          operations:\n            - method: POST\n              name: delete-contacts\n              description: \"Delete one or more contacts.\"\n              call: \"salesforce-mc.delete-contacts\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/data-extensions/{key}/rows\n          name: data-extension-rows\n          description: \"Data Extension row operations.\"\n          operations:\n            - method: GET\n              name: get-data-extension-rows\n              description: \"Get rows from a Data Extension.\"\n              call: \"salesforce-mc.get-data-extension-rows\"\n              with:\n                key: \"rest.key\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n         \
  \   - method: POST\n              name: insert-data-extension-rows\n              description: \"Insert or upsert rows into a Data Extension.\"\n              call: \"salesforce-mc.insert-data-extension-rows\"\n              with:\n                key: \"rest.key\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/emails\n          name: email-sends\n          description: \"Triggered email send operations.\"\n          operations:\n            - method: POST\n              name: create-email-send\n              description: \"Create and initiate a triggered email send.\"\n              call: \"salesforce-mc.create-email-send\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/sms\n          name: sms-sends\n          description: \"SMS send operations.\"\n          operations:\n            - method: POST\n              name: create-sms-send\n  \
  \            description: \"Create and initiate an SMS send.\"\n              call: \"salesforce-mc.create-sms-send\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/messages/{messageKey}/status\n          name: message-status\n          description: \"Message delivery status.\"\n          operations:\n            - method: GET\n              name: get-message-status\n              description: \"Get the delivery status of an email message.\"\n              call: \"salesforce-mc.get-message-status\"\n              with:\n                messageKey: \"rest.messageKey\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/journeys\n          name: journeys\n          description: \"Journey Builder journey management.\"\n          operations:\n            - method: GET\n              name: list-journeys\n              description: \"List Marketing Cloud\
  \ journeys.\"\n              call: \"salesforce-mc.list-journeys\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/journeys/{interactionId}\n          name: journey\n          description: \"Individual journey operations.\"\n          operations:\n            - method: GET\n              name: get-journey\n              description: \"Get a journey by ID.\"\n              call: \"salesforce-mc.get-journey\"\n              with:\n                interactionId: \"rest.interactionId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/journey-events\n          name: journey-events\n          description: \"Journey entry event operations.\"\n          operations:\n            - method: POST\n              name: fire-journey-event\n              description: \"Fire a journey entry event to enroll a contact.\"\n              call: \"salesforce-mc.fire-journey-event\"\
  \n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/assets\n          name: assets\n          description: \"Content Builder asset management.\"\n          operations:\n            - method: GET\n              name: list-assets\n              description: \"List content assets.\"\n              call: \"salesforce-mc.list-assets\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-asset\n              description: \"Create a content asset.\"\n              call: \"salesforce-mc.create-asset\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/assets/{id}\n          name: asset\n          description: \"Individual asset operations.\"\n          operations:\n            - method: GET\n              name: get-asset\n              description: \"Get\
  \ a content asset by ID.\"\n              call: \"salesforce-mc.get-asset\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: update-asset\n              description: \"Update a content asset.\"\n              call: \"salesforce-mc.update-asset\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-asset\n              description: \"Delete a content asset.\"\n              call: \"salesforce-mc.delete-asset\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9091\n      namespace: marketing-automation-mcp\n      transport: http\n      description:\
  \ \"MCP server for AI-assisted Salesforce marketing automation.\"\n      tools:\n        - name: list-contacts\n          description: \"List contacts in the Marketing Cloud account.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"salesforce-mc.list-contacts\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-contact\n          description: \"Get a Marketing Cloud contact by contact key.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"salesforce-mc.get-contact\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-contacts\n          description: \"Delete one or more contacts from Marketing Cloud.\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: false\n          call: \"salesforce-mc.delete-contacts\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n        - name: get-data-extension-rows\n          description: \"Get rows from a Marketing Cloud Data Extension.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"salesforce-mc.get-data-extension-rows\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: insert-data-extension-rows\n          description: \"Insert or upsert rows into a Marketing Cloud Data Extension.\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"salesforce-mc.insert-data-extension-rows\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-email-send\n          description: \"Create and initiate a triggered email send to one or more recipients.\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"salesforce-mc.create-email-send\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-sms-send\n          description: \"Create and initiate an SMS send to one or more recipients.\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"salesforce-mc.create-sms-send\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-message-status\n          description: \"Get the delivery status of a triggered email send.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"salesforce-mc.get-message-status\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-journeys\n          description: \"List Marketing Cloud Journey Builder journeys.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"salesforce-mc.list-journeys\"\n        \
  \  outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-journey\n          description: \"Get detailed information about a Marketing Cloud journey.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"salesforce-mc.get-journey\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: fire-journey-event\n          description: \"Fire a journey entry event to enroll a contact in a journey.\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"salesforce-mc.fire-journey-event\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-assets\n          description: \"List Marketing Cloud Content Builder assets.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"salesforce-mc.list-assets\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n        - name: create-asset\n          description: \"Create a new content asset in Content Builder.\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"salesforce-mc.create-asset\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-asset\n          description: \"Get a Content Builder asset by ID.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"salesforce-mc.get-asset\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-asset\n          description: \"Update a Content Builder asset.\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"salesforce-mc.update-asset\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-asset\n\
  \          description: \"Delete a Content Builder asset.\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"salesforce-mc.delete-asset\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
