---
categories:
- crm-sales
consumed_apis:
- dataverse-web-api
description: Unified data platform capability combining Dataverse account, contact, and entity management with OData query support. Used by Power Platform developers and CRM integration teams.
layout: capability
name: Microsoft Power Apps Data Platform
operations:
- description: List accounts
  method: GET
  name: list-accounts
  path: /v1/accounts
- description: Create an account
  method: POST
  name: create-account
  path: /v1/accounts
personas: []
provider_name: Microsoft Power Apps
provider_slug: microsoft-power-apps
search_terms:
- retrieve entity definitions
- update account
- data platform
- list accounts
- power platform
- retrieve multiple accounts
- create a new contact
- retrieve a single account
- low-code
- account management
- microsoft
- update a contact
- business applications
- update an account
- enterprise
- delete an account
- no-code
- power apps
- create an account
- get account
- list entities
- list contacts
- create contact
- retrieve a single entity definition
- create a new account
- create account
- dataverse
- update contact
- get contact
- delete contact
- delete account
- cloud
- delete a contact
- retrieve multiple contacts
- get entity
- saas
- retrieve a single contact
slug: data-platform
tags:
- Microsoft
- Power Apps
- Dataverse
- Data Platform
tools:
- description: Retrieve multiple accounts
  hints:
    openWorld: true
    readOnly: true
  name: list-accounts
- description: Retrieve a single account
  hints:
    readOnly: true
  name: get-account
- description: Create a new account
  hints: {}
  name: create-account
- description: Update an account
  hints: {}
  name: update-account
- description: Delete an account
  hints:
    destructive: true
  name: delete-account
- description: Retrieve multiple contacts
  hints:
    openWorld: true
    readOnly: true
  name: list-contacts
- description: Retrieve a single contact
  hints:
    readOnly: true
  name: get-contact
- description: Create a new contact
  hints: {}
  name: create-contact
- description: Update a contact
  hints: {}
  name: update-contact
- description: Delete a contact
  hints:
    destructive: true
  name: delete-contact
- description: Retrieve entity definitions
  hints:
    readOnly: true
  name: list-entities
- description: Retrieve a single entity definition
  hints:
    readOnly: true
  name: get-entity
---
