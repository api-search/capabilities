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
- photo assets.
- get a rendition.
- ai image editing
- album assets.
- ai auto tone.
- edit image
- lightroom catalog.
- list photo albums.
- get album
- add assets to an album.
- list photo assets in a catalog.
- get the lightroom catalog.
- apply ai auto tone adjustment.
- apply auto tone.
- apply programmatic edits to an image.
- auto tone
- apply presets.
- get a specific album.
- specific asset operations.
- photography
- get the user's catalog.
- preset application.
- apply lightroom presets to an image.
- get rendition
- list assets in an album.
- apply presets
- upload master
- delete an album.
- delete album
- add assets to album
- photo albums.
- create or update album
- adobe
- asset renditions.
- image editing.
- upload an original master file.
- cloud storage
- get a specific photo asset.
- get asset details.
- list albums
- get asset
- auto straighten
- get a rendered version of an asset.
- list album assets
- lightroom
- ai auto straighten.
- get develop xmp
- get catalog
- apply auto straighten.
- create or update an album.
- image editing
- edit an image.
- metadata
- photo management
- list albums.
- list assets in a catalog.
- get xmp develop settings.
- list assets
- apply ai auto straighten.
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
