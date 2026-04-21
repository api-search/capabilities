---
consumed_apis:
- servicenow-contact
- servicenow-service-catalog
- servicenow-trouble-ticket
description: Unified workflow for customer service operations combining contact management, service catalog browsing and ordering, and trouble ticket handling. Used by customer service agents and self-service portal integrations.
layout: capability
name: ServiceNow Customer Service
operations:
- description: List CSM contacts.
  method: GET
  name: list-contacts
  path: /v1/contacts
- description: Create a CSM contact.
  method: POST
  name: create-contact
  path: /v1/contacts
- description: Get a specific contact.
  method: GET
  name: get-contact
  path: /v1/contacts/{id}
- description: List service catalogs.
  method: GET
  name: list-catalogs
  path: /v1/catalogs
- description: List catalog items.
  method: GET
  name: list-catalog-items
  path: /v1/catalog-items
- description: Get catalog item details.
  method: GET
  name: get-catalog-item
  path: /v1/catalog-items/{sys_id}
- description: Get cart contents.
  method: GET
  name: get-cart
  path: /v1/cart
- description: Empty the cart.
  method: DELETE
  name: empty-cart
  path: /v1/cart
- description: List trouble tickets.
  method: GET
  name: list-trouble-tickets
  path: /v1/trouble-tickets
- description: Create a trouble ticket.
  method: POST
  name: create-trouble-ticket
  path: /v1/trouble-tickets
personas: []
provider_name: ServiceNow
provider_slug: servicenow
search_terms:
- get category
- catalog item browsing.
- create a csm contact.
- list contacts
- single contact operations.
- create trouble ticket
- list catalog items.
- get cart contents.
- create a trouble ticket.
- list service catalogs.
- remove all items from the shopping cart.
- submit cart order
- servicenow
- list trouble tickets.
- it service management
- retrieve a specific csm contact.
- get catalog item
- shopping cart.
- trouble ticket operations.
- list catalog items with optional filtering.
- enterprise platform
- service catalog
- service catalog browsing.
- empty cart
- list trouble tickets
- single catalog item.
- get cart
- create a new csm contact.
- csm contact management.
- get a specific contact.
- list csm contacts.
- itsm
- order a catalog item immediately.
- workflows
- t1
- list available service catalogs.
- add item to cart
- list catalog items
- get catalog item details.
- retrieve shopping cart contents.
- add a catalog item to the shopping cart.
- get trouble ticket
- update trouble ticket
- get catalog
- digital workflows
- self service
- customer service
- create contact
- retrieve a specific trouble ticket.
- processes
- empty the cart.
- list catalogs
- get contact
- retrieve a catalog category with subcategories.
- retrieve catalog item details with variables.
- automation
- contacts
- list csm contacts with optional filtering.
- workflow automation
- retrieve a specific service catalog.
- submit cart as a service catalog request.
- update an existing trouble ticket.
- order item now
- cloud services
slug: customer-service
tags:
- ServiceNow
- Customer Service
- Service Catalog
- Contacts
- Self Service
tools:
- description: List CSM contacts with optional filtering.
  hints:
    idempotent: true
    openWorld: true
    readOnly: true
  name: list-contacts
- description: Create a new CSM contact.
  hints:
    idempotent: false
    readOnly: false
  name: create-contact
- description: Retrieve a specific CSM contact.
  hints:
    idempotent: true
    readOnly: true
  name: get-contact
- description: List available service catalogs.
  hints:
    idempotent: true
    openWorld: true
    readOnly: true
  name: list-catalogs
- description: Retrieve a specific service catalog.
  hints:
    idempotent: true
    readOnly: true
  name: get-catalog
- description: Retrieve a catalog category with subcategories.
  hints:
    idempotent: true
    readOnly: true
  name: get-category
- description: List catalog items with optional filtering.
  hints:
    idempotent: true
    openWorld: true
    readOnly: true
  name: list-catalog-items
- description: Retrieve catalog item details with variables.
  hints:
    idempotent: true
    readOnly: true
  name: get-catalog-item
- description: Add a catalog item to the shopping cart.
  hints:
    idempotent: false
    readOnly: false
  name: add-item-to-cart
- description: Order a catalog item immediately.
  hints:
    idempotent: false
    readOnly: false
  name: order-item-now
- description: Retrieve shopping cart contents.
  hints:
    idempotent: true
    readOnly: true
  name: get-cart
- description: Remove all items from the shopping cart.
  hints:
    destructive: true
    idempotent: true
  name: empty-cart
- description: Submit cart as a service catalog request.
  hints:
    idempotent: false
    readOnly: false
  name: submit-cart-order
- description: List trouble tickets.
  hints:
    idempotent: true
    openWorld: true
    readOnly: true
  name: list-trouble-tickets
- description: Create a trouble ticket.
  hints:
    idempotent: false
    readOnly: false
  name: create-trouble-ticket
- description: Retrieve a specific trouble ticket.
  hints:
    idempotent: true
    readOnly: true
  name: get-trouble-ticket
- description: Update an existing trouble ticket.
  hints:
    idempotent: true
    readOnly: false
  name: update-trouble-ticket
---
