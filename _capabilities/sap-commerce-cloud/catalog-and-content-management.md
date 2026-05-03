---
categories: []
consumed_apis:
- sap-commerce-occ
- sap-commerce-pcm
- sap-commerce-asm
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
- single product catalog.
- search customers for assisted service.
- sap
- list product categories within a catalog version.
- search products in the catalog.
- commerce
- get catalog
- customer search for assisted service.
- search the product catalog for content management review.
- get structure, versions, and configuration of a product catalog.
- list catalogs
- b2b
- omnichannel
- customer experience
- list categories
- search customers
- create support ticket
- get catalog details.
- ecommerce
- search for customer accounts to assist through the asm interface.
- retail
- create a customer support ticket for order or product issues.
- b2c
- product catalog management.
- catalog
- search products
- product search.
- content management
- list product catalogs.
- list available product catalogs in sap commerce cloud.
slug: catalog-and-content-management
source_filename: catalog-and-content-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"SAP Commerce Cloud Catalog and Content Management\"\n  description: \"Workflow capability for managing product catalogs, categories, and content in SAP Commerce Cloud. Combines catalog browsing, product content management, and customer service workflows. Used by catalog managers, merchandisers, and content administrators.\"\n  tags:\n    - Catalog\n    - Commerce\n    - Content Management\n    - SAP\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SAP_COMMERCE_OAUTH_TOKEN: SAP_COMMERCE_OAUTH_TOKEN\n\ncapability:\n  consumes:\n    - import: sap-commerce-occ\n      location: ./shared/commerce-web-services.yaml\n    - import: sap-commerce-pcm\n      location: ./shared/product-content-management.yaml\n    - import: sap-commerce-asm\n      location: ./shared/assisted-service.yaml\n\n  exposes:\n    - type: rest\n      port: 8081\n      namespace: sap-commerce-catalog-api\n      description:\
  \ \"Unified REST API for SAP Commerce Cloud catalog and content management.\"\n      resources:\n        - path: /v1/catalogs\n          name: catalogs\n          description: \"Product catalog management.\"\n          operations:\n            - method: GET\n              name: list-catalogs\n              description: \"List product catalogs.\"\n              call: \"sap-commerce-pcm.list-catalogs\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/catalogs/{catalogId}\n          name: catalog\n          description: \"Single product catalog.\"\n          operations:\n            - method: GET\n              name: get-catalog\n              description: \"Get catalog details.\"\n              call: \"sap-commerce-pcm.get-catalog\"\n              with:\n                catalogId: \"rest.catalogId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/products\n\
  \          name: products\n          description: \"Product search.\"\n          operations:\n            - method: GET\n              name: search-products\n              description: \"Search products in the catalog.\"\n              call: \"sap-commerce-occ.search-products\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/customers\n          name: customers\n          description: \"Customer search for assisted service.\"\n          operations:\n            - method: GET\n              name: search-customers\n              description: \"Search customers for assisted service.\"\n              call: \"sap-commerce-asm.search-customers\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9081\n      namespace: sap-commerce-catalog-mcp\n      transport: http\n      description: \"MCP server for AI-assisted SAP Commerce Cloud catalog\
  \ and content management.\"\n      tools:\n        - name: list-catalogs\n          description: \"List available product catalogs in SAP Commerce Cloud.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"sap-commerce-pcm.list-catalogs\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-catalog\n          description: \"Get structure, versions, and configuration of a product catalog.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"sap-commerce-pcm.get-catalog\"\n          with:\n            catalogId: \"tools.catalogId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-categories\n          description: \"List product categories within a catalog version.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"sap-commerce-pcm.list-categories\"\
  \n          with:\n            catalogId: \"tools.catalogId\"\n            catalogVersionId: \"tools.catalogVersionId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: search-products\n          description: \"Search the product catalog for content management review.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"sap-commerce-occ.search-products\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: search-customers\n          description: \"Search for customer accounts to assist through the ASM interface.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"sap-commerce-asm.search-customers\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-support-ticket\n          description: \"Create a customer support ticket for order or\
  \ product issues.\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"sap-commerce-asm.create-ticket\"\n          with:\n            customerId: \"tools.customerId\"\n            subject: \"tools.subject\"\n            message: \"tools.message\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
