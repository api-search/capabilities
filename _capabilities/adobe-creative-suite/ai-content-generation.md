---
categories: []
consumed_apis:
- firefly
description: AI-powered content generation workflow using Adobe Firefly for creating images, videos, and visual variations from text prompts. Used by content creators, marketers, and designers who need to rapidly produce visual assets using generative AI.
layout: capability
name: Adobe AI Content Generation
operations:
- description: Generate images from a text prompt
  method: POST
  name: generate-images
  path: /v1/generations
- description: Generate images similar to a reference image
  method: POST
  name: generate-similar-images
  path: /v1/generations/similar
- description: Expand an image beyond its boundaries
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
- description: Generate a video from a text prompt
  method: POST
  name: generate-video
  path: /v1/videos
- description: Get the status of an async generation job
  method: GET
  name: get-job-status
  path: /v1/jobs/{jobId}
personas: []
provider_name: Adobe Creative Suite
provider_slug: adobe-creative-suite
search_terms:
- generate a short video clip from a text prompt
- graphics
- image generation
- generate similar images
- text-to-image generation
- expand an image beyond its original boundaries using generative ai
- get the status of an async generation job
- generate composite
- generate an ai object and composite it into a scene image
- generate one or more images from a text prompt using adobe firefly
- generate images
- generative fill operations
- creative
- fill a masked region of an image with ai-generated content
- generate and composite an ai object into a scene
- similar image generation from reference
- generative image expansion
- expand an image beyond its boundaries
- design
- generate images similar to a reference image
- fill a masked region with ai-generated content
- photography
- video generation
- get the status of an asynchronous firefly generation job
- generative ai
- generate images from a text prompt
- expand image
- ai object compositing
- firefly
- generate video
- content generation
- adobe
- generation job status
- ai video generation
- video
- fill image
- generate images visually similar to a reference image
- generate a video from a text prompt
- get job status
slug: ai-content-generation
source_filename: ai-content-generation.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Adobe AI Content Generation\"\n  description: \"AI-powered content generation workflow using Adobe Firefly for creating images, videos, and visual variations from text prompts. Used by content creators, marketers, and designers who need to rapidly produce visual assets using generative AI.\"\n  tags:\n    - Adobe\n    - Firefly\n    - Generative AI\n    - Content Generation\n    - Image Generation\n    - Video Generation\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      ADOBE_FIREFLY_TOKEN: ADOBE_FIREFLY_TOKEN\n\ncapability:\n  consumes:\n    - import: firefly\n      location: ./shared/firefly.yaml\n\n  exposes:\n    - type: rest\n      port: 8081\n      namespace: ai-content-generation-api\n      description: \"Unified REST API for AI-powered content generation using Adobe Firefly.\"\n      resources:\n        - path: /v1/generations\n          name: generations\n          description:\
  \ \"Text-to-image generation\"\n          operations:\n            - method: POST\n              name: generate-images\n              description: \"Generate images from a text prompt\"\n              call: \"firefly.generate-images-async\"\n              with:\n                prompt: \"rest.prompt\"\n                negative_prompt: \"rest.negative_prompt\"\n                content_class: \"rest.content_class\"\n                num_variations: \"rest.num_variations\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/generations/similar\n          name: similar-generations\n          description: \"Similar image generation from reference\"\n          operations:\n            - method: POST\n              name: generate-similar-images\n              description: \"Generate images similar to a reference image\"\n              call: \"firefly.generate-similar-images-async\"\n              with:\n                prompt:\
  \ \"rest.prompt\"\n                image: \"rest.image\"\n                num_variations: \"rest.num_variations\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/expansions\n          name: expansions\n          description: \"Generative image expansion\"\n          operations:\n            - method: POST\n              name: expand-image\n              description: \"Expand an image beyond its boundaries\"\n              call: \"firefly.expand-image-async\"\n              with:\n                prompt: \"rest.prompt\"\n                image: \"rest.image\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/fills\n          name: fills\n          description: \"Generative fill operations\"\n          operations:\n            - method: POST\n              name: fill-image\n              description: \"Fill a masked region with AI-generated content\"\
  \n              call: \"firefly.fill-image-async\"\n              with:\n                prompt: \"rest.prompt\"\n                image: \"rest.image\"\n                mask: \"rest.mask\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/composites\n          name: composites\n          description: \"AI object compositing\"\n          operations:\n            - method: POST\n              name: generate-composite\n              description: \"Generate and composite an AI object into a scene\"\n              call: \"firefly.generate-object-composite-async\"\n              with:\n                prompt: \"rest.prompt\"\n                image: \"rest.image\"\n                mask: \"rest.mask\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/videos\n          name: videos\n          description: \"AI video generation\"\n          operations:\n\
  \            - method: POST\n              name: generate-video\n              description: \"Generate a video from a text prompt\"\n              call: \"firefly.generate-video-async\"\n              with:\n                prompt: \"rest.prompt\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/jobs/{jobId}\n          name: jobs\n          description: \"Generation job status\"\n          operations:\n            - method: GET\n              name: get-job-status\n              description: \"Get the status of an async generation job\"\n              call: \"firefly.get-generation-status\"\n              with:\n                jobId: \"rest.jobId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9091\n      namespace: ai-content-generation-mcp\n      transport: http\n      description: \"MCP server for AI-assisted content generation\
  \ using Adobe Firefly.\"\n      tools:\n        - name: generate-images\n          description: \"Generate one or more images from a text prompt using Adobe Firefly\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"firefly.generate-images-async\"\n          with:\n            prompt: \"tools.prompt\"\n            negative_prompt: \"tools.negative_prompt\"\n            content_class: \"tools.content_class\"\n            num_variations: \"tools.num_variations\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: generate-similar-images\n          description: \"Generate images visually similar to a reference image\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"firefly.generate-similar-images-async\"\n          with:\n            prompt: \"tools.prompt\"\n            image:\
  \ \"tools.image\"\n            num_variations: \"tools.num_variations\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: expand-image\n          description: \"Expand an image beyond its original boundaries using generative AI\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"firefly.expand-image-async\"\n          with:\n            prompt: \"tools.prompt\"\n            image: \"tools.image\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: fill-image\n          description: \"Fill a masked region of an image with AI-generated content\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"firefly.fill-image-async\"\n          with:\n            prompt: \"tools.prompt\"\n            image: \"tools.image\"\n          \
  \  mask: \"tools.mask\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: generate-composite\n          description: \"Generate an AI object and composite it into a scene image\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"firefly.generate-object-composite-async\"\n          with:\n            prompt: \"tools.prompt\"\n            image: \"tools.image\"\n            mask: \"tools.mask\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: generate-video\n          description: \"Generate a short video clip from a text prompt\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"firefly.generate-video-async\"\n          with:\n            prompt: \"tools.prompt\"\n          outputParameters:\n            - type: object\n\
  \              mapping: \"$.\"\n\n        - name: get-job-status\n          description: \"Get the status of an asynchronous Firefly generation job\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"firefly.get-generation-status\"\n          with:\n            jobId: \"tools.jobId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/adobe-creative-suite/refs/heads/main/capabilities/ai-content-generation.yaml
tags:
- Adobe
- Firefly
- Generative AI
- Content Generation
- Image Generation
- Video Generation
tools:
- description: Generate one or more images from a text prompt using Adobe Firefly
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: generate-images
- description: Generate images visually similar to a reference image
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: generate-similar-images
- description: Expand an image beyond its original boundaries using generative AI
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: expand-image
- description: Fill a masked region of an image with AI-generated content
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: fill-image
- description: Generate an AI object and composite it into a scene image
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: generate-composite
- description: Generate a short video clip from a text prompt
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: generate-video
- description: Get the status of an asynchronous Firefly generation job
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-job-status
---
