---
categories:
- automation
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
- product cropping operations
- remove background
- product crop
- graphics
- apply resize, flatten, or trim operations to a psd
- create artboards within a psd document
- create an alpha mask for an image
- create artboard
- apply document operations
- document-level operations
- alpha mask creation
- automation
- create an alpha mask for an image using adobe sensei ai
- replace smart object content in a psd document
- image processing
- creative
- edit text layers in a psd
- replace smart object content in a psd
- get the status of an async photoshop job
- remove the background from an image using adobe sensei ai
- create renditions from a psd or image
- smart object editing
- auto-crop an image to focus on the primary product
- read, add, modify, or delete layers in a psd document
- image editing
- create mask
- layer management
- edit smart object
- design
- create artboards in a psd document
- photography
- create renditions from a psd or image in jpeg, png, or tiff
- background removal operations
- create rendition
- job status polling
- remove the background from an image
- edit text layers
- text layer editing
- manage layers in a psd document
- manage layers
- adobe
- straighten image
- edit text content and styling in psd text layers
- straighten a rotated image
- photoshop
- artboard creation
- rendition creation
- automatically straighten a rotated image
- video
- image straightening
- apply resize, flatten, or trim operations to a psd document
- get the status of an asynchronous photoshop api job
- auto-crop an image to the primary product
- get job status
slug: image-editing
source_filename: image-editing.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Adobe Image Editing\"\n  description: \"Automated image editing and processing workflow using the Adobe Photoshop API for background removal, masking, layer management, rendition creation, document operations, and smart object editing. Used by production designers, e-commerce teams, and digital asset managers who need to automate image processing at scale.\"\n  tags:\n    - Adobe\n    - Photoshop\n    - Image Editing\n    - Image Processing\n    - Layer Management\n    - Automation\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      ADOBE_PHOTOSHOP_TOKEN: ADOBE_PHOTOSHOP_TOKEN\n\ncapability:\n  consumes:\n    - import: photoshop\n      location: ./shared/photoshop.yaml\n\n  exposes:\n    - type: rest\n      port: 8082\n      namespace: image-editing-api\n      description: \"Unified REST API for automated image editing and processing using Adobe Photoshop.\"\n      resources:\n\
  \        - path: /v1/cutouts\n          name: cutouts\n          description: \"Background removal operations\"\n          operations:\n            - method: POST\n              name: remove-background\n              description: \"Remove the background from an image\"\n              call: \"photoshop.remove-background\"\n              with:\n                input: \"rest.input\"\n                output: \"rest.output\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/masks\n          name: masks\n          description: \"Alpha mask creation\"\n          operations:\n            - method: POST\n              name: create-mask\n              description: \"Create an alpha mask for an image\"\n              call: \"photoshop.create-mask\"\n              with:\n                input: \"rest.input\"\n                output: \"rest.output\"\n              outputParameters:\n                - type: object\n           \
  \       mapping: \"$.\"\n\n        - path: /v1/product-crops\n          name: product-crops\n          description: \"Product cropping operations\"\n          operations:\n            - method: POST\n              name: product-crop\n              description: \"Auto-crop an image to the primary product\"\n              call: \"photoshop.product-crop\"\n              with:\n                input: \"rest.input\"\n                output: \"rest.output\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/straighten-jobs\n          name: straighten-jobs\n          description: \"Image straightening\"\n          operations:\n            - method: POST\n              name: straighten-image\n              description: \"Straighten a rotated image\"\n              call: \"photoshop.straighten-image\"\n              with:\n                input: \"rest.input\"\n                output: \"rest.output\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/text-edits\n          name: text-edits\n          description: \"Text layer editing\"\n          operations:\n            - method: POST\n              name: edit-text-layers\n              description: \"Edit text layers in a PSD\"\n              call: \"photoshop.edit-text-layers\"\n              with:\n                inputs: \"rest.inputs\"\n                outputs: \"rest.outputs\"\n                options: \"rest.options\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/layers\n          name: layers\n          description: \"Layer management\"\n          operations:\n            - method: POST\n              name: manage-layers\n              description: \"Manage layers in a PSD document\"\n              call: \"photoshop.manage-layers\"\n              with:\n                inputs: \"rest.inputs\"\n               \
  \ outputs: \"rest.outputs\"\n                options: \"rest.options\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/document-operations\n          name: document-operations\n          description: \"Document-level operations\"\n          operations:\n            - method: POST\n              name: apply-document-operations\n              description: \"Apply resize, flatten, or trim operations to a PSD\"\n              call: \"photoshop.apply-document-operations\"\n              with:\n                inputs: \"rest.inputs\"\n                outputs: \"rest.outputs\"\n                options: \"rest.options\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/renditions\n          name: renditions\n          description: \"Rendition creation\"\n          operations:\n            - method: POST\n              name: create-rendition\n     \
  \         description: \"Create renditions from a PSD or image\"\n              call: \"photoshop.create-rendition\"\n              with:\n                inputs: \"rest.inputs\"\n                outputs: \"rest.outputs\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/smart-objects\n          name: smart-objects\n          description: \"Smart object editing\"\n          operations:\n            - method: POST\n              name: edit-smart-object\n              description: \"Replace smart object content in a PSD\"\n              call: \"photoshop.edit-smart-object\"\n              with:\n                inputs: \"rest.inputs\"\n                outputs: \"rest.outputs\"\n                options: \"rest.options\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/artboards\n          name: artboards\n          description: \"Artboard creation\"\
  \n          operations:\n            - method: POST\n              name: create-artboard\n              description: \"Create artboards in a PSD document\"\n              call: \"photoshop.create-artboard\"\n              with:\n                inputs: \"rest.inputs\"\n                outputs: \"rest.outputs\"\n                options: \"rest.options\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/jobs/{jobId}\n          name: jobs\n          description: \"Job status polling\"\n          operations:\n            - method: GET\n              name: get-job-status\n              description: \"Get the status of an async Photoshop job\"\n              call: \"photoshop.get-job-status\"\n              with:\n                jobId: \"rest.jobId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9092\n      namespace: image-editing-mcp\n\
  \      transport: http\n      description: \"MCP server for AI-assisted image editing and processing using Adobe Photoshop.\"\n      tools:\n        - name: remove-background\n          description: \"Remove the background from an image using Adobe Sensei AI\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"photoshop.remove-background\"\n          with:\n            input: \"tools.input\"\n            output: \"tools.output\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-mask\n          description: \"Create an alpha mask for an image using Adobe Sensei AI\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"photoshop.create-mask\"\n          with:\n            input: \"tools.input\"\n            output: \"tools.output\"\n          outputParameters:\n           \
  \ - type: object\n              mapping: \"$.\"\n\n        - name: product-crop\n          description: \"Auto-crop an image to focus on the primary product\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"photoshop.product-crop\"\n          with:\n            input: \"tools.input\"\n            output: \"tools.output\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: straighten-image\n          description: \"Automatically straighten a rotated image\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"photoshop.straighten-image\"\n          with:\n            input: \"tools.input\"\n            output: \"tools.output\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: edit-text-layers\n          description: \"Edit\
  \ text content and styling in PSD text layers\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"photoshop.edit-text-layers\"\n          with:\n            inputs: \"tools.inputs\"\n            outputs: \"tools.outputs\"\n            options: \"tools.options\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: manage-layers\n          description: \"Read, add, modify, or delete layers in a PSD document\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"photoshop.manage-layers\"\n          with:\n            inputs: \"tools.inputs\"\n            outputs: \"tools.outputs\"\n            options: \"tools.options\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: apply-document-operations\n          description: \"Apply resize,\
  \ flatten, or trim operations to a PSD document\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"photoshop.apply-document-operations\"\n          with:\n            inputs: \"tools.inputs\"\n            outputs: \"tools.outputs\"\n            options: \"tools.options\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-rendition\n          description: \"Create renditions from a PSD or image in JPEG, PNG, or TIFF\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"photoshop.create-rendition\"\n          with:\n            inputs: \"tools.inputs\"\n            outputs: \"tools.outputs\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: edit-smart-object\n          description: \"Replace smart object content in\
  \ a PSD document\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"photoshop.edit-smart-object\"\n          with:\n            inputs: \"tools.inputs\"\n            outputs: \"tools.outputs\"\n            options: \"tools.options\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-artboard\n          description: \"Create artboards within a PSD document\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"photoshop.create-artboard\"\n          with:\n            inputs: \"tools.inputs\"\n            outputs: \"tools.outputs\"\n            options: \"tools.options\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-job-status\n          description: \"Get the status of an asynchronous Photoshop API job\"\n \
  \         hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"photoshop.get-job-status\"\n          with:\n            jobId: \"tools.jobId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/adobe-creative-suite/refs/heads/main/capabilities/image-editing.yaml
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
