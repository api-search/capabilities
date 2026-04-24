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
- create rendition
- edit text layers
- get metadata for a specific stock file
- stock license vector
- create artboards in a psd document
- firefly get job status
- photoshop manage layers
- background removal
- get the status of an async firefly generation job
- generate similar images
- stock license image
- firefly generate images
- apply document operations
- license a stock video clip
- alpha mask creation
- video
- expand an image beyond its boundaries using firefly
- license a stock video clip for use in a project
- generate a video from a text prompt using firefly
- create renditions from a psd or image in jpeg, png, or tiff
- photoshop remove background
- ai-powered image expansion
- psd document operations
- photography
- psd artboard creation
- get detailed metadata for a specific stock file
- ai video generation
- fill image
- get photoshop job status
- get the status of an async photoshop job
- generate images similar to a reference image using firefly
- stock asset search
- photoshop create rendition
- replace smart object content in a psd
- fill a masked region with ai-generated content
- apply resize, flatten, or trim operations to a psd document
- ai object compositing
- edit text layers in a psd document
- remove the background from an image using photoshop sensei ai
- photoshop straighten image
- stock search files
- license a vector or illustration
- ai-powered generative fill
- manage layers
- stock video licensing
- firefly expand image
- photoshop create artboard
- manage layers in a psd document
- smart object replacement
- automatically straighten a rotated image
- firefly generation job status
- search the adobe stock library
- ai image generation from text prompts
- edit text content and styling in psd text layers
- generative ai
- design
- firefly generate composite
- photoshop operation job status
- license a vector or illustration for use in a project
- create artboards within a psd document
- auto-crop an image to the primary product
- expand image
- generate images from a text prompt using firefly
- create an alpha mask for an image
- create an alpha mask for an image using photoshop sensei ai
- stock vector licensing
- generate images from a text prompt using adobe firefly
- apply resize, flatten, or trim operations to a psd
- create mask
- photoshop product crop
- expand an image beyond its boundaries using firefly generative ai
- firefly generate video
- image editing
- remove background from an image using photoshop
- license vector
- stock image licensing
- generate composite
- generate similar image variations
- product cropping
- photoshop create mask
- product crop
- license image
- straighten image
- stock file metadata
- replace smart object content in a psd document
- read, add, modify, or delete layers in a psd document
- photoshop edit text layers
- adobe
- generate an ai object and composite it into a scene using firefly
- stock get file metadata
- generate video
- stock license video
- psd text layer editing
- get the adobe stock content category tree
- photoshop get job status
- generate and composite an ai object into a scene
- search the adobe stock library for photos, illustrations, vectors, and videos
- creative production
- auto-crop an image to focus on the primary product
- firefly fill image
- image straightening
- search stock files
- generate images similar to a reference image
- create renditions from a psd or image
- creative
- license a stock photo
- graphics
- remove background
- stock assets
- edit smart object
- psd layer management
- license a stock photo for use in a project
- fill a masked region of an image with ai-generated content using firefly
- photoshop apply document operations
- firefly generate similar images
- stock get categories
- get stock file metadata
- image rendition creation
- photoshop edit smart object
- generate images
- license video
- create artboard
- get firefly job status
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
