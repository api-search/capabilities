---
categories: []
consumed_apis: []
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
- remove image background
- inpaint a masked region of an image using a text prompt
- fill masked regions with ai-generated content
- remove image backgrounds
- text to image
- generate ultra image
- ai
- search and replace
- find and replace objects in images
- video generation
- generate a photorealistic or artistic image from a text prompt using stable image ultra (highest quality)
- image generation
- generate images using stable image core (fast)
- erase from image
- image creation
- generate sd3 image
- generate image ultra
- fill a masked region of an image with ai-generated content guided by a text prompt
- stable diffusion
- generate image sd3
- replace background and relight
- remove objects from images
- extend an image beyond its current edges by generating new content that continues the scene
- search and recolor in image
- machine learning
- 3d generation
- inpaint image
- generate an image from a text prompt using stable image core
- remove background
- outpaint image
- generate an image using stable diffusion 3 or 3.5 models
- generative ai
- replace the image background and adjust lighting conditions
- generate core image
- erase an object from an image using a mask
- replace background and adjust lighting
- generate image core
- generate images using stable diffusion 3 or 3.5
- image editing
- replace an image's background with a new scene and adjust lighting to match
- generate images using stable image ultra
- generate an image from a text prompt using stable image core (fast and affordable)
- extend an image beyond its boundaries
- find specific objects in an image and change their color using text descriptions
- remove the background from an image automatically
- extend an image with new content in any direction
- generate an image using stable diffusion 3 or 3.5 (text-to-image or image-to-image)
- replace specific objects in an image using text descriptions
- automatically detect and remove the background from an image, isolating the foreground subject
- generate a high-quality image from a text prompt using stable image ultra
- search and replace in image
- creative workflow
- remove a specific object or region from an image using a mask
- find specific objects in an image by text description and replace them with new content
- stability ai
slug: image-creation
source_filename: image-creation.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Stability AI Image Creation\n  description: Unified workflow for AI-powered image creation using Stability AI's complete image generation and editing suite.\n    Combines text-to-image generation across all model tiers (Ultra, Core, SD3) with image editing operations including inpainting,\n    outpainting, background removal, and object replacement. Designed for creative professionals, marketing teams, and product\n    designers who need programmatic control over image assets.\n  tags:\n  - Stability AI\n  - Image Creation\n  - Generative AI\n  - Image Generation\n  - Image Editing\n  - Creative Workflow\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    STABILITY_AI_API_KEY: STABILITY_AI_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: stable-image-generate\n    baseUri: https://api.stability.ai\n    description: Generate images from text prompts using Stable Diffusion models\n\
  \    authentication:\n      type: bearer\n      token: '{{STABILITY_AI_API_KEY}}'\n    resources:\n    - name: generate-ultra\n      path: /v2beta/stable-image/generate/ultra\n      description: Generate using Stable Image Ultra - highest quality model\n      operations:\n      - name: generate-image-ultra\n        method: POST\n        description: Generate a high-quality image from a text prompt using Stable Image Ultra\n        body:\n          type: multipart\n          data:\n            prompt: '{{tools.prompt}}'\n            negative_prompt: '{{tools.negative_prompt}}'\n            aspect_ratio: '{{tools.aspect_ratio}}'\n            seed: '{{tools.seed}}'\n            output_format: '{{tools.output_format}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: generate-core\n      path: /v2beta/stable-image/generate/core\n      description: Generate using Stable Image Core - fast and affordable\
  \ model\n      operations:\n      - name: generate-image-core\n        method: POST\n        description: Generate an image from a text prompt using Stable Image Core\n        body:\n          type: multipart\n          data:\n            prompt: '{{tools.prompt}}'\n            negative_prompt: '{{tools.negative_prompt}}'\n            aspect_ratio: '{{tools.aspect_ratio}}'\n            seed: '{{tools.seed}}'\n            output_format: '{{tools.output_format}}'\n            style_preset: '{{tools.style_preset}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: generate-sd3\n      path: /v2beta/stable-image/generate/sd3\n      description: Generate using Stable Diffusion 3 and 3.5 models\n      operations:\n      - name: generate-image-sd3\n        method: POST\n        description: Generate an image using Stable Diffusion 3 or 3.5 with text-to-image or image-to-image\n        body:\n          type:\
  \ multipart\n          data:\n            prompt: '{{tools.prompt}}'\n            negative_prompt: '{{tools.negative_prompt}}'\n            model: '{{tools.model}}'\n            mode: '{{tools.mode}}'\n            aspect_ratio: '{{tools.aspect_ratio}}'\n            seed: '{{tools.seed}}'\n            output_format: '{{tools.output_format}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: stable-image-edit\n    baseUri: https://api.stability.ai\n    description: Edit images using AI-powered inpainting, outpainting, erasing, and replacement\n    authentication:\n      type: bearer\n      token: '{{STABILITY_AI_API_KEY}}'\n    resources:\n    - name: inpaint\n      path: /v2beta/stable-image/edit/inpaint\n      description: Fill masked regions of an image with AI-generated content\n      operations:\n      - name: edit-image-inpaint\n        method: POST\n        description: Inpaint\
  \ a masked region of an image using a text prompt\n        body:\n          type: multipart\n          data:\n            image: '{{tools.image}}'\n            mask: '{{tools.mask}}'\n            prompt: '{{tools.prompt}}'\n            negative_prompt: '{{tools.negative_prompt}}'\n            seed: '{{tools.seed}}'\n            output_format: '{{tools.output_format}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: outpaint\n      path: /v2beta/stable-image/edit/outpaint\n      description: Extend an image beyond its boundaries\n      operations:\n      - name: edit-image-outpaint\n        method: POST\n        description: Extend an image by generating new content beyond its borders\n        body:\n          type: multipart\n          data:\n            image: '{{tools.image}}'\n            prompt: '{{tools.prompt}}'\n            left: '{{tools.left}}'\n            right: '{{tools.right}}'\n  \
  \          up: '{{tools.up}}'\n            down: '{{tools.down}}'\n            output_format: '{{tools.output_format}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: erase\n      path: /v2beta/stable-image/edit/erase\n      description: Remove objects from an image\n      operations:\n      - name: edit-image-erase\n        method: POST\n        description: Erase an object from an image by masking the area\n        body:\n          type: multipart\n          data:\n            image: '{{tools.image}}'\n            mask: '{{tools.mask}}'\n            output_format: '{{tools.output_format}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: search-and-replace\n      path: /v2beta/stable-image/edit/search-and-replace\n      description: Find and replace objects in an image\n      operations:\n      - name:\
  \ edit-image-search-and-replace\n        method: POST\n        description: Find specific objects in an image and replace them using text descriptions\n        body:\n          type: multipart\n          data:\n            image: '{{tools.image}}'\n            prompt: '{{tools.prompt}}'\n            search_prompt: '{{tools.search_prompt}}'\n            negative_prompt: '{{tools.negative_prompt}}'\n            output_format: '{{tools.output_format}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: search-and-recolor\n      path: /v2beta/stable-image/edit/search-and-recolor\n      description: Find and recolor objects in an image\n      operations:\n      - name: edit-image-search-and-recolor\n        method: POST\n        description: Find specific objects in an image and recolor them\n        body:\n          type: multipart\n          data:\n            image: '{{tools.image}}'\n            prompt:\
  \ '{{tools.prompt}}'\n            select_prompt: '{{tools.select_prompt}}'\n            output_format: '{{tools.output_format}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: remove-background\n      path: /v2beta/stable-image/edit/remove-background\n      description: Remove the background from an image\n      operations:\n      - name: edit-image-remove-background\n        method: POST\n        description: Automatically remove the background from an image\n        body:\n          type: multipart\n          data:\n            image: '{{tools.image}}'\n            output_format: '{{tools.output_format}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: replace-background-and-relight\n      path: /v2beta/stable-image/edit/replace-background-and-relight\n      description: Replace background and adjust lighting\
  \ in an image\n      operations:\n      - name: edit-image-replace-background-and-relight\n        method: POST\n        description: Replace the background of an image and adjust lighting to match\n        body:\n          type: multipart\n          data:\n            image: '{{tools.image}}'\n            background_prompt: '{{tools.background_prompt}}'\n            foreground_prompt: '{{tools.foreground_prompt}}'\n            output_format: '{{tools.output_format}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: image-creation-api\n    description: Unified REST API for Stability AI image creation and editing workflows.\n    resources:\n    - path: /v1/generate/ultra\n      name: generate-ultra\n      description: Generate images using Stable Image Ultra\n      operations:\n      - method: POST\n        name: generate-image-ultra\n        description:\
  \ Generate a high-quality image from a text prompt using Stable Image Ultra\n        call: stable-image-generate.generate-image-ultra\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/generate/core\n      name: generate-core\n      description: Generate images using Stable Image Core (fast)\n      operations:\n      - method: POST\n        name: generate-image-core\n        description: Generate an image from a text prompt using Stable Image Core\n        call: stable-image-generate.generate-image-core\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/generate/sd3\n      name: generate-sd3\n      description: Generate images using Stable Diffusion 3 or 3.5\n      operations:\n      - method: POST\n        name: generate-image-sd3\n        description: Generate an image using Stable Diffusion 3 or 3.5 models\n        call: stable-image-generate.generate-image-sd3\n        outputParameters:\n        - type:\
  \ object\n          mapping: $.\n    - path: /v1/edit/inpaint\n      name: inpaint\n      description: Fill masked regions with AI-generated content\n      operations:\n      - method: POST\n        name: inpaint-image\n        description: Inpaint a masked region of an image using a text prompt\n        call: stable-image-edit.edit-image-inpaint\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/edit/outpaint\n      name: outpaint\n      description: Extend an image beyond its boundaries\n      operations:\n      - method: POST\n        name: outpaint-image\n        description: Extend an image with new content in any direction\n        call: stable-image-edit.edit-image-outpaint\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/edit/erase\n      name: erase\n      description: Remove objects from images\n      operations:\n      - method: POST\n        name: erase-from-image\n        description: Erase an\
  \ object from an image using a mask\n        call: stable-image-edit.edit-image-erase\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/edit/search-and-replace\n      name: search-and-replace\n      description: Find and replace objects in images\n      operations:\n      - method: POST\n        name: search-and-replace\n        description: Replace specific objects in an image using text descriptions\n        call: stable-image-edit.edit-image-search-and-replace\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/edit/remove-background\n      name: remove-background\n      description: Remove image backgrounds\n      operations:\n      - method: POST\n        name: remove-background\n        description: Remove the background from an image automatically\n        call: stable-image-edit.edit-image-remove-background\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/edit/replace-background\n\
  \      name: replace-background\n      description: Replace background and adjust lighting\n      operations:\n      - method: POST\n        name: replace-background-and-relight\n        description: Replace the image background and adjust lighting conditions\n        call: stable-image-edit.edit-image-replace-background-and-relight\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: image-creation-mcp\n    transport: http\n    description: MCP server for AI-assisted image creation and editing with Stability AI.\n    tools:\n    - name: generate-ultra-image\n      description: Generate a photorealistic or artistic image from a text prompt using Stable Image Ultra (highest quality)\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: stable-image-generate.generate-image-ultra\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: generate-core-image\n\
  \      description: Generate an image from a text prompt using Stable Image Core (fast and affordable)\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: stable-image-generate.generate-image-core\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: generate-sd3-image\n      description: Generate an image using Stable Diffusion 3 or 3.5 (text-to-image or image-to-image)\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: stable-image-generate.generate-image-sd3\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: inpaint-image\n      description: Fill a masked region of an image with AI-generated content guided by a text prompt\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: stable-image-edit.edit-image-inpaint\n      outputParameters:\n      - type: object\n     \
  \   mapping: $.\n    - name: outpaint-image\n      description: Extend an image beyond its current edges by generating new content that continues the scene\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: stable-image-edit.edit-image-outpaint\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: erase-from-image\n      description: Remove a specific object or region from an image using a mask\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: stable-image-edit.edit-image-erase\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-and-replace-in-image\n      description: Find specific objects in an image by text description and replace them with new content\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: stable-image-edit.edit-image-search-and-replace\n   \
  \   outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-and-recolor-in-image\n      description: Find specific objects in an image and change their color using text descriptions\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: stable-image-edit.edit-image-search-and-recolor\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: remove-image-background\n      description: Automatically detect and remove the background from an image, isolating the foreground subject\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: stable-image-edit.edit-image-remove-background\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: replace-background-and-relight\n      description: Replace an image's background with a new scene and adjust lighting to match\n      hints:\n        readOnly: false\n        destructive:\
  \ false\n        idempotent: false\n      call: stable-image-edit.edit-image-replace-background-and-relight\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
