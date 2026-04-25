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
- list journeys
- update a journey
- list all contact attribute set definitions
- email
- automation
- contact management
- publish a journey
- create a new customer journey
- personalization
- get a journey
- list attribute sets
- search contacts by criteria
- email marketing
- get a contact
- delete contact
- create one or more contacts in marketing cloud
- update an existing journey specification
- delete journey
- search for contacts using filter criteria
- search contacts
- contact search
- create contacts
- create one or more contacts
- marketing
- publish journey
- salesforce
- get journey
- attribute set definitions
- update an existing contact's attributes
- update contact
- update journey
- delete a journey
- retrieve a journey by id
- single contact operations
- journey publishing
- single journey operations
- create journey
- list all journeys
- digital marketing
- publish a journey to activate customer entry
- create a journey
- get contact
- customer journey
- marketing automation
- update a contact
- delete a contact from marketing cloud
- list customer journeys with filtering and pagination
- delete a contact
- journey management
- retrieve a contact by contact key
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
