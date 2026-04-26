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
- license a stock photo
- apply document operations
- firefly get job status
- ai-powered generative fill
- remove background from an image using photoshop
- photoshop straighten image
- create renditions from a psd or image
- license a stock video clip for use in a project
- search the adobe stock library
- psd text layer editing
- generate images similar to a reference image
- get photoshop job status
- stock search files
- license a vector or illustration
- photoshop create rendition
- design
- edit smart object
- generate composite
- get stock file metadata
- edit text layers in a psd document
- expand image
- apply resize, flatten, or trim operations to a psd document
- license vector
- read, add, modify, or delete layers in a psd document
- create an alpha mask for an image
- photoshop get job status
- photoshop create artboard
- stock get categories
- get metadata for a specific stock file
- expand an image beyond its boundaries using firefly generative ai
- replace smart object content in a psd
- manage layers in a psd document
- create artboard
- stock asset search
- photoshop manage layers
- create artboards in a psd document
- firefly generate images
- generate similar images
- photoshop product crop
- image rendition creation
- edit text content and styling in psd text layers
- manage layers
- license a stock video clip
- firefly fill image
- firefly generate similar images
- auto-crop an image to the primary product
- auto-crop an image to focus on the primary product
- remove background
- license a stock photo for use in a project
- automatically straighten a rotated image
- license image
- stock video licensing
- graphics
- create rendition
- generate images similar to a reference image using firefly
- creative
- stock license image
- photoshop edit smart object
- ai object compositing
- fill a masked region with ai-generated content
- generate an ai object and composite it into a scene using firefly
- psd document operations
- smart object replacement
- create mask
- search the adobe stock library for photos, illustrations, vectors, and videos
- generate images
- firefly expand image
- psd layer management
- photoshop apply document operations
- stock license vector
- photoshop create mask
- license video
- firefly generate video
- photoshop operation job status
- generate images from a text prompt using firefly
- stock get file metadata
- image editing
- apply resize, flatten, or trim operations to a psd
- photoshop remove background
- generate video
- generate and composite an ai object into a scene
- stock license video
- stock file metadata
- image straightening
- fill image
- firefly generation job status
- generate images from a text prompt using adobe firefly
- stock image licensing
- creative production
- generate a video from a text prompt using firefly
- ai image generation from text prompts
- get the adobe stock content category tree
- license a vector or illustration for use in a project
- psd artboard creation
- create an alpha mask for an image using photoshop sensei ai
- photoshop edit text layers
- edit text layers
- get the status of an async firefly generation job
- create artboards within a psd document
- get the status of an async photoshop job
- adobe
- replace smart object content in a psd document
- background removal
- create renditions from a psd or image in jpeg, png, or tiff
- firefly generate composite
- stock vector licensing
- remove the background from an image using photoshop sensei ai
- ai-powered image expansion
- search stock files
- ai video generation
- product crop
- generate similar image variations
- video
- get firefly job status
- fill a masked region of an image with ai-generated content using firefly
- get detailed metadata for a specific stock file
- alpha mask creation
- expand an image beyond its boundaries using firefly
- product cropping
- stock assets
- straighten image
- generative ai
- photography
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
