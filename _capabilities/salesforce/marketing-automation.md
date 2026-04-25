---
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
- list journeys
- get a content builder asset by id.
- individual contact operations.
- journey entry event operations.
- insert or upsert rows into a marketing cloud data extension.
- create and initiate an sms send to one or more recipients.
- enterprise
- data extension row operations.
- list marketing cloud journeys.
- create a content asset.
- sales
- customer service
- marketing cloud
- cloud
- delete a content builder asset.
- list assets
- ai
- update asset
- create asset
- journeys
- email marketing
- insert data extension rows
- get a content asset by id.
- get rows from a marketing cloud data extension.
- list marketing cloud journey builder journeys.
- insert or upsert rows into a data extension.
- individual journey operations.
- update a content builder asset.
- update a content asset.
- message delivery status.
- list content assets.
- individual asset operations.
- fire journey event
- get a marketing cloud contact by contact key.
- marketing cloud contact management.
- get asset
- get the delivery status of a triggered email send.
- list marketing cloud content builder assets.
- delete one or more contacts.
- marketing
- platform
- salesforce
- contact deletion operations.
- get journey
- delete one or more contacts from marketing cloud.
- create a new content asset in content builder.
- get detailed information about a marketing cloud journey.
- journey builder journey management.
- get message status
- list contacts
- fire a journey entry event to enroll a contact in a journey.
- create and initiate a triggered email send.
- list contacts in the marketing cloud account.
- create email send
- sms send operations.
- commerce
- content builder asset management.
- crm
- get a contact by contact key.
- get a journey by id.
- delete asset
- analytics
- get contact
- create and initiate an sms send.
- marketing automation
- create sms send
- create and initiate a triggered email send to one or more recipients.
- get the delivery status of an email message.
- delete a content asset.
- get data extension rows
- fire a journey entry event to enroll a contact.
- triggered email send operations.
- delete contacts
- get rows from a data extension.
slug: marketing-automation
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
