---
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
- list assets in a catalog.
- apply programmatic edits to an image.
- upload master
- get a rendered version of an asset.
- auto straighten
- apply presets.
- ai image editing
- get xmp develop settings.
- list assets
- auto tone
- image editing.
- image editing
- photo albums.
- create or update an album.
- list albums.
- edit image
- list assets in an album.
- list albums
- apply ai auto straighten.
- apply presets
- get asset
- apply auto tone.
- ai auto straighten.
- get the lightroom catalog.
- specific asset operations.
- lightroom
- delete album
- apply auto straighten.
- apply ai auto tone adjustment.
- lightroom catalog.
- upload an original master file.
- list album assets
- photography
- list photo assets in a catalog.
- preset application.
- cloud storage
- get album
- get catalog
- list photo albums.
- metadata
- get a specific album.
- add assets to an album.
- get the user's catalog.
- ai auto tone.
- get asset details.
- get rendition
- adobe
- create or update album
- delete an album.
- photo assets.
- apply lightroom presets to an image.
- edit an image.
- get a rendition.
- get a specific photo asset.
- get develop xmp
- album assets.
- photo management
- asset renditions.
- add assets to album
slug: photo-management
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
