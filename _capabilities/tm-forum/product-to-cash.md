---
categories: []
consumed_apis:
- tmf620
- tmf622
description: Unified workflow capability combining TM Forum Product Catalog (TMF620), Product Ordering (TMF622), and Product Inventory (TMF637) APIs for end-to-end product lifecycle management from catalog to active subscriptions. Used by BSS architects and order managers.
layout: capability
name: TM Forum Product-to-Cash
operations:
- description: List product catalog categories
  method: GET
  name: list-catalog-categories
  path: /v1/product-catalog/categories
- description: Create a product catalog category
  method: POST
  name: create-catalog-category
  path: /v1/product-catalog/categories
- description: List product offerings
  method: GET
  name: list-product-offerings
  path: /v1/product-catalog/offerings
- description: Create a product offering
  method: POST
  name: create-product-offering
  path: /v1/product-catalog/offerings
- description: List product orders
  method: GET
  name: list-product-orders
  path: /v1/product-orders
- description: Create a new product order
  method: POST
  name: create-product-order
  path: /v1/product-orders
- description: Retrieve a specific product order
  method: GET
  name: get-product-order
  path: /v1/product-orders/{id}
personas: []
provider_name: TM Forum
provider_slug: tm-forum
search_terms:
- create product offering
- list product offerings
- manages customer and party master data across systems
- product catalog categories
- CRM Admin
- standards
- network operations center engineer managing network incidents
- product catalog
- open apis
- oss
- unified party/customer data management across bss systems
- product, service, and resource catalog management
- Master Data Manager
- create a product offering
- retrieve a specific product offering
- product, service, and resource ordering
- NOC Engineer
- product offerings
- list product catalog categories
- list product catalog categories from tmf620
- Support Agent
- trouble ticket and incident management
- list product orders
- bss
- list product offerings from the catalog
- get product offering
- create product order
- product inventory
- retrieve a specific product order by id
- product, service, and resource inventory
- list catalog categories
- create a new product order
- customer and party lifecycle management
- tm forum
- create a new product catalog category
- get catalog category
- BSS Architect
- product ordering
- manages product ordering and fulfillment workflows
- end-to-end flow from product catalog through ordering to billing
- retrieve a specific product order
- create a product catalog category
- get product order
- retrieve a specific product catalog category
- Order Manager
- product orders
- submit a new product order
- customer-reported issue lifecycle from ticket creation to resolution
- telecommunications
- individual product order
- designs and implements bss systems using tm forum open apis
- telco
- list product orders from tmf622
- handles customer trouble tickets and incident resolution
- create catalog category
slug: product-to-cash
source_filename: product-to-cash.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"TM Forum Product-to-Cash\"\n  description: \"Unified workflow capability combining TM Forum Product Catalog (TMF620), Product Ordering (TMF622), and Product Inventory (TMF637) APIs for end-to-end product lifecycle management from catalog to active subscriptions. Used by BSS architects and order managers.\"\n  tags:\n    - TM Forum\n    - Product Catalog\n    - Product Ordering\n    - Product Inventory\n    - BSS\n    - Telecommunications\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      TMF_API_KEY: TMF_API_KEY\n\ncapability:\n  consumes:\n    - import: tmf620\n      location: ./shared/tmf620-product-catalog.yaml\n    - import: tmf622\n      location: ./shared/tmf622-product-ordering.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: product-to-cash-api\n      description: \"Unified REST API for TM Forum product-to-cash workflow.\"\n      resources:\n  \
  \      - path: /v1/product-catalog/categories\n          name: catalog-categories\n          description: \"Product catalog categories\"\n          operations:\n            - method: GET\n              name: list-catalog-categories\n              description: \"List product catalog categories\"\n              call: \"tmf620.listCategory\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n            - method: POST\n              name: create-catalog-category\n              description: \"Create a product catalog category\"\n              call: \"tmf620.createCategory\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/product-catalog/offerings\n          name: product-offerings\n          description: \"Product offerings\"\n          operations:\n            - method: GET\n              name: list-product-offerings\n              description: \"List product offerings\"\
  \n              call: \"tmf620.listProductOffering\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n            - method: POST\n              name: create-product-offering\n              description: \"Create a product offering\"\n              call: \"tmf620.createProductOffering\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/product-orders\n          name: product-orders\n          description: \"Product orders\"\n          operations:\n            - method: GET\n              name: list-product-orders\n              description: \"List product orders\"\n              call: \"tmf622.listProductOrder\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n            - method: POST\n              name: create-product-order\n              description: \"Create a new product order\"\n              call: \"tmf622.createProductOrder\"\
  \n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/product-orders/{id}\n          name: product-order\n          description: \"Individual product order\"\n          operations:\n            - method: GET\n              name: get-product-order\n              description: \"Retrieve a specific product order\"\n              call: \"tmf622.retrieveProductOrder\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: product-to-cash-mcp\n      transport: http\n      description: \"MCP server for AI-assisted TM Forum product-to-cash workflow.\"\n      tools:\n        - name: list-catalog-categories\n          description: \"List product catalog categories from TMF620\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"tmf620.listCategory\"\
  \n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n        - name: get-catalog-category\n          description: \"Retrieve a specific product catalog category\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"tmf620.retrieveCategory\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-catalog-category\n          description: \"Create a new product catalog category\"\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"tmf620.createCategory\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-product-offerings\n          description: \"List product offerings from the catalog\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"tmf620.listProductOffering\"\
  \n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n        - name: get-product-offering\n          description: \"Retrieve a specific product offering\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"tmf620.retrieveProductOffering\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-product-orders\n          description: \"List product orders from TMF622\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"tmf622.listProductOrder\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n        - name: get-product-order\n          description: \"Retrieve a specific product order by ID\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"tmf622.retrieveProductOrder\"\n          with:\n\
  \            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-product-order\n          description: \"Submit a new product order\"\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"tmf622.createProductOrder\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/tm-forum/refs/heads/main/capabilities/product-to-cash.yaml
tags:
- TM Forum
- Product Catalog
- Product Ordering
- Product Inventory
- BSS
- Telecommunications
tools:
- description: List product catalog categories from TMF620
  hints:
    openWorld: true
    readOnly: true
  name: list-catalog-categories
- description: Retrieve a specific product catalog category
  hints:
    openWorld: false
    readOnly: true
  name: get-catalog-category
- description: Create a new product catalog category
  hints:
    openWorld: false
    readOnly: false
  name: create-catalog-category
- description: List product offerings from the catalog
  hints:
    openWorld: true
    readOnly: true
  name: list-product-offerings
- description: Retrieve a specific product offering
  hints:
    openWorld: false
    readOnly: true
  name: get-product-offering
- description: List product orders from TMF622
  hints:
    openWorld: true
    readOnly: true
  name: list-product-orders
- description: Retrieve a specific product order by ID
  hints:
    openWorld: false
    readOnly: true
  name: get-product-order
- description: Submit a new product order
  hints:
    openWorld: false
    readOnly: false
  name: create-product-order
---
