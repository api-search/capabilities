---
categories: []
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
- get licensing statistics
- license image
- get the stock content category tree
- get license stats
- get the license history for the authenticated member
- get license history
- stock content search
- get the authenticated member profile
- adobe
- stock content categories
- get category tree
- get licensing statistics for the authenticated member
- search the adobe stock library for photos, illustrations, vectors, and videos
- license a stock video clip
- content sourcing
- get the hierarchical category tree for adobe stock content
- video
- get detailed metadata for a specific stock file by content id
- get the authenticated adobe stock member profile and quota information
- license a stock photo for use in a project
- license a vector or illustration for use in a project
- get metadata for a specific stock file
- get member profile
- video licensing
- digital assets
- image licensing
- license history
- vector and illustration licensing
- license video
- stock file metadata
- licensing
- license a vector or illustration
- creative
- photography
- design
- search
- license a stock photo
- licensing statistics
- license vector
- license a stock video clip for use in a project
- get stock file metadata
- graphics
- get license history for the member
- stock
- search the adobe stock library
- member profile and quota
- search stock files
slug: stock-asset-sourcing
source_filename: stock-asset-sourcing.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Adobe Stock Asset Sourcing\"\n  description: \"Stock asset discovery, licensing, and management workflow using the Adobe Stock API. Used by content curators, marketing teams, and creative directors to search for stock photos, illustrations, vectors, and videos, license them for projects, and manage licensing history and quotas.\"\n  tags:\n    - Adobe\n    - Stock\n    - Digital Assets\n    - Licensing\n    - Content Sourcing\n    - Search\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      ADOBE_STOCK_TOKEN: ADOBE_STOCK_TOKEN\n      ADOBE_STOCK_API_KEY: ADOBE_STOCK_API_KEY\n\ncapability:\n  consumes:\n    - import: stock\n      location: ./shared/stock.yaml\n\n  exposes:\n    - type: rest\n      port: 8084\n      namespace: stock-asset-sourcing-api\n      description: \"Unified REST API for stock asset discovery, licensing, and management using Adobe Stock.\"\n      resources:\n\
  \        - path: /v1/stock-files\n          name: stock-files\n          description: \"Stock content search\"\n          operations:\n            - method: GET\n              name: search-stock-files\n              description: \"Search the Adobe Stock library\"\n              call: \"stock.search-stock-files\"\n              with:\n                search_parameters[words]: \"rest.keywords\"\n                search_parameters[limit]: \"rest.limit\"\n                search_parameters[offset]: \"rest.offset\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/stock-files/{content_id}\n          name: stock-file-detail\n          description: \"Stock file metadata\"\n          operations:\n            - method: GET\n              name: get-stock-file-metadata\n              description: \"Get metadata for a specific stock file\"\n              call: \"stock.get-stock-file-metadata\"\n              with:\n           \
  \     content_id: \"rest.content_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/categories\n          name: categories\n          description: \"Stock content categories\"\n          operations:\n            - method: GET\n              name: get-category-tree\n              description: \"Get the stock content category tree\"\n              call: \"stock.get-category-tree\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/members/profile\n          name: member-profile\n          description: \"Member profile and quota\"\n          operations:\n            - method: GET\n              name: get-member-profile\n              description: \"Get the authenticated member profile\"\n              call: \"stock.get-member-profile\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    \
  \    - path: /v1/licenses\n          name: licenses\n          description: \"License history\"\n          operations:\n            - method: GET\n              name: get-license-history\n              description: \"Get license history for the member\"\n              call: \"stock.get-license-history\"\n              with:\n                search_parameters[limit]: \"rest.limit\"\n                search_parameters[offset]: \"rest.offset\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/licenses/images\n          name: license-images\n          description: \"Image licensing\"\n          operations:\n            - method: POST\n              name: license-image\n              description: \"License a stock photo\"\n              call: \"stock.license-image\"\n              with:\n                content_id: \"rest.content_id\"\n                license: \"rest.license\"\n              outputParameters:\n        \
  \        - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/licenses/vectors\n          name: license-vectors\n          description: \"Vector and illustration licensing\"\n          operations:\n            - method: POST\n              name: license-vector\n              description: \"License a vector or illustration\"\n              call: \"stock.license-vector\"\n              with:\n                content_id: \"rest.content_id\"\n                license: \"rest.license\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/licenses/videos\n          name: license-videos\n          description: \"Video licensing\"\n          operations:\n            - method: POST\n              name: license-video\n              description: \"License a stock video clip\"\n              call: \"stock.license-video\"\n              with:\n                content_id: \"rest.content_id\"\n                license:\
  \ \"rest.license\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/licenses/stats\n          name: license-stats\n          description: \"Licensing statistics\"\n          operations:\n            - method: POST\n              name: get-license-stats\n              description: \"Get licensing statistics\"\n              call: \"stock.get-license-stats\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9094\n      namespace: stock-asset-sourcing-mcp\n      transport: http\n      description: \"MCP server for AI-assisted stock asset discovery and licensing using Adobe Stock.\"\n      tools:\n        - name: search-stock-files\n          description: \"Search the Adobe Stock library for photos, illustrations, vectors, and videos\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent:\
  \ true\n          call: \"stock.search-stock-files\"\n          with:\n            search_parameters[words]: \"tools.keywords\"\n            search_parameters[limit]: \"tools.limit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-stock-file-metadata\n          description: \"Get detailed metadata for a specific stock file by content ID\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"stock.get-stock-file-metadata\"\n          with:\n            content_id: \"tools.content_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-category-tree\n          description: \"Get the hierarchical category tree for Adobe Stock content\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"stock.get-category-tree\"\n       \
  \   outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-member-profile\n          description: \"Get the authenticated Adobe Stock member profile and quota information\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"stock.get-member-profile\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-license-history\n          description: \"Get the license history for the authenticated member\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"stock.get-license-history\"\n          with:\n            search_parameters[limit]: \"tools.limit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: license-image\n          description: \"License a stock photo for use in a project\"\n\
  \          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"stock.license-image\"\n          with:\n            content_id: \"tools.content_id\"\n            license: \"tools.license\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: license-vector\n          description: \"License a vector or illustration for use in a project\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"stock.license-vector\"\n          with:\n            content_id: \"tools.content_id\"\n            license: \"tools.license\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: license-video\n          description: \"License a stock video clip for use in a project\"\n          hints:\n            readOnly: false\n            destructive: false\n         \
  \   idempotent: false\n          call: \"stock.license-video\"\n          with:\n            content_id: \"tools.content_id\"\n            license: \"tools.license\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-license-stats\n          description: \"Get licensing statistics for the authenticated member\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"stock.get-license-stats\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/adobe-creative-suite/refs/heads/main/capabilities/stock-asset-sourcing.yaml
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
