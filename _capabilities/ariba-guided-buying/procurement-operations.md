---
categories:
- procurement-supply-chain
consumed_apis:
- ariba-catalog-shop
- ariba-asset-mgmt
description: Unified procurement operations workflow combining catalog shopping and asset management for enterprise buyers and procurement administrators.
layout: capability
name: Ariba Guided Buying - Procurement Operations
operations:
- description: Get catalog items and facets from SAP Business Network.
  method: GET
  name: get-shop
  path: /v1/shops/{shopId}
- description: List catalog items from a shop.
  method: GET
  name: list-items
  path: /v1/shops/{shopId}/items
- description: Get search suggestions from catalog.
  method: GET
  name: autocomplete
  path: /v1/shops/{shopId}/autocomplete
- description: List purchase requisitions with asset items.
  method: GET
  name: list-requisitions
  path: /v1/requisitions
- description: Count asset-based requisitions.
  method: GET
  name: count-requisitions
  path: /v1/requisitions/count
- description: Assign asset numbers to requisition line items.
  method: POST
  name: update-assets
  path: /v1/requisitions/batch/assets
personas: []
provider_name: Ariba Guided Buying
provider_slug: ariba-guided-buying
search_terms:
- list requisitions
- list catalog items with details from an sap ariba shop.
- list sap ariba purchase requisitions containing asset line items pending asset assignment.
- list catalog items
- get typeahead search suggestions from an sap ariba catalog.
- management of supplier product catalogs on sap business network.
- assign unique asset numbers to line items on sap ariba purchase requisitions.
- catalog search typeahead.
- shopping
- catalog shop items and facets.
- unified catalog shopping and asset management workflow
- list catalog items from a shop.
- autocomplete
- administrator who manages asset assignments and procurement workflows.
- requisition count.
- assign asset numbers
- get shop catalog
- employee who uses guided buying to search catalogs and create purchase requests.
- get catalog items and facets from sap business network.
- batch asset assignment.
- requisitions
- ariba
- Procurement Administrator
- sap
- update assets
- b2b
- catalog item listing.
- get shop
- assign asset numbers to requisition line items.
- list items
- retrieve catalog items and facets from an sap ariba shop on sap business network.
- get search suggestions from catalog.
- asset-based purchase requisitions.
- catalog
- erp
- Enterprise Buyer
- list asset requisitions
- tracking and assignment of asset numbers to purchased items.
- get total count of asset-based purchase requisitions in sap ariba.
- search catalog
- count asset requisitions
- count asset-based requisitions.
- supply chain
- asset management
- count requisitions
- list purchase requisitions with asset items.
- procurement
slug: procurement-operations
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Ariba Guided Buying - Procurement Operations\"\n  description: \"Unified procurement operations workflow combining catalog shopping and asset management for enterprise buyers and procurement administrators.\"\n  tags:\n    - Ariba\n    - Asset Management\n    - Catalog\n    - Procurement\n    - SAP\n    - Shopping\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      ARIBA_CATALOG_OAUTH_TOKEN: ARIBA_CATALOG_OAUTH_TOKEN\n      ARIBA_ASSET_OAUTH_TOKEN: ARIBA_ASSET_OAUTH_TOKEN\n\ncapability:\n  consumes:\n    - import: ariba-catalog-shop\n      location: ./shared/catalog-shop-api.yaml\n    - import: ariba-asset-mgmt\n      location: ./shared/asset-management-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: ariba-procurement-api\n      description: \"Unified REST API for SAP Ariba Guided Buying procurement operations.\"\n      resources:\n        - path: /v1/shops/{shopId}\n\
  \          name: shop\n          description: \"Catalog shop items and facets.\"\n          operations:\n            - method: GET\n              name: get-shop\n              description: \"Get catalog items and facets from SAP Business Network.\"\n              call: \"ariba-catalog-shop.get-shop\"\n              with:\n                shopID: \"rest.shopId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/shops/{shopId}/items\n          name: shop-items\n          description: \"Catalog item listing.\"\n          operations:\n            - method: GET\n              name: list-items\n              description: \"List catalog items from a shop.\"\n              call: \"ariba-catalog-shop.list-shop-items\"\n              with:\n                shopID: \"rest.shopId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/shops/{shopId}/autocomplete\n\
  \          name: catalog-autocomplete\n          description: \"Catalog search typeahead.\"\n          operations:\n            - method: GET\n              name: autocomplete\n              description: \"Get search suggestions from catalog.\"\n              call: \"ariba-catalog-shop.get-shop-autocomplete\"\n              with:\n                shopID: \"rest.shopId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/requisitions\n          name: requisitions\n          description: \"Asset-based purchase requisitions.\"\n          operations:\n            - method: GET\n              name: list-requisitions\n              description: \"List purchase requisitions with asset items.\"\n              call: \"ariba-asset-mgmt.list-asset-requisitions\"\n              with:\n                realm: \"rest.realm\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n      \
  \  - path: /v1/requisitions/count\n          name: requisitions-count\n          description: \"Requisition count.\"\n          operations:\n            - method: GET\n              name: count-requisitions\n              description: \"Count asset-based requisitions.\"\n              call: \"ariba-asset-mgmt.count-asset-requisitions\"\n              with:\n                realm: \"rest.realm\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/requisitions/batch/assets\n          name: requisitions-batch\n          description: \"Batch asset assignment.\"\n          operations:\n            - method: POST\n              name: update-assets\n              description: \"Assign asset numbers to requisition line items.\"\n              call: \"ariba-asset-mgmt.update-asset-line-items\"\n              with:\n                realm: \"rest.realm\"\n              outputParameters:\n                - type: object\n        \
  \          mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: ariba-procurement-mcp\n      transport: http\n      description: \"MCP server for AI-assisted SAP Ariba Guided Buying procurement operations.\"\n      tools:\n        - name: get-shop-catalog\n          description: \"Retrieve catalog items and facets from an SAP Ariba shop on SAP Business Network.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"ariba-catalog-shop.get-shop\"\n          with:\n            shopID: \"tools.shopID\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-catalog-items\n          description: \"List catalog items with details from an SAP Ariba shop.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"ariba-catalog-shop.list-shop-items\"\n          with:\n            shopID: \"tools.shopID\"\n          outputParameters:\n            -\
  \ type: object\n              mapping: \"$.\"\n        - name: search-catalog\n          description: \"Get typeahead search suggestions from an SAP Ariba catalog.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"ariba-catalog-shop.get-shop-autocomplete\"\n          with:\n            shopID: \"tools.shopID\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-asset-requisitions\n          description: \"List SAP Ariba purchase requisitions containing asset line items pending asset assignment.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"ariba-asset-mgmt.list-asset-requisitions\"\n          with:\n            realm: \"tools.realm\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: count-asset-requisitions\n          description: \"Get total count of asset-based purchase requisitions\
  \ in SAP Ariba.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"ariba-asset-mgmt.count-asset-requisitions\"\n          with:\n            realm: \"tools.realm\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: assign-asset-numbers\n          description: \"Assign unique asset numbers to line items on SAP Ariba purchase requisitions.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"ariba-asset-mgmt.update-asset-line-items\"\n          with:\n            realm: \"tools.realm\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/ariba-guided-buying/refs/heads/main/capabilities/procurement-operations.yaml
tags:
- Ariba
- Asset Management
- Catalog
- Procurement
- SAP
- Shopping
tools:
- description: Retrieve catalog items and facets from an SAP Ariba shop on SAP Business Network.
  hints:
    openWorld: true
    readOnly: true
  name: get-shop-catalog
- description: List catalog items with details from an SAP Ariba shop.
  hints:
    openWorld: true
    readOnly: true
  name: list-catalog-items
- description: Get typeahead search suggestions from an SAP Ariba catalog.
  hints:
    openWorld: true
    readOnly: true
  name: search-catalog
- description: List SAP Ariba purchase requisitions containing asset line items pending asset assignment.
  hints:
    openWorld: false
    readOnly: true
  name: list-asset-requisitions
- description: Get total count of asset-based purchase requisitions in SAP Ariba.
  hints:
    openWorld: false
    readOnly: true
  name: count-asset-requisitions
- description: Assign unique asset numbers to line items on SAP Ariba purchase requisitions.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: assign-asset-numbers
---
