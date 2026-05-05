---
categories: []
consumed_apis:
- tmf629
- tmf621
description: Unified workflow capability combining TM Forum Customer Management (TMF629) and Trouble Ticket (TMF621) APIs for end-to-end customer support operations, from customer lookup to ticket resolution. Used by support agents and NOC engineers.
layout: capability
name: TM Forum Customer Support
operations:
- description: List customer accounts
  method: GET
  name: list-customers
  path: /v1/customers
- description: Create a new customer account
  method: POST
  name: create-customer
  path: /v1/customers
- description: Retrieve a customer account
  method: GET
  name: get-customer
  path: /v1/customers/{id}
- description: List trouble tickets
  method: GET
  name: list-trouble-tickets
  path: /v1/trouble-tickets
- description: Create a new trouble ticket
  method: POST
  name: create-trouble-ticket
  path: /v1/trouble-tickets
- description: Retrieve a trouble ticket
  method: GET
  name: get-trouble-ticket
  path: /v1/trouble-tickets/{id}
- description: Update a trouble ticket status
  method: PATCH
  name: update-trouble-ticket
  path: /v1/trouble-tickets/{id}
personas: []
provider_name: TM Forum
provider_slug: tm-forum
search_terms:
- open apis
- trouble ticket and incident management
- retrieve a specific customer account by id
- CRM Admin
- designs and implements bss systems using tm forum open apis
- list customers
- Support Agent
- product, service, and resource inventory
- bss
- individual customer account
- customer and party lifecycle management
- individual trouble ticket
- update trouble ticket
- list customer accounts
- telco
- Order Manager
- create a new customer account
- oss
- product, service, and resource ordering
- NOC Engineer
- trouble tickets
- handles customer trouble tickets and incident resolution
- update customer
- network operations center engineer managing network incidents
- manages product ordering and fulfillment workflows
- update trouble ticket status, severity, or resolution
- create trouble ticket
- partially update a customer account
- telecommunications
- Master Data Manager
- get customer
- customer-reported issue lifecycle from ticket creation to resolution
- BSS Architect
- standards
- support
- unified party/customer data management across bss systems
- end-to-end flow from product catalog through ordering to billing
- list or find customer accounts
- get trouble ticket
- retrieve a specific trouble ticket by id
- retrieve a customer account
- trouble ticket
- list trouble tickets
- create customer
- create a new customer trouble ticket
- retrieve a trouble ticket
- list or find trouble tickets
- manages customer and party master data across systems
- customer accounts
- customer management
- update a trouble ticket status
- product, service, and resource catalog management
- create a new trouble ticket
- tm forum
slug: customer-support
source_filename: customer-support.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"TM Forum Customer Support\"\n  description: \"Unified workflow capability combining TM Forum Customer Management (TMF629) and Trouble Ticket (TMF621) APIs for end-to-end customer support operations, from customer lookup to ticket resolution. Used by support agents and NOC engineers.\"\n  tags:\n    - TM Forum\n    - Customer Management\n    - Trouble Ticket\n    - Support\n    - Telecommunications\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      TMF_API_KEY: TMF_API_KEY\n\ncapability:\n  consumes:\n    - import: tmf629\n      location: ./shared/tmf629-customer-management.yaml\n    - import: tmf621\n      location: ./shared/tmf621-trouble-ticket.yaml\n\n  exposes:\n    - type: rest\n      port: 8081\n      namespace: customer-support-api\n      description: \"Unified REST API for TM Forum customer support workflow.\"\n      resources:\n        - path: /v1/customers\n        \
  \  name: customers\n          description: \"Customer accounts\"\n          operations:\n            - method: GET\n              name: list-customers\n              description: \"List customer accounts\"\n              call: \"tmf629.listCustomer\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n            - method: POST\n              name: create-customer\n              description: \"Create a new customer account\"\n              call: \"tmf629.createCustomer\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/customers/{id}\n          name: customer\n          description: \"Individual customer account\"\n          operations:\n            - method: GET\n              name: get-customer\n              description: \"Retrieve a customer account\"\n              call: \"tmf629.retrieveCustomer\"\n              with:\n                id: \"rest.id\"\n       \
  \       outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/trouble-tickets\n          name: trouble-tickets\n          description: \"Trouble tickets\"\n          operations:\n            - method: GET\n              name: list-trouble-tickets\n              description: \"List trouble tickets\"\n              call: \"tmf621.listTroubleTicket\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n            - method: POST\n              name: create-trouble-ticket\n              description: \"Create a new trouble ticket\"\n              call: \"tmf621.createTroubleTicket\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/trouble-tickets/{id}\n          name: trouble-ticket\n          description: \"Individual trouble ticket\"\n          operations:\n            - method: GET\n              name: get-trouble-ticket\n\
  \              description: \"Retrieve a trouble ticket\"\n              call: \"tmf621.retrieveTroubleTicket\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PATCH\n              name: update-trouble-ticket\n              description: \"Update a trouble ticket status\"\n              call: \"tmf621.patchTroubleTicket\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9091\n      namespace: customer-support-mcp\n      transport: http\n      description: \"MCP server for AI-assisted TM Forum customer support operations.\"\n      tools:\n        - name: list-customers\n          description: \"List or find customer accounts\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"tmf629.listCustomer\"\
  \n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n        - name: get-customer\n          description: \"Retrieve a specific customer account by ID\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"tmf629.retrieveCustomer\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-customer\n          description: \"Create a new customer account\"\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"tmf629.createCustomer\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-customer\n          description: \"Partially update a customer account\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"tmf629.patchCustomer\"\n      \
  \    with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-trouble-tickets\n          description: \"List or find trouble tickets\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"tmf621.listTroubleTicket\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n        - name: get-trouble-ticket\n          description: \"Retrieve a specific trouble ticket by ID\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"tmf621.retrieveTroubleTicket\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-trouble-ticket\n          description: \"Create a new customer trouble ticket\"\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"tmf621.createTroubleTicket\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-trouble-ticket\n          description: \"Update trouble ticket status, severity, or resolution\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"tmf621.patchTroubleTicket\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/tm-forum/refs/heads/main/capabilities/customer-support.yaml
tags:
- TM Forum
- Customer Management
- Trouble Ticket
- Support
- Telecommunications
tools:
- description: List or find customer accounts
  hints:
    openWorld: true
    readOnly: true
  name: list-customers
- description: Retrieve a specific customer account by ID
  hints:
    openWorld: false
    readOnly: true
  name: get-customer
- description: Create a new customer account
  hints:
    openWorld: false
    readOnly: false
  name: create-customer
- description: Partially update a customer account
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: update-customer
- description: List or find trouble tickets
  hints:
    openWorld: true
    readOnly: true
  name: list-trouble-tickets
- description: Retrieve a specific trouble ticket by ID
  hints:
    openWorld: false
    readOnly: true
  name: get-trouble-ticket
- description: Create a new customer trouble ticket
  hints:
    openWorld: false
    readOnly: false
  name: create-trouble-ticket
- description: Update trouble ticket status, severity, or resolution
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: update-trouble-ticket
---
