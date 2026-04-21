---
consumed_apis:
- photoshop
description: Automated image editing and processing workflow using the Adobe Photoshop API for background removal, masking, layer management, rendition creation, document operations, and smart object editing. Used by production designers, e-commerce teams, and digital asset managers who need to automate image processing at scale.
layout: capability
name: Adobe Image Editing
operations:
- description: Remove the background from an image
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
- description: Straighten a rotated image
  method: POST
  name: straighten-image
  path: /v1/straighten-jobs
- description: Edit text layers in a PSD
  method: POST
  name: edit-text-layers
  path: /v1/text-edits
- description: Manage layers in a PSD document
  method: POST
  name: manage-layers
  path: /v1/layers
- description: Apply resize, flatten, or trim operations to a PSD
  method: POST
  name: apply-document-operations
  path: /v1/document-operations
- description: Create renditions from a PSD or image
  method: POST
  name: create-rendition
  path: /v1/renditions
- description: Replace smart object content in a PSD
  method: POST
  name: edit-smart-object
  path: /v1/smart-objects
- description: Create artboards in a PSD document
  method: POST
  name: create-artboard
  path: /v1/artboards
- description: Get the status of an async Photoshop job
  method: GET
  name: get-job-status
  path: /v1/jobs/{jobId}
personas: []
provider_name: Adobe Creative Suite
provider_slug: adobe-creative-suite
search_terms:
- photoshop
- alpha mask creation
- image straightening
- auto-crop an image to the primary product
- create rendition
- creative
- create renditions from a psd or image in jpeg, png, or tiff
- replace smart object content in a psd document
- create artboards in a psd document
- read, add, modify, or delete layers in a psd document
- get the status of an asynchronous photoshop api job
- manage layers in a psd document
- straighten a rotated image
- remove the background from an image using adobe sensei ai
- artboard creation
- graphics
- text layer editing
- photography
- remove the background from an image
- apply document operations
- image editing
- product crop
- design
- adobe
- automatically straighten a rotated image
- image processing
- rendition creation
- automation
- video
- smart object editing
- create artboards within a psd document
- create an alpha mask for an image
- apply resize, flatten, or trim operations to a psd document
- manage layers
- document-level operations
- auto-crop an image to focus on the primary product
- remove background
- edit text layers
- create artboard
- job status polling
- product cropping operations
- get the status of an async photoshop job
- apply resize, flatten, or trim operations to a psd
- create renditions from a psd or image
- replace smart object content in a psd
- create mask
- edit smart object
- create an alpha mask for an image using adobe sensei ai
- edit text content and styling in psd text layers
- edit text layers in a psd
- background removal operations
- straighten image
- get job status
- layer management
slug: image-editing
tags:
- Adobe
- Photoshop
- Image Editing
- Image Processing
- Layer Management
- Automation
tools:
- description: Remove the background from an image using Adobe Sensei AI
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: remove-background
- description: Create an alpha mask for an image using Adobe Sensei AI
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-mask
- description: Auto-crop an image to focus on the primary product
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: product-crop
- description: Automatically straighten a rotated image
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: straighten-image
- description: Edit text content and styling in PSD text layers
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: edit-text-layers
- description: Read, add, modify, or delete layers in a PSD document
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: manage-layers
- description: Apply resize, flatten, or trim operations to a PSD document
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: apply-document-operations
- description: Create renditions from a PSD or image in JPEG, PNG, or TIFF
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-rendition
- description: Replace smart object content in a PSD document
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: edit-smart-object
- description: Create artboards within a PSD document
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-artboard
- description: Get the status of an asynchronous Photoshop API job
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-job-status
---
