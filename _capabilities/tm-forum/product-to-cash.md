---
categories: []
consumed_apis: []
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
- retrieve a specific product order by id
- handles customer trouble tickets and incident resolution
- list catalog categories
- create a product catalog category
- individual product order
- product inventory
- open apis
- get product order
- create product offering
- product catalog
- Order Manager
- NOC Engineer
- Master Data Manager
- telco
- standards
- get product offering
- retrieve a specific product offering
- product, service, and resource catalog management
- create product order
- list product offerings
- product catalog categories
- telecommunications
- list product offerings from the catalog
- tm forum
- retrieve a specific product catalog category
- manages product ordering and fulfillment workflows
- list product catalog categories from tmf620
- BSS Architect
- customer and party lifecycle management
- product ordering
- list product orders
- Support Agent
- retrieve a specific product order
- designs and implements bss systems using tm forum open apis
- create a new product catalog category
- product, service, and resource inventory
- trouble ticket and incident management
- manages customer and party master data across systems
- end-to-end flow from product catalog through ordering to billing
- unified party/customer data management across bss systems
- submit a new product order
- bss
- product, service, and resource ordering
- CRM Admin
- list product catalog categories
- product orders
- customer-reported issue lifecycle from ticket creation to resolution
- create a product offering
- list product orders from tmf622
- oss
- product offerings
- create a new product order
- get catalog category
- network operations center engineer managing network incidents
- create catalog category
slug: product-to-cash
source_filename: product-to-cash.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: TM Forum Product-to-Cash\n  description: Unified workflow capability combining TM Forum Product Catalog (TMF620), Product Ordering (TMF622), and Product\n    Inventory (TMF637) APIs for end-to-end product lifecycle management from catalog to active subscriptions. Used by BSS\n    architects and order managers.\n  tags:\n  - TM Forum\n  - Product Catalog\n  - Product Ordering\n  - Product Inventory\n  - BSS\n  - Telecommunications\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    TMF_API_KEY: TMF_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: tmf620\n    baseUri: https://serverRoot/tmf-api/productCatalogManagement/v5\n    description: TM Forum Product Catalog Management API v5\n    authentication:\n      type: bearer\n      token: '{{TMF_API_KEY}}'\n    resources:\n    - name: category\n      path: /category\n      description: Product catalog categories\n      operations:\n  \
  \    - name: listCategory\n        method: GET\n        description: TM Forum List or Find Category Objects\n        inputParameters:\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Comma-separated list of fields to return\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Offset for pagination\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Limit for pagination\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n      - name: createCategory\n        method: POST\n        description: TM Forum Create a Category\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n           \
  \ name: '{{tools.name}}'\n            description: '{{tools.description}}'\n      - name: retrieveCategory\n        method: GET\n        description: TM Forum Retrieve a Category by ID\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Category identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: catalog\n      path: /catalog\n      description: Product catalogs\n      operations:\n      - name: listCatalog\n        method: GET\n        description: TM Forum List or Find Catalog Objects\n        inputParameters:\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Offset for pagination\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Limit for pagination\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n      - name: retrieveCatalog\n        method: GET\n        description: TM Forum Retrieve a Catalog by ID\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Catalog identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: productOffering\n      path: /productOffering\n      description: Product offerings\n      operations:\n      - name: listProductOffering\n        method: GET\n        description: TM Forum List or Find Product Offering Objects\n        inputParameters:\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Offset for pagination\n        - name: limit\n          in: query\n          type: integer\n          required: false\n\
  \          description: Limit for pagination\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n      - name: createProductOffering\n        method: POST\n        description: TM Forum Create a Product Offering\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            description: '{{tools.description}}'\n      - name: retrieveProductOffering\n        method: GET\n        description: TM Forum Retrieve a Product Offering by ID\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Product offering identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace:\
  \ tmf622\n    baseUri: https://serverRoot/tmf-api/productOrderingManagement/v5\n    description: TM Forum Product Ordering Management API v5\n    authentication:\n      type: bearer\n      token: '{{TMF_API_KEY}}'\n    resources:\n    - name: productOrder\n      path: /productOrder\n      description: Product orders\n      operations:\n      - name: listProductOrder\n        method: GET\n        description: TM Forum List or Find Product Order Objects\n        inputParameters:\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Offset for pagination\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Limit for pagination\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n      - name: createProductOrder\n        method: POST\n        description: TM Forum Create a Product Order\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            requestedStartDate: '{{tools.requestedStartDate}}'\n            orderItem: '{{tools.orderItem}}'\n      - name: retrieveProductOrder\n        method: GET\n        description: TM Forum Retrieve a Product Order by ID\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Product order identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: patchProductOrder\n        method: PATCH\n        description: TM Forum Update Partially a Product Order\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Product order identifier\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: product-to-cash-api\n    description: Unified REST API for TM Forum product-to-cash workflow.\n    resources:\n    - path: /v1/product-catalog/categories\n      name: catalog-categories\n      description: Product catalog categories\n      operations:\n      - method: GET\n        name: list-catalog-categories\n        description: List product catalog categories\n        call: tmf620.listCategory\n        outputParameters:\n        - type: array\n          mapping: $.\n      - method: POST\n        name: create-catalog-category\n        description: Create a product catalog category\n        call: tmf620.createCategory\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/product-catalog/offerings\n      name: product-offerings\n      description: Product offerings\n      operations:\n  \
  \    - method: GET\n        name: list-product-offerings\n        description: List product offerings\n        call: tmf620.listProductOffering\n        outputParameters:\n        - type: array\n          mapping: $.\n      - method: POST\n        name: create-product-offering\n        description: Create a product offering\n        call: tmf620.createProductOffering\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/product-orders\n      name: product-orders\n      description: Product orders\n      operations:\n      - method: GET\n        name: list-product-orders\n        description: List product orders\n        call: tmf622.listProductOrder\n        outputParameters:\n        - type: array\n          mapping: $.\n      - method: POST\n        name: create-product-order\n        description: Create a new product order\n        call: tmf622.createProductOrder\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path:\
  \ /v1/product-orders/{id}\n      name: product-order\n      description: Individual product order\n      operations:\n      - method: GET\n        name: get-product-order\n        description: Retrieve a specific product order\n        call: tmf622.retrieveProductOrder\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: product-to-cash-mcp\n    transport: http\n    description: MCP server for AI-assisted TM Forum product-to-cash workflow.\n    tools:\n    - name: list-catalog-categories\n      description: List product catalog categories from TMF620\n      hints:\n        readOnly: true\n        openWorld: true\n      call: tmf620.listCategory\n      outputParameters:\n      - type: array\n        mapping: $.\n    - name: get-catalog-category\n      description: Retrieve a specific product catalog category\n      hints:\n        readOnly: true\n        openWorld: false\n      call:\
  \ tmf620.retrieveCategory\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-catalog-category\n      description: Create a new product catalog category\n      hints:\n        readOnly: false\n        openWorld: false\n      call: tmf620.createCategory\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-product-offerings\n      description: List product offerings from the catalog\n      hints:\n        readOnly: true\n        openWorld: true\n      call: tmf620.listProductOffering\n      outputParameters:\n      - type: array\n        mapping: $.\n    - name: get-product-offering\n      description: Retrieve a specific product offering\n      hints:\n        readOnly: true\n        openWorld: false\n      call: tmf620.retrieveProductOffering\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-product-orders\n     \
  \ description: List product orders from TMF622\n      hints:\n        readOnly: true\n        openWorld: true\n      call: tmf622.listProductOrder\n      outputParameters:\n      - type: array\n        mapping: $.\n    - name: get-product-order\n      description: Retrieve a specific product order by ID\n      hints:\n        readOnly: true\n        openWorld: false\n      call: tmf622.retrieveProductOrder\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-product-order\n      description: Submit a new product order\n      hints:\n        readOnly: false\n        openWorld: false\n      call: tmf622.createProductOrder\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
