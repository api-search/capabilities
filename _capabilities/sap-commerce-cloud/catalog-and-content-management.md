---
categories: []
consumed_apis: []
description: Workflow capability for managing product catalogs, categories, and content in SAP Commerce Cloud. Combines catalog browsing, product content management, and customer service workflows. Used by catalog managers, merchandisers, and content administrators.
layout: capability
name: SAP Commerce Cloud Catalog and Content Management
operations:
- description: List product catalogs.
  method: GET
  name: list-catalogs
  path: /v1/catalogs
- description: Get catalog details.
  method: GET
  name: get-catalog
  path: /v1/catalogs/{catalogId}
- description: Search products in the catalog.
  method: GET
  name: search-products
  path: /v1/products
- description: Search customers for assisted service.
  method: GET
  name: search-customers
  path: /v1/customers
personas: []
provider_name: SAP Commerce Cloud
provider_slug: sap-commerce-cloud
search_terms:
- customer search for assisted service.
- create a customer support ticket for order or product issues.
- search products in the catalog.
- list available product catalogs in sap commerce cloud.
- list catalogs
- get catalog
- omnichannel
- retail
- b2b
- search customers
- content management
- commerce
- ecommerce
- b2c
- single product catalog.
- sap
- get catalog details.
- list categories
- create support ticket
- get structure, versions, and configuration of a product catalog.
- list product catalogs.
- search the product catalog for content management review.
- product catalog management.
- search for customer accounts to assist through the asm interface.
- catalog
- customer experience
- search products
- search customers for assisted service.
- list product categories within a catalog version.
- product search.
slug: catalog-and-content-management
source_filename: catalog-and-content-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: SAP Commerce Cloud Catalog and Content Management\n  description: Workflow capability for managing product catalogs, categories, and content in SAP Commerce Cloud. Combines\n    catalog browsing, product content management, and customer service workflows. Used by catalog managers, merchandisers,\n    and content administrators.\n  tags:\n  - Catalog\n  - Commerce\n  - Content Management\n  - SAP\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SAP_COMMERCE_OAUTH_TOKEN: SAP_COMMERCE_OAUTH_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: sap-commerce-occ\n    baseUri: https://{tenant}.{region}.commercecloud.sap/occ/v2/{baseSiteId}\n    description: SAP Commerce Cloud OCC v2 REST API.\n    authentication:\n      type: bearer\n      token: '{{SAP_COMMERCE_OAUTH_TOKEN}}'\n    resources:\n    - name: products\n      path: /products\n      description: Product catalog browsing and search.\n\
  \      operations:\n      - name: search-products\n        method: GET\n        description: Search for products using free-text or faceted navigation.\n        inputParameters:\n        - name: query\n          in: query\n          type: string\n          required: false\n          description: Search query or facet filter\n        - name: currentPage\n          in: query\n          type: integer\n          required: false\n          description: Current page number (0-based)\n        - name: pageSize\n          in: query\n          type: integer\n          required: false\n          description: Number of results per page\n        - name: sort\n          in: query\n          type: string\n          required: false\n          description: Sort criteria\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Response field set (BASIC, DEFAULT, FULL)\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n      - name: get-product\n        method: GET\n        description: Get detailed information about a specific product.\n        inputParameters:\n        - name: productCode\n          in: path\n          type: string\n          required: true\n          description: Product code identifier\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Response field set\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: carts\n      path: /users/{userId}/carts\n      description: Shopping cart management.\n      operations:\n      - name: get-cart\n        method: GET\n        description: Get the current cart for a user.\n        inputParameters:\n        - name: userId\n          in: path\n          type: string\n          required: true\n          description: User identifier or 'current'\
  \ for authenticated user\n        - name: cartId\n          in: path\n          type: string\n          required: true\n          description: Cart identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: add-to-cart\n        method: POST\n        description: Add a product to the cart.\n        inputParameters:\n        - name: userId\n          in: path\n          type: string\n          required: true\n          description: User identifier\n        - name: cartId\n          in: path\n          type: string\n          required: true\n          description: Cart identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            product:\n              code: '{{tools.productCode}}'\n            quantity: '{{tools.quantity}}'\n    - name: orders\n      path:\
  \ /users/{userId}/orders\n      description: Order management and history.\n      operations:\n      - name: list-orders\n        method: GET\n        description: List orders for a user.\n        inputParameters:\n        - name: userId\n          in: path\n          type: string\n          required: true\n          description: User identifier\n        - name: pageSize\n          in: query\n          type: integer\n          required: false\n          description: Number of results per page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-order\n        method: GET\n        description: Get details of a specific order.\n        inputParameters:\n        - name: userId\n          in: path\n          type: string\n          required: true\n          description: User identifier\n        - name: code\n          in: path\n          type: string\n          required: true\n          description:\
  \ Order code\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: stores\n      path: /stores\n      description: Physical store locator.\n      operations:\n      - name: list-stores\n        method: GET\n        description: List physical stores with optional location search.\n        inputParameters:\n        - name: query\n          in: query\n          type: string\n          required: false\n          description: Location search query\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: sap-commerce-pcm\n    baseUri: https://{tenant}.{region}.commercecloud.sap/occ/v2/{baseSiteId}\n    description: SAP Commerce Cloud Product Content Management via OCC API.\n    authentication:\n      type: bearer\n      token: '{{SAP_COMMERCE_OAUTH_TOKEN}}'\n    resources:\n    - name: catalogs\n      path:\
  \ /catalogs\n      description: Product catalog management.\n      operations:\n      - name: list-catalogs\n        method: GET\n        description: List available product catalogs.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-catalog\n        method: GET\n        description: Get details of a specific catalog.\n        inputParameters:\n        - name: catalogId\n          in: path\n          type: string\n          required: true\n          description: Catalog identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: categories\n      path: /catalogs/{catalogId}/versions/{catalogVersionId}/categories\n      description: Category management within a catalog.\n      operations:\n      - name: list-categories\n        method: GET\n        description: List categories in a catalog version.\n  \
  \      inputParameters:\n        - name: catalogId\n          in: path\n          type: string\n          required: true\n          description: Catalog identifier\n        - name: catalogVersionId\n          in: path\n          type: string\n          required: true\n          description: Catalog version identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: sap-commerce-asm\n    baseUri: https://{tenant}.{region}.commercecloud.sap/assistedservicewebservices\n    description: SAP Commerce Cloud Assisted Service Module REST API.\n    authentication:\n      type: bearer\n      token: '{{SAP_COMMERCE_OAUTH_TOKEN}}'\n    resources:\n    - name: customers\n      path: /customers\n      description: Customer search and management for assisted service.\n      operations:\n      - name: search-customers\n        method: GET\n        description: Search for customers by name or email\
  \ to assist.\n        inputParameters:\n        - name: query\n          in: query\n          type: string\n          required: false\n          description: Search query (name, email, or account number)\n        - name: pageSize\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: customer-support-tickets\n      path: /tickets\n      description: Customer support ticket management.\n      operations:\n      - name: create-ticket\n        method: POST\n        description: Create a customer support ticket.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            customerId: '{{tools.customerId}}'\n            subject: '{{tools.subject}}'\n     \
  \       message: '{{tools.message}}'\n      - name: list-tickets\n        method: GET\n        description: List support tickets for a customer.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8081\n    namespace: sap-commerce-catalog-api\n    description: Unified REST API for SAP Commerce Cloud catalog and content management.\n    resources:\n    - path: /v1/catalogs\n      name: catalogs\n      description: Product catalog management.\n      operations:\n      - method: GET\n        name: list-catalogs\n        description: List product catalogs.\n        call: sap-commerce-pcm.list-catalogs\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/catalogs/{catalogId}\n      name: catalog\n      description: Single product catalog.\n      operations:\n      - method: GET\n        name: get-catalog\n        description: Get catalog details.\n\
  \        call: sap-commerce-pcm.get-catalog\n        with:\n          catalogId: rest.catalogId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/products\n      name: products\n      description: Product search.\n      operations:\n      - method: GET\n        name: search-products\n        description: Search products in the catalog.\n        call: sap-commerce-occ.search-products\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/customers\n      name: customers\n      description: Customer search for assisted service.\n      operations:\n      - method: GET\n        name: search-customers\n        description: Search customers for assisted service.\n        call: sap-commerce-asm.search-customers\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9081\n    namespace: sap-commerce-catalog-mcp\n    transport: http\n    description: MCP server for AI-assisted\
  \ SAP Commerce Cloud catalog and content management.\n    tools:\n    - name: list-catalogs\n      description: List available product catalogs in SAP Commerce Cloud.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: sap-commerce-pcm.list-catalogs\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-catalog\n      description: Get structure, versions, and configuration of a product catalog.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: sap-commerce-pcm.get-catalog\n      with:\n        catalogId: tools.catalogId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-categories\n      description: List product categories within a catalog version.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: sap-commerce-pcm.list-categories\n      with:\n        catalogId: tools.catalogId\n        catalogVersionId: tools.catalogVersionId\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: search-products\n      description: Search the product catalog for content management review.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: sap-commerce-occ.search-products\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-customers\n      description: Search for customer accounts to assist through the ASM interface.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: sap-commerce-asm.search-customers\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-support-ticket\n      description: Create a customer support ticket for order or product issues.\n      hints:\n        readOnly: false\n        idempotent: false\n      call: sap-commerce-asm.create-ticket\n      with:\n        customerId: tools.customerId\n        subject: tools.subject\n        message: tools.message\n      outputParameters:\n      - type:\
  \ object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/sap-commerce-cloud/refs/heads/main/capabilities/catalog-and-content-management.yaml
tags:
- Catalog
- Commerce
- Content Management
- SAP
tools:
- description: List available product catalogs in SAP Commerce Cloud.
  hints:
    openWorld: true
    readOnly: true
  name: list-catalogs
- description: Get structure, versions, and configuration of a product catalog.
  hints:
    openWorld: false
    readOnly: true
  name: get-catalog
- description: List product categories within a catalog version.
  hints:
    openWorld: true
    readOnly: true
  name: list-categories
- description: Search the product catalog for content management review.
  hints:
    openWorld: true
    readOnly: true
  name: search-products
- description: Search for customer accounts to assist through the ASM interface.
  hints:
    openWorld: true
    readOnly: true
  name: search-customers
- description: Create a customer support ticket for order or product issues.
  hints:
    idempotent: false
    readOnly: false
  name: create-support-ticket
---
