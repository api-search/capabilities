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
- get shop
- count asset-based requisitions.
- assign unique asset numbers to line items on sap ariba purchase requisitions.
- unified catalog shopping and asset management workflow
- get shop catalog
- employee who uses guided buying to search catalogs and create purchase requests.
- count requisitions
- requisition count.
- requisitions
- retrieve catalog items and facets from an sap ariba shop on sap business network.
- list requisitions
- erp
- supply chain
- asset-based purchase requisitions.
- batch asset assignment.
- b2b
- Enterprise Buyer
- catalog shop items and facets.
- catalog item listing.
- shopping
- assign asset numbers
- autocomplete
- search catalog
- tracking and assignment of asset numbers to purchased items.
- list catalog items
- count asset requisitions
- list purchase requisitions with asset items.
- get catalog items and facets from sap business network.
- get typeahead search suggestions from an sap ariba catalog.
- get search suggestions from catalog.
- list items
- asset management
- get total count of asset-based purchase requisitions in sap ariba.
- administrator who manages asset assignments and procurement workflows.
- procurement
- catalog
- ariba
- catalog search typeahead.
- Procurement Administrator
- list catalog items with details from an sap ariba shop.
- list sap ariba purchase requisitions containing asset line items pending asset assignment.
- sap
- list asset requisitions
- management of supplier product catalogs on sap business network.
- list catalog items from a shop.
- assign asset numbers to requisition line items.
- update assets
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
