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
- delete a content asset.
- get rows from a data extension.
- get journey
- get a content builder asset by id.
- sms send operations.
- insert or upsert rows into a marketing cloud data extension.
- get asset
- create asset
- delete a content builder asset.
- individual contact operations.
- list contacts in the marketing cloud account.
- fire a journey entry event to enroll a contact.
- triggered email send operations.
- create and initiate a triggered email send.
- get the delivery status of an email message.
- individual asset operations.
- email marketing
- list journeys
- get data extension rows
- fire journey event
- get a marketing cloud contact by contact key.
- analytics
- platform
- marketing cloud
- get rows from a marketing cloud data extension.
- marketing automation
- delete one or more contacts from marketing cloud.
- cloud
- data extension row operations.
- journey builder journey management.
- enterprise
- list assets
- commerce
- marketing
- fire a journey entry event to enroll a contact in a journey.
- delete one or more contacts.
- insert or upsert rows into a data extension.
- list marketing cloud content builder assets.
- create and initiate a triggered email send to one or more recipients.
- marketing cloud contact management.
- get message status
- update a content builder asset.
- delete contacts
- ai
- create email send
- get a content asset by id.
- contact deletion operations.
- journey entry event operations.
- get detailed information about a marketing cloud journey.
- create a new content asset in content builder.
- get a contact by contact key.
- update asset
- list content assets.
- journeys
- list marketing cloud journeys.
- get the delivery status of a triggered email send.
- get a journey by id.
- content builder asset management.
- create a content asset.
- get contact
- sales
- salesforce
- insert data extension rows
- crm
- individual journey operations.
- update a content asset.
- create and initiate an sms send.
- delete asset
- list contacts
- list marketing cloud journey builder journeys.
- message delivery status.
- customer service
- create sms send
- create and initiate an sms send to one or more recipients.
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
