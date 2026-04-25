---
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
- procurement
- get typeahead search suggestions from an sap ariba catalog.
- get shop catalog
- get total count of asset-based purchase requisitions in sap ariba.
- list catalog items from a shop.
- list sap ariba purchase requisitions containing asset line items pending asset assignment.
- ariba
- requisitions
- unified catalog shopping and asset management workflow
- retrieve catalog items and facets from an sap ariba shop on sap business network.
- Enterprise Buyer
- administrator who manages asset assignments and procurement workflows.
- autocomplete
- list asset requisitions
- get search suggestions from catalog.
- update assets
- get shop
- asset-based purchase requisitions.
- assign asset numbers to requisition line items.
- catalog
- employee who uses guided buying to search catalogs and create purchase requests.
- count requisitions
- tracking and assignment of asset numbers to purchased items.
- sap
- list items
- b2b
- management of supplier product catalogs on sap business network.
- Procurement Administrator
- assign unique asset numbers to line items on sap ariba purchase requisitions.
- get catalog items and facets from sap business network.
- supply chain
- count asset-based requisitions.
- count asset requisitions
- requisition count.
- catalog item listing.
- batch asset assignment.
- asset management
- shopping
- catalog search typeahead.
- list requisitions
- list catalog items with details from an sap ariba shop.
- search catalog
- list purchase requisitions with asset items.
- list catalog items
- assign asset numbers
- erp
- catalog shop items and facets.
slug: procurement-operations
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
