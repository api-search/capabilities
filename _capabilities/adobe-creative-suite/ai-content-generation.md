---
categories: []
consumed_apis: []
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
- graphics
- video generation
- generate and composite an ai object into a scene
- generative image expansion
- generate images similar to a reference image
- generate one or more images from a text prompt using adobe firefly
- generate images from a text prompt
- design
- generation job status
- creative
- content generation
- generative ai
- fill a masked region of an image with ai-generated content
- photography
- expand image
- get job status
- generative fill operations
- expand an image beyond its original boundaries using generative ai
- fill a masked region with ai-generated content
- expand an image beyond its boundaries
- text-to-image generation
- generate a video from a text prompt
- video
- similar image generation from reference
- fill image
- generate a short video clip from a text prompt
- generate composite
- generate an ai object and composite it into a scene image
- generate images visually similar to a reference image
- adobe
- generate images
- generate video
- image generation
- generate similar images
- ai video generation
- firefly
- get the status of an async generation job
- get the status of an asynchronous firefly generation job
- ai object compositing
slug: ai-content-generation
source_filename: ai-content-generation.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Adobe AI Content Generation\n  description: AI-powered content generation workflow using Adobe Firefly for creating images, videos, and visual variations\n    from text prompts. Used by content creators, marketers, and designers who need to rapidly produce visual assets using\n    generative AI.\n  tags:\n  - Adobe\n  - Firefly\n  - Generative AI\n  - Content Generation\n  - Image Generation\n  - Video Generation\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    ADOBE_FIREFLY_TOKEN: ADOBE_FIREFLY_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: firefly\n    baseUri: https://firefly-api.adobe.io/v3\n    description: Adobe Firefly API for generative AI image and video creation\n    authentication:\n      type: bearer\n      token: '{{ADOBE_FIREFLY_TOKEN}}'\n    resources:\n    - name: image-generation\n      path: /images\n      description: Text-to-image and image variation generation\
  \ operations\n      operations:\n      - name: generate-images-async\n        method: POST\n        path: /generate-async\n        description: Generates one or more images from a text prompt using the Adobe Firefly generative AI model\n        body:\n          type: json\n          data:\n            prompt: '{{tools.prompt}}'\n            negativePrompt: '{{tools.negative_prompt}}'\n            contentClass: '{{tools.content_class}}'\n            numVariations: '{{tools.num_variations}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: generate-similar-images-async\n        method: POST\n        path: /generate-similar-async\n        description: Generates images visually similar to a provided reference image\n        body:\n          type: json\n          data:\n            prompt: '{{tools.prompt}}'\n            image: '{{tools.image}}'\n            numVariations: '{{tools.num_variations}}'\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: generative-expand\n      path: /images\n      description: Expand images beyond their original boundaries\n      operations:\n      - name: expand-image-async\n        method: POST\n        path: /expand-async\n        description: Expands an existing image beyond its original boundaries using generative AI\n        body:\n          type: json\n          data:\n            prompt: '{{tools.prompt}}'\n            negativePrompt: '{{tools.negative_prompt}}'\n            image: '{{tools.image}}'\n            numVariations: '{{tools.num_variations}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: generative-fill\n      path: /images\n      description: Fill selected regions of images with AI-generated content\n      operations:\n      - name: fill-image-async\n\
  \        method: POST\n        path: /fill-async\n        description: Fills a masked region of an existing image with AI-generated content based on a text prompt\n        body:\n          type: json\n          data:\n            prompt: '{{tools.prompt}}'\n            negativePrompt: '{{tools.negative_prompt}}'\n            image: '{{tools.image}}'\n            mask: '{{tools.mask}}'\n            numVariations: '{{tools.num_variations}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: object-composite\n      path: /images\n      description: Composite AI-generated objects into existing images\n      operations:\n      - name: generate-object-composite-async\n        method: POST\n        path: /generate-object-composite-async\n        description: Generates an AI-rendered object and composites it into an existing scene image\n        body:\n          type: json\n          data:\n            prompt:\
  \ '{{tools.prompt}}'\n            negativePrompt: '{{tools.negative_prompt}}'\n            contentClass: '{{tools.content_class}}'\n            image: '{{tools.image}}'\n            mask: '{{tools.mask}}'\n            numVariations: '{{tools.num_variations}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: video-generation\n      path: /videos\n      description: Generate video from text prompts\n      operations:\n      - name: generate-video-async\n        method: POST\n        path: /generate-async\n        description: Generates a short video clip from a text prompt using the Adobe Firefly video generation model\n        body:\n          type: json\n          data:\n            prompt: '{{tools.prompt}}'\n            negativePrompt: '{{tools.negative_prompt}}'\n            duration: '{{tools.duration}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n     \
  \     type: object\n          value: $.\n    - name: status\n      path: /status\n      description: Asynchronous job status polling\n      operations:\n      - name: get-generation-status\n        method: GET\n        path: /{jobId}\n        description: Retrieves the current status of an asynchronous Firefly generation job\n        inputParameters:\n        - name: jobId\n          in: path\n          type: string\n          required: true\n          description: Unique identifier of the generation job to check\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8081\n    namespace: ai-content-generation-api\n    description: Unified REST API for AI-powered content generation using Adobe Firefly.\n    resources:\n    - path: /v1/generations\n      name: generations\n      description: Text-to-image generation\n      operations:\n      - method: POST\n        name: generate-images\n\
  \        description: Generate images from a text prompt\n        call: firefly.generate-images-async\n        with:\n          prompt: rest.prompt\n          negative_prompt: rest.negative_prompt\n          content_class: rest.content_class\n          num_variations: rest.num_variations\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/generations/similar\n      name: similar-generations\n      description: Similar image generation from reference\n      operations:\n      - method: POST\n        name: generate-similar-images\n        description: Generate images similar to a reference image\n        call: firefly.generate-similar-images-async\n        with:\n          prompt: rest.prompt\n          image: rest.image\n          num_variations: rest.num_variations\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/expansions\n      name: expansions\n      description: Generative image expansion\n      operations:\n\
  \      - method: POST\n        name: expand-image\n        description: Expand an image beyond its boundaries\n        call: firefly.expand-image-async\n        with:\n          prompt: rest.prompt\n          image: rest.image\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/fills\n      name: fills\n      description: Generative fill operations\n      operations:\n      - method: POST\n        name: fill-image\n        description: Fill a masked region with AI-generated content\n        call: firefly.fill-image-async\n        with:\n          prompt: rest.prompt\n          image: rest.image\n          mask: rest.mask\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/composites\n      name: composites\n      description: AI object compositing\n      operations:\n      - method: POST\n        name: generate-composite\n        description: Generate and composite an AI object into a scene\n        call: firefly.generate-object-composite-async\n\
  \        with:\n          prompt: rest.prompt\n          image: rest.image\n          mask: rest.mask\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/videos\n      name: videos\n      description: AI video generation\n      operations:\n      - method: POST\n        name: generate-video\n        description: Generate a video from a text prompt\n        call: firefly.generate-video-async\n        with:\n          prompt: rest.prompt\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/jobs/{jobId}\n      name: jobs\n      description: Generation job status\n      operations:\n      - method: GET\n        name: get-job-status\n        description: Get the status of an async generation job\n        call: firefly.get-generation-status\n        with:\n          jobId: rest.jobId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9091\n    namespace: ai-content-generation-mcp\n\
  \    transport: http\n    description: MCP server for AI-assisted content generation using Adobe Firefly.\n    tools:\n    - name: generate-images\n      description: Generate one or more images from a text prompt using Adobe Firefly\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: firefly.generate-images-async\n      with:\n        prompt: tools.prompt\n        negative_prompt: tools.negative_prompt\n        content_class: tools.content_class\n        num_variations: tools.num_variations\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: generate-similar-images\n      description: Generate images visually similar to a reference image\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: firefly.generate-similar-images-async\n      with:\n        prompt: tools.prompt\n        image: tools.image\n        num_variations: tools.num_variations\n     \
  \ outputParameters:\n      - type: object\n        mapping: $.\n    - name: expand-image\n      description: Expand an image beyond its original boundaries using generative AI\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: firefly.expand-image-async\n      with:\n        prompt: tools.prompt\n        image: tools.image\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: fill-image\n      description: Fill a masked region of an image with AI-generated content\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: firefly.fill-image-async\n      with:\n        prompt: tools.prompt\n        image: tools.image\n        mask: tools.mask\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: generate-composite\n      description: Generate an AI object and composite it into a scene image\n      hints:\n        readOnly: false\n\
  \        destructive: false\n        idempotent: false\n      call: firefly.generate-object-composite-async\n      with:\n        prompt: tools.prompt\n        image: tools.image\n        mask: tools.mask\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: generate-video\n      description: Generate a short video clip from a text prompt\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: firefly.generate-video-async\n      with:\n        prompt: tools.prompt\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-job-status\n      description: Get the status of an asynchronous Firefly generation job\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: firefly.get-generation-status\n      with:\n        jobId: tools.jobId\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
