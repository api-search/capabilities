---
categories: []
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
- list catalog items
- list trouble tickets
- add a catalog item to the shopping cart.
- service catalog browsing.
- get catalog item
- remove all items from the shopping cart.
- workflow automation
- create a csm contact.
- get contact
- it service management
- create trouble ticket
- list service catalogs.
- processes
- retrieve a specific service catalog.
- list csm contacts.
- retrieve catalog item details with variables.
- servicenow
- itsm
- empty the cart.
- contacts
- get cart contents.
- add item to cart
- list available service catalogs.
- cloud services
- customer service
- submit cart as a service catalog request.
- retrieve a specific csm contact.
- get catalog item details.
- list contacts
- create a trouble ticket.
- get trouble ticket
- retrieve a specific trouble ticket.
- update trouble ticket
- trouble ticket operations.
- self service
- catalog item browsing.
- workflows
- automation
- get catalog
- empty cart
- shopping cart.
- get cart
- submit cart order
- retrieve a catalog category with subcategories.
- create a new csm contact.
- get a specific contact.
- list trouble tickets.
- order a catalog item immediately.
- create contact
- single contact operations.
- service catalog
- single catalog item.
- list catalogs
- order item now
- digital workflows
- csm contact management.
- update an existing trouble ticket.
- list catalog items with optional filtering.
- get category
- retrieve shopping cart contents.
- enterprise platform
- list csm contacts with optional filtering.
- t1
- list catalog items.
slug: customer-service
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"ServiceNow Customer Service\"\n  description: \"Unified workflow for customer service operations combining contact management, service catalog browsing and ordering, and trouble ticket handling. Used by customer service agents and self-service portal integrations.\"\n  tags:\n    - ServiceNow\n    - Customer Service\n    - Service Catalog\n    - Contacts\n    - Self Service\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      SERVICENOW_USERNAME: SERVICENOW_USERNAME\n      SERVICENOW_PASSWORD: SERVICENOW_PASSWORD\n      SERVICENOW_INSTANCE: SERVICENOW_INSTANCE\n\ncapability:\n  consumes:\n    - import: servicenow-contact\n      location: ./shared/contact.yaml\n    - import: servicenow-service-catalog\n      location: ./shared/service-catalog.yaml\n    - import: servicenow-trouble-ticket\n      location: ./shared/trouble-ticket.yaml\n\n  exposes:\n    - type: rest\n      port: 8081\n\
  \      namespace: servicenow-customer-service-api\n      description: \"Unified REST API for ServiceNow customer service operations.\"\n      resources:\n        - path: /v1/contacts\n          name: contacts\n          description: \"CSM contact management.\"\n          operations:\n            - method: GET\n              name: list-contacts\n              description: \"List CSM contacts.\"\n              call: \"servicenow-contact.list-contacts\"\n              with:\n                sysparm_query: \"rest.sysparm_query\"\n                sysparm_limit: \"rest.sysparm_limit\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.result\"\n            - method: POST\n              name: create-contact\n              description: \"Create a CSM contact.\"\n              call: \"servicenow-contact.create-contact\"\n              with:\n                first_name: \"rest.first_name\"\n                last_name: \"rest.last_name\"\n            \
  \    email: \"rest.email\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.result\"\n        - path: /v1/contacts/{id}\n          name: contact-detail\n          description: \"Single contact operations.\"\n          operations:\n            - method: GET\n              name: get-contact\n              description: \"Get a specific contact.\"\n              call: \"servicenow-contact.get-contact\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.result\"\n        - path: /v1/catalogs\n          name: catalogs\n          description: \"Service catalog browsing.\"\n          operations:\n            - method: GET\n              name: list-catalogs\n              description: \"List service catalogs.\"\n              call: \"servicenow-service-catalog.list-catalogs\"\n              with:\n                sysparm_limit: \"rest.sysparm_limit\"\
  \n              outputParameters:\n                - type: object\n                  mapping: \"$.result\"\n        - path: /v1/catalog-items\n          name: catalog-items\n          description: \"Catalog item browsing.\"\n          operations:\n            - method: GET\n              name: list-catalog-items\n              description: \"List catalog items.\"\n              call: \"servicenow-service-catalog.list-catalog-items\"\n              with:\n                sysparm_catalog: \"rest.sysparm_catalog\"\n                sysparm_category: \"rest.sysparm_category\"\n                sysparm_limit: \"rest.sysparm_limit\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.result\"\n        - path: /v1/catalog-items/{sys_id}\n          name: catalog-item-detail\n          description: \"Single catalog item.\"\n          operations:\n            - method: GET\n              name: get-catalog-item\n              description: \"Get catalog item\
  \ details.\"\n              call: \"servicenow-service-catalog.get-catalog-item\"\n              with:\n                sys_id: \"rest.sys_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.result\"\n        - path: /v1/cart\n          name: cart\n          description: \"Shopping cart.\"\n          operations:\n            - method: GET\n              name: get-cart\n              description: \"Get cart contents.\"\n              call: \"servicenow-service-catalog.get-cart\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.result\"\n            - method: DELETE\n              name: empty-cart\n              description: \"Empty the cart.\"\n              call: \"servicenow-service-catalog.empty-cart\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.result\"\n        - path: /v1/trouble-tickets\n          name: trouble-tickets\n          description:\
  \ \"Trouble ticket operations.\"\n          operations:\n            - method: GET\n              name: list-trouble-tickets\n              description: \"List trouble tickets.\"\n              call: \"servicenow-trouble-ticket.list-trouble-tickets\"\n              with:\n                limit: \"rest.limit\"\n                severity: \"rest.severity\"\n                status: \"rest.status\"\n                ticketType: \"rest.ticketType\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-trouble-ticket\n              description: \"Create a trouble ticket.\"\n              call: \"servicenow-trouble-ticket.create-trouble-ticket\"\n              with:\n                name: \"rest.name\"\n                description: \"rest.description\"\n                severity: \"rest.severity\"\n                status: \"rest.status\"\n                ticketType: \"rest.ticketType\"\n       \
  \       outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9091\n      namespace: servicenow-customer-service-mcp\n      transport: http\n      description: \"MCP server for AI-assisted ServiceNow customer service workflows.\"\n      tools:\n        - name: list-contacts\n          description: \"List CSM contacts with optional filtering.\"\n          hints:\n            readOnly: true\n            idempotent: true\n            openWorld: true\n          call: \"servicenow-contact.list-contacts\"\n          with:\n            sysparm_query: \"tools.sysparm_query\"\n            sysparm_limit: \"tools.sysparm_limit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.result\"\n        - name: create-contact\n          description: \"Create a new CSM contact.\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"servicenow-contact.create-contact\"\
  \n          with:\n            first_name: \"tools.first_name\"\n            last_name: \"tools.last_name\"\n            email: \"tools.email\"\n            phone: \"tools.phone\"\n          outputParameters:\n            - type: object\n              mapping: \"$.result\"\n        - name: get-contact\n          description: \"Retrieve a specific CSM contact.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"servicenow-contact.get-contact\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.result\"\n        - name: list-catalogs\n          description: \"List available service catalogs.\"\n          hints:\n            readOnly: true\n            idempotent: true\n            openWorld: true\n          call: \"servicenow-service-catalog.list-catalogs\"\n          with:\n            sysparm_limit: \"tools.sysparm_limit\"\n          outputParameters:\n        \
  \    - type: object\n              mapping: \"$.result\"\n        - name: get-catalog\n          description: \"Retrieve a specific service catalog.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"servicenow-service-catalog.get-catalog\"\n          with:\n            sys_id: \"tools.sys_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.result\"\n        - name: get-category\n          description: \"Retrieve a catalog category with subcategories.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"servicenow-service-catalog.get-category\"\n          with:\n            sys_id: \"tools.sys_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.result\"\n        - name: list-catalog-items\n          description: \"List catalog items with optional filtering.\"\n          hints:\n            readOnly: true\n            idempotent:\
  \ true\n            openWorld: true\n          call: \"servicenow-service-catalog.list-catalog-items\"\n          with:\n            sysparm_catalog: \"tools.sysparm_catalog\"\n            sysparm_category: \"tools.sysparm_category\"\n            sysparm_limit: \"tools.sysparm_limit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.result\"\n        - name: get-catalog-item\n          description: \"Retrieve catalog item details with variables.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"servicenow-service-catalog.get-catalog-item\"\n          with:\n            sys_id: \"tools.sys_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.result\"\n        - name: add-item-to-cart\n          description: \"Add a catalog item to the shopping cart.\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"servicenow-service-catalog.add-item-to-cart\"\
  \n          with:\n            sys_id: \"tools.sys_id\"\n            quantity: \"tools.quantity\"\n            variables: \"tools.variables\"\n          outputParameters:\n            - type: object\n              mapping: \"$.result\"\n        - name: order-item-now\n          description: \"Order a catalog item immediately.\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"servicenow-service-catalog.order-item-now\"\n          with:\n            sys_id: \"tools.sys_id\"\n            quantity: \"tools.quantity\"\n            variables: \"tools.variables\"\n          outputParameters:\n            - type: object\n              mapping: \"$.result\"\n        - name: get-cart\n          description: \"Retrieve shopping cart contents.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"servicenow-service-catalog.get-cart\"\n          outputParameters:\n            - type: object\n              mapping:\
  \ \"$.result\"\n        - name: empty-cart\n          description: \"Remove all items from the shopping cart.\"\n          hints:\n            destructive: true\n            idempotent: true\n          call: \"servicenow-service-catalog.empty-cart\"\n          outputParameters:\n            - type: object\n              mapping: \"$.result\"\n        - name: submit-cart-order\n          description: \"Submit cart as a service catalog request.\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"servicenow-service-catalog.submit-cart-order\"\n          outputParameters:\n            - type: object\n              mapping: \"$.result\"\n        - name: list-trouble-tickets\n          description: \"List trouble tickets.\"\n          hints:\n            readOnly: true\n            idempotent: true\n            openWorld: true\n          call: \"servicenow-trouble-ticket.list-trouble-tickets\"\n          with:\n            limit: \"tools.limit\"\
  \n            severity: \"tools.severity\"\n            status: \"tools.status\"\n            ticketType: \"tools.ticketType\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-trouble-ticket\n          description: \"Create a trouble ticket.\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"servicenow-trouble-ticket.create-trouble-ticket\"\n          with:\n            name: \"tools.name\"\n            description: \"tools.description\"\n            severity: \"tools.severity\"\n            status: \"tools.status\"\n            ticketType: \"tools.ticketType\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-trouble-ticket\n          description: \"Retrieve a specific trouble ticket.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"servicenow-trouble-ticket.get-trouble-ticket\"\
  \n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-trouble-ticket\n          description: \"Update an existing trouble ticket.\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"servicenow-trouble-ticket.update-trouble-ticket\"\n          with:\n            id: \"tools.id\"\n            name: \"tools.name\"\n            severity: \"tools.severity\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/servicenow/refs/heads/main/capabilities/customer-service.yaml
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
