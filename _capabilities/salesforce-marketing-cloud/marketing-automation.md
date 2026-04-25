---
consumed_apis:
- marketing-cloud-rest
description: Unified workflow for digital marketers to manage contacts, orchestrate customer journeys, and automate multi-channel campaigns across email, SMS, and push channels.
layout: capability
name: Salesforce Marketing Cloud Automation
operations:
- description: Create one or more contacts
  method: POST
  name: create-contacts
  path: /v1/contacts
- description: Search contacts by criteria
  method: POST
  name: search-contacts
  path: /v1/contacts/search
- description: Get a contact
  method: GET
  name: get-contact
  path: /v1/contacts/{contactKey}
- description: Update a contact
  method: PATCH
  name: update-contact
  path: /v1/contacts/{contactKey}
- description: Delete a contact
  method: DELETE
  name: delete-contact
  path: /v1/contacts/{contactKey}
- description: List all journeys
  method: GET
  name: list-journeys
  path: /v1/journeys
- description: Create a journey
  method: POST
  name: create-journey
  path: /v1/journeys
- description: Get a journey
  method: GET
  name: get-journey
  path: /v1/journeys/{id}
- description: Update a journey
  method: PUT
  name: update-journey
  path: /v1/journeys/{id}
- description: Delete a journey
  method: DELETE
  name: delete-journey
  path: /v1/journeys/{id}
- description: Publish a journey
  method: POST
  name: publish-journey
  path: /v1/journeys/{id}/publish
- description: List attribute sets
  method: GET
  name: list-attribute-sets
  path: /v1/attribute-sets
personas: []
provider_name: Salesforce Marketing Cloud
provider_slug: salesforce-marketing-cloud
search_terms:
- update a contact
- get contact
- email marketing
- get a contact
- journey management
- create journey
- retrieve a contact by contact key
- search contacts by criteria
- delete a journey
- create a journey
- customer journey
- search for contacts using filter criteria
- publish a journey
- publish journey
- contact search
- get a journey
- journey publishing
- single contact operations
- delete a contact from marketing cloud
- automation
- list journeys
- list all contact attribute set definitions
- salesforce
- digital marketing
- list customer journeys with filtering and pagination
- create a new customer journey
- single journey operations
- list attribute sets
- get journey
- list all journeys
- attribute set definitions
- update contact
- create one or more contacts
- delete a contact
- retrieve a journey by id
- search contacts
- delete contact
- delete journey
- update an existing journey specification
- contact management
- update an existing contact's attributes
- marketing automation
- email
- publish a journey to activate customer entry
- create one or more contacts in marketing cloud
- marketing
- update a journey
- create contacts
- update journey
- personalization
slug: marketing-automation
tags:
- Salesforce
- Marketing Automation
- Customer Journey
- Email Marketing
tools:
- description: Create one or more contacts in Marketing Cloud
  hints:
    readOnly: false
  name: create-contacts
- description: Search for contacts using filter criteria
  hints:
    idempotent: true
    readOnly: true
  name: search-contacts
- description: Retrieve a contact by contact key
  hints:
    readOnly: true
  name: get-contact
- description: Update an existing contact's attributes
  hints:
    idempotent: true
    readOnly: false
  name: update-contact
- description: Delete a contact from Marketing Cloud
  hints:
    destructive: true
  name: delete-contact
- description: List all contact attribute set definitions
  hints:
    readOnly: true
  name: list-attribute-sets
- description: List customer journeys with filtering and pagination
  hints:
    readOnly: true
  name: list-journeys
- description: Create a new customer journey
  hints:
    readOnly: false
  name: create-journey
- description: Retrieve a journey by ID
  hints:
    readOnly: true
  name: get-journey
- description: Update an existing journey specification
  hints:
    idempotent: true
    readOnly: false
  name: update-journey
- description: Delete a journey
  hints:
    destructive: true
  name: delete-journey
- description: Publish a journey to activate customer entry
  hints:
    readOnly: false
  name: publish-journey
---
