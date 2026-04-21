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
- stock get categories
- get the adobe stock content category tree
- creative production
- product cropping
- stock license vector
- license a stock photo for use in a project
- stock license video
- stock license image
- photoshop product crop
- firefly generate video
- get the status of an async firefly generation job
- apply resize, flatten, or trim operations to a psd document
- alpha mask creation
- straighten image
- generate images similar to a reference image using firefly
- creative
- image rendition creation
- photoshop get job status
- image straightening
- stock assets
- get the status of an async photoshop job
- remove background
- photoshop edit smart object
- replace smart object content in a psd
- get photoshop job status
- search the adobe stock library
- get detailed metadata for a specific stock file
- license a stock photo
- create renditions from a psd or image in jpeg, png, or tiff
- design
- firefly get job status
- fill image
- edit text content and styling in psd text layers
- stock vector licensing
- firefly generate similar images
- apply resize, flatten, or trim operations to a psd
- psd layer management
- photoshop edit text layers
- photoshop operation job status
- firefly generation job status
- psd document operations
- remove background from an image using photoshop
- replace smart object content in a psd document
- create an alpha mask for an image
- stock asset search
- psd artboard creation
- license a stock video clip for use in a project
- create artboards in a psd document
- create rendition
- expand an image beyond its boundaries using firefly generative ai
- image editing
- create renditions from a psd or image
- firefly generate images
- photoshop create rendition
- stock get file metadata
- psd text layer editing
- license a stock video clip
- license a vector or illustration
- fill a masked region of an image with ai-generated content using firefly
- search the adobe stock library for photos, illustrations, vectors, and videos
- auto-crop an image to the primary product
- generate a video from a text prompt using firefly
- firefly generate composite
- apply document operations
- edit smart object
- ai-powered image expansion
- manage layers in a psd document
- generate composite
- product crop
- photoshop remove background
- expand image
- ai-powered generative fill
- photoshop create mask
- license vector
- get stock file metadata
- photoshop create artboard
- ai image generation from text prompts
- generate similar image variations
- manage layers
- generate video
- license image
- firefly fill image
- fill a masked region with ai-generated content
- edit text layers
- background removal
- photoshop straighten image
- ai video generation
- photoshop apply document operations
- stock search files
- stock file metadata
- remove the background from an image using photoshop sensei ai
- create mask
- auto-crop an image to focus on the primary product
- ai object compositing
- video
- generate similar images
- license a vector or illustration for use in a project
- smart object replacement
- photoshop manage layers
- get firefly job status
- generate images from a text prompt using firefly
- generate images from a text prompt using adobe firefly
- stock video licensing
- graphics
- create artboard
- read, add, modify, or delete layers in a psd document
- license video
- stock image licensing
- generate an ai object and composite it into a scene using firefly
- edit text layers in a psd document
- search stock files
- expand an image beyond its boundaries using firefly
- photography
- generate images similar to a reference image
- adobe
- generate and composite an ai object into a scene
- automatically straighten a rotated image
- get metadata for a specific stock file
- create artboards within a psd document
- create an alpha mask for an image using photoshop sensei ai
- generative ai
- generate images
- firefly expand image
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
