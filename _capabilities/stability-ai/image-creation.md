---
categories: []
consumed_apis:
- stable-image-generate
- stable-image-edit
description: Unified workflow for AI-powered image creation using Stability AI's complete image generation and editing suite. Combines text-to-image generation across all model tiers (Ultra, Core, SD3) with image editing operations including inpainting, outpainting, background removal, and object replacement. Designed for creative professionals, marketing teams, and product designers who need programmatic control over image assets.
layout: capability
name: Stability AI Image Creation
operations:
- description: Generate a high-quality image from a text prompt using Stable Image Ultra
  method: POST
  name: generate-image-ultra
  path: /v1/generate/ultra
- description: Generate an image from a text prompt using Stable Image Core
  method: POST
  name: generate-image-core
  path: /v1/generate/core
- description: Generate an image using Stable Diffusion 3 or 3.5 models
  method: POST
  name: generate-image-sd3
  path: /v1/generate/sd3
- description: Inpaint a masked region of an image using a text prompt
  method: POST
  name: inpaint-image
  path: /v1/edit/inpaint
- description: Extend an image with new content in any direction
  method: POST
  name: outpaint-image
  path: /v1/edit/outpaint
- description: Erase an object from an image using a mask
  method: POST
  name: erase-from-image
  path: /v1/edit/erase
- description: Replace specific objects in an image using text descriptions
  method: POST
  name: search-and-replace
  path: /v1/edit/search-and-replace
- description: Remove the background from an image automatically
  method: POST
  name: remove-background
  path: /v1/edit/remove-background
- description: Replace the image background and adjust lighting conditions
  method: POST
  name: replace-background-and-relight
  path: /v1/edit/replace-background
personas: []
provider_name: Stability AI
provider_slug: stability-ai
search_terms:
- extend an image beyond its current edges by generating new content that continues the scene
- image creation
- generate an image using stable diffusion 3 or 3.5 (text-to-image or image-to-image)
- remove background
- remove objects from images
- generate a high-quality image from a text prompt using stable image ultra
- find and replace objects in images
- generate image ultra
- fill masked regions with ai-generated content
- ai
- creative workflow
- outpaint image
- remove a specific object or region from an image using a mask
- find specific objects in an image by text description and replace them with new content
- generative ai
- inpaint image
- remove image backgrounds
- remove image background
- text to image
- erase an object from an image using a mask
- extend an image beyond its boundaries
- generate sd3 image
- stable diffusion
- replace the image background and adjust lighting conditions
- search and replace in image
- find specific objects in an image and change their color using text descriptions
- search and replace
- generate ultra image
- generate images using stable image core (fast)
- 3d generation
- generate a photorealistic or artistic image from a text prompt using stable image ultra (highest quality)
- extend an image with new content in any direction
- replace specific objects in an image using text descriptions
- replace background and relight
- image editing
- search and recolor in image
- video generation
- machine learning
- generate an image from a text prompt using stable image core (fast and affordable)
- generate images using stable image ultra
- fill a masked region of an image with ai-generated content guided by a text prompt
- generate core image
- automatically detect and remove the background from an image, isolating the foreground subject
- image generation
- generate images using stable diffusion 3 or 3.5
- stability ai
- remove the background from an image automatically
- generate image core
- erase from image
- generate image sd3
- generate an image using stable diffusion 3 or 3.5 models
- inpaint a masked region of an image using a text prompt
- replace an image's background with a new scene and adjust lighting to match
- replace background and adjust lighting
- generate an image from a text prompt using stable image core
slug: image-creation
source_filename: image-creation.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Stability AI Image Creation\"\n  description: >-\n    Unified workflow for AI-powered image creation using Stability AI's complete\n    image generation and editing suite. Combines text-to-image generation across\n    all model tiers (Ultra, Core, SD3) with image editing operations including\n    inpainting, outpainting, background removal, and object replacement.\n    Designed for creative professionals, marketing teams, and product designers\n    who need programmatic control over image assets.\n  tags:\n    - Stability AI\n    - Image Creation\n    - Generative AI\n    - Image Generation\n    - Image Editing\n    - Creative Workflow\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      STABILITY_AI_API_KEY: STABILITY_AI_API_KEY\n\ncapability:\n  consumes:\n    - import: stable-image-generate\n      location: ./shared/stable-image-generate.yaml\n    - import: stable-image-edit\n\
  \      location: ./shared/stable-image-edit.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: image-creation-api\n      description: \"Unified REST API for Stability AI image creation and editing workflows.\"\n      resources:\n        - path: /v1/generate/ultra\n          name: generate-ultra\n          description: \"Generate images using Stable Image Ultra\"\n          operations:\n            - method: POST\n              name: generate-image-ultra\n              description: \"Generate a high-quality image from a text prompt using Stable Image Ultra\"\n              call: \"stable-image-generate.generate-image-ultra\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/generate/core\n          name: generate-core\n          description: \"Generate images using Stable Image Core (fast)\"\n          operations:\n            - method: POST\n              name: generate-image-core\n         \
  \     description: \"Generate an image from a text prompt using Stable Image Core\"\n              call: \"stable-image-generate.generate-image-core\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/generate/sd3\n          name: generate-sd3\n          description: \"Generate images using Stable Diffusion 3 or 3.5\"\n          operations:\n            - method: POST\n              name: generate-image-sd3\n              description: \"Generate an image using Stable Diffusion 3 or 3.5 models\"\n              call: \"stable-image-generate.generate-image-sd3\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/edit/inpaint\n          name: inpaint\n          description: \"Fill masked regions with AI-generated content\"\n          operations:\n            - method: POST\n              name: inpaint-image\n              description: \"Inpaint a\
  \ masked region of an image using a text prompt\"\n              call: \"stable-image-edit.edit-image-inpaint\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/edit/outpaint\n          name: outpaint\n          description: \"Extend an image beyond its boundaries\"\n          operations:\n            - method: POST\n              name: outpaint-image\n              description: \"Extend an image with new content in any direction\"\n              call: \"stable-image-edit.edit-image-outpaint\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/edit/erase\n          name: erase\n          description: \"Remove objects from images\"\n          operations:\n            - method: POST\n              name: erase-from-image\n              description: \"Erase an object from an image using a mask\"\n              call: \"stable-image-edit.edit-image-erase\"\
  \n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/edit/search-and-replace\n          name: search-and-replace\n          description: \"Find and replace objects in images\"\n          operations:\n            - method: POST\n              name: search-and-replace\n              description: \"Replace specific objects in an image using text descriptions\"\n              call: \"stable-image-edit.edit-image-search-and-replace\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/edit/remove-background\n          name: remove-background\n          description: \"Remove image backgrounds\"\n          operations:\n            - method: POST\n              name: remove-background\n              description: \"Remove the background from an image automatically\"\n              call: \"stable-image-edit.edit-image-remove-background\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/edit/replace-background\n          name: replace-background\n          description: \"Replace background and adjust lighting\"\n          operations:\n            - method: POST\n              name: replace-background-and-relight\n              description: \"Replace the image background and adjust lighting conditions\"\n              call: \"stable-image-edit.edit-image-replace-background-and-relight\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: image-creation-mcp\n      transport: http\n      description: \"MCP server for AI-assisted image creation and editing with Stability AI.\"\n      tools:\n        - name: generate-ultra-image\n          description: \"Generate a photorealistic or artistic image from a text prompt using Stable Image Ultra (highest quality)\"\n          hints:\n   \
  \         readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"stable-image-generate.generate-image-ultra\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: generate-core-image\n          description: \"Generate an image from a text prompt using Stable Image Core (fast and affordable)\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"stable-image-generate.generate-image-core\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: generate-sd3-image\n          description: \"Generate an image using Stable Diffusion 3 or 3.5 (text-to-image or image-to-image)\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"stable-image-generate.generate-image-sd3\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n\n        - name: inpaint-image\n          description: \"Fill a masked region of an image with AI-generated content guided by a text prompt\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"stable-image-edit.edit-image-inpaint\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: outpaint-image\n          description: \"Extend an image beyond its current edges by generating new content that continues the scene\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"stable-image-edit.edit-image-outpaint\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: erase-from-image\n          description: \"Remove a specific object or region from an image using a mask\"\n  \
  \        hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"stable-image-edit.edit-image-erase\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: search-and-replace-in-image\n          description: \"Find specific objects in an image by text description and replace them with new content\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"stable-image-edit.edit-image-search-and-replace\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: search-and-recolor-in-image\n          description: \"Find specific objects in an image and change their color using text descriptions\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"stable-image-edit.edit-image-search-and-recolor\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: remove-image-background\n          description: \"Automatically detect and remove the background from an image, isolating the foreground subject\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"stable-image-edit.edit-image-remove-background\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: replace-background-and-relight\n          description: \"Replace an image's background with a new scene and adjust lighting to match\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"stable-image-edit.edit-image-replace-background-and-relight\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/stability-ai/refs/heads/main/capabilities/image-creation.yaml
tags:
- Stability AI
- Image Creation
- Generative AI
- Image Generation
- Image Editing
- Creative Workflow
tools:
- description: Generate a photorealistic or artistic image from a text prompt using Stable Image Ultra (highest quality)
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: generate-ultra-image
- description: Generate an image from a text prompt using Stable Image Core (fast and affordable)
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: generate-core-image
- description: Generate an image using Stable Diffusion 3 or 3.5 (text-to-image or image-to-image)
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: generate-sd3-image
- description: Fill a masked region of an image with AI-generated content guided by a text prompt
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: inpaint-image
- description: Extend an image beyond its current edges by generating new content that continues the scene
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: outpaint-image
- description: Remove a specific object or region from an image using a mask
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: erase-from-image
- description: Find specific objects in an image by text description and replace them with new content
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: search-and-replace-in-image
- description: Find specific objects in an image and change their color using text descriptions
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: search-and-recolor-in-image
- description: Automatically detect and remove the background from an image, isolating the foreground subject
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: remove-image-background
- description: Replace an image's background with a new scene and adjust lighting to match
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: replace-background-and-relight
---
