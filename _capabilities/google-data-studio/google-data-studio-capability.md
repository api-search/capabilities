---
categories: []
consumed_apis: []
description: The Looker Studio API (formerly Google Data Studio API) enables programmatic management of Looker Studio assets, including searching for assets and managing permissions within Google Workspace or Cloud Identity organizations. The API is only available to users that belong to an organization with Google Workspace or Cloud Identity.
layout: capability
name: Google Data Studio API
operations:
- description: Google Data Studio Search Looker Studio assets
  method: GET
  name: searchassets
  path: /assets:search
- description: Google Data Studio Get asset permissions
  method: GET
  name: getpermissions
  path: /assets/{assetName}/permissions
- description: Google Data Studio Update asset permissions
  method: PATCH
  name: patchpermissions
  path: /assets/{assetName}/permissions
- description: Google Data Studio Add members to an asset
  method: POST
  name: addmembers
  path: /assets/{assetName}/permissions:addMembers
- description: Google Data Studio Revoke all permissions for members
  method: POST
  name: revokeallpermissions
  path: /assets/{assetName}/permissions:revokeAllPermissions
personas: []
provider_name: Google Data Studio
provider_slug: google-data-studio
search_terms:
- visualization
- analytics
- google data studio add members to an asset
- api
- searchassets
- google
- addmembers
- business intelligence
- revokeallpermissions
- dashboards
- getpermissions
- google data studio get asset permissions
- studio
- google data studio search looker studio assets
- patchpermissions
- google data studio update asset permissions
- reporting
- data
- google data studio revoke all permissions for members
slug: google-data-studio-capability
source_filename: google-data-studio-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google Data Studio API\n  description: The Looker Studio API (formerly Google Data Studio API) enables programmatic management of Looker Studio assets,\n    including searching for assets and managing permissions within Google Workspace or Cloud Identity organizations. The API\n    is only available to users that belong to an organization with Google Workspace or Cloud Identity.\n  tags:\n  - Google\n  - Data\n  - Studio\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: google-data-studio\n    baseUri: https://datastudio.googleapis.com/v1\n    description: Google Data Studio API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{GOOGLE_DATA_STUDIO_TOKEN}}'\n    resources:\n    - name: assets-search\n      path: /assets:search\n      operations:\n      - name: searchassets\n        method: GET\n        description: Google Data Studio Search Looker Studio\
  \ assets\n        inputParameters:\n        - name: assetTypes\n          in: query\n          type: string\n          required: true\n          description: The asset type to search. Exactly one asset type must be specified.\n        - name: title\n          in: query\n          type: string\n          description: Search string checked against asset title and description. Supports advanced search syntax including\n            creator:me, creator:user@example.com, owner:me, owner:user@\n        - name: includeTrashed\n          in: query\n          type: boolean\n          description: When true, includes only trashed assets. When false or omitted, excludes trashed assets. Defaults to\n            false.\n        - name: owner\n          in: query\n          type: string\n          description: Filter by the asset owner's email address.\n        - name: orderBy\n          in: query\n          type: string\n          description: Sort order for the results. Supported values are title,\
  \ last_viewed_by_me, create_time, last_accessed_time,\n            and id.\n        - name: pageSize\n          in: query\n          type: integer\n          description: The maximum number of results to return per page. Defaults to 1000.\n        - name: pageToken\n          in: query\n          type: string\n          description: Token for pagination. Use the nextPageToken or previousPageToken value from a prior response to retrieve\n            subsequent pages.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: assets-assetname-permissions\n      path: /assets/{assetName}/permissions\n      operations:\n      - name: getpermissions\n        method: GET\n        description: Google Data Studio Get asset permissions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: patchpermissions\n        method: PATCH\n\
  \        description: Google Data Studio Update asset permissions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: assets-assetname-permissions-addmembers\n      path: /assets/{assetName}/permissions:addMembers\n      operations:\n      - name: addmembers\n        method: POST\n        description: Google Data Studio Add members to an asset\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: assets-assetname-permissions-revokeallpermission\n      path: /assets/{assetName}/permissions:revokeAllPermissions\n      operations:\n      - name: revokeallpermissions\n        method: POST\n        description: Google Data Studio Revoke all permissions for members\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n \
  \   port: 8080\n    namespace: google-data-studio-rest\n    description: REST adapter for Google Data Studio API.\n    resources:\n    - path: /assets:search\n      name: searchassets\n      operations:\n      - method: GET\n        name: searchassets\n        description: Google Data Studio Search Looker Studio assets\n        call: google-data-studio.searchassets\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /assets/{assetName}/permissions\n      name: getpermissions\n      operations:\n      - method: GET\n        name: getpermissions\n        description: Google Data Studio Get asset permissions\n        call: google-data-studio.getpermissions\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /assets/{assetName}/permissions\n      name: patchpermissions\n      operations:\n      - method: PATCH\n        name: patchpermissions\n        description: Google Data Studio Update asset permissions\n        call:\
  \ google-data-studio.patchpermissions\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /assets/{assetName}/permissions:addMembers\n      name: addmembers\n      operations:\n      - method: POST\n        name: addmembers\n        description: Google Data Studio Add members to an asset\n        call: google-data-studio.addmembers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /assets/{assetName}/permissions:revokeAllPermissions\n      name: revokeallpermissions\n      operations:\n      - method: POST\n        name: revokeallpermissions\n        description: Google Data Studio Revoke all permissions for members\n        call: google-data-studio.revokeallpermissions\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: google-data-studio-mcp\n    transport: http\n    description: MCP adapter for Google Data Studio API for AI agent use.\n    tools:\n\
  \    - name: searchassets\n      description: Google Data Studio Search Looker Studio assets\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-data-studio.searchassets\n      with:\n        assetTypes: tools.assetTypes\n        title: tools.title\n        includeTrashed: tools.includeTrashed\n        owner: tools.owner\n        orderBy: tools.orderBy\n        pageSize: tools.pageSize\n        pageToken: tools.pageToken\n      inputParameters:\n      - name: assetTypes\n        type: string\n        description: The asset type to search. Exactly one asset type must be specified.\n        required: true\n      - name: title\n        type: string\n        description: Search string checked against asset title and description. Supports advanced search syntax including\n          creator:me, creator:user@example.com, owner:me, owner:user@\n      - name: includeTrashed\n        type: boolean\n        description: When true, includes\
  \ only trashed assets. When false or omitted, excludes trashed assets. Defaults to\n          false.\n      - name: owner\n        type: string\n        description: Filter by the asset owner's email address.\n      - name: orderBy\n        type: string\n        description: Sort order for the results. Supported values are title, last_viewed_by_me, create_time, last_accessed_time,\n          and id.\n      - name: pageSize\n        type: integer\n        description: The maximum number of results to return per page. Defaults to 1000.\n      - name: pageToken\n        type: string\n        description: Token for pagination. Use the nextPageToken or previousPageToken value from a prior response to retrieve\n          subsequent pages.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getpermissions\n      description: Google Data Studio Get asset permissions\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call:\
  \ google-data-studio.getpermissions\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: patchpermissions\n      description: Google Data Studio Update asset permissions\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-data-studio.patchpermissions\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: addmembers\n      description: Google Data Studio Add members to an asset\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-data-studio.addmembers\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: revokeallpermissions\n      description: Google Data Studio Revoke all permissions for members\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-data-studio.revokeallpermissions\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    GOOGLE_DATA_STUDIO_TOKEN: GOOGLE_DATA_STUDIO_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-data-studio/refs/heads/main/capabilities/google-data-studio-capability.yaml
tags:
- Google
- Data
- Studio
- API
tools:
- description: Google Data Studio Search Looker Studio assets
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: searchassets
- description: Google Data Studio Get asset permissions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getpermissions
- description: Google Data Studio Update asset permissions
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: patchpermissions
- description: Google Data Studio Add members to an asset
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: addmembers
- description: Google Data Studio Revoke all permissions for members
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: revokeallpermissions
---
