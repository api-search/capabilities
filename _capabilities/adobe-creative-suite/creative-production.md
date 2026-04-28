---
categories: []
consumed_apis:
- firefly
- photoshop
- stock
description: End-to-end creative asset production workflow combining AI content generation (Firefly), image editing and manipulation (Photoshop), and stock asset sourcing and licensing (Stock). Used by creative directors, production designers, and marketing teams to find, generate, edit, and finalize visual assets.
layout: capability
name: Adobe Creative Production
operations:
- description: Generate images from a text prompt using Firefly
  method: POST
  name: generate-images
  path: /v1/generations
- description: Generate images similar to a reference image
  method: POST
  name: generate-similar-images
  path: /v1/generations/similar
- description: Expand an image beyond its boundaries using Firefly
  method: POST
  name: expand-image
  path: /v1/expansions
- description: Fill a masked region with AI-generated content
  method: POST
  name: fill-image
  path: /v1/fills
- description: Generate and composite an AI object into a scene
  method: POST
  name: generate-composite
  path: /v1/composites
- description: Generate a video from a text prompt using Firefly
  method: POST
  name: generate-video
  path: /v1/videos
- description: Remove background from an image using Photoshop
  method: POST
  name: remove-background
  path: /v1/cutouts
- description: Create an alpha mask for an image
  method: POST
  name: create-mask
  path: /v1/masks
- description: Auto-crop an image to the primary product
  method: POST
  name: product-crop
  path: /v1/product-crops
- description: Create renditions from a PSD or image
  method: POST
  name: create-rendition
  path: /v1/renditions
- description: Manage layers in a PSD document
  method: POST
  name: manage-layers
  path: /v1/layers
- description: Edit text layers in a PSD document
  method: POST
  name: edit-text-layers
  path: /v1/text-edits
- description: Replace smart object content in a PSD
  method: POST
  name: edit-smart-object
  path: /v1/smart-objects
- description: Apply resize, flatten, or trim operations to a PSD
  method: POST
  name: apply-document-operations
  path: /v1/document-operations
- description: Create artboards in a PSD document
  method: POST
  name: create-artboard
  path: /v1/artboards
- description: Automatically straighten a rotated image
  method: POST
  name: straighten-image
  path: /v1/straighten-jobs
- description: Search the Adobe Stock library
  method: GET
  name: search-stock-files
  path: /v1/stock-files
- description: Get metadata for a specific stock file
  method: GET
  name: get-stock-file-metadata
  path: /v1/stock-files/{content_id}
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
- description: Get the status of an async Firefly generation job
  method: GET
  name: get-firefly-job-status
  path: /v1/firefly-jobs/{jobId}
- description: Get the status of an async Photoshop job
  method: GET
  name: get-photoshop-job-status
  path: /v1/photoshop-jobs/{jobId}
personas: []
provider_name: Adobe Creative Suite
provider_slug: adobe-creative-suite
search_terms:
- ai image generation from text prompts
- stock vector licensing
- generate an ai object and composite it into a scene using firefly
- photoshop manage layers
- read, add, modify, or delete layers in a psd document
- license a stock photo
- psd text layer editing
- license vector
- expand an image beyond its boundaries using firefly
- stock assets
- photoshop get job status
- product crop
- photoshop operation job status
- create artboards within a psd document
- image rendition creation
- auto-crop an image to the primary product
- apply resize, flatten, or trim operations to a psd document
- firefly get job status
- photoshop remove background
- creative production
- license a stock video clip
- background removal
- create renditions from a psd or image in jpeg, png, or tiff
- create renditions from a psd or image
- generate similar image variations
- get metadata for a specific stock file
- generate images from a text prompt using adobe firefly
- license video
- create an alpha mask for an image using photoshop sensei ai
- firefly generate composite
- photoshop apply document operations
- stock get categories
- create artboard
- auto-crop an image to focus on the primary product
- stock license video
- ai video generation
- stock license image
- ai-powered generative fill
- edit text layers in a psd document
- stock search files
- generate video
- creative
- search the adobe stock library for photos, illustrations, vectors, and videos
- license image
- generate images similar to a reference image using firefly
- stock get file metadata
- photoshop straighten image
- edit smart object
- search the adobe stock library
- get photoshop job status
- generate images from a text prompt using firefly
- photoshop edit text layers
- apply resize, flatten, or trim operations to a psd
- get firefly job status
- generate and composite an ai object into a scene
- get the status of an async photoshop job
- stock video licensing
- create artboards in a psd document
- manage layers in a psd document
- stock file metadata
- photoshop product crop
- graphics
- smart object replacement
- photography
- photoshop edit smart object
- replace smart object content in a psd document
- license a stock video clip for use in a project
- stock image licensing
- stock asset search
- license a vector or illustration for use in a project
- fill image
- automatically straighten a rotated image
- straighten image
- firefly generate images
- image editing
- generate images similar to a reference image
- firefly generate similar images
- remove background
- apply document operations
- firefly generate video
- generative ai
- firefly expand image
- photoshop create mask
- adobe
- ai object compositing
- generate a video from a text prompt using firefly
- design
- get stock file metadata
- photoshop create artboard
- firefly generation job status
- ai-powered image expansion
- firefly fill image
- remove the background from an image using photoshop sensei ai
- fill a masked region of an image with ai-generated content using firefly
- license a vector or illustration
- remove background from an image using photoshop
- generate images
- psd artboard creation
- replace smart object content in a psd
- expand an image beyond its boundaries using firefly generative ai
- photoshop create rendition
- search stock files
- edit text layers
- fill a masked region with ai-generated content
- stock license vector
- manage layers
- get detailed metadata for a specific stock file
- get the adobe stock content category tree
- get the status of an async firefly generation job
- product cropping
- create rendition
- image straightening
- create an alpha mask for an image
- edit text content and styling in psd text layers
- license a stock photo for use in a project
- generate composite
- alpha mask creation
- video
- expand image
- generate similar images
- psd document operations
- create mask
- psd layer management
slug: creative-production
tags:
- Adobe
- Creative Production
- Generative AI
- Image Editing
- Stock Assets
tools:
- description: Generate images from a text prompt using Adobe Firefly
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: firefly-generate-images
- description: Generate images similar to a reference image using Firefly
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: firefly-generate-similar-images
- description: Expand an image beyond its boundaries using Firefly generative AI
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: firefly-expand-image
- description: Fill a masked region of an image with AI-generated content using Firefly
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: firefly-fill-image
- description: Generate an AI object and composite it into a scene using Firefly
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: firefly-generate-composite
- description: Generate a video from a text prompt using Firefly
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: firefly-generate-video
- description: Get the status of an async Firefly generation job
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: firefly-get-job-status
- description: Remove the background from an image using Photoshop Sensei AI
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: photoshop-remove-background
- description: Create an alpha mask for an image using Photoshop Sensei AI
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: photoshop-create-mask
- description: Auto-crop an image to focus on the primary product
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: photoshop-product-crop
- description: Automatically straighten a rotated image
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: photoshop-straighten-image
- description: Edit text content and styling in PSD text layers
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: photoshop-edit-text-layers
- description: Read, add, modify, or delete layers in a PSD document
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: photoshop-manage-layers
- description: Apply resize, flatten, or trim operations to a PSD document
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: photoshop-apply-document-operations
- description: Create renditions from a PSD or image in JPEG, PNG, or TIFF
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: photoshop-create-rendition
- description: Replace smart object content in a PSD document
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: photoshop-edit-smart-object
- description: Create artboards within a PSD document
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: photoshop-create-artboard
- description: Get the status of an async Photoshop job
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: photoshop-get-job-status
- description: Search the Adobe Stock library for photos, illustrations, vectors, and videos
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: stock-search-files
- description: Get detailed metadata for a specific stock file
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: stock-get-file-metadata
- description: License a stock photo for use in a project
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: stock-license-image
- description: License a vector or illustration for use in a project
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: stock-license-vector
- description: License a stock video clip for use in a project
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: stock-license-video
- description: Get the Adobe Stock content category tree
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: stock-get-categories
---
