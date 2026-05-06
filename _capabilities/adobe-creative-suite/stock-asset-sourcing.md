---
categories: []
consumed_apis: []
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
- stock content categories
- video licensing
- graphics
- content sourcing
- image licensing
- get license history
- search stock files
- license a vector or illustration for use in a project
- license video
- design
- stock
- creative
- get member profile
- get the authenticated member profile
- get licensing statistics
- license a stock video clip for use in a project
- license a vector or illustration
- photography
- stock content search
- license image
- vector and illustration licensing
- licensing statistics
- stock file metadata
- license history
- search the adobe stock library
- license vector
- digital assets
- member profile and quota
- license a stock photo
- get stock file metadata
- get licensing statistics for the authenticated member
- search
- video
- get metadata for a specific stock file
- adobe
- get the hierarchical category tree for adobe stock content
- search the adobe stock library for photos, illustrations, vectors, and videos
- get the stock content category tree
- get category tree
- get license stats
- get the license history for the authenticated member
- get the authenticated adobe stock member profile and quota information
- get detailed metadata for a specific stock file by content id
- license a stock photo for use in a project
- license a stock video clip
- licensing
- get license history for the member
slug: stock-asset-sourcing
source_filename: stock-asset-sourcing.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Adobe Stock Asset Sourcing\n  description: Stock asset discovery, licensing, and management workflow using the Adobe Stock API. Used by content curators,\n    marketing teams, and creative directors to search for stock photos, illustrations, vectors, and videos, license them for\n    projects, and manage licensing history and quotas.\n  tags:\n  - Adobe\n  - Stock\n  - Digital Assets\n  - Licensing\n  - Content Sourcing\n  - Search\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    ADOBE_STOCK_TOKEN: ADOBE_STOCK_TOKEN\n    ADOBE_STOCK_API_KEY: ADOBE_STOCK_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: stock\n    baseUri: https://stock.adobe.io/Rest\n    description: Adobe Stock API for searching and licensing stock content\n    authentication:\n      type: bearer\n      token: '{{ADOBE_STOCK_TOKEN}}'\n    resources:\n    - name: search\n      path: /Media/1/Search\n      description:\
  \ Search and discover stock content\n      operations:\n      - name: search-stock-files\n        method: GET\n        path: /Files\n        description: Searches the Adobe Stock library for files matching specified criteria\n        inputParameters:\n        - name: locale\n          in: query\n          type: string\n          required: false\n          description: BCP 47 locale code for localized search results\n        - name: search_parameters[words]\n          in: query\n          type: string\n          required: false\n          description: Keywords to search for in the stock library\n        - name: search_parameters[limit]\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results to return per page (1-64)\n        - name: search_parameters[offset]\n          in: query\n          type: integer\n          required: false\n          description: Number of results to skip for pagination\n        - name: search_parameters[filters][content_type:photo]\n\
  \          in: query\n          type: integer\n          required: false\n          description: Include photos in results (1 = include, 0 = exclude)\n        - name: search_parameters[filters][content_type:illustration]\n          in: query\n          type: integer\n          required: false\n          description: Include illustrations in results (1 = include, 0 = exclude)\n        - name: search_parameters[filters][content_type:vector]\n          in: query\n          type: integer\n          required: false\n          description: Include vector files in results (1 = include, 0 = exclude)\n        - name: search_parameters[filters][content_type:video]\n          in: query\n          type: integer\n          required: false\n          description: Include video files in results (1 = include, 0 = exclude)\n        - name: search_parameters[filters][orientation]\n          in: query\n          type: string\n          required: false\n          description: Filter by image orientation\n\
  \        - name: search_parameters[filters][premium]\n          in: query\n          type: string\n          required: false\n          description: Filter by premium status\n        - name: result_columns[]\n          in: query\n          type: array\n          required: false\n          description: Fields to include in the response\n        - name: x-api-key\n          in: header\n          type: string\n          required: true\n          description: Adobe Stock API key (client ID)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-stock-file-metadata\n        method: GET\n        path: /Files/{content_id}\n        description: Retrieves detailed metadata for a specific stock file by its content ID\n        inputParameters:\n        - name: content_id\n          in: path\n          type: integer\n          required: true\n          description: Adobe Stock unique content identifier\n   \
  \     - name: locale\n          in: query\n          type: string\n          required: false\n          description: BCP 47 locale for localized response data\n        - name: result_columns[]\n          in: query\n          type: array\n          required: false\n          description: Fields to include in the response\n        - name: x-api-key\n          in: header\n          type: string\n          required: true\n          description: Adobe Stock API key (client ID)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-category-tree\n        method: GET\n        path: /CategoryTree\n        description: Retrieves the hierarchical category tree used to organize Adobe Stock content\n        inputParameters:\n        - name: locale\n          in: query\n          type: string\n          required: false\n          description: BCP 47 locale for localized category names\n        - name: category_id\n\
  \          in: query\n          type: integer\n          required: false\n          description: Root category ID to retrieve subtree from\n        - name: x-api-key\n          in: header\n          type: string\n          required: true\n          description: Adobe Stock API key (client ID)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: member\n      path: /Member/1\n      description: Member profile and licensing operations\n      operations:\n      - name: get-member-profile\n        method: GET\n        path: /Profile\n        description: Retrieves the profile of the authenticated Adobe Stock member including quota information\n        inputParameters:\n        - name: locale\n          in: query\n          type: string\n          required: false\n          description: BCP 47 locale for localized profile data\n        - name: x-api-key\n          in: header\n          type: string\n    \
  \      required: true\n          description: Adobe Stock API key (client ID)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: license\n      path: /Member/1\n      description: License stock assets for use in projects\n      operations:\n      - name: get-license-history\n        method: GET\n        path: /License\n        description: Retrieves the license history for the authenticated member\n        inputParameters:\n        - name: locale\n          in: query\n          type: string\n          required: false\n          description: BCP 47 locale for localized response data\n        - name: search_parameters[limit]\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results to return\n        - name: search_parameters[offset]\n          in: query\n          type: integer\n          required: false\n          description: Number\
  \ of results to skip for pagination\n        - name: result_columns[]\n          in: query\n          type: array\n          required: false\n          description: Fields to include in the license history response\n        - name: x-api-key\n          in: header\n          type: string\n          required: true\n          description: Adobe Stock API key (client ID)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: license-image\n        method: POST\n        path: /LicenseImage\n        description: Licenses a stock photo for use in a project\n        inputParameters:\n        - name: x-api-key\n          in: header\n          type: string\n          required: true\n          description: Adobe Stock API key (client ID)\n        body:\n          type: json\n          data:\n            content_id: '{{tools.content_id}}'\n            license: '{{tools.license}}'\n            locale: '{{tools.locale}}'\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: license-vector\n        method: POST\n        path: /LicenseVectorOrIllustration\n        description: Licenses a vector or illustration stock file for use in a project\n        inputParameters:\n        - name: x-api-key\n          in: header\n          type: string\n          required: true\n          description: Adobe Stock API key (client ID)\n        body:\n          type: json\n          data:\n            content_id: '{{tools.content_id}}'\n            license: '{{tools.license}}'\n            locale: '{{tools.locale}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: license-video\n        method: POST\n        path: /LicenseVideo\n        description: Licenses a stock video clip for use in a project\n        inputParameters:\n        - name: x-api-key\n\
  \          in: header\n          type: string\n          required: true\n          description: Adobe Stock API key (client ID)\n        body:\n          type: json\n          data:\n            content_id: '{{tools.content_id}}'\n            license: '{{tools.license}}'\n            locale: '{{tools.locale}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-license-stats\n        method: POST\n        path: /LicenseStats\n        description: Retrieves licensing statistics for the authenticated member\n        inputParameters:\n        - name: x-api-key\n          in: header\n          type: string\n          required: true\n          description: Adobe Stock API key (client ID)\n        body:\n          type: json\n          data:\n            locale: '{{tools.locale}}'\n            result_columns: '{{tools.result_columns}}'\n        outputRawFormat: json\n        outputParameters:\n    \
  \    - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8084\n    namespace: stock-asset-sourcing-api\n    description: Unified REST API for stock asset discovery, licensing, and management using Adobe Stock.\n    resources:\n    - path: /v1/stock-files\n      name: stock-files\n      description: Stock content search\n      operations:\n      - method: GET\n        name: search-stock-files\n        description: Search the Adobe Stock library\n        call: stock.search-stock-files\n        with:\n          search_parameters[words]: rest.keywords\n          search_parameters[limit]: rest.limit\n          search_parameters[offset]: rest.offset\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/stock-files/{content_id}\n      name: stock-file-detail\n      description: Stock file metadata\n      operations:\n      - method: GET\n        name: get-stock-file-metadata\n        description: Get metadata\
  \ for a specific stock file\n        call: stock.get-stock-file-metadata\n        with:\n          content_id: rest.content_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/categories\n      name: categories\n      description: Stock content categories\n      operations:\n      - method: GET\n        name: get-category-tree\n        description: Get the stock content category tree\n        call: stock.get-category-tree\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/members/profile\n      name: member-profile\n      description: Member profile and quota\n      operations:\n      - method: GET\n        name: get-member-profile\n        description: Get the authenticated member profile\n        call: stock.get-member-profile\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/licenses\n      name: licenses\n      description: License history\n      operations:\n\
  \      - method: GET\n        name: get-license-history\n        description: Get license history for the member\n        call: stock.get-license-history\n        with:\n          search_parameters[limit]: rest.limit\n          search_parameters[offset]: rest.offset\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/licenses/images\n      name: license-images\n      description: Image licensing\n      operations:\n      - method: POST\n        name: license-image\n        description: License a stock photo\n        call: stock.license-image\n        with:\n          content_id: rest.content_id\n          license: rest.license\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/licenses/vectors\n      name: license-vectors\n      description: Vector and illustration licensing\n      operations:\n      - method: POST\n        name: license-vector\n        description: License a vector or illustration\n       \
  \ call: stock.license-vector\n        with:\n          content_id: rest.content_id\n          license: rest.license\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/licenses/videos\n      name: license-videos\n      description: Video licensing\n      operations:\n      - method: POST\n        name: license-video\n        description: License a stock video clip\n        call: stock.license-video\n        with:\n          content_id: rest.content_id\n          license: rest.license\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/licenses/stats\n      name: license-stats\n      description: Licensing statistics\n      operations:\n      - method: POST\n        name: get-license-stats\n        description: Get licensing statistics\n        call: stock.get-license-stats\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9094\n    namespace: stock-asset-sourcing-mcp\n\
  \    transport: http\n    description: MCP server for AI-assisted stock asset discovery and licensing using Adobe Stock.\n    tools:\n    - name: search-stock-files\n      description: Search the Adobe Stock library for photos, illustrations, vectors, and videos\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: stock.search-stock-files\n      with:\n        search_parameters[words]: tools.keywords\n        search_parameters[limit]: tools.limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-stock-file-metadata\n      description: Get detailed metadata for a specific stock file by content ID\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: stock.get-stock-file-metadata\n      with:\n        content_id: tools.content_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-category-tree\n      description: Get the\
  \ hierarchical category tree for Adobe Stock content\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: stock.get-category-tree\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-member-profile\n      description: Get the authenticated Adobe Stock member profile and quota information\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: stock.get-member-profile\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-license-history\n      description: Get the license history for the authenticated member\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: stock.get-license-history\n      with:\n        search_parameters[limit]: tools.limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: license-image\n      description: License a stock photo\
  \ for use in a project\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: stock.license-image\n      with:\n        content_id: tools.content_id\n        license: tools.license\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: license-vector\n      description: License a vector or illustration for use in a project\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: stock.license-vector\n      with:\n        content_id: tools.content_id\n        license: tools.license\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: license-video\n      description: License a stock video clip for use in a project\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: stock.license-video\n      with:\n        content_id: tools.content_id\n        license: tools.license\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: get-license-stats\n      description: Get licensing statistics for the authenticated member\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: stock.get-license-stats\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
