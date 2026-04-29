---
api_specs:
- filename: lightroom-services-openapi.yml
  format: yaml
  label: lightroom-services
  slug: lightroom-services
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/lightroom/refs/heads/main/openapi/lightroom-services-openapi.yml
categories: []
consumed_apis:
- lightroom-services
- firefly-services
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
- album assets.
- ai image editing
- list albums
- lightroom catalog.
- adobe
- auto tone
- list photo albums.
- apply presets
- delete an album.
- specific asset operations.
- get a rendered version of an asset.
- upload master
- cloud storage
- preset application.
- upload an original master file.
- get the user's catalog.
- ai auto tone.
- get xmp develop settings.
- list assets in a catalog.
- photo assets.
- list albums.
- create or update album
- add assets to album
- asset renditions.
- apply ai auto straighten.
- get develop xmp
- apply ai auto tone adjustment.
- edit image
- apply lightroom presets to an image.
- metadata
- photography
- apply programmatic edits to an image.
- lightroom
- delete album
- get album
- apply auto straighten.
- create or update an album.
- photo albums.
- list assets in an album.
- list assets
- get asset
- get a specific photo asset.
- auto straighten
- apply presets.
- image editing.
- edit an image.
- list photo assets in a catalog.
- get a rendition.
- image editing
- photo management
- get rendition
- apply auto tone.
- get asset details.
- ai auto straighten.
- get a specific album.
- get the lightroom catalog.
- get catalog
- add assets to an album.
- list album assets
slug: photo-management
source_filename: photo-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Adobe Lightroom Photo Management\"\n  description: \"Unified workflow combining Lightroom cloud services for catalog, asset, and album management with Firefly Services AI-powered editing. Used by photographers and creative developers to manage and enhance photos programmatically.\"\n  tags:\n    - Adobe\n    - Lightroom\n    - Photography\n    - AI Image Editing\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      ADOBE_OAUTH_TOKEN: ADOBE_OAUTH_TOKEN\n      ADOBE_API_KEY: ADOBE_API_KEY\n\ncapability:\n  consumes:\n    - import: lightroom-services\n      location: ./shared/lightroom-services.yaml\n    - import: firefly-services\n      location: ./shared/firefly-services.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: photo-management-api\n      description: \"Unified REST API for Lightroom photo management and AI editing.\"\n      resources:\n        - path:\
  \ /v1/catalog\n          name: catalog\n          description: \"Lightroom catalog.\"\n          operations:\n            - method: GET\n              name: get-catalog\n              description: \"Get the user's catalog.\"\n              call: \"lightroom-services.get-catalog\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/assets\n          name: assets\n          description: \"Photo assets.\"\n          operations:\n            - method: GET\n              name: list-assets\n              description: \"List assets in a catalog.\"\n              call: \"lightroom-services.list-assets\"\n              with:\n                catalog_id: \"rest.catalog_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/assets/{asset_id}\n          name: asset-detail\n          description: \"Specific asset operations.\"\n          operations:\n         \
  \   - method: GET\n              name: get-asset\n              description: \"Get asset details.\"\n              call: \"lightroom-services.get-asset\"\n              with:\n                catalog_id: \"rest.catalog_id\"\n                asset_id: \"rest.asset_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/assets/{asset_id}/renditions/{rendition_type}\n          name: renditions\n          description: \"Asset renditions.\"\n          operations:\n            - method: GET\n              name: get-rendition\n              description: \"Get a rendition.\"\n              call: \"lightroom-services.get-rendition\"\n              with:\n                catalog_id: \"rest.catalog_id\"\n                asset_id: \"rest.asset_id\"\n                rendition_type: \"rest.rendition_type\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/albums\n\
  \          name: albums\n          description: \"Photo albums.\"\n          operations:\n            - method: GET\n              name: list-albums\n              description: \"List albums.\"\n              call: \"lightroom-services.list-albums\"\n              with:\n                catalog_id: \"rest.catalog_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/albums/{album_id}/assets\n          name: album-assets\n          description: \"Album assets.\"\n          operations:\n            - method: GET\n              name: list-album-assets\n              description: \"List assets in an album.\"\n              call: \"lightroom-services.list-album-assets\"\n              with:\n                catalog_id: \"rest.catalog_id\"\n                album_id: \"rest.album_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/auto-tone\n      \
  \    name: auto-tone\n          description: \"AI auto tone.\"\n          operations:\n            - method: POST\n              name: auto-tone\n              description: \"Apply auto tone.\"\n              call: \"firefly-services.auto-tone\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/auto-straighten\n          name: auto-straighten\n          description: \"AI auto straighten.\"\n          operations:\n            - method: POST\n              name: auto-straighten\n              description: \"Apply auto straighten.\"\n              call: \"firefly-services.auto-straighten\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/presets\n          name: presets\n          description: \"Preset application.\"\n          operations:\n            - method: POST\n              name: apply-presets\n              description: \"Apply presets.\"\n\
  \              call: \"firefly-services.apply-presets\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/edit\n          name: edit\n          description: \"Image editing.\"\n          operations:\n            - method: POST\n              name: edit-image\n              description: \"Edit an image.\"\n              call: \"firefly-services.edit-image\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9080\n      namespace: photo-management-mcp\n      transport: http\n      description: \"MCP server for AI-assisted photo management and editing.\"\n      tools:\n        - name: get-catalog\n          description: \"Get the Lightroom catalog.\"\n          hints:\n            readOnly: true\n          call: \"lightroom-services.get-catalog\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n    \
  \    - name: list-assets\n          description: \"List photo assets in a catalog.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"lightroom-services.list-assets\"\n          with:\n            catalog_id: \"tools.catalog_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-asset\n          description: \"Get a specific photo asset.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"lightroom-services.get-asset\"\n          with:\n            catalog_id: \"tools.catalog_id\"\n            asset_id: \"tools.asset_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: upload-master\n          description: \"Upload an original master file.\"\n          hints:\n            readOnly: false\n          call: \"lightroom-services.upload-master\"\n          with:\n            catalog_id: \"\
  tools.catalog_id\"\n            asset_id: \"tools.asset_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-develop-xmp\n          description: \"Get XMP develop settings.\"\n          hints:\n            readOnly: true\n          call: \"lightroom-services.get-develop-xmp\"\n          with:\n            catalog_id: \"tools.catalog_id\"\n            asset_id: \"tools.asset_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-rendition\n          description: \"Get a rendered version of an asset.\"\n          hints:\n            readOnly: true\n          call: \"lightroom-services.get-rendition\"\n          with:\n            catalog_id: \"tools.catalog_id\"\n            asset_id: \"tools.asset_id\"\n            rendition_type: \"tools.rendition_type\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-albums\n\
  \          description: \"List photo albums.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"lightroom-services.list-albums\"\n          with:\n            catalog_id: \"tools.catalog_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-album\n          description: \"Get a specific album.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"lightroom-services.get-album\"\n          with:\n            catalog_id: \"tools.catalog_id\"\n            album_id: \"tools.album_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-or-update-album\n          description: \"Create or update an album.\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"lightroom-services.create-or-update-album\"\n          with:\n            catalog_id: \"\
  tools.catalog_id\"\n            album_id: \"tools.album_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-album\n          description: \"Delete an album.\"\n          hints:\n            readOnly: false\n            destructive: true\n          call: \"lightroom-services.delete-album\"\n          with:\n            catalog_id: \"tools.catalog_id\"\n            album_id: \"tools.album_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-album-assets\n          description: \"List assets in an album.\"\n          hints:\n            readOnly: true\n          call: \"lightroom-services.list-album-assets\"\n          with:\n            catalog_id: \"tools.catalog_id\"\n            album_id: \"tools.album_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: add-assets-to-album\n          description: \"Add\
  \ assets to an album.\"\n          hints:\n            readOnly: false\n          call: \"lightroom-services.add-assets-to-album\"\n          with:\n            catalog_id: \"tools.catalog_id\"\n            album_id: \"tools.album_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: auto-tone\n          description: \"Apply AI auto tone adjustment.\"\n          hints:\n            readOnly: false\n          call: \"firefly-services.auto-tone\"\n          with:\n            input_href: \"tools.input_href\"\n            input_storage: \"tools.input_storage\"\n            output_href: \"tools.output_href\"\n            output_storage: \"tools.output_storage\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: auto-straighten\n          description: \"Apply AI auto straighten.\"\n          hints:\n            readOnly: false\n          call: \"firefly-services.auto-straighten\"\n\
  \          with:\n            input_href: \"tools.input_href\"\n            input_storage: \"tools.input_storage\"\n            output_href: \"tools.output_href\"\n            output_storage: \"tools.output_storage\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: apply-presets\n          description: \"Apply Lightroom presets to an image.\"\n          hints:\n            readOnly: false\n          call: \"firefly-services.apply-presets\"\n          with:\n            input_href: \"tools.input_href\"\n            input_storage: \"tools.input_storage\"\n            output_href: \"tools.output_href\"\n            output_storage: \"tools.output_storage\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: edit-image\n          description: \"Apply programmatic edits to an image.\"\n          hints:\n            readOnly: false\n          call: \"firefly-services.edit-image\"\n   \
  \       with:\n            input_href: \"tools.input_href\"\n            input_storage: \"tools.input_storage\"\n            output_href: \"tools.output_href\"\n            output_storage: \"tools.output_storage\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
