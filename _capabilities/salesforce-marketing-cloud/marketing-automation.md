---
categories: []
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
- email
- list all contact attribute set definitions
- get journey
- automation
- single journey operations
- create a journey
- create contacts
- list attribute sets
- delete journey
- search contacts by criteria
- email marketing
- list journeys
- delete a contact
- retrieve a contact by contact key
- list customer journeys with filtering and pagination
- delete a contact from marketing cloud
- get a journey
- contact search
- customer journey
- update an existing journey specification
- marketing automation
- search contacts
- update a contact
- update contact
- single contact operations
- get a contact
- journey management
- delete a journey
- marketing
- update journey
- create a new customer journey
- list all journeys
- contact management
- create one or more contacts
- update an existing contact's attributes
- retrieve a journey by id
- create one or more contacts in marketing cloud
- digital marketing
- publish journey
- publish a journey
- delete contact
- create journey
- get contact
- update a journey
- personalization
- salesforce
- search for contacts using filter criteria
- publish a journey to activate customer entry
- attribute set definitions
- journey publishing
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
