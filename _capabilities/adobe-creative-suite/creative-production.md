---
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
- creative production
- generate images similar to a reference image using firefly
- photoshop manage layers
- license a vector or illustration for use in a project
- firefly generate images
- photoshop create mask
- create mask
- stock vector licensing
- ai object compositing
- create artboards in a psd document
- ai-powered generative fill
- video
- photoshop edit smart object
- psd document operations
- license video
- ai image generation from text prompts
- fill a masked region of an image with ai-generated content using firefly
- generative ai
- edit text content and styling in psd text layers
- adobe
- photoshop straighten image
- license a stock photo
- get stock file metadata
- get detailed metadata for a specific stock file
- generate similar images
- expand image
- remove background from an image using photoshop
- generate similar image variations
- remove background
- stock license vector
- design
- fill image
- psd layer management
- search stock files
- apply resize, flatten, or trim operations to a psd document
- generate images similar to a reference image
- generate video
- firefly get job status
- product crop
- photoshop operation job status
- firefly generate similar images
- auto-crop an image to focus on the primary product
- creative
- straighten image
- get the adobe stock content category tree
- generate images from a text prompt using adobe firefly
- create renditions from a psd or image in jpeg, png, or tiff
- fill a masked region with ai-generated content
- generate composite
- photoshop product crop
- create renditions from a psd or image
- stock file metadata
- smart object replacement
- replace smart object content in a psd document
- license a stock photo for use in a project
- photography
- search the adobe stock library
- license a stock video clip for use in a project
- automatically straighten a rotated image
- photoshop apply document operations
- generate an ai object and composite it into a scene using firefly
- graphics
- license vector
- get the status of an async photoshop job
- edit text layers
- edit smart object
- image rendition creation
- firefly generate composite
- photoshop create artboard
- expand an image beyond its boundaries using firefly generative ai
- generate images from a text prompt using firefly
- ai-powered image expansion
- edit text layers in a psd document
- get firefly job status
- replace smart object content in a psd
- firefly fill image
- license a stock video clip
- ai video generation
- get the status of an async firefly generation job
- get photoshop job status
- photoshop edit text layers
- stock assets
- psd artboard creation
- stock license video
- stock image licensing
- product cropping
- apply document operations
- firefly expand image
- stock get categories
- create artboard
- stock asset search
- firefly generate video
- license image
- create artboards within a psd document
- auto-crop an image to the primary product
- image straightening
- firefly generation job status
- stock license image
- generate a video from a text prompt using firefly
- license a vector or illustration
- remove the background from an image using photoshop sensei ai
- stock search files
- photoshop remove background
- read, add, modify, or delete layers in a psd document
- image editing
- apply resize, flatten, or trim operations to a psd
- photoshop create rendition
- generate and composite an ai object into a scene
- get metadata for a specific stock file
- generate images
- manage layers in a psd document
- create an alpha mask for an image
- expand an image beyond its boundaries using firefly
- alpha mask creation
- search the adobe stock library for photos, illustrations, vectors, and videos
- create an alpha mask for an image using photoshop sensei ai
- photoshop get job status
- psd text layer editing
- stock video licensing
- background removal
- manage layers
- stock get file metadata
- create rendition
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
