---
consumed_apis:
- stock
description: Stock asset discovery, licensing, and management workflow using the Adobe Stock API. Used by content curators, marketing teams, and creative directors to search for stock photos, illustrations, vectors, and videos, license them for projects, and manage licensing history and quotas.
layout: capability
name: Adobe Stock Asset Sourcing
operations:
- description: Search the Adobe Stock library
  method: GET
  name: search-stock-files
  path: /v1/stock-files
- description: Get metadata for a specific stock file
  method: GET
  name: get-stock-file-metadata
  path: /v1/stock-files/{content_id}
- description: Get the stock content category tree
  method: GET
  name: get-category-tree
  path: /v1/categories
- description: Get the authenticated member profile
  method: GET
  name: get-member-profile
  path: /v1/members/profile
- description: Get license history for the member
  method: GET
  name: get-license-history
  path: /v1/licenses
- description: License a stock photo
  method: POST
  name: license-image
  path: /v1/licenses/images
- description: License a vector or illustration
  method: POST
  name: license-vector
  path: /v1/licenses/vectors
- description: License a stock video clip
  method: POST
  name: license-video
  path: /v1/licenses/videos
- description: Get licensing statistics
  method: POST
  name: get-license-stats
  path: /v1/licenses/stats
personas: []
provider_name: Adobe Creative Suite
provider_slug: adobe-creative-suite
search_terms:
- license vector
- license video
- digital assets
- license history
- stock file metadata
- get the license history for the authenticated member
- search the adobe stock library for photos, illustrations, vectors, and videos
- search stock files
- get the authenticated adobe stock member profile and quota information
- search the adobe stock library
- license image
- design
- stock content search
- photography
- search
- get licensing statistics for the authenticated member
- get category tree
- get stock file metadata
- member profile and quota
- get license history
- get license history for the member
- adobe
- get license stats
- vector and illustration licensing
- get the hierarchical category tree for adobe stock content
- get the authenticated member profile
- license a stock video clip for use in a project
- get detailed metadata for a specific stock file by content id
- get the stock content category tree
- stock content categories
- stock
- license a stock photo for use in a project
- license a stock video clip
- creative
- get metadata for a specific stock file
- license a vector or illustration
- licensing statistics
- video licensing
- license a vector or illustration for use in a project
- video
- graphics
- get member profile
- get licensing statistics
- license a stock photo
- licensing
- content sourcing
- image licensing
slug: stock-asset-sourcing
tags:
- Adobe
- Stock
- Digital Assets
- Licensing
- Content Sourcing
- Search
tools:
- description: Search the Adobe Stock library for photos, illustrations, vectors, and videos
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: search-stock-files
- description: Get detailed metadata for a specific stock file by content ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-stock-file-metadata
- description: Get the hierarchical category tree for Adobe Stock content
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-category-tree
- description: Get the authenticated Adobe Stock member profile and quota information
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-member-profile
- description: Get the license history for the authenticated member
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-license-history
- description: License a stock photo for use in a project
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: license-image
- description: License a vector or illustration for use in a project
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: license-vector
- description: License a stock video clip for use in a project
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: license-video
- description: Get licensing statistics for the authenticated member
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-license-stats
---
