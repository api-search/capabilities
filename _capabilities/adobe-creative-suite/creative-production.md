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
- generative ai
- remove background
- firefly generate video
- generate images similar to a reference image using firefly
- stock search files
- license video
- license vector
- ai-powered image expansion
- license a vector or illustration for use in a project
- create rendition
- photoshop operation job status
- generate composite
- psd text layer editing
- get the status of an async firefly generation job
- get the adobe stock content category tree
- apply resize, flatten, or trim operations to a psd
- read, add, modify, or delete layers in a psd document
- straighten image
- ai-powered generative fill
- background removal
- generate images from a text prompt using adobe firefly
- automatically straighten a rotated image
- firefly expand image
- image rendition creation
- ai video generation
- smart object replacement
- manage layers
- psd layer management
- get photoshop job status
- psd document operations
- generate a video from a text prompt using firefly
- photography
- get metadata for a specific stock file
- stock image licensing
- edit text layers in a psd document
- edit text content and styling in psd text layers
- create artboards within a psd document
- get firefly job status
- fill a masked region of an image with ai-generated content using firefly
- search the adobe stock library for photos, illustrations, vectors, and videos
- stock license image
- photoshop create rendition
- auto-crop an image to the primary product
- firefly generate similar images
- create mask
- creative
- generate images from a text prompt using firefly
- generate similar images
- stock license video
- generate an ai object and composite it into a scene using firefly
- stock video licensing
- remove background from an image using photoshop
- manage layers in a psd document
- generate images similar to a reference image
- firefly generate images
- generate images
- get detailed metadata for a specific stock file
- search the adobe stock library
- photoshop manage layers
- stock file metadata
- photoshop apply document operations
- ai image generation from text prompts
- photoshop remove background
- license a vector or illustration
- psd artboard creation
- replace smart object content in a psd
- photoshop product crop
- firefly generate composite
- photoshop edit smart object
- get stock file metadata
- photoshop get job status
- image editing
- search stock files
- stock asset search
- fill a masked region with ai-generated content
- apply resize, flatten, or trim operations to a psd document
- fill image
- graphics
- create renditions from a psd or image in jpeg, png, or tiff
- stock vector licensing
- license image
- expand an image beyond its boundaries using firefly
- firefly fill image
- expand an image beyond its boundaries using firefly generative ai
- photoshop create artboard
- product crop
- license a stock video clip for use in a project
- get the status of an async photoshop job
- photoshop edit text layers
- auto-crop an image to focus on the primary product
- image straightening
- adobe
- edit smart object
- create artboard
- photoshop create mask
- firefly generation job status
- generate similar image variations
- generate video
- alpha mask creation
- stock license vector
- product cropping
- remove the background from an image using photoshop sensei ai
- expand image
- design
- create an alpha mask for an image
- license a stock photo for use in a project
- firefly get job status
- stock get file metadata
- generate and composite an ai object into a scene
- creative production
- license a stock video clip
- create an alpha mask for an image using photoshop sensei ai
- replace smart object content in a psd document
- stock get categories
- video
- create artboards in a psd document
- ai object compositing
- apply document operations
- create renditions from a psd or image
- license a stock photo
- stock assets
- photoshop straighten image
- edit text layers
slug: creative-production
source_filename: creative-production.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Adobe Creative Production\"\n  description: \"End-to-end creative asset production workflow combining AI content generation (Firefly), image editing and manipulation (Photoshop), and stock asset sourcing and licensing (Stock). Used by creative directors, production designers, and marketing teams to find, generate, edit, and finalize visual assets.\"\n  tags:\n    - Adobe\n    - Creative Production\n    - Generative AI\n    - Image Editing\n    - Stock Assets\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      ADOBE_FIREFLY_TOKEN: ADOBE_FIREFLY_TOKEN\n      ADOBE_PHOTOSHOP_TOKEN: ADOBE_PHOTOSHOP_TOKEN\n      ADOBE_STOCK_TOKEN: ADOBE_STOCK_TOKEN\n      ADOBE_STOCK_API_KEY: ADOBE_STOCK_API_KEY\n\ncapability:\n  consumes:\n    - import: firefly\n      location: ./shared/firefly.yaml\n    - import: photoshop\n      location: ./shared/photoshop.yaml\n    - import: stock\n      location:\
  \ ./shared/stock.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: creative-production-api\n      description: \"Unified REST API for end-to-end creative asset production combining AI generation, image editing, and stock sourcing.\"\n      resources:\n        # AI Generation\n        - path: /v1/generations\n          name: generations\n          description: \"AI image generation from text prompts\"\n          operations:\n            - method: POST\n              name: generate-images\n              description: \"Generate images from a text prompt using Firefly\"\n              call: \"firefly.generate-images-async\"\n              with:\n                prompt: \"rest.prompt\"\n                negative_prompt: \"rest.negative_prompt\"\n                content_class: \"rest.content_class\"\n                num_variations: \"rest.num_variations\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path:\
  \ /v1/generations/similar\n          name: similar-generations\n          description: \"Generate similar image variations\"\n          operations:\n            - method: POST\n              name: generate-similar-images\n              description: \"Generate images similar to a reference image\"\n              call: \"firefly.generate-similar-images-async\"\n              with:\n                prompt: \"rest.prompt\"\n                image: \"rest.image\"\n                num_variations: \"rest.num_variations\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/expansions\n          name: expansions\n          description: \"AI-powered image expansion\"\n          operations:\n            - method: POST\n              name: expand-image\n              description: \"Expand an image beyond its boundaries using Firefly\"\n              call: \"firefly.expand-image-async\"\n              with:\n                prompt:\
  \ \"rest.prompt\"\n                image: \"rest.image\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/fills\n          name: fills\n          description: \"AI-powered generative fill\"\n          operations:\n            - method: POST\n              name: fill-image\n              description: \"Fill a masked region with AI-generated content\"\n              call: \"firefly.fill-image-async\"\n              with:\n                prompt: \"rest.prompt\"\n                image: \"rest.image\"\n                mask: \"rest.mask\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/composites\n          name: composites\n          description: \"AI object compositing\"\n          operations:\n            - method: POST\n              name: generate-composite\n              description: \"Generate and composite an AI object into a scene\"\n\
  \              call: \"firefly.generate-object-composite-async\"\n              with:\n                prompt: \"rest.prompt\"\n                image: \"rest.image\"\n                mask: \"rest.mask\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/videos\n          name: videos\n          description: \"AI video generation\"\n          operations:\n            - method: POST\n              name: generate-video\n              description: \"Generate a video from a text prompt using Firefly\"\n              call: \"firefly.generate-video-async\"\n              with:\n                prompt: \"rest.prompt\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        # Image Editing\n        - path: /v1/cutouts\n          name: cutouts\n          description: \"Background removal\"\n          operations:\n            - method: POST\n              name: remove-background\n\
  \              description: \"Remove background from an image using Photoshop\"\n              call: \"photoshop.remove-background\"\n              with:\n                input: \"rest.input\"\n                output: \"rest.output\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/masks\n          name: masks\n          description: \"Alpha mask creation\"\n          operations:\n            - method: POST\n              name: create-mask\n              description: \"Create an alpha mask for an image\"\n              call: \"photoshop.create-mask\"\n              with:\n                input: \"rest.input\"\n                output: \"rest.output\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/product-crops\n          name: product-crops\n          description: \"Product cropping\"\n          operations:\n            - method: POST\n  \
  \            name: product-crop\n              description: \"Auto-crop an image to the primary product\"\n              call: \"photoshop.product-crop\"\n              with:\n                input: \"rest.input\"\n                output: \"rest.output\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/renditions\n          name: renditions\n          description: \"Image rendition creation\"\n          operations:\n            - method: POST\n              name: create-rendition\n              description: \"Create renditions from a PSD or image\"\n              call: \"photoshop.create-rendition\"\n              with:\n                inputs: \"rest.inputs\"\n                outputs: \"rest.outputs\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/layers\n          name: layers\n          description: \"PSD layer management\"\n         \
  \ operations:\n            - method: POST\n              name: manage-layers\n              description: \"Manage layers in a PSD document\"\n              call: \"photoshop.manage-layers\"\n              with:\n                inputs: \"rest.inputs\"\n                outputs: \"rest.outputs\"\n                options: \"rest.options\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/text-edits\n          name: text-edits\n          description: \"PSD text layer editing\"\n          operations:\n            - method: POST\n              name: edit-text-layers\n              description: \"Edit text layers in a PSD document\"\n              call: \"photoshop.edit-text-layers\"\n              with:\n                inputs: \"rest.inputs\"\n                outputs: \"rest.outputs\"\n                options: \"rest.options\"\n              outputParameters:\n                - type: object\n                  mapping:\
  \ \"$.\"\n\n        - path: /v1/smart-objects\n          name: smart-objects\n          description: \"Smart object replacement\"\n          operations:\n            - method: POST\n              name: edit-smart-object\n              description: \"Replace smart object content in a PSD\"\n              call: \"photoshop.edit-smart-object\"\n              with:\n                inputs: \"rest.inputs\"\n                outputs: \"rest.outputs\"\n                options: \"rest.options\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/document-operations\n          name: document-operations\n          description: \"PSD document operations\"\n          operations:\n            - method: POST\n              name: apply-document-operations\n              description: \"Apply resize, flatten, or trim operations to a PSD\"\n              call: \"photoshop.apply-document-operations\"\n              with:\n            \
  \    inputs: \"rest.inputs\"\n                outputs: \"rest.outputs\"\n                options: \"rest.options\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/artboards\n          name: artboards\n          description: \"PSD artboard creation\"\n          operations:\n            - method: POST\n              name: create-artboard\n              description: \"Create artboards in a PSD document\"\n              call: \"photoshop.create-artboard\"\n              with:\n                inputs: \"rest.inputs\"\n                outputs: \"rest.outputs\"\n                options: \"rest.options\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/straighten-jobs\n          name: straighten-jobs\n          description: \"Image straightening\"\n          operations:\n            - method: POST\n              name: straighten-image\n          \
  \    description: \"Automatically straighten a rotated image\"\n              call: \"photoshop.straighten-image\"\n              with:\n                input: \"rest.input\"\n                output: \"rest.output\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        # Stock Assets\n        - path: /v1/stock-files\n          name: stock-files\n          description: \"Stock asset search\"\n          operations:\n            - method: GET\n              name: search-stock-files\n              description: \"Search the Adobe Stock library\"\n              call: \"stock.search-stock-files\"\n              with:\n                search_parameters[words]: \"rest.keywords\"\n                search_parameters[limit]: \"rest.limit\"\n                search_parameters[offset]: \"rest.offset\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/stock-files/{content_id}\n\
  \          name: stock-file-detail\n          description: \"Stock file metadata\"\n          operations:\n            - method: GET\n              name: get-stock-file-metadata\n              description: \"Get metadata for a specific stock file\"\n              call: \"stock.get-stock-file-metadata\"\n              with:\n                content_id: \"rest.content_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/licenses/images\n          name: license-images\n          description: \"Stock image licensing\"\n          operations:\n            - method: POST\n              name: license-image\n              description: \"License a stock photo\"\n              call: \"stock.license-image\"\n              with:\n                content_id: \"rest.content_id\"\n                license: \"rest.license\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n   \
  \     - path: /v1/licenses/vectors\n          name: license-vectors\n          description: \"Stock vector licensing\"\n          operations:\n            - method: POST\n              name: license-vector\n              description: \"License a vector or illustration\"\n              call: \"stock.license-vector\"\n              with:\n                content_id: \"rest.content_id\"\n                license: \"rest.license\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/licenses/videos\n          name: license-videos\n          description: \"Stock video licensing\"\n          operations:\n            - method: POST\n              name: license-video\n              description: \"License a stock video clip\"\n              call: \"stock.license-video\"\n              with:\n                content_id: \"rest.content_id\"\n                license: \"rest.license\"\n              outputParameters:\n           \
  \     - type: object\n                  mapping: \"$.\"\n\n        # Job Status (unified across Firefly and Photoshop)\n        - path: /v1/firefly-jobs/{jobId}\n          name: firefly-jobs\n          description: \"Firefly generation job status\"\n          operations:\n            - method: GET\n              name: get-firefly-job-status\n              description: \"Get the status of an async Firefly generation job\"\n              call: \"firefly.get-generation-status\"\n              with:\n                jobId: \"rest.jobId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/photoshop-jobs/{jobId}\n          name: photoshop-jobs\n          description: \"Photoshop operation job status\"\n          operations:\n            - method: GET\n              name: get-photoshop-job-status\n              description: \"Get the status of an async Photoshop job\"\n              call: \"photoshop.get-job-status\"\n  \
  \            with:\n                jobId: \"rest.jobId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: creative-production-mcp\n      transport: http\n      description: \"MCP server for AI-assisted creative asset production combining generation, editing, and stock sourcing.\"\n      tools:\n        # Firefly - AI Generation\n        - name: firefly-generate-images\n          description: \"Generate images from a text prompt using Adobe Firefly\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"firefly.generate-images-async\"\n          with:\n            prompt: \"tools.prompt\"\n            negative_prompt: \"tools.negative_prompt\"\n            content_class: \"tools.content_class\"\n            num_variations: \"tools.num_variations\"\n          outputParameters:\n            - type: object\n  \
  \            mapping: \"$.\"\n\n        - name: firefly-generate-similar-images\n          description: \"Generate images similar to a reference image using Firefly\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"firefly.generate-similar-images-async\"\n          with:\n            prompt: \"tools.prompt\"\n            image: \"tools.image\"\n            num_variations: \"tools.num_variations\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: firefly-expand-image\n          description: \"Expand an image beyond its boundaries using Firefly generative AI\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"firefly.expand-image-async\"\n          with:\n            prompt: \"tools.prompt\"\n            image: \"tools.image\"\n          outputParameters:\n            - type:\
  \ object\n              mapping: \"$.\"\n\n        - name: firefly-fill-image\n          description: \"Fill a masked region of an image with AI-generated content using Firefly\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"firefly.fill-image-async\"\n          with:\n            prompt: \"tools.prompt\"\n            image: \"tools.image\"\n            mask: \"tools.mask\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: firefly-generate-composite\n          description: \"Generate an AI object and composite it into a scene using Firefly\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"firefly.generate-object-composite-async\"\n          with:\n            prompt: \"tools.prompt\"\n            image: \"tools.image\"\n            mask: \"tools.mask\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n\n        - name: firefly-generate-video\n          description: \"Generate a video from a text prompt using Firefly\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"firefly.generate-video-async\"\n          with:\n            prompt: \"tools.prompt\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: firefly-get-job-status\n          description: \"Get the status of an async Firefly generation job\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"firefly.get-generation-status\"\n          with:\n            jobId: \"tools.jobId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        # Photoshop - Image Editing\n        - name: photoshop-remove-background\n          description:\
  \ \"Remove the background from an image using Photoshop Sensei AI\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"photoshop.remove-background\"\n          with:\n            input: \"tools.input\"\n            output: \"tools.output\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: photoshop-create-mask\n          description: \"Create an alpha mask for an image using Photoshop Sensei AI\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"photoshop.create-mask\"\n          with:\n            input: \"tools.input\"\n            output: \"tools.output\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: photoshop-product-crop\n          description: \"Auto-crop an image to focus on the primary product\"\n          hints:\n\
  \            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"photoshop.product-crop\"\n          with:\n            input: \"tools.input\"\n            output: \"tools.output\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: photoshop-straighten-image\n          description: \"Automatically straighten a rotated image\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"photoshop.straighten-image\"\n          with:\n            input: \"tools.input\"\n            output: \"tools.output\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: photoshop-edit-text-layers\n          description: \"Edit text content and styling in PSD text layers\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n\
  \          call: \"photoshop.edit-text-layers\"\n          with:\n            inputs: \"tools.inputs\"\n            outputs: \"tools.outputs\"\n            options: \"tools.options\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: photoshop-manage-layers\n          description: \"Read, add, modify, or delete layers in a PSD document\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"photoshop.manage-layers\"\n          with:\n            inputs: \"tools.inputs\"\n            outputs: \"tools.outputs\"\n            options: \"tools.options\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: photoshop-apply-document-operations\n          description: \"Apply resize, flatten, or trim operations to a PSD document\"\n          hints:\n            readOnly: false\n            destructive: false\n  \
  \          idempotent: false\n          call: \"photoshop.apply-document-operations\"\n          with:\n            inputs: \"tools.inputs\"\n            outputs: \"tools.outputs\"\n            options: \"tools.options\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: photoshop-create-rendition\n          description: \"Create renditions from a PSD or image in JPEG, PNG, or TIFF\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"photoshop.create-rendition\"\n          with:\n            inputs: \"tools.inputs\"\n            outputs: \"tools.outputs\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: photoshop-edit-smart-object\n          description: \"Replace smart object content in a PSD document\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent:\
  \ false\n          call: \"photoshop.edit-smart-object\"\n          with:\n            inputs: \"tools.inputs\"\n            outputs: \"tools.outputs\"\n            options: \"tools.options\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: photoshop-create-artboard\n          description: \"Create artboards within a PSD document\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"photoshop.create-artboard\"\n          with:\n            inputs: \"tools.inputs\"\n            outputs: \"tools.outputs\"\n            options: \"tools.options\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: photoshop-get-job-status\n          description: \"Get the status of an async Photoshop job\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n     \
  \     call: \"photoshop.get-job-status\"\n          with:\n            jobId: \"tools.jobId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        # Stock - Asset Sourcing\n        - name: stock-search-files\n          description: \"Search the Adobe Stock library for photos, illustrations, vectors, and videos\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"stock.search-stock-files\"\n          with:\n            search_parameters[words]: \"tools.keywords\"\n            search_parameters[limit]: \"tools.limit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: stock-get-file-metadata\n          description: \"Get detailed metadata for a specific stock file\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"stock.get-stock-file-metadata\"\
  \n          with:\n            content_id: \"tools.content_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: stock-license-image\n          description: \"License a stock photo for use in a project\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"stock.license-image\"\n          with:\n            content_id: \"tools.content_id\"\n            license: \"tools.license\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: stock-license-vector\n          description: \"License a vector or illustration for use in a project\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"stock.license-vector\"\n          with:\n            content_id: \"tools.content_id\"\n            license: \"tools.license\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n\n        - name: stock-license-video\n          description: \"License a stock video clip for use in a project\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"stock.license-video\"\n          with:\n            content_id: \"tools.content_id\"\n            license: \"tools.license\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: stock-get-categories\n          description: \"Get the Adobe Stock content category tree\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"stock.get-category-tree\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/adobe-creative-suite/refs/heads/main/capabilities/creative-production.yaml
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
