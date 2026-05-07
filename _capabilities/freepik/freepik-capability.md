---
categories: []
consumed_apis: []
description: Freepik's developer platform (operated through Magnific) provides AI-powered image generation, video generation, image editing, audio generation, and access to Freepik's stock library of vectors, photos, icons, and templates. Asynchronous tasks are polled by task ID.
layout: capability
name: Freepik / Magnific API
operations:
- description: Search stock resources
  method: GET
  name: listresources
  path: /v1/resources
- description: Generate image with Mystic
  method: POST
  name: generatemystic
  path: /v1/ai/mystic
- description: Generate image with Flux 2 Pro
  method: POST
  name: generateflux2pro
  path: /v1/ai/flux-2-pro
- description: Generate image with Flux 2 Turbo
  method: POST
  name: generateflux2turbo
  path: /v1/ai/flux-2-turbo
- description: Generate image with Flux Pro v1.1
  method: POST
  name: generatefluxprov11
  path: /v1/ai/flux-pro-v1-1
- description: Generate image with Flux Dev
  method: POST
  name: generatefluxdev
  path: /v1/ai/flux-dev
- description: Generate image with HyperFlux
  method: POST
  name: generatehyperflux
  path: /v1/ai/hyperflux
- description: Generate image with Seedream v4.5
  method: POST
  name: generateseedream
  path: /v1/ai/seedream-v4-5
- description: Generate image with Runway
  method: POST
  name: generaterunway
  path: /v1/ai/runway
- description: Generate video with Kling v2.1 Pro
  method: POST
  name: generatekling21pro
  path: /v1/ai/kling-v2.1-pro
- description: Generate video with Kling v2.5 Pro
  method: POST
  name: generatekling25pro
  path: /v1/ai/kling-v2.5-pro
- description: Generate video with Minimax Hailuo 02 1080p
  method: POST
  name: generateminimaxhailuo
  path: /v1/ai/minimax-hailuo-02-1080p
- description: Creative image upscaler
  method: POST
  name: imageupscaler
  path: /v1/ai/image-upscaler
- description: Relight image
  method: POST
  name: imagerelight
  path: /v1/ai/image-relight
- description: Apply style transfer
  method: POST
  name: imagestyletransfer
  path: /v1/ai/image-styletransfer
- description: Remove background
  method: POST
  name: removebackground
  path: /v1/ai/remove-background
- description: Expand image
  method: POST
  name: imageexpand
  path: /v1/ai/image-expand
- description: Generate music
  method: POST
  name: generatemusic
  path: /v1/ai/music-generation
- description: List music generation tasks
  method: GET
  name: listmusictasks
  path: /v1/ai/music-generation
- description: Generate sound effects
  method: POST
  name: generatesoundeffects
  path: /v1/ai/sound-effects
- description: Audio isolation from audio or video
  method: POST
  name: audioisolation
  path: /v1/ai/audio-isolation
- description: Poll task status
  method: GET
  name: gettask
  path: /v1/ai/{endpoint}/{taskId}
personas: []
provider_name: Freepik
provider_slug: freepik
search_terms:
- generate image with flux pro v1.1
- generate image with hyperflux
- generate music
- generateflux2pro
- imageexpand
- expand image
- generatemusic
- ai
- generatekling21pro
- api
- audio isolation from audio or video
- generate video with kling v2.5 pro
- photos
- video generation
- generateflux2turbo
- image generation
- generateseedream
- imagerelight
- apply style transfer
- list music generation tasks
- freepik
- generate image with flux 2 pro
- gettask
- generate video with kling v2.1 pro
- graphics
- listresources
- illustrations
- generate image with flux 2 turbo
- generate image with flux dev
- generateminimaxhailuo
- generaterunway
- relight image
- removebackground
- remove background
- generatesoundeffects
- search stock resources
- creative image upscaler
- poll task status
- imagestyletransfer
- generatekling25pro
- generatefluxprov11
- generate image with runway
- audioisolation
- listmusictasks
- generate video with minimax hailuo 02 1080p
- generatemystic
- generatefluxdev
- generate image with seedream v4.5
- imageupscaler
- generatehyperflux
- generate image with mystic
- generate sound effects
slug: freepik-capability
source_filename: freepik-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Freepik / Magnific API\n  description: Freepik's developer platform (operated through Magnific) provides AI-powered image generation, video generation,\n    image editing, audio generation, and access to Freepik's stock library of vectors, photos, icons, and templates. Asynchronous\n    tasks are polled by task ID.\n  tags:\n  - Freepik\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: freepik\n    baseUri: https://api.magnific.com\n    description: Freepik / Magnific API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: x-magnific-api-key\n      value: '{{FREEPIK_TOKEN}}'\n    resources:\n    - name: v1-resources\n      path: /v1/resources\n      operations:\n      - name: listresources\n        method: GET\n        description: Search stock resources\n        inputParameters:\n        - name: Accept-Language\n          in: header\n   \
  \       type: string\n        - name: page\n          in: query\n          type: integer\n        - name: limit\n          in: query\n          type: integer\n        - name: term\n          in: query\n          type: string\n        - name: order\n          in: query\n          type: string\n        - name: filters\n          in: query\n          type: string\n          description: Advanced filters (orientation, content_type, license, color, author, ai-generated, vector, psd, people).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-ai-mystic\n      path: /v1/ai/mystic\n      operations:\n      - name: generatemystic\n        method: POST\n        description: Generate image with Mystic\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-ai-flux-2-pro\n      path: /v1/ai/flux-2-pro\n      operations:\n\
  \      - name: generateflux2pro\n        method: POST\n        description: Generate image with Flux 2 Pro\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-ai-flux-2-turbo\n      path: /v1/ai/flux-2-turbo\n      operations:\n      - name: generateflux2turbo\n        method: POST\n        description: Generate image with Flux 2 Turbo\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-ai-flux-pro-v1-1\n      path: /v1/ai/flux-pro-v1-1\n      operations:\n      - name: generatefluxprov11\n        method: POST\n        description: Generate image with Flux Pro v1.1\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-ai-flux-dev\n      path: /v1/ai/flux-dev\n      operations:\n      - name: generatefluxdev\n        method:\
  \ POST\n        description: Generate image with Flux Dev\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-ai-hyperflux\n      path: /v1/ai/hyperflux\n      operations:\n      - name: generatehyperflux\n        method: POST\n        description: Generate image with HyperFlux\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-ai-seedream-v4-5\n      path: /v1/ai/seedream-v4-5\n      operations:\n      - name: generateseedream\n        method: POST\n        description: Generate image with Seedream v4.5\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-ai-runway\n      path: /v1/ai/runway\n      operations:\n      - name: generaterunway\n        method: POST\n        description: Generate image with Runway\n     \
  \   outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-ai-kling-v2-1-pro\n      path: /v1/ai/kling-v2.1-pro\n      operations:\n      - name: generatekling21pro\n        method: POST\n        description: Generate video with Kling v2.1 Pro\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-ai-kling-v2-5-pro\n      path: /v1/ai/kling-v2.5-pro\n      operations:\n      - name: generatekling25pro\n        method: POST\n        description: Generate video with Kling v2.5 Pro\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-ai-minimax-hailuo-02-1080p\n      path: /v1/ai/minimax-hailuo-02-1080p\n      operations:\n      - name: generateminimaxhailuo\n        method: POST\n        description: Generate video with Minimax Hailuo\
  \ 02 1080p\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-ai-image-upscaler\n      path: /v1/ai/image-upscaler\n      operations:\n      - name: imageupscaler\n        method: POST\n        description: Creative image upscaler\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-ai-image-relight\n      path: /v1/ai/image-relight\n      operations:\n      - name: imagerelight\n        method: POST\n        description: Relight image\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-ai-image-styletransfer\n      path: /v1/ai/image-styletransfer\n      operations:\n      - name: imagestyletransfer\n        method: POST\n        description: Apply style transfer\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: v1-ai-remove-background\n      path: /v1/ai/remove-background\n      operations:\n      - name: removebackground\n        method: POST\n        description: Remove background\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-ai-image-expand\n      path: /v1/ai/image-expand\n      operations:\n      - name: imageexpand\n        method: POST\n        description: Expand image\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-ai-music-generation\n      path: /v1/ai/music-generation\n      operations:\n      - name: generatemusic\n        method: POST\n        description: Generate music\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name:\
  \ listmusictasks\n        method: GET\n        description: List music generation tasks\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-ai-sound-effects\n      path: /v1/ai/sound-effects\n      operations:\n      - name: generatesoundeffects\n        method: POST\n        description: Generate sound effects\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-ai-audio-isolation\n      path: /v1/ai/audio-isolation\n      operations:\n      - name: audioisolation\n        method: POST\n        description: Audio isolation from audio or video\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-ai-endpoint-taskid\n      path: /v1/ai/{endpoint}/{taskId}\n      operations:\n      - name: gettask\n        method: GET\n  \
  \      description: Poll task status\n        inputParameters:\n        - name: endpoint\n          in: path\n          type: string\n          required: true\n        - name: taskId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: freepik-rest\n    description: REST adapter for Freepik / Magnific API.\n    resources:\n    - path: /v1/resources\n      name: listresources\n      operations:\n      - method: GET\n        name: listresources\n        description: Search stock resources\n        call: freepik.listresources\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/ai/mystic\n      name: generatemystic\n      operations:\n      - method: POST\n        name: generatemystic\n        description: Generate image with Mystic\n        call: freepik.generatemystic\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/ai/flux-2-pro\n      name: generateflux2pro\n      operations:\n      - method: POST\n        name: generateflux2pro\n        description: Generate image with Flux 2 Pro\n        call: freepik.generateflux2pro\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/ai/flux-2-turbo\n      name: generateflux2turbo\n      operations:\n      - method: POST\n        name: generateflux2turbo\n        description: Generate image with Flux 2 Turbo\n        call: freepik.generateflux2turbo\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/ai/flux-pro-v1-1\n      name: generatefluxprov11\n      operations:\n      - method: POST\n        name: generatefluxprov11\n        description: Generate image with Flux Pro v1.1\n        call: freepik.generatefluxprov11\n        outputParameters:\n        - type: object\n          mapping: $.\n\
  \    - path: /v1/ai/flux-dev\n      name: generatefluxdev\n      operations:\n      - method: POST\n        name: generatefluxdev\n        description: Generate image with Flux Dev\n        call: freepik.generatefluxdev\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/ai/hyperflux\n      name: generatehyperflux\n      operations:\n      - method: POST\n        name: generatehyperflux\n        description: Generate image with HyperFlux\n        call: freepik.generatehyperflux\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/ai/seedream-v4-5\n      name: generateseedream\n      operations:\n      - method: POST\n        name: generateseedream\n        description: Generate image with Seedream v4.5\n        call: freepik.generateseedream\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/ai/runway\n      name: generaterunway\n      operations:\n      - method: POST\n\
  \        name: generaterunway\n        description: Generate image with Runway\n        call: freepik.generaterunway\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/ai/kling-v2.1-pro\n      name: generatekling21pro\n      operations:\n      - method: POST\n        name: generatekling21pro\n        description: Generate video with Kling v2.1 Pro\n        call: freepik.generatekling21pro\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/ai/kling-v2.5-pro\n      name: generatekling25pro\n      operations:\n      - method: POST\n        name: generatekling25pro\n        description: Generate video with Kling v2.5 Pro\n        call: freepik.generatekling25pro\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/ai/minimax-hailuo-02-1080p\n      name: generateminimaxhailuo\n      operations:\n      - method: POST\n        name: generateminimaxhailuo\n        description:\
  \ Generate video with Minimax Hailuo 02 1080p\n        call: freepik.generateminimaxhailuo\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/ai/image-upscaler\n      name: imageupscaler\n      operations:\n      - method: POST\n        name: imageupscaler\n        description: Creative image upscaler\n        call: freepik.imageupscaler\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/ai/image-relight\n      name: imagerelight\n      operations:\n      - method: POST\n        name: imagerelight\n        description: Relight image\n        call: freepik.imagerelight\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/ai/image-styletransfer\n      name: imagestyletransfer\n      operations:\n      - method: POST\n        name: imagestyletransfer\n        description: Apply style transfer\n        call: freepik.imagestyletransfer\n        outputParameters:\n        - type:\
  \ object\n          mapping: $.\n    - path: /v1/ai/remove-background\n      name: removebackground\n      operations:\n      - method: POST\n        name: removebackground\n        description: Remove background\n        call: freepik.removebackground\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/ai/image-expand\n      name: imageexpand\n      operations:\n      - method: POST\n        name: imageexpand\n        description: Expand image\n        call: freepik.imageexpand\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/ai/music-generation\n      name: generatemusic\n      operations:\n      - method: POST\n        name: generatemusic\n        description: Generate music\n        call: freepik.generatemusic\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/ai/music-generation\n      name: listmusictasks\n      operations:\n      - method: GET\n        name: listmusictasks\n\
  \        description: List music generation tasks\n        call: freepik.listmusictasks\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/ai/sound-effects\n      name: generatesoundeffects\n      operations:\n      - method: POST\n        name: generatesoundeffects\n        description: Generate sound effects\n        call: freepik.generatesoundeffects\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/ai/audio-isolation\n      name: audioisolation\n      operations:\n      - method: POST\n        name: audioisolation\n        description: Audio isolation from audio or video\n        call: freepik.audioisolation\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/ai/{endpoint}/{taskId}\n      name: gettask\n      operations:\n      - method: GET\n        name: gettask\n        description: Poll task status\n        call: freepik.gettask\n        with:\n          endpoint:\
  \ rest.endpoint\n          taskId: rest.taskId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: freepik-mcp\n    transport: http\n    description: MCP adapter for Freepik / Magnific API for AI agent use.\n    tools:\n    - name: listresources\n      description: Search stock resources\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: freepik.listresources\n      with:\n        page: tools.page\n        limit: tools.limit\n        term: tools.term\n        order: tools.order\n        filters: tools.filters\n      inputParameters:\n      - name: page\n        type: integer\n        description: page\n      - name: limit\n        type: integer\n        description: limit\n      - name: term\n        type: string\n        description: term\n      - name: order\n        type: string\n        description: order\n      - name: filters\n        type: string\n        description:\
  \ Advanced filters (orientation, content_type, license, color, author, ai-generated, vector, psd, people).\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: generatemystic\n      description: Generate image with Mystic\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: freepik.generatemystic\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: generateflux2pro\n      description: Generate image with Flux 2 Pro\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: freepik.generateflux2pro\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: generateflux2turbo\n      description: Generate image with Flux 2 Turbo\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: freepik.generateflux2turbo\n      outputParameters:\n      - type: object\n   \
  \     mapping: $.\n    - name: generatefluxprov11\n      description: Generate image with Flux Pro v1.1\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: freepik.generatefluxprov11\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: generatefluxdev\n      description: Generate image with Flux Dev\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: freepik.generatefluxdev\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: generatehyperflux\n      description: Generate image with HyperFlux\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: freepik.generatehyperflux\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: generateseedream\n      description: Generate image with Seedream v4.5\n      hints:\n        readOnly: false\n        destructive:\
  \ false\n        idempotent: false\n      call: freepik.generateseedream\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: generaterunway\n      description: Generate image with Runway\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: freepik.generaterunway\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: generatekling21pro\n      description: Generate video with Kling v2.1 Pro\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: freepik.generatekling21pro\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: generatekling25pro\n      description: Generate video with Kling v2.5 Pro\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: freepik.generatekling25pro\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name:\
  \ generateminimaxhailuo\n      description: Generate video with Minimax Hailuo 02 1080p\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: freepik.generateminimaxhailuo\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: imageupscaler\n      description: Creative image upscaler\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: freepik.imageupscaler\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: imagerelight\n      description: Relight image\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: freepik.imagerelight\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: imagestyletransfer\n      description: Apply style transfer\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: freepik.imagestyletransfer\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: removebackground\n      description: Remove background\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: freepik.removebackground\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: imageexpand\n      description: Expand image\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: freepik.imageexpand\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: generatemusic\n      description: Generate music\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: freepik.generatemusic\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listmusictasks\n      description: List music generation tasks\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent:\
  \ true\n      call: freepik.listmusictasks\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: generatesoundeffects\n      description: Generate sound effects\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: freepik.generatesoundeffects\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: audioisolation\n      description: Audio isolation from audio or video\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: freepik.audioisolation\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: gettask\n      description: Poll task status\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: freepik.gettask\n      with:\n        endpoint: tools.endpoint\n        taskId: tools.taskId\n      inputParameters:\n      - name: endpoint\n        type: string\n\
  \        description: endpoint\n        required: true\n      - name: taskId\n        type: string\n        description: taskId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    FREEPIK_TOKEN: FREEPIK_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/freepik/refs/heads/main/capabilities/freepik-capability.yaml
tags:
- Freepik
- API
tools:
- description: Search stock resources
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listresources
- description: Generate image with Mystic
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: generatemystic
- description: Generate image with Flux 2 Pro
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: generateflux2pro
- description: Generate image with Flux 2 Turbo
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: generateflux2turbo
- description: Generate image with Flux Pro v1.1
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: generatefluxprov11
- description: Generate image with Flux Dev
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: generatefluxdev
- description: Generate image with HyperFlux
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: generatehyperflux
- description: Generate image with Seedream v4.5
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: generateseedream
- description: Generate image with Runway
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: generaterunway
- description: Generate video with Kling v2.1 Pro
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: generatekling21pro
- description: Generate video with Kling v2.5 Pro
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: generatekling25pro
- description: Generate video with Minimax Hailuo 02 1080p
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: generateminimaxhailuo
- description: Creative image upscaler
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: imageupscaler
- description: Relight image
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: imagerelight
- description: Apply style transfer
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: imagestyletransfer
- description: Remove background
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: removebackground
- description: Expand image
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: imageexpand
- description: Generate music
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: generatemusic
- description: List music generation tasks
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listmusictasks
- description: Generate sound effects
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: generatesoundeffects
- description: Audio isolation from audio or video
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: audioisolation
- description: Poll task status
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettask
---
