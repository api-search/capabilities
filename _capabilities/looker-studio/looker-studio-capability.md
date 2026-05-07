---
categories: []
consumed_apis: []
description: The Looker Studio API enables developers to programmatically manage reports, data sources, and permissions. It provides methods for searching assets and managing asset permissions including getting, updating, adding, and removing members. The API is available to users that belong to an organization with Google Workspace or Cloud Identity.
layout: capability
name: Looker Studio API
operations:
- description: Search Looker Studio assets
  method: GET
  name: searchassets
  path: /assets:search
- description: Looker Studio Get asset permissions
  method: GET
  name: getassetpermissions
  path: /assets/{assetId}/permissions
- description: Looker Studio Update asset permissions
  method: PATCH
  name: updateassetpermissions
  path: /assets/{assetId}/permissions
- description: Looker Studio Add members to asset permissions
  method: POST
  name: addassetmembers
  path: /assets/{assetId}/permissions:addMembers
- description: Looker Studio Revoke all permissions for members
  method: POST
  name: revokeallassetpermissions
  path: /assets/{assetId}/permissions:revokeAllPermissions
personas: []
provider_name: Looker Studio
provider_slug: looker-studio
search_terms:
- analytics
- revokeallassetpermissions
- looker studio add members to asset permissions
- api
- updateassetpermissions
- looker studio update asset permissions
- looker studio get asset permissions
- searchassets
- google
- business intelligence
- looker
- search looker studio assets
- reports
- dashboards
- studio
- looker studio revoke all permissions for members
- addassetmembers
- getassetpermissions
- data visualization
slug: looker-studio-capability
source_filename: looker-studio-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Looker Studio API\n  description: The Looker Studio API enables developers to programmatically manage reports, data sources, and permissions.\n    It provides methods for searching assets and managing asset permissions including getting, updating, adding, and removing\n    members. The API is available to users that belong to an organization with Google Workspace or Cloud Identity.\n  tags:\n  - Looker\n  - Studio\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: looker-studio\n    baseUri: https://datastudio.googleapis.com/v1\n    description: Looker Studio API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{LOOKER_STUDIO_TOKEN}}'\n    resources:\n    - name: assets-search\n      path: /assets:search\n      operations:\n      - name: searchassets\n        method: GET\n        description: Search Looker Studio assets\n        inputParameters:\n    \
  \    - name: assetTypes\n          in: query\n          type: array\n          required: true\n          description: The types of assets to search for. Valid values are REPORT and DATA_SOURCE.\n        - name: title\n          in: query\n          type: string\n          description: Filter assets by title (partial match).\n        - name: includeTrash\n          in: query\n          type: boolean\n          description: Whether to include trashed assets in the results.\n        - name: orderBy\n          in: query\n          type: string\n          description: Field to order results by, such as title, createTime, or updateTime.\n        - name: pageSize\n          in: query\n          type: integer\n          description: Maximum number of assets to return per page.\n        - name: pageToken\n          in: query\n          type: string\n          description: Token for retrieving the next page of results.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n    - name: assets-assetid-permissions\n      path: /assets/{assetId}/permissions\n      operations:\n      - name: getassetpermissions\n        method: GET\n        description: Looker Studio Get asset permissions\n        inputParameters:\n        - name: assetId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the Looker Studio asset.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateassetpermissions\n        method: PATCH\n        description: Looker Studio Update asset permissions\n        inputParameters:\n        - name: assetId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the Looker Studio asset.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n    - name: assets-assetid-permissions-addmembers\n      path: /assets/{assetId}/permissions:addMembers\n      operations:\n      - name: addassetmembers\n        method: POST\n        description: Looker Studio Add members to asset permissions\n        inputParameters:\n        - name: assetId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the Looker Studio asset.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: assets-assetid-permissions-revokeallpermissions\n      path: /assets/{assetId}/permissions:revokeAllPermissions\n      operations:\n      - name: revokeallassetpermissions\n        method: POST\n        description: Looker Studio Revoke all permissions for members\n        inputParameters:\n        - name: assetId\n          in: path\n          type: string\n          required: true\n          description:\
  \ The unique identifier of the Looker Studio asset.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: looker-studio-rest\n    description: REST adapter for Looker Studio API.\n    resources:\n    - path: /assets:search\n      name: searchassets\n      operations:\n      - method: GET\n        name: searchassets\n        description: Search Looker Studio assets\n        call: looker-studio.searchassets\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /assets/{assetId}/permissions\n      name: getassetpermissions\n      operations:\n      - method: GET\n        name: getassetpermissions\n        description: Looker Studio Get asset permissions\n        call: looker-studio.getassetpermissions\n        with:\n          assetId: rest.assetId\n        outputParameters:\n        - type: object\n          mapping: $.\n  \
  \  - path: /assets/{assetId}/permissions\n      name: updateassetpermissions\n      operations:\n      - method: PATCH\n        name: updateassetpermissions\n        description: Looker Studio Update asset permissions\n        call: looker-studio.updateassetpermissions\n        with:\n          assetId: rest.assetId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /assets/{assetId}/permissions:addMembers\n      name: addassetmembers\n      operations:\n      - method: POST\n        name: addassetmembers\n        description: Looker Studio Add members to asset permissions\n        call: looker-studio.addassetmembers\n        with:\n          assetId: rest.assetId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /assets/{assetId}/permissions:revokeAllPermissions\n      name: revokeallassetpermissions\n      operations:\n      - method: POST\n        name: revokeallassetpermissions\n        description: Looker Studio\
  \ Revoke all permissions for members\n        call: looker-studio.revokeallassetpermissions\n        with:\n          assetId: rest.assetId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: looker-studio-mcp\n    transport: http\n    description: MCP adapter for Looker Studio API for AI agent use.\n    tools:\n    - name: searchassets\n      description: Search Looker Studio assets\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: looker-studio.searchassets\n      with:\n        assetTypes: tools.assetTypes\n        title: tools.title\n        includeTrash: tools.includeTrash\n        orderBy: tools.orderBy\n        pageSize: tools.pageSize\n        pageToken: tools.pageToken\n      inputParameters:\n      - name: assetTypes\n        type: array\n        description: The types of assets to search for. Valid values are REPORT and DATA_SOURCE.\n        required: true\n\
  \      - name: title\n        type: string\n        description: Filter assets by title (partial match).\n      - name: includeTrash\n        type: boolean\n        description: Whether to include trashed assets in the results.\n      - name: orderBy\n        type: string\n        description: Field to order results by, such as title, createTime, or updateTime.\n      - name: pageSize\n        type: integer\n        description: Maximum number of assets to return per page.\n      - name: pageToken\n        type: string\n        description: Token for retrieving the next page of results.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getassetpermissions\n      description: Looker Studio Get asset permissions\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: looker-studio.getassetpermissions\n      with:\n        assetId: tools.assetId\n      inputParameters:\n      - name: assetId\n        type: string\n\
  \        description: The unique identifier of the Looker Studio asset.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateassetpermissions\n      description: Looker Studio Update asset permissions\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: looker-studio.updateassetpermissions\n      with:\n        assetId: tools.assetId\n      inputParameters:\n      - name: assetId\n        type: string\n        description: The unique identifier of the Looker Studio asset.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: addassetmembers\n      description: Looker Studio Add members to asset permissions\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: looker-studio.addassetmembers\n      with:\n        assetId: tools.assetId\n      inputParameters:\n      - name: assetId\n\
  \        type: string\n        description: The unique identifier of the Looker Studio asset.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: revokeallassetpermissions\n      description: Looker Studio Revoke all permissions for members\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: looker-studio.revokeallassetpermissions\n      with:\n        assetId: tools.assetId\n      inputParameters:\n      - name: assetId\n        type: string\n        description: The unique identifier of the Looker Studio asset.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    LOOKER_STUDIO_TOKEN: LOOKER_STUDIO_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/looker-studio/refs/heads/main/capabilities/looker-studio-capability.yaml
tags:
- Looker
- Studio
- API
tools:
- description: Search Looker Studio assets
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: searchassets
- description: Looker Studio Get asset permissions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getassetpermissions
- description: Looker Studio Update asset permissions
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateassetpermissions
- description: Looker Studio Add members to asset permissions
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: addassetmembers
- description: Looker Studio Revoke all permissions for members
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: revokeallassetpermissions
---
