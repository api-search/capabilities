---
categories: []
consumed_apis: []
description: The Ludo.ai REST API provides programmatic access to AI-powered game asset generation capabilities. Developers can generate sprites, icons, UI assets, textures, and backgrounds through image generation endpoints, edit existing images with text instructions, convert 2D images to 3D GLB models with PBR textures, create animated spritesheets from static images, produce sound effects, music tracks, character voices, and generate short videos. All API requests require an API key passed via the Authentication header, and requests consume credits that vary by endpoint type. The API is currently in be
layout: capability
name: Ludo.ai REST API
operations:
- description: Ludo.ai Generate a game-ready image
  method: POST
  name: createimage
  path: /images/create
- description: Ludo.ai Edit an existing image
  method: POST
  name: editimage
  path: /images/edit
- description: Ludo.ai Generate an image matching a reference style
  method: POST
  name: generatewithstyle
  path: /images/generate-with-style
- description: Ludo.ai Generate a new pose for an existing sprite
  method: POST
  name: generatepose
  path: /images/generate-pose
- description: Ludo.ai Remove background from an image
  method: POST
  name: removeimagebackground
  path: /images/remove-background
- description: Ludo.ai Create animated spritesheets from static images
  method: POST
  name: animatesprite
  path: /sprites/animate
- description: Ludo.ai Transfer motion onto a static sprite
  method: POST
  name: transfermotion
  path: /sprites/transfer-motion
- description: Ludo.ai List available animation presets
  method: GET
  name: listanimationpresets
  path: /animation-presets
- description: Ludo.ai Convert a 2D image to a 3D model
  method: POST
  name: create3dmodel
  path: /3d-models/create
- description: Ludo.ai Generate a short video from an image
  method: POST
  name: createvideo
  path: /videos/create
- description: Ludo.ai Generate a game sound effect
  method: POST
  name: createsoundeffect
  path: /audio/sound-effects
- description: Ludo.ai Generate background music
  method: POST
  name: createmusic
  path: /audio/music
- description: Ludo.ai Generate a unique character voice
  method: POST
  name: createvoice
  path: /audio/voice
- description: Ludo.ai Clone a voice from an audio sample
  method: POST
  name: createspeech
  path: /audio/speech
- description: Ludo.ai Generate speech using a preset voice
  method: POST
  name: createspeechpreset
  path: /audio/speech-preset
- description: Ludo.ai Retrieve generated image results
  method: GET
  name: getimageresults
  path: /results/images
- description: Ludo.ai Retrieve generated spritesheet results
  method: GET
  name: getspriteresults
  path: /results/sprites
- description: Ludo.ai Retrieve generated video results
  method: GET
  name: getvideoresults
  path: /results/videos
- description: Ludo.ai Retrieve generated audio results
  method: GET
  name: getaudioresults
  path: /results/audio
- description: Ludo.ai Retrieve generated 3D model results
  method: GET
  name: get3dmodelresults
  path: /results/3d-models
personas: []
provider_name: Ludo.ai
provider_slug: ludo-ai
search_terms:
- createmusic
- getspriteresults
- ludo.ai generate a unique character voice
- ludo.ai transfer motion onto a static sprite
- getaudioresults
- ludo.ai generate an image matching a reference style
- create3dmodel
- ludo.ai clone a voice from an audio sample
- createvoice
- ludo.ai generate background music
- ai
- api
- game development
- listanimationpresets
- getvideoresults
- ludo.ai generate speech using a preset voice
- createimage
- ludo.ai generate a game sound effect
- ludo.ai remove background from an image
- getimageresults
- createsoundeffect
- artificial intelligence
- createspeech
- game design
- removeimagebackground
- ludo.ai edit an existing image
- asset generation
- generatewithstyle
- ludo.ai retrieve generated image results
- transfermotion
- ludo.ai generate a game-ready image
- ludo.ai list available animation presets
- ludo.ai retrieve generated spritesheet results
- ludo.ai generate a new pose for an existing sprite
- ludo.ai retrieve generated 3d model results
- createspeechpreset
- ludo.ai retrieve generated video results
- ludo.ai generate a short video from an image
- editimage
- ludo.ai retrieve generated audio results
- ludo
- animatesprite
- generatepose
- ludo.ai convert a 2d image to a 3d model
- createvideo
- get3dmodelresults
- ludo.ai create animated spritesheets from static images
slug: ludo-ai-capability
source_filename: ludo-ai-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Ludo.ai REST API\n  description: The Ludo.ai REST API provides programmatic access to AI-powered game asset generation capabilities. Developers\n    can generate sprites, icons, UI assets, textures, and backgrounds through image generation endpoints, edit existing images\n    with text instructions, convert 2D images to 3D GLB models with PBR textures, create animated spritesheets from static\n    images, produce sound effects, music tracks, character voices, and generate short videos. All API requests require an\n    API key passed via the Authentication header, and requests consume credits that vary by endpoint type. The API is currently\n    in be\n  tags:\n  - Ludo\n  - Ai\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: ludo-ai\n    baseUri: https://api.ludo.ai/api\n    description: Ludo.ai REST API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n\
  \      name: Authentication\n      value: '{{LUDO_AI_TOKEN}}'\n    resources:\n    - name: images-create\n      path: /images/create\n      operations:\n      - name: createimage\n        method: POST\n        description: Ludo.ai Generate a game-ready image\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: images-edit\n      path: /images/edit\n      operations:\n      - name: editimage\n        method: POST\n        description: Ludo.ai Edit an existing image\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: images-generate-with-style\n      path: /images/generate-with-style\n      operations:\n      - name: generatewithstyle\n        method: POST\n        description: Ludo.ai Generate an image matching a reference style\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n   \
  \       type: object\n          value: $.\n    - name: images-generate-pose\n      path: /images/generate-pose\n      operations:\n      - name: generatepose\n        method: POST\n        description: Ludo.ai Generate a new pose for an existing sprite\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: images-remove-background\n      path: /images/remove-background\n      operations:\n      - name: removeimagebackground\n        method: POST\n        description: Ludo.ai Remove background from an image\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: sprites-animate\n      path: /sprites/animate\n      operations:\n      - name: animatesprite\n        method: POST\n        description: Ludo.ai Create animated spritesheets from static images\n        outputRawFormat: json\n        outputParameters:\n        -\
  \ name: result\n          type: object\n          value: $.\n    - name: sprites-transfer-motion\n      path: /sprites/transfer-motion\n      operations:\n      - name: transfermotion\n        method: POST\n        description: Ludo.ai Transfer motion onto a static sprite\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: animation-presets\n      path: /animation-presets\n      operations:\n      - name: listanimationpresets\n        method: GET\n        description: Ludo.ai List available animation presets\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: 3d-models-create\n      path: /3d-models/create\n      operations:\n      - name: create3dmodel\n        method: POST\n        description: Ludo.ai Convert a 2D image to a 3D model\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n    - name: videos-create\n      path: /videos/create\n      operations:\n      - name: createvideo\n        method: POST\n        description: Ludo.ai Generate a short video from an image\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: audio-sound-effects\n      path: /audio/sound-effects\n      operations:\n      - name: createsoundeffect\n        method: POST\n        description: Ludo.ai Generate a game sound effect\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: audio-music\n      path: /audio/music\n      operations:\n      - name: createmusic\n        method: POST\n        description: Ludo.ai Generate background music\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name:\
  \ audio-voice\n      path: /audio/voice\n      operations:\n      - name: createvoice\n        method: POST\n        description: Ludo.ai Generate a unique character voice\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: audio-speech\n      path: /audio/speech\n      operations:\n      - name: createspeech\n        method: POST\n        description: Ludo.ai Clone a voice from an audio sample\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: audio-speech-preset\n      path: /audio/speech-preset\n      operations:\n      - name: createspeechpreset\n        method: POST\n        description: Ludo.ai Generate speech using a preset voice\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: results-images\n      path: /results/images\n\
  \      operations:\n      - name: getimageresults\n        method: GET\n        description: Ludo.ai Retrieve generated image results\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: results-sprites\n      path: /results/sprites\n      operations:\n      - name: getspriteresults\n        method: GET\n        description: Ludo.ai Retrieve generated spritesheet results\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: results-videos\n      path: /results/videos\n      operations:\n      - name: getvideoresults\n        method: GET\n        description: Ludo.ai Retrieve generated video results\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: results-audio\n      path: /results/audio\n      operations:\n      - name: getaudioresults\n\
  \        method: GET\n        description: Ludo.ai Retrieve generated audio results\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: results-3d-models\n      path: /results/3d-models\n      operations:\n      - name: get3dmodelresults\n        method: GET\n        description: Ludo.ai Retrieve generated 3D model results\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: ludo-ai-rest\n    description: REST adapter for Ludo.ai REST API.\n    resources:\n    - path: /images/create\n      name: createimage\n      operations:\n      - method: POST\n        name: createimage\n        description: Ludo.ai Generate a game-ready image\n        call: ludo-ai.createimage\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /images/edit\n  \
  \    name: editimage\n      operations:\n      - method: POST\n        name: editimage\n        description: Ludo.ai Edit an existing image\n        call: ludo-ai.editimage\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /images/generate-with-style\n      name: generatewithstyle\n      operations:\n      - method: POST\n        name: generatewithstyle\n        description: Ludo.ai Generate an image matching a reference style\n        call: ludo-ai.generatewithstyle\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /images/generate-pose\n      name: generatepose\n      operations:\n      - method: POST\n        name: generatepose\n        description: Ludo.ai Generate a new pose for an existing sprite\n        call: ludo-ai.generatepose\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /images/remove-background\n      name: removeimagebackground\n      operations:\n      - method:\
  \ POST\n        name: removeimagebackground\n        description: Ludo.ai Remove background from an image\n        call: ludo-ai.removeimagebackground\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /sprites/animate\n      name: animatesprite\n      operations:\n      - method: POST\n        name: animatesprite\n        description: Ludo.ai Create animated spritesheets from static images\n        call: ludo-ai.animatesprite\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /sprites/transfer-motion\n      name: transfermotion\n      operations:\n      - method: POST\n        name: transfermotion\n        description: Ludo.ai Transfer motion onto a static sprite\n        call: ludo-ai.transfermotion\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /animation-presets\n      name: listanimationpresets\n      operations:\n      - method: GET\n        name: listanimationpresets\n\
  \        description: Ludo.ai List available animation presets\n        call: ludo-ai.listanimationpresets\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /3d-models/create\n      name: create3dmodel\n      operations:\n      - method: POST\n        name: create3dmodel\n        description: Ludo.ai Convert a 2D image to a 3D model\n        call: ludo-ai.create3dmodel\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /videos/create\n      name: createvideo\n      operations:\n      - method: POST\n        name: createvideo\n        description: Ludo.ai Generate a short video from an image\n        call: ludo-ai.createvideo\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /audio/sound-effects\n      name: createsoundeffect\n      operations:\n      - method: POST\n        name: createsoundeffect\n        description: Ludo.ai Generate a game sound effect\n        call: ludo-ai.createsoundeffect\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /audio/music\n      name: createmusic\n      operations:\n      - method: POST\n        name: createmusic\n        description: Ludo.ai Generate background music\n        call: ludo-ai.createmusic\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /audio/voice\n      name: createvoice\n      operations:\n      - method: POST\n        name: createvoice\n        description: Ludo.ai Generate a unique character voice\n        call: ludo-ai.createvoice\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /audio/speech\n      name: createspeech\n      operations:\n      - method: POST\n        name: createspeech\n        description: Ludo.ai Clone a voice from an audio sample\n        call: ludo-ai.createspeech\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /audio/speech-preset\n      name: createspeechpreset\n\
  \      operations:\n      - method: POST\n        name: createspeechpreset\n        description: Ludo.ai Generate speech using a preset voice\n        call: ludo-ai.createspeechpreset\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /results/images\n      name: getimageresults\n      operations:\n      - method: GET\n        name: getimageresults\n        description: Ludo.ai Retrieve generated image results\n        call: ludo-ai.getimageresults\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /results/sprites\n      name: getspriteresults\n      operations:\n      - method: GET\n        name: getspriteresults\n        description: Ludo.ai Retrieve generated spritesheet results\n        call: ludo-ai.getspriteresults\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /results/videos\n      name: getvideoresults\n      operations:\n      - method: GET\n        name: getvideoresults\n\
  \        description: Ludo.ai Retrieve generated video results\n        call: ludo-ai.getvideoresults\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /results/audio\n      name: getaudioresults\n      operations:\n      - method: GET\n        name: getaudioresults\n        description: Ludo.ai Retrieve generated audio results\n        call: ludo-ai.getaudioresults\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /results/3d-models\n      name: get3dmodelresults\n      operations:\n      - method: GET\n        name: get3dmodelresults\n        description: Ludo.ai Retrieve generated 3D model results\n        call: ludo-ai.get3dmodelresults\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: ludo-ai-mcp\n    transport: http\n    description: MCP adapter for Ludo.ai REST API for AI agent use.\n    tools:\n    - name: createimage\n      description:\
  \ Ludo.ai Generate a game-ready image\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: ludo-ai.createimage\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: editimage\n      description: Ludo.ai Edit an existing image\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: ludo-ai.editimage\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: generatewithstyle\n      description: Ludo.ai Generate an image matching a reference style\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: ludo-ai.generatewithstyle\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: generatepose\n      description: Ludo.ai Generate a new pose for an existing sprite\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n  \
  \    call: ludo-ai.generatepose\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: removeimagebackground\n      description: Ludo.ai Remove background from an image\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: ludo-ai.removeimagebackground\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: animatesprite\n      description: Ludo.ai Create animated spritesheets from static images\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: ludo-ai.animatesprite\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: transfermotion\n      description: Ludo.ai Transfer motion onto a static sprite\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: ludo-ai.transfermotion\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name:\
  \ listanimationpresets\n      description: Ludo.ai List available animation presets\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: ludo-ai.listanimationpresets\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create3dmodel\n      description: Ludo.ai Convert a 2D image to a 3D model\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: ludo-ai.create3dmodel\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createvideo\n      description: Ludo.ai Generate a short video from an image\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: ludo-ai.createvideo\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createsoundeffect\n      description: Ludo.ai Generate a game sound effect\n      hints:\n        readOnly: false\n        destructive:\
  \ false\n        idempotent: false\n      call: ludo-ai.createsoundeffect\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createmusic\n      description: Ludo.ai Generate background music\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: ludo-ai.createmusic\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createvoice\n      description: Ludo.ai Generate a unique character voice\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: ludo-ai.createvoice\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createspeech\n      description: Ludo.ai Clone a voice from an audio sample\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: ludo-ai.createspeech\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createspeechpreset\n\
  \      description: Ludo.ai Generate speech using a preset voice\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: ludo-ai.createspeechpreset\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getimageresults\n      description: Ludo.ai Retrieve generated image results\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: ludo-ai.getimageresults\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getspriteresults\n      description: Ludo.ai Retrieve generated spritesheet results\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: ludo-ai.getspriteresults\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getvideoresults\n      description: Ludo.ai Retrieve generated video results\n      hints:\n        readOnly: true\n        destructive: false\n\
  \        idempotent: true\n      call: ludo-ai.getvideoresults\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getaudioresults\n      description: Ludo.ai Retrieve generated audio results\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: ludo-ai.getaudioresults\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get3dmodelresults\n      description: Ludo.ai Retrieve generated 3D model results\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: ludo-ai.get3dmodelresults\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    LUDO_AI_TOKEN: LUDO_AI_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/ludo-ai/refs/heads/main/capabilities/ludo-ai-capability.yaml
tags:
- Ludo
- Ai
- API
tools:
- description: Ludo.ai Generate a game-ready image
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createimage
- description: Ludo.ai Edit an existing image
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: editimage
- description: Ludo.ai Generate an image matching a reference style
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: generatewithstyle
- description: Ludo.ai Generate a new pose for an existing sprite
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: generatepose
- description: Ludo.ai Remove background from an image
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: removeimagebackground
- description: Ludo.ai Create animated spritesheets from static images
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: animatesprite
- description: Ludo.ai Transfer motion onto a static sprite
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: transfermotion
- description: Ludo.ai List available animation presets
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listanimationpresets
- description: Ludo.ai Convert a 2D image to a 3D model
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create3dmodel
- description: Ludo.ai Generate a short video from an image
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createvideo
- description: Ludo.ai Generate a game sound effect
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createsoundeffect
- description: Ludo.ai Generate background music
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createmusic
- description: Ludo.ai Generate a unique character voice
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createvoice
- description: Ludo.ai Clone a voice from an audio sample
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createspeech
- description: Ludo.ai Generate speech using a preset voice
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createspeechpreset
- description: Ludo.ai Retrieve generated image results
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getimageresults
- description: Ludo.ai Retrieve generated spritesheet results
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getspriteresults
- description: Ludo.ai Retrieve generated video results
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getvideoresults
- description: Ludo.ai Retrieve generated audio results
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getaudioresults
- description: Ludo.ai Retrieve generated 3D model results
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get3dmodelresults
---
