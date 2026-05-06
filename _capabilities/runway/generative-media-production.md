---
categories: []
consumed_apis: []
description: Comprehensive generative media production capability for Runway. Enables creative professionals, developers, and AI workflows to generate videos from text or images, animate characters with motion capture (Act Two), sync faces to audio (lip sync), enhance video quality (upscale, frame interpolation), generate sound effects, produce images from text, and build real-time conversational avatar experiences. Combines Runway's video generation, image generation, and characters APIs into unified creative production workflows.
layout: capability
name: Runway Generative Media Production
operations:
- description: Generate video from text prompt
  method: POST
  name: create-text-to-video
  path: /v1/text-to-video
- description: Generate video from image
  method: POST
  name: create-image-to-video
  path: /v1/image-to-video
- description: Transform video with text guidance
  method: POST
  name: create-video-to-video
  path: /v1/video-to-video
- description: Animate character using Act Two model
  method: POST
  name: create-character-performance
  path: /v1/character-performance
- description: Animate face to speak audio
  method: POST
  name: create-lip-sync
  path: /v1/lip-sync
- description: Upscale video quality
  method: POST
  name: create-video-upscale
  path: /v1/video-upscale
- description: Interpolate video frames
  method: POST
  name: create-frame-interpolation
  path: /v1/frame-interpolation
- description: Generate sound effects for video
  method: POST
  name: create-sound-effect
  path: /v1/sound-effects
- description: Generate image from text prompt
  method: POST
  name: create-text-to-image
  path: /v1/text-to-image
- description: Get task status and output URLs
  method: GET
  name: get-task
  path: /v1/tasks/{id}
- description: Create a conversational avatar
  method: POST
  name: create-avatar
  path: /v1/avatars
- description: Start a realtime avatar session
  method: POST
  name: create-session
  path: /v1/sessions
personas: []
provider_name: Runway
provider_slug: runway
search_terms:
- generate ai sound effects from a text description, optionally synchronized to a video
- cancel generation task
- transform video with text guidance
- check generation task
- generate sound effects
- video generation
- webrtc
- create video to video
- generate image from text
- upscale video quality
- create lip sync
- create a custom runway conversational avatar from a reference image with defined personality and voice
- image-to-video generation
- generate video from text prompt
- create avatar
- create session
- generative ai
- creative tools
- interpolate frames
- video resolution enhancement
- lip sync face to audio
- get task
- upload avatar knowledge
- transform an existing video using a text prompt as guidance with the gen-4 aleph model
- sync lips to audio
- generation task status and management
- generate sound effects for video
- generate a high-quality image from a text prompt using runway gen-4 image or gemini 3 pro image
- create sound effect
- get task status and output urls
- avatar realtime webrtc sessions
- animate a character image or video using a reference performance video with the act two model
- enhance video resolution and quality using runway's upscale model
- create conversational avatar
- artificial intelligence
- avatars
- generate a video from a text prompt using runway gen-4.5, veo 3.1, or veo 3.1 fast models. returns a task id to poll for completion.
- create image to video
- runway
- text-to-image generation
- machine learning
- check the status of a runway generation task and retrieve output urls when completed
- create video upscale
- animate character using act two model
- animate face to speak audio
- animate character
- generate image from text prompt
- generate video from image
- character animation from reference performance
- create text to video
- create frame interpolation
- create text to image
- create a conversational avatar
- characters
- text-to-video generation
- ai sound effect generation
- generate video from text
- cancel a pending or running runway generation task
- start a real-time webrtc session connecting a user to a runway avatar for live conversation
- image generation
- create character performance
- upscale video
- conversational avatar management
- start avatar session
- upload a knowledge document that an avatar can reference during live conversations
- generate a video from an input image, optionally guided by a text prompt. supports gen-4, gen-4 turbo, gen-4.5, and aleph models.
- video-to-video transformation
- transform video
- start a realtime avatar session
- video frame rate enhancement
- increase video frame rate and smoothness through ai frame interpolation
- interpolate video frames
- animate a face in an image or video to match provided audio - supports 28+ languages
slug: generative-media-production
source_filename: generative-media-production.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Runway Generative Media Production\n  description: Comprehensive generative media production capability for Runway. Enables creative professionals, developers,\n    and AI workflows to generate videos from text or images, animate characters with motion capture (Act Two), sync faces\n    to audio (lip sync), enhance video quality (upscale, frame interpolation), generate sound effects, produce images from\n    text, and build real-time conversational avatar experiences. Combines Runway's video generation, image generation, and\n    characters APIs into unified creative production workflows.\n  tags:\n  - Runway\n  - Video Generation\n  - Image Generation\n  - Generative AI\n  - Artificial Intelligence\n  - Creative Tools\n  - Avatars\n  - Characters\n  - Machine Learning\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    RUNWAY_API_KEY: RUNWAY_API_KEY\ncapability:\n  consumes:\n  - type: http\n   \
  \ namespace: runway-video\n    baseUri: https://api.dev.runwayml.com/v1\n    description: Runway video generation API\n    authentication:\n      type: bearer\n      token: '{{env.RUNWAY_API_KEY}}'\n    resources:\n    - name: image-to-video\n      path: /image_to_video\n      description: Generate video from an input image\n      operations:\n      - name: create-image-to-video\n        method: POST\n        description: Create image-to-video generation task\n        inputParameters:\n        - name: X-Runway-Version\n          in: header\n          type: string\n          required: true\n          description: API version header (2024-11-06)\n        body:\n          type: json\n          data:\n            model: '{{tools.model}}'\n            promptImage: '{{tools.promptImage}}'\n            promptText: '{{tools.promptText}}'\n            duration: '{{tools.duration}}'\n            ratio: '{{tools.ratio}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n    - name: text-to-video\n      path: /text_to_video\n      description: Generate video from text prompt only\n      operations:\n      - name: create-text-to-video\n        method: POST\n        description: Create text-to-video generation task\n        inputParameters:\n        - name: X-Runway-Version\n          in: header\n          type: string\n          required: true\n          description: API version header\n        body:\n          type: json\n          data:\n            model: '{{tools.model}}'\n            promptText: '{{tools.promptText}}'\n            duration: '{{tools.duration}}'\n            ratio: '{{tools.ratio}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: video-to-video\n      path: /video_to_video\n      description: Transform existing video with text guidance\n      operations:\n      - name: create-video-to-video\n    \
  \    method: POST\n        description: Create video-to-video generation task\n        inputParameters:\n        - name: X-Runway-Version\n          in: header\n          type: string\n          required: true\n          description: API version header\n        body:\n          type: json\n          data:\n            model: '{{tools.model}}'\n            promptVideo: '{{tools.promptVideo}}'\n            promptText: '{{tools.promptText}}'\n            ratio: '{{tools.ratio}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: character-performance\n      path: /character_performance\n      description: Animate characters using reference performance video\n      operations:\n      - name: create-character-performance\n        method: POST\n        description: Create character performance (Act Two) task\n        inputParameters:\n        - name: X-Runway-Version\n          in: header\n          type:\
  \ string\n          required: true\n          description: API version header\n        body:\n          type: json\n          data:\n            model: '{{tools.model}}'\n            character: '{{tools.character}}'\n            reference: '{{tools.reference}}'\n            ratio: '{{tools.ratio}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: lip-sync\n      path: /lip_sync\n      description: Animate face to speak audio\n      operations:\n      - name: create-lip-sync\n        method: POST\n        description: Create lip sync generation task\n        inputParameters:\n        - name: X-Runway-Version\n          in: header\n          type: string\n          required: true\n          description: API version header\n        body:\n          type: json\n          data:\n            model: '{{tools.model}}'\n            input: '{{tools.input}}'\n            audio: '{{tools.audio}}'\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: video-upscale\n      path: /video_upscale\n      description: Upscale video resolution\n      operations:\n      - name: create-video-upscale\n        method: POST\n        description: Create video upscale task\n        inputParameters:\n        - name: X-Runway-Version\n          in: header\n          type: string\n          required: true\n          description: API version header\n        body:\n          type: json\n          data:\n            model: '{{tools.model}}'\n            videoUri: '{{tools.videoUri}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: frame-interpolation\n      path: /frame_interpolation\n      description: Interpolate video frames for smoother motion\n      operations:\n      - name: create-frame-interpolation\n        method: POST\n        description:\
  \ Create frame interpolation task\n        inputParameters:\n        - name: X-Runway-Version\n          in: header\n          type: string\n          required: true\n          description: API version header\n        body:\n          type: json\n          data:\n            model: '{{tools.model}}'\n            videoUri: '{{tools.videoUri}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: sound-effect\n      path: /sound_effect\n      description: Generate AI sound effects for video\n      operations:\n      - name: create-sound-effect\n        method: POST\n        description: Create sound effect generation task\n        inputParameters:\n        - name: X-Runway-Version\n          in: header\n          type: string\n          required: true\n          description: API version header\n        body:\n          type: json\n          data:\n            model: '{{tools.model}}'\n            promptText:\
  \ '{{tools.promptText}}'\n            videoUri: '{{tools.videoUri}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tasks\n      path: /tasks/{id}\n      description: Task status and management\n      operations:\n      - name: get-task\n        method: GET\n        description: Get task status and output\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Task UUID\n        - name: X-Runway-Version\n          in: header\n          type: string\n          required: true\n          description: API version header\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-task\n        method: DELETE\n        description: Cancel or delete a task\n        inputParameters:\n        - name: id\n          in: path\n         \
  \ type: string\n          required: true\n          description: Task UUID\n        - name: X-Runway-Version\n          in: header\n          type: string\n          required: true\n          description: API version header\n    - name: uploads\n      path: /uploads\n      description: Upload media files for use in generation requests\n      operations:\n      - name: create-upload\n        method: POST\n        description: Upload a temporary media file\n        inputParameters:\n        - name: X-Runway-Version\n          in: header\n          type: string\n          required: true\n          description: API version header\n        body:\n          type: json\n          data:\n            filename: '{{tools.filename}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: runway-image\n    baseUri: https://api.dev.runwayml.com/v1\n    description: Runway image generation API\n  \
  \  authentication:\n      type: bearer\n      token: '{{env.RUNWAY_API_KEY}}'\n    resources:\n    - name: text-to-image\n      path: /text_to_image\n      description: Generate images from text prompts\n      operations:\n      - name: create-text-to-image\n        method: POST\n        description: Create text-to-image generation task\n        inputParameters:\n        - name: X-Runway-Version\n          in: header\n          type: string\n          required: true\n          description: API version header (2024-11-06)\n        body:\n          type: json\n          data:\n            model: '{{tools.model}}'\n            promptText: '{{tools.promptText}}'\n            ratio: '{{tools.ratio}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tasks\n      path: /tasks/{id}\n      description: Poll image generation task status\n      operations:\n      - name: get-task\n        method: GET\n    \
  \    description: Get task status and output URLs\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Task UUID\n        - name: X-Runway-Version\n          in: header\n          type: string\n          required: true\n          description: API version header\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: runway-characters\n    baseUri: https://api.dev.runwayml.com/v1\n    description: Runway Characters API for conversational avatars\n    authentication:\n      type: bearer\n      token: '{{env.RUNWAY_API_KEY}}'\n    resources:\n    - name: avatars\n      path: /avatars\n      description: Create and manage persistent avatar personas\n      operations:\n      - name: create-avatar\n        method: POST\n        description: Create a new avatar with appearance, voice, and personality\n   \
  \     inputParameters:\n        - name: X-Runway-Version\n          in: header\n          type: string\n          required: true\n          description: API version header (2024-11-06)\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            referenceImage: '{{tools.referenceImage}}'\n            personality: '{{tools.personality}}'\n            voice: '{{tools.voice}}'\n            openingMessage: '{{tools.openingMessage}}'\n            documentIds: '{{tools.documentIds}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: realtime-sessions\n      path: /realtime_sessions\n      description: Create WebRTC sessions for live avatar conversations\n      operations:\n      - name: create-session\n        method: POST\n        description: Create a realtime WebRTC session\n        inputParameters:\n        - name: X-Runway-Version\n          in: header\n  \
  \        type: string\n          required: true\n          description: API version header\n        body:\n          type: json\n          data:\n            model: '{{tools.model}}'\n            avatar: '{{tools.avatar}}'\n            maxSessionDurationSeconds: '{{tools.maxSessionDurationSeconds}}'\n            personality: '{{tools.personality}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: documents\n      path: /documents\n      description: Upload knowledge documents for avatars\n      operations:\n      - name: create-document\n        method: POST\n        description: Upload a knowledge document\n        inputParameters:\n        - name: X-Runway-Version\n          in: header\n          type: string\n          required: true\n          description: API version header\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            content: '{{tools.content}}'\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: document\n      path: /documents/{id}\n      description: Manage individual knowledge documents\n      operations:\n      - name: delete-document\n        method: DELETE\n        description: Delete a knowledge document\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Document UUID\n        - name: X-Runway-Version\n          in: header\n          type: string\n          required: true\n          description: API version header\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: generative-media-api\n    description: Unified REST API for Runway generative media production workflows.\n    resources:\n    - path: /v1/text-to-video\n      name: text-to-video\n      description: Text-to-video generation\n      operations:\n      - method: POST\n        name:\
  \ create-text-to-video\n        description: Generate video from text prompt\n        call: runway-video.create-text-to-video\n        with:\n          model: rest.model\n          promptText: rest.promptText\n          duration: rest.duration\n          ratio: rest.ratio\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/image-to-video\n      name: image-to-video\n      description: Image-to-video generation\n      operations:\n      - method: POST\n        name: create-image-to-video\n        description: Generate video from image\n        call: runway-video.create-image-to-video\n        with:\n          model: rest.model\n          promptImage: rest.promptImage\n          promptText: rest.promptText\n          duration: rest.duration\n          ratio: rest.ratio\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/video-to-video\n      name: video-to-video\n      description: Video-to-video transformation\n\
  \      operations:\n      - method: POST\n        name: create-video-to-video\n        description: Transform video with text guidance\n        call: runway-video.create-video-to-video\n        with:\n          model: rest.model\n          promptVideo: rest.promptVideo\n          promptText: rest.promptText\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/character-performance\n      name: character-performance\n      description: Character animation from reference performance\n      operations:\n      - method: POST\n        name: create-character-performance\n        description: Animate character using Act Two model\n        call: runway-video.create-character-performance\n        with:\n          model: rest.model\n          character: rest.character\n          reference: rest.reference\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/lip-sync\n      name: lip-sync\n      description: Lip sync face\
  \ to audio\n      operations:\n      - method: POST\n        name: create-lip-sync\n        description: Animate face to speak audio\n        call: runway-video.create-lip-sync\n        with:\n          model: rest.model\n          input: rest.input\n          audio: rest.audio\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/video-upscale\n      name: video-upscale\n      description: Video resolution enhancement\n      operations:\n      - method: POST\n        name: create-video-upscale\n        description: Upscale video quality\n        call: runway-video.create-video-upscale\n        with:\n          model: rest.model\n          videoUri: rest.videoUri\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/frame-interpolation\n      name: frame-interpolation\n      description: Video frame rate enhancement\n      operations:\n      - method: POST\n        name: create-frame-interpolation\n        description:\
  \ Interpolate video frames\n        call: runway-video.create-frame-interpolation\n        with:\n          model: rest.model\n          videoUri: rest.videoUri\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/sound-effects\n      name: sound-effects\n      description: AI sound effect generation\n      operations:\n      - method: POST\n        name: create-sound-effect\n        description: Generate sound effects for video\n        call: runway-video.create-sound-effect\n        with:\n          model: rest.model\n          promptText: rest.promptText\n          videoUri: rest.videoUri\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/text-to-image\n      name: text-to-image\n      description: Text-to-image generation\n      operations:\n      - method: POST\n        name: create-text-to-image\n        description: Generate image from text prompt\n        call: runway-image.create-text-to-image\n    \
  \    with:\n          model: rest.model\n          promptText: rest.promptText\n          ratio: rest.ratio\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/tasks/{id}\n      name: task\n      description: Generation task status and management\n      operations:\n      - method: GET\n        name: get-task\n        description: Get task status and output URLs\n        call: runway-video.get-task\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/avatars\n      name: avatars\n      description: Conversational avatar management\n      operations:\n      - method: POST\n        name: create-avatar\n        description: Create a conversational avatar\n        call: runway-characters.create-avatar\n        with:\n          name: rest.name\n          referenceImage: rest.referenceImage\n          personality: rest.personality\n          voice: rest.voice\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /v1/sessions\n      name: sessions\n      description: Avatar realtime WebRTC sessions\n      operations:\n      - method: POST\n        name: create-session\n        description: Start a realtime avatar session\n        call: runway-characters.create-session\n        with:\n          model: rest.model\n          avatar: rest.avatar\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: generative-media-mcp\n    transport: http\n    description: MCP server for AI-assisted generative media production using Runway APIs.\n    tools:\n    - name: generate-video-from-text\n      description: Generate a video from a text prompt using Runway Gen-4.5, Veo 3.1, or Veo 3.1 Fast models. Returns a task\n        ID to poll for completion.\n      hints:\n        readOnly: false\n        openWorld: false\n      call: runway-video.create-text-to-video\n      with:\n        model:\
  \ tools.model\n        promptText: tools.promptText\n        duration: tools.duration\n        ratio: tools.ratio\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: generate-video-from-image\n      description: Generate a video from an input image, optionally guided by a text prompt. Supports Gen-4, Gen-4 Turbo,\n        Gen-4.5, and Aleph models.\n      hints:\n        readOnly: false\n        openWorld: false\n      call: runway-video.create-image-to-video\n      with:\n        model: tools.model\n        promptImage: tools.promptImage\n        promptText: tools.promptText\n        duration: tools.duration\n        ratio: tools.ratio\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: transform-video\n      description: Transform an existing video using a text prompt as guidance with the Gen-4 Aleph model\n      hints:\n        readOnly: false\n        openWorld: false\n      call: runway-video.create-video-to-video\n      with:\n\
  \        model: tools.model\n        promptVideo: tools.promptVideo\n        promptText: tools.promptText\n        ratio: tools.ratio\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: animate-character\n      description: Animate a character image or video using a reference performance video with the Act Two model\n      hints:\n        readOnly: false\n        openWorld: false\n      call: runway-video.create-character-performance\n      with:\n        model: tools.model\n        character: tools.character\n        reference: tools.reference\n        ratio: tools.ratio\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: sync-lips-to-audio\n      description: Animate a face in an image or video to match provided audio - supports 28+ languages\n      hints:\n        readOnly: false\n        openWorld: false\n      call: runway-video.create-lip-sync\n      with:\n        model: tools.model\n        input: tools.input\n        audio:\
  \ tools.audio\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: upscale-video\n      description: Enhance video resolution and quality using Runway's upscale model\n      hints:\n        readOnly: false\n        openWorld: false\n      call: runway-video.create-video-upscale\n      with:\n        model: tools.model\n        videoUri: tools.videoUri\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: interpolate-frames\n      description: Increase video frame rate and smoothness through AI frame interpolation\n      hints:\n        readOnly: false\n        openWorld: false\n      call: runway-video.create-frame-interpolation\n      with:\n        model: tools.model\n        videoUri: tools.videoUri\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: generate-sound-effects\n      description: Generate AI sound effects from a text description, optionally synchronized to a video\n      hints:\n       \
  \ readOnly: false\n        openWorld: false\n      call: runway-video.create-sound-effect\n      with:\n        model: tools.model\n        promptText: tools.promptText\n        videoUri: tools.videoUri\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: generate-image-from-text\n      description: Generate a high-quality image from a text prompt using Runway Gen-4 Image or Gemini 3 Pro Image\n      hints:\n        readOnly: false\n        openWorld: false\n      call: runway-image.create-text-to-image\n      with:\n        model: tools.model\n        promptText: tools.promptText\n        ratio: tools.ratio\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: check-generation-task\n      description: Check the status of a Runway generation task and retrieve output URLs when completed\n      hints:\n        readOnly: true\n        openWorld: true\n      call: runway-video.get-task\n      with:\n        id: tools.id\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: cancel-generation-task\n      description: Cancel a pending or running Runway generation task\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: runway-video.delete-task\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-conversational-avatar\n      description: Create a custom Runway conversational avatar from a reference image with defined personality and voice\n      hints:\n        readOnly: false\n        openWorld: false\n      call: runway-characters.create-avatar\n      with:\n        name: tools.name\n        referenceImage: tools.referenceImage\n        personality: tools.personality\n        voice: tools.voice\n        openingMessage: tools.openingMessage\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: start-avatar-session\n      description: Start a real-time WebRTC\
  \ session connecting a user to a Runway avatar for live conversation\n      hints:\n        readOnly: false\n        openWorld: false\n      call: runway-characters.create-session\n      with:\n        model: tools.model\n        avatar: tools.avatar\n        maxSessionDurationSeconds: tools.maxSessionDurationSeconds\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: upload-avatar-knowledge\n      description: Upload a knowledge document that an avatar can reference during live conversations\n      hints:\n        readOnly: false\n        openWorld: false\n      call: runway-characters.create-document\n      with:\n        name: tools.name\n        content: tools.content\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/runway/refs/heads/main/capabilities/generative-media-production.yaml
tags:
- Runway
- Video Generation
- Image Generation
- Generative AI
- Artificial Intelligence
- Creative Tools
- Avatars
- Characters
- Machine Learning
tools:
- description: Generate a video from a text prompt using Runway Gen-4.5, Veo 3.1, or Veo 3.1 Fast models. Returns a task ID to poll for completion.
  hints:
    openWorld: false
    readOnly: false
  name: generate-video-from-text
- description: Generate a video from an input image, optionally guided by a text prompt. Supports Gen-4, Gen-4 Turbo, Gen-4.5, and Aleph models.
  hints:
    openWorld: false
    readOnly: false
  name: generate-video-from-image
- description: Transform an existing video using a text prompt as guidance with the Gen-4 Aleph model
  hints:
    openWorld: false
    readOnly: false
  name: transform-video
- description: Animate a character image or video using a reference performance video with the Act Two model
  hints:
    openWorld: false
    readOnly: false
  name: animate-character
- description: Animate a face in an image or video to match provided audio - supports 28+ languages
  hints:
    openWorld: false
    readOnly: false
  name: sync-lips-to-audio
- description: Enhance video resolution and quality using Runway's upscale model
  hints:
    openWorld: false
    readOnly: false
  name: upscale-video
- description: Increase video frame rate and smoothness through AI frame interpolation
  hints:
    openWorld: false
    readOnly: false
  name: interpolate-frames
- description: Generate AI sound effects from a text description, optionally synchronized to a video
  hints:
    openWorld: false
    readOnly: false
  name: generate-sound-effects
- description: Generate a high-quality image from a text prompt using Runway Gen-4 Image or Gemini 3 Pro Image
  hints:
    openWorld: false
    readOnly: false
  name: generate-image-from-text
- description: Check the status of a Runway generation task and retrieve output URLs when completed
  hints:
    openWorld: true
    readOnly: true
  name: check-generation-task
- description: Cancel a pending or running Runway generation task
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: cancel-generation-task
- description: Create a custom Runway conversational avatar from a reference image with defined personality and voice
  hints:
    openWorld: false
    readOnly: false
  name: create-conversational-avatar
- description: Start a real-time WebRTC session connecting a user to a Runway avatar for live conversation
  hints:
    openWorld: false
    readOnly: false
  name: start-avatar-session
- description: Upload a knowledge document that an avatar can reference during live conversations
  hints:
    openWorld: false
    readOnly: false
  name: upload-avatar-knowledge
---
