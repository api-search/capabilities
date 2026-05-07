---
categories: []
consumed_apis: []
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
- submit cart order
- create a trouble ticket.
- create trouble ticket
- empty the cart.
- get contact
- self service
- service catalog browsing.
- automation
- workflow automation
- catalog item browsing.
- get cart
- retrieve a specific service catalog.
- list catalog items.
- retrieve a specific trouble ticket.
- create contact
- list trouble tickets
- list catalog items with optional filtering.
- add a catalog item to the shopping cart.
- retrieve shopping cart contents.
- list catalog items
- list csm contacts with optional filtering.
- list catalogs
- enterprise platform
- submit cart as a service catalog request.
- get a specific contact.
- get trouble ticket
- order a catalog item immediately.
- contacts
- it service management
- order item now
- t1
- list service catalogs.
- single catalog item.
- update trouble ticket
- list csm contacts.
- list contacts
- digital workflows
- create a new csm contact.
- get category
- create a csm contact.
- get cart contents.
- update an existing trouble ticket.
- cloud services
- servicenow
- add item to cart
- get catalog item
- list trouble tickets.
- service catalog
- empty cart
- trouble ticket operations.
- list available service catalogs.
- itsm
- csm contact management.
- get catalog item details.
- workflows
- customer service
- single contact operations.
- processes
- remove all items from the shopping cart.
- shopping cart.
- get catalog
- retrieve a specific csm contact.
- retrieve a catalog category with subcategories.
- retrieve catalog item details with variables.
slug: customer-service
source_filename: customer-service.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: ServiceNow Customer Service\n  description: Unified workflow for customer service operations combining contact management, service catalog browsing and\n    ordering, and trouble ticket handling. Used by customer service agents and self-service portal integrations.\n  tags:\n  - ServiceNow\n  - Customer Service\n  - Service Catalog\n  - Contacts\n  - Self Service\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SERVICENOW_USERNAME: SERVICENOW_USERNAME\n    SERVICENOW_PASSWORD: SERVICENOW_PASSWORD\n    SERVICENOW_INSTANCE: SERVICENOW_INSTANCE\ncapability:\n  consumes:\n  - type: http\n    namespace: servicenow-contact\n    baseUri: https://{{SERVICENOW_INSTANCE}}.servicenow.com/api/now\n    description: ServiceNow Contact API for managing CSM contacts.\n    authentication:\n      type: basic\n      username: '{{SERVICENOW_USERNAME}}'\n      password: '{{SERVICENOW_PASSWORD}}'\n    resources:\n \
  \   - name: contacts\n      path: /contact\n      description: CSM contact operations.\n      operations:\n      - name: list-contacts\n        method: GET\n        description: Retrieve a list of CSM contacts.\n        inputParameters:\n        - name: sysparm_query\n          in: query\n          type: string\n          required: false\n          description: Encoded query to filter contacts.\n        - name: sysparm_limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of records to return.\n        - name: sysparm_offset\n          in: query\n          type: integer\n          required: false\n          description: Starting record index for pagination.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.result\n      - name: create-contact\n        method: POST\n        description: Create a new CSM contact.\n        body:\n          type: json\n\
  \          data:\n            first_name: '{{tools.first_name}}'\n            last_name: '{{tools.last_name}}'\n            email: '{{tools.email}}'\n            phone: '{{tools.phone}}'\n            company: '{{tools.company}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.result\n      - name: get-contact\n        method: GET\n        path: /{id}\n        description: Retrieve a specific contact by sys_id.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The sys_id of the contact.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.result\n  - type: http\n    namespace: servicenow-service-catalog\n    baseUri: https://{{SERVICENOW_INSTANCE}}.service-now.com/api/sn_sc\n    description: ServiceNow Service Catalog API for browsing and ordering catalog\
  \ items.\n    authentication:\n      type: basic\n      username: '{{SERVICENOW_USERNAME}}'\n      password: '{{SERVICENOW_PASSWORD}}'\n    resources:\n    - name: catalogs\n      path: /servicecatalog/catalogs\n      description: Service catalog operations.\n      operations:\n      - name: list-catalogs\n        method: GET\n        description: List all available service catalogs.\n        inputParameters:\n        - name: sysparm_limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of catalogs to return.\n        - name: sysparm_offset\n          in: query\n          type: integer\n          required: false\n          description: Starting index for pagination.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.result\n      - name: get-catalog\n        method: GET\n        path: /{sys_id}\n        description: Retrieve a specific service catalog.\n\
  \        inputParameters:\n        - name: sys_id\n          in: path\n          type: string\n          required: true\n          description: The unique identifier for the catalog.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.result\n    - name: categories\n      path: /servicecatalog/categories\n      description: Catalog category operations.\n      operations:\n      - name: get-category\n        method: GET\n        path: /{sys_id}\n        description: Retrieve a catalog category with child categories.\n        inputParameters:\n        - name: sys_id\n          in: path\n          type: string\n          required: true\n          description: The unique identifier for the category.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.result\n    - name: catalog-items\n      path: /servicecatalog/items\n      description: Catalog\
  \ item operations.\n      operations:\n      - name: list-catalog-items\n        method: GET\n        description: List catalog items with optional filtering.\n        inputParameters:\n        - name: sysparm_catalog\n          in: query\n          type: string\n          required: false\n          description: Filter by catalog sys_id.\n        - name: sysparm_category\n          in: query\n          type: string\n          required: false\n          description: Filter by category sys_id.\n        - name: sysparm_limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of items to return.\n        - name: sysparm_offset\n          in: query\n          type: integer\n          required: false\n          description: Starting index for pagination.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.result\n      - name: get-catalog-item\n        method:\
  \ GET\n        path: /{sys_id}\n        description: Retrieve a catalog item with variables and pricing.\n        inputParameters:\n        - name: sys_id\n          in: path\n          type: string\n          required: true\n          description: The unique identifier for the catalog item.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.result\n      - name: add-item-to-cart\n        method: POST\n        path: /{sys_id}/add_to_cart\n        description: Add a catalog item to the shopping cart.\n        inputParameters:\n        - name: sys_id\n          in: path\n          type: string\n          required: true\n          description: The catalog item sys_id.\n        body:\n          type: json\n          data:\n            sysparm_quantity: '{{tools.quantity}}'\n            variables: '{{tools.variables}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.result\n      - name: order-item-now\n        method: POST\n        path: /{sys_id}/order_now\n        description: Order a catalog item immediately without using the cart.\n        inputParameters:\n        - name: sys_id\n          in: path\n          type: string\n          required: true\n          description: The catalog item sys_id.\n        body:\n          type: json\n          data:\n            sysparm_quantity: '{{tools.quantity}}'\n            variables: '{{tools.variables}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.result\n    - name: cart\n      path: /servicecatalog/cart\n      description: Shopping cart operations.\n      operations:\n      - name: get-cart\n        method: GET\n        description: Retrieve the current user's shopping cart.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n         \
  \ value: $.result\n      - name: empty-cart\n        method: DELETE\n        description: Remove all items from the shopping cart.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.result\n      - name: submit-cart-order\n        method: POST\n        path: /submit_order\n        description: Submit all cart items as a service catalog request.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.result\n  - type: http\n    namespace: servicenow-trouble-ticket\n    baseUri: https://{{SERVICENOW_INSTANCE}}.servicenow.com/api/sn_ind_tsm_sdwan/ticket\n    description: ServiceNow Trouble Ticket Open API (TMF621) for managing tickets across Cases, Incidents, and Service Problem\n      Cases.\n    authentication:\n      type: basic\n      username: '{{SERVICENOW_USERNAME}}'\n      password: '{{SERVICENOW_PASSWORD}}'\n    resources:\n    - name: trouble-tickets\n\
  \      path: /troubleTicket\n      description: Trouble ticket operations.\n      operations:\n      - name: list-trouble-tickets\n        method: GET\n        description: Retrieve all trouble tickets.\n        inputParameters:\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Comma-separated list of fields to return.\n        - name: id\n          in: query\n          type: string\n          required: false\n          description: Filter by sys_id.\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum records to return.\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Starting index for pagination.\n        - name: severity\n          in: query\n          type: string\n          required: false\n          description: Filter by severity.\n        - name: status\n        \
  \  in: query\n          type: string\n          required: false\n          description: Filter by status.\n        - name: ticketType\n          in: query\n          type: string\n          required: false\n          description: Filter by ticket type (Case, Incident, Service Problem Case).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-trouble-ticket\n        method: POST\n        description: Create a trouble ticket.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            description: '{{tools.description}}'\n            severity: '{{tools.severity}}'\n            status: '{{tools.status}}'\n            ticketType: '{{tools.ticketType}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-trouble-ticket\n        method: GET\n        path: /{id}\n\
  \        description: Retrieve a specific trouble ticket.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The sys_id of the trouble ticket.\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Fields to return.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-trouble-ticket\n        method: PATCH\n        path: /{id}\n        description: Update a trouble ticket.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The sys_id of the trouble ticket.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            description: '{{tools.description}}'\n            severity: '{{tools.severity}}'\n            status:\
  \ '{{tools.status}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8081\n    namespace: servicenow-customer-service-api\n    description: Unified REST API for ServiceNow customer service operations.\n    resources:\n    - path: /v1/contacts\n      name: contacts\n      description: CSM contact management.\n      operations:\n      - method: GET\n        name: list-contacts\n        description: List CSM contacts.\n        call: servicenow-contact.list-contacts\n        with:\n          sysparm_query: rest.sysparm_query\n          sysparm_limit: rest.sysparm_limit\n        outputParameters:\n        - type: object\n          mapping: $.result\n      - method: POST\n        name: create-contact\n        description: Create a CSM contact.\n        call: servicenow-contact.create-contact\n        with:\n          first_name: rest.first_name\n          last_name: rest.last_name\n\
  \          email: rest.email\n        outputParameters:\n        - type: object\n          mapping: $.result\n    - path: /v1/contacts/{id}\n      name: contact-detail\n      description: Single contact operations.\n      operations:\n      - method: GET\n        name: get-contact\n        description: Get a specific contact.\n        call: servicenow-contact.get-contact\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.result\n    - path: /v1/catalogs\n      name: catalogs\n      description: Service catalog browsing.\n      operations:\n      - method: GET\n        name: list-catalogs\n        description: List service catalogs.\n        call: servicenow-service-catalog.list-catalogs\n        with:\n          sysparm_limit: rest.sysparm_limit\n        outputParameters:\n        - type: object\n          mapping: $.result\n    - path: /v1/catalog-items\n      name: catalog-items\n      description: Catalog item browsing.\n \
  \     operations:\n      - method: GET\n        name: list-catalog-items\n        description: List catalog items.\n        call: servicenow-service-catalog.list-catalog-items\n        with:\n          sysparm_catalog: rest.sysparm_catalog\n          sysparm_category: rest.sysparm_category\n          sysparm_limit: rest.sysparm_limit\n        outputParameters:\n        - type: object\n          mapping: $.result\n    - path: /v1/catalog-items/{sys_id}\n      name: catalog-item-detail\n      description: Single catalog item.\n      operations:\n      - method: GET\n        name: get-catalog-item\n        description: Get catalog item details.\n        call: servicenow-service-catalog.get-catalog-item\n        with:\n          sys_id: rest.sys_id\n        outputParameters:\n        - type: object\n          mapping: $.result\n    - path: /v1/cart\n      name: cart\n      description: Shopping cart.\n      operations:\n      - method: GET\n        name: get-cart\n        description: Get\
  \ cart contents.\n        call: servicenow-service-catalog.get-cart\n        outputParameters:\n        - type: object\n          mapping: $.result\n      - method: DELETE\n        name: empty-cart\n        description: Empty the cart.\n        call: servicenow-service-catalog.empty-cart\n        outputParameters:\n        - type: object\n          mapping: $.result\n    - path: /v1/trouble-tickets\n      name: trouble-tickets\n      description: Trouble ticket operations.\n      operations:\n      - method: GET\n        name: list-trouble-tickets\n        description: List trouble tickets.\n        call: servicenow-trouble-ticket.list-trouble-tickets\n        with:\n          limit: rest.limit\n          severity: rest.severity\n          status: rest.status\n          ticketType: rest.ticketType\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-trouble-ticket\n        description: Create a trouble ticket.\n        call:\
  \ servicenow-trouble-ticket.create-trouble-ticket\n        with:\n          name: rest.name\n          description: rest.description\n          severity: rest.severity\n          status: rest.status\n          ticketType: rest.ticketType\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9091\n    namespace: servicenow-customer-service-mcp\n    transport: http\n    description: MCP server for AI-assisted ServiceNow customer service workflows.\n    tools:\n    - name: list-contacts\n      description: List CSM contacts with optional filtering.\n      hints:\n        readOnly: true\n        idempotent: true\n        openWorld: true\n      call: servicenow-contact.list-contacts\n      with:\n        sysparm_query: tools.sysparm_query\n        sysparm_limit: tools.sysparm_limit\n      outputParameters:\n      - type: object\n        mapping: $.result\n    - name: create-contact\n      description: Create a new CSM contact.\n      hints:\n  \
  \      readOnly: false\n        idempotent: false\n      call: servicenow-contact.create-contact\n      with:\n        first_name: tools.first_name\n        last_name: tools.last_name\n        email: tools.email\n        phone: tools.phone\n      outputParameters:\n      - type: object\n        mapping: $.result\n    - name: get-contact\n      description: Retrieve a specific CSM contact.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: servicenow-contact.get-contact\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.result\n    - name: list-catalogs\n      description: List available service catalogs.\n      hints:\n        readOnly: true\n        idempotent: true\n        openWorld: true\n      call: servicenow-service-catalog.list-catalogs\n      with:\n        sysparm_limit: tools.sysparm_limit\n      outputParameters:\n      - type: object\n        mapping: $.result\n    - name: get-catalog\n      description:\
  \ Retrieve a specific service catalog.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: servicenow-service-catalog.get-catalog\n      with:\n        sys_id: tools.sys_id\n      outputParameters:\n      - type: object\n        mapping: $.result\n    - name: get-category\n      description: Retrieve a catalog category with subcategories.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: servicenow-service-catalog.get-category\n      with:\n        sys_id: tools.sys_id\n      outputParameters:\n      - type: object\n        mapping: $.result\n    - name: list-catalog-items\n      description: List catalog items with optional filtering.\n      hints:\n        readOnly: true\n        idempotent: true\n        openWorld: true\n      call: servicenow-service-catalog.list-catalog-items\n      with:\n        sysparm_catalog: tools.sysparm_catalog\n        sysparm_category: tools.sysparm_category\n        sysparm_limit: tools.sysparm_limit\n\
  \      outputParameters:\n      - type: object\n        mapping: $.result\n    - name: get-catalog-item\n      description: Retrieve catalog item details with variables.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: servicenow-service-catalog.get-catalog-item\n      with:\n        sys_id: tools.sys_id\n      outputParameters:\n      - type: object\n        mapping: $.result\n    - name: add-item-to-cart\n      description: Add a catalog item to the shopping cart.\n      hints:\n        readOnly: false\n        idempotent: false\n      call: servicenow-service-catalog.add-item-to-cart\n      with:\n        sys_id: tools.sys_id\n        quantity: tools.quantity\n        variables: tools.variables\n      outputParameters:\n      - type: object\n        mapping: $.result\n    - name: order-item-now\n      description: Order a catalog item immediately.\n      hints:\n        readOnly: false\n        idempotent: false\n      call: servicenow-service-catalog.order-item-now\n\
  \      with:\n        sys_id: tools.sys_id\n        quantity: tools.quantity\n        variables: tools.variables\n      outputParameters:\n      - type: object\n        mapping: $.result\n    - name: get-cart\n      description: Retrieve shopping cart contents.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: servicenow-service-catalog.get-cart\n      outputParameters:\n      - type: object\n        mapping: $.result\n    - name: empty-cart\n      description: Remove all items from the shopping cart.\n      hints:\n        destructive: true\n        idempotent: true\n      call: servicenow-service-catalog.empty-cart\n      outputParameters:\n      - type: object\n        mapping: $.result\n    - name: submit-cart-order\n      description: Submit cart as a service catalog request.\n      hints:\n        readOnly: false\n        idempotent: false\n      call: servicenow-service-catalog.submit-cart-order\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.result\n    - name: list-trouble-tickets\n      description: List trouble tickets.\n      hints:\n        readOnly: true\n        idempotent: true\n        openWorld: true\n      call: servicenow-trouble-ticket.list-trouble-tickets\n      with:\n        limit: tools.limit\n        severity: tools.severity\n        status: tools.status\n        ticketType: tools.ticketType\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-trouble-ticket\n      description: Create a trouble ticket.\n      hints:\n        readOnly: false\n        idempotent: false\n      call: servicenow-trouble-ticket.create-trouble-ticket\n      with:\n        name: tools.name\n        description: tools.description\n        severity: tools.severity\n        status: tools.status\n        ticketType: tools.ticketType\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-trouble-ticket\n      description: Retrieve a specific trouble ticket.\n      hints:\n\
  \        readOnly: true\n        idempotent: true\n      call: servicenow-trouble-ticket.get-trouble-ticket\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-trouble-ticket\n      description: Update an existing trouble ticket.\n      hints:\n        readOnly: false\n        idempotent: true\n      call: servicenow-trouble-ticket.update-trouble-ticket\n      with:\n        id: tools.id\n        name: tools.name\n        severity: tools.severity\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
