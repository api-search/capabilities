---
categories: []
consumed_apis: []
description: Unified workflow combining Lightroom cloud services for catalog, asset, and album management with Firefly Services AI-powered editing. Used by photographers and creative developers to manage and enhance photos programmatically.
layout: capability
name: Adobe Lightroom Photo Management
operations:
- description: Get the user's catalog.
  method: GET
  name: get-catalog
  path: /v1/catalog
- description: List assets in a catalog.
  method: GET
  name: list-assets
  path: /v1/assets
- description: Get asset details.
  method: GET
  name: get-asset
  path: /v1/assets/{asset_id}
- description: Get a rendition.
  method: GET
  name: get-rendition
  path: /v1/assets/{asset_id}/renditions/{rendition_type}
- description: List albums.
  method: GET
  name: list-albums
  path: /v1/albums
- description: List assets in an album.
  method: GET
  name: list-album-assets
  path: /v1/albums/{album_id}/assets
- description: Apply auto tone.
  method: POST
  name: auto-tone
  path: /v1/auto-tone
- description: Apply auto straighten.
  method: POST
  name: auto-straighten
  path: /v1/auto-straighten
- description: Apply presets.
  method: POST
  name: apply-presets
  path: /v1/presets
- description: Edit an image.
  method: POST
  name: edit-image
  path: /v1/edit
personas: []
provider_name: Adobe Lightroom
provider_slug: lightroom
search_terms:
- photo albums.
- get the user's catalog.
- photo assets.
- list photo assets in a catalog.
- list assets in an album.
- get asset
- get catalog
- get a specific album.
- apply presets.
- get a specific photo asset.
- upload an original master file.
- photography
- create or update an album.
- lightroom
- preset application.
- edit image
- get the lightroom catalog.
- get xmp develop settings.
- get develop xmp
- specific asset operations.
- album assets.
- upload master
- list album assets
- apply presets
- edit an image.
- ai auto straighten.
- apply ai auto tone adjustment.
- list assets in a catalog.
- delete album
- apply ai auto straighten.
- apply auto straighten.
- get asset details.
- cloud storage
- lightroom catalog.
- add assets to an album.
- get rendition
- add assets to album
- apply programmatic edits to an image.
- list assets
- asset renditions.
- image editing
- create or update album
- get album
- adobe
- delete an album.
- auto straighten
- apply lightroom presets to an image.
- list albums
- photo management
- list photo albums.
- ai image editing
- ai auto tone.
- image editing.
- auto tone
- metadata
- get a rendition.
- list albums.
- get a rendered version of an asset.
- apply auto tone.
slug: photo-management
source_filename: photo-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Adobe Lightroom Photo Management\n  description: Unified workflow combining Lightroom cloud services for catalog, asset, and album management with Firefly Services\n    AI-powered editing. Used by photographers and creative developers to manage and enhance photos programmatically.\n  tags:\n  - Adobe\n  - Lightroom\n  - Photography\n  - AI Image Editing\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    ADOBE_OAUTH_TOKEN: ADOBE_OAUTH_TOKEN\n    ADOBE_API_KEY: ADOBE_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: lightroom-services\n    baseUri: https://lr.adobe.io/v2\n    description: Adobe Lightroom Services API for cloud catalog, assets, and albums.\n    authentication:\n      type: bearer\n      token: '{{ADOBE_OAUTH_TOKEN}}'\n    resources:\n    - name: catalog\n      path: /catalog\n      description: Lightroom catalog operations.\n      operations:\n      - name: get-health-check\n\
  \        method: GET\n        description: Check API health status.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-catalog\n        method: GET\n        description: Get the current user's catalog.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-catalog-by-id\n        method: GET\n        description: Get a catalog by ID.\n        inputParameters:\n        - name: catalog_id\n          in: path\n          type: string\n          required: true\n          description: Catalog ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: assets\n      path: /catalogs/{catalog_id}/assets\n      description: Photo and video asset operations.\n      operations:\n\
  \      - name: list-assets\n        method: GET\n        description: List assets in a catalog.\n        inputParameters:\n        - name: catalog_id\n          in: path\n          type: string\n          required: true\n          description: Catalog ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-asset\n        method: GET\n        description: Get a specific asset.\n        inputParameters:\n        - name: catalog_id\n          in: path\n          type: string\n          required: true\n          description: Catalog ID\n        - name: asset_id\n          in: path\n          type: string\n          required: true\n          description: Asset ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-or-update-asset\n        method: PUT\n        description: Create or update an asset revision.\n\
  \        inputParameters:\n        - name: catalog_id\n          in: path\n          type: string\n          required: true\n          description: Catalog ID\n        - name: asset_id\n          in: path\n          type: string\n          required: true\n          description: Asset ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: upload-master\n        method: PUT\n        description: Upload the master (original) file for an asset.\n        inputParameters:\n        - name: catalog_id\n          in: path\n          type: string\n          required: true\n          description: Catalog ID\n        - name: asset_id\n          in: path\n          type: string\n          required: true\n          description: Asset ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-develop-xmp\n        method: GET\n\
  \        description: Get the XMP develop settings for an asset.\n        inputParameters:\n        - name: catalog_id\n          in: path\n          type: string\n          required: true\n          description: Catalog ID\n        - name: asset_id\n          in: path\n          type: string\n          required: true\n          description: Asset ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: put-develop-xmp\n        method: PUT\n        description: Set the XMP develop settings for an asset.\n        inputParameters:\n        - name: catalog_id\n          in: path\n          type: string\n          required: true\n          description: Catalog ID\n        - name: asset_id\n          in: path\n          type: string\n          required: true\n          description: Asset ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n       \
  \   value: $.\n      - name: get-rendition\n        method: GET\n        description: Get a rendition of an asset.\n        inputParameters:\n        - name: catalog_id\n          in: path\n          type: string\n          required: true\n          description: Catalog ID\n        - name: asset_id\n          in: path\n          type: string\n          required: true\n          description: Asset ID\n        - name: rendition_type\n          in: path\n          type: string\n          required: true\n          description: Rendition type (thumbnail2x, 640, 1024, 2048, fullsize)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: albums\n      path: /catalogs/{catalog_id}/albums\n      description: Album management.\n      operations:\n      - name: list-albums\n        method: GET\n        description: List albums in a catalog.\n        inputParameters:\n        - name: catalog_id\n          in: path\n\
  \          type: string\n          required: true\n          description: Catalog ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-album\n        method: GET\n        description: Get a specific album.\n        inputParameters:\n        - name: catalog_id\n          in: path\n          type: string\n          required: true\n          description: Catalog ID\n        - name: album_id\n          in: path\n          type: string\n          required: true\n          description: Album ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-or-update-album\n        method: PUT\n        description: Create or update an album.\n        inputParameters:\n        - name: catalog_id\n          in: path\n          type: string\n          required: true\n          description: Catalog ID\n        - name:\
  \ album_id\n          in: path\n          type: string\n          required: true\n          description: Album ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-album\n        method: DELETE\n        description: Delete an album.\n        inputParameters:\n        - name: catalog_id\n          in: path\n          type: string\n          required: true\n          description: Catalog ID\n        - name: album_id\n          in: path\n          type: string\n          required: true\n          description: Album ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-album-assets\n        method: GET\n        description: List assets in an album.\n        inputParameters:\n        - name: catalog_id\n          in: path\n          type: string\n          required: true\n          description: Catalog\
  \ ID\n        - name: album_id\n          in: path\n          type: string\n          required: true\n          description: Album ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: add-assets-to-album\n        method: PUT\n        description: Add assets to an album.\n        inputParameters:\n        - name: catalog_id\n          in: path\n          type: string\n          required: true\n          description: Catalog ID\n        - name: album_id\n          in: path\n          type: string\n          required: true\n          description: Album ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: firefly-services\n    baseUri: https://image.adobe.io\n    description: Adobe Firefly Services Lightroom API for AI-powered image editing.\n    authentication:\n      type: bearer\n      token:\
  \ '{{ADOBE_OAUTH_TOKEN}}'\n    resources:\n    - name: editing\n      path: /lrService\n      description: AI-powered image editing operations.\n      operations:\n      - name: auto-tone\n        method: POST\n        description: Automatically adjust tonal values for optimal exposure and contrast.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            inputs:\n              href: '{{tools.input_href}}'\n              storage: '{{tools.input_storage}}'\n            outputs:\n            - href: '{{tools.output_href}}'\n              storage: '{{tools.output_storage}}'\n              type: '{{tools.output_type}}'\n      - name: auto-straighten\n        method: POST\n        description: Automatically detect and correct image horizon alignment.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            inputs:\n              href: '{{tools.input_href}}'\n              storage: '{{tools.input_storage}}'\n            outputs:\n            - href: '{{tools.output_href}}'\n              storage: '{{tools.output_storage}}'\n              type: '{{tools.output_type}}'\n      - name: apply-presets\n        method: POST\n        description: Apply Lightroom presets to an image.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            inputs:\n              href: '{{tools.input_href}}'\n              storage: '{{tools.input_storage}}'\n            outputs:\n            - href: '{{tools.output_href}}'\n              storage: '{{tools.output_storage}}'\n              type: '{{tools.output_type}}'\n\
  \      - name: edit-image\n        method: POST\n        description: Apply programmatic edits to an image.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            inputs:\n              href: '{{tools.input_href}}'\n              storage: '{{tools.input_storage}}'\n            outputs:\n            - href: '{{tools.output_href}}'\n              storage: '{{tools.output_storage}}'\n              type: '{{tools.output_type}}'\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: photo-management-api\n    description: Unified REST API for Lightroom photo management and AI editing.\n    resources:\n    - path: /v1/catalog\n      name: catalog\n      description: Lightroom catalog.\n      operations:\n      - method: GET\n        name: get-catalog\n        description: Get the user's catalog.\n        call: lightroom-services.get-catalog\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/assets\n      name: assets\n      description: Photo assets.\n      operations:\n      - method: GET\n        name: list-assets\n        description: List assets in a catalog.\n        call: lightroom-services.list-assets\n        with:\n          catalog_id: rest.catalog_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/assets/{asset_id}\n      name: asset-detail\n      description: Specific asset operations.\n      operations:\n      - method: GET\n        name: get-asset\n        description: Get asset details.\n        call: lightroom-services.get-asset\n        with:\n          catalog_id: rest.catalog_id\n          asset_id: rest.asset_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/assets/{asset_id}/renditions/{rendition_type}\n      name: renditions\n      description: Asset renditions.\n      operations:\n\
  \      - method: GET\n        name: get-rendition\n        description: Get a rendition.\n        call: lightroom-services.get-rendition\n        with:\n          catalog_id: rest.catalog_id\n          asset_id: rest.asset_id\n          rendition_type: rest.rendition_type\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/albums\n      name: albums\n      description: Photo albums.\n      operations:\n      - method: GET\n        name: list-albums\n        description: List albums.\n        call: lightroom-services.list-albums\n        with:\n          catalog_id: rest.catalog_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/albums/{album_id}/assets\n      name: album-assets\n      description: Album assets.\n      operations:\n      - method: GET\n        name: list-album-assets\n        description: List assets in an album.\n        call: lightroom-services.list-album-assets\n        with:\n        \
  \  catalog_id: rest.catalog_id\n          album_id: rest.album_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/auto-tone\n      name: auto-tone\n      description: AI auto tone.\n      operations:\n      - method: POST\n        name: auto-tone\n        description: Apply auto tone.\n        call: firefly-services.auto-tone\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/auto-straighten\n      name: auto-straighten\n      description: AI auto straighten.\n      operations:\n      - method: POST\n        name: auto-straighten\n        description: Apply auto straighten.\n        call: firefly-services.auto-straighten\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/presets\n      name: presets\n      description: Preset application.\n      operations:\n      - method: POST\n        name: apply-presets\n        description: Apply presets.\n        call: firefly-services.apply-presets\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/edit\n      name: edit\n      description: Image editing.\n      operations:\n      - method: POST\n        name: edit-image\n        description: Edit an image.\n        call: firefly-services.edit-image\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9080\n    namespace: photo-management-mcp\n    transport: http\n    description: MCP server for AI-assisted photo management and editing.\n    tools:\n    - name: get-catalog\n      description: Get the Lightroom catalog.\n      hints:\n        readOnly: true\n      call: lightroom-services.get-catalog\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-assets\n      description: List photo assets in a catalog.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: lightroom-services.list-assets\n      with:\n        catalog_id: tools.catalog_id\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-asset\n      description: Get a specific photo asset.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: lightroom-services.get-asset\n      with:\n        catalog_id: tools.catalog_id\n        asset_id: tools.asset_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: upload-master\n      description: Upload an original master file.\n      hints:\n        readOnly: false\n      call: lightroom-services.upload-master\n      with:\n        catalog_id: tools.catalog_id\n        asset_id: tools.asset_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-develop-xmp\n      description: Get XMP develop settings.\n      hints:\n        readOnly: true\n      call: lightroom-services.get-develop-xmp\n      with:\n        catalog_id: tools.catalog_id\n        asset_id: tools.asset_id\n      outputParameters:\n      - type:\
  \ object\n        mapping: $.\n    - name: get-rendition\n      description: Get a rendered version of an asset.\n      hints:\n        readOnly: true\n      call: lightroom-services.get-rendition\n      with:\n        catalog_id: tools.catalog_id\n        asset_id: tools.asset_id\n        rendition_type: tools.rendition_type\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-albums\n      description: List photo albums.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: lightroom-services.list-albums\n      with:\n        catalog_id: tools.catalog_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-album\n      description: Get a specific album.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: lightroom-services.get-album\n      with:\n        catalog_id: tools.catalog_id\n        album_id: tools.album_id\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: create-or-update-album\n      description: Create or update an album.\n      hints:\n        readOnly: false\n        idempotent: true\n      call: lightroom-services.create-or-update-album\n      with:\n        catalog_id: tools.catalog_id\n        album_id: tools.album_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-album\n      description: Delete an album.\n      hints:\n        readOnly: false\n        destructive: true\n      call: lightroom-services.delete-album\n      with:\n        catalog_id: tools.catalog_id\n        album_id: tools.album_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-album-assets\n      description: List assets in an album.\n      hints:\n        readOnly: true\n      call: lightroom-services.list-album-assets\n      with:\n        catalog_id: tools.catalog_id\n        album_id: tools.album_id\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: add-assets-to-album\n      description: Add assets to an album.\n      hints:\n        readOnly: false\n      call: lightroom-services.add-assets-to-album\n      with:\n        catalog_id: tools.catalog_id\n        album_id: tools.album_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: auto-tone\n      description: Apply AI auto tone adjustment.\n      hints:\n        readOnly: false\n      call: firefly-services.auto-tone\n      with:\n        input_href: tools.input_href\n        input_storage: tools.input_storage\n        output_href: tools.output_href\n        output_storage: tools.output_storage\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: auto-straighten\n      description: Apply AI auto straighten.\n      hints:\n        readOnly: false\n      call: firefly-services.auto-straighten\n      with:\n        input_href: tools.input_href\n        input_storage: tools.input_storage\n        output_href:\
  \ tools.output_href\n        output_storage: tools.output_storage\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: apply-presets\n      description: Apply Lightroom presets to an image.\n      hints:\n        readOnly: false\n      call: firefly-services.apply-presets\n      with:\n        input_href: tools.input_href\n        input_storage: tools.input_storage\n        output_href: tools.output_href\n        output_storage: tools.output_storage\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: edit-image\n      description: Apply programmatic edits to an image.\n      hints:\n        readOnly: false\n      call: firefly-services.edit-image\n      with:\n        input_href: tools.input_href\n        input_storage: tools.input_storage\n        output_href: tools.output_href\n        output_storage: tools.output_storage\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/lightroom/refs/heads/main/capabilities/photo-management.yaml
tags:
- Adobe
- Lightroom
- Photography
- AI Image Editing
tools:
- description: Get the Lightroom catalog.
  hints:
    readOnly: true
  name: get-catalog
- description: List photo assets in a catalog.
  hints:
    openWorld: true
    readOnly: true
  name: list-assets
- description: Get a specific photo asset.
  hints:
    idempotent: true
    readOnly: true
  name: get-asset
- description: Upload an original master file.
  hints:
    readOnly: false
  name: upload-master
- description: Get XMP develop settings.
  hints:
    readOnly: true
  name: get-develop-xmp
- description: Get a rendered version of an asset.
  hints:
    readOnly: true
  name: get-rendition
- description: List photo albums.
  hints:
    openWorld: true
    readOnly: true
  name: list-albums
- description: Get a specific album.
  hints:
    idempotent: true
    readOnly: true
  name: get-album
- description: Create or update an album.
  hints:
    idempotent: true
    readOnly: false
  name: create-or-update-album
- description: Delete an album.
  hints:
    destructive: true
    readOnly: false
  name: delete-album
- description: List assets in an album.
  hints:
    readOnly: true
  name: list-album-assets
- description: Add assets to an album.
  hints:
    readOnly: false
  name: add-assets-to-album
- description: Apply AI auto tone adjustment.
  hints:
    readOnly: false
  name: auto-tone
- description: Apply AI auto straighten.
  hints:
    readOnly: false
  name: auto-straighten
- description: Apply Lightroom presets to an image.
  hints:
    readOnly: false
  name: apply-presets
- description: Apply programmatic edits to an image.
  hints:
    readOnly: false
  name: edit-image
---
