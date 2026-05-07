---
categories: []
consumed_apis: []
description: Media management combining Stream video platform and Images service for uploading, processing, and delivering video and image content at scale. Used by content creators and media engineers.
layout: capability
name: Cloudflare Media and Content
operations:
- description: List videos.
  method: GET
  name: list-videos
  path: /v1/videos
- description: List images.
  method: GET
  name: list-images
  path: /v1/images
personas: []
provider_name: Cloudflare
provider_slug: cloudflare
search_terms:
- cloudflare
- ddos protection
- create a direct upload url for images.
- video
- stream list videos
- containers
- list live streaming inputs.
- list all images.
- delete a video.
- create a live streaming input.
- list images
- get image details.
- ai gateway
- delete an image.
- platform
- list all videos.
- list images.
- images delete image
- edge computing
- artificial intelligence
- create a direct upload url.
- edge
- stream create direct upload
- web performance
- upload an image.
- stream get video
- real-time communication
- serverless
- image management.
- api gateway
- images list images
- object storage
- stream delete video
- stream create live input
- stream list live inputs
- cloud
- stream upload video
- media
- images
- list videos
- list videos.
- list image variants.
- dns
- cdn
- video management.
- images upload image
- get video details.
- images create direct upload
- images get image
- security
- upload a video from url.
- images list variants
slug: media-and-content
source_filename: media-and-content.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Cloudflare Media and Content\n  description: Media management combining Stream video platform and Images service for uploading, processing, and delivering\n    video and image content at scale. Used by content creators and media engineers.\n  tags:\n  - Cloudflare\n  - Media\n  - Video\n  - Images\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    CLOUDFLARE_API_TOKEN: CLOUDFLARE_API_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: cloudflare-stream\n    baseUri: https://api.cloudflare.com/client/v4\n    description: Cloudflare Stream API for video management and live streaming.\n    authentication:\n      type: bearer\n      token: '{{CLOUDFLARE_API_TOKEN}}'\n    resources:\n    - name: videos\n      path: /accounts/{account_id}/stream\n      description: Manage videos.\n      operations:\n      - name: list-videos\n        method: GET\n        description: List all videos.\n    \
  \    inputParameters:\n        - name: account_id\n          in: path\n          type: string\n          required: true\n          description: Account identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: upload-video\n        method: POST\n        description: Upload a video from URL.\n        inputParameters:\n        - name: account_id\n          in: path\n          type: string\n          required: true\n          description: Account identifier.\n        body:\n          type: json\n          data:\n            url: '{{tools.url}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: video\n      path: /accounts/{account_id}/stream/{video_id}\n      description: Manage a specific video.\n      operations:\n      - name: get-video\n        method: GET\n        description: Get video details.\n   \
  \     inputParameters:\n        - name: account_id\n          in: path\n          type: string\n          required: true\n          description: Account identifier.\n        - name: video_id\n          in: path\n          type: string\n          required: true\n          description: Video identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-video\n        method: DELETE\n        description: Delete a video.\n        inputParameters:\n        - name: account_id\n          in: path\n          type: string\n          required: true\n          description: Account identifier.\n        - name: video_id\n          in: path\n          type: string\n          required: true\n          description: Video identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: live-inputs\n      path: /accounts/{account_id}/stream/live_inputs\n\
  \      description: Manage live inputs.\n      operations:\n      - name: list-live-inputs\n        method: GET\n        description: List live inputs.\n        inputParameters:\n        - name: account_id\n          in: path\n          type: string\n          required: true\n          description: Account identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-live-input\n        method: POST\n        description: Create a live input.\n        inputParameters:\n        - name: account_id\n          in: path\n          type: string\n          required: true\n          description: Account identifier.\n        body:\n          type: json\n          data:\n            meta: '{{tools.meta}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: direct-upload\n      path: /accounts/{account_id}/stream/direct_upload\n\
  \      description: Create direct upload URLs.\n      operations:\n      - name: create-direct-upload\n        method: POST\n        description: Create a direct upload URL.\n        inputParameters:\n        - name: account_id\n          in: path\n          type: string\n          required: true\n          description: Account identifier.\n        body:\n          type: json\n          data:\n            maxDurationSeconds: '{{tools.max_duration_seconds}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: cloudflare-images\n    baseUri: https://api.cloudflare.com/client/v4\n    description: Cloudflare Images API for managing image uploads, variants, and transformations.\n    authentication:\n      type: bearer\n      token: '{{CLOUDFLARE_API_TOKEN}}'\n    resources:\n    - name: images\n      path: /accounts/{account_id}/images/v1\n      description: Manage images.\n      operations:\n\
  \      - name: list-images\n        method: GET\n        description: List all images.\n        inputParameters:\n        - name: account_id\n          in: path\n          type: string\n          required: true\n          description: Account identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: upload-image\n        method: POST\n        description: Upload an image.\n        inputParameters:\n        - name: account_id\n          in: path\n          type: string\n          required: true\n          description: Account identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: image\n      path: /accounts/{account_id}/images/v1/{image_id}\n      description: Manage a specific image.\n      operations:\n      - name: get-image\n        method: GET\n        description: Get image details.\n     \
  \   inputParameters:\n        - name: account_id\n          in: path\n          type: string\n          required: true\n          description: Account identifier.\n        - name: image_id\n          in: path\n          type: string\n          required: true\n          description: Image identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-image\n        method: DELETE\n        description: Delete an image.\n        inputParameters:\n        - name: account_id\n          in: path\n          type: string\n          required: true\n          description: Account identifier.\n        - name: image_id\n          in: path\n          type: string\n          required: true\n          description: Image identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: variants\n      path: /accounts/{account_id}/images/v1/variants\n\
  \      description: Manage image variants.\n      operations:\n      - name: list-image-variants\n        method: GET\n        description: List image variants.\n        inputParameters:\n        - name: account_id\n          in: path\n          type: string\n          required: true\n          description: Account identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-image-variant\n        method: POST\n        description: Create an image variant.\n        inputParameters:\n        - name: account_id\n          in: path\n          type: string\n          required: true\n          description: Account identifier.\n        body:\n          type: json\n          data:\n            id: '{{tools.id}}'\n            options: '{{tools.options}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: direct-upload\n\
  \      path: /accounts/{account_id}/images/v2/direct_upload\n      description: Create direct upload URLs.\n      operations:\n      - name: create-image-direct-upload\n        method: POST\n        description: Create a direct upload URL for an image.\n        inputParameters:\n        - name: account_id\n          in: path\n          type: string\n          required: true\n          description: Account identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8083\n    namespace: media-content-api\n    description: Unified REST API for Cloudflare media and content services.\n    resources:\n    - path: /v1/videos\n      name: videos\n      description: Video management.\n      operations:\n      - method: GET\n        name: list-videos\n        description: List videos.\n        call: cloudflare-stream.list-videos\n        with:\n          account_id: rest.account_id\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/images\n      name: images\n      description: Image management.\n      operations:\n      - method: GET\n        name: list-images\n        description: List images.\n        call: cloudflare-images.list-images\n        with:\n          account_id: rest.account_id\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9083\n    namespace: media-content-mcp\n    transport: http\n    description: MCP server for AI-assisted Cloudflare media management.\n    tools:\n    - name: stream-list-videos\n      description: List all videos.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: cloudflare-stream.list-videos\n      with:\n        account_id: tools.account_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: stream-upload-video\n      description: Upload a video from URL.\n      hints:\n        readOnly:\
  \ false\n      call: cloudflare-stream.upload-video\n      with:\n        account_id: tools.account_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: stream-get-video\n      description: Get video details.\n      hints:\n        readOnly: true\n      call: cloudflare-stream.get-video\n      with:\n        account_id: tools.account_id\n        video_id: tools.video_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: stream-delete-video\n      description: Delete a video.\n      hints:\n        destructive: true\n        idempotent: true\n      call: cloudflare-stream.delete-video\n      with:\n        account_id: tools.account_id\n        video_id: tools.video_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: stream-list-live-inputs\n      description: List live streaming inputs.\n      hints:\n        readOnly: true\n      call: cloudflare-stream.list-live-inputs\n      with:\n        account_id:\
  \ tools.account_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: stream-create-live-input\n      description: Create a live streaming input.\n      hints:\n        readOnly: false\n      call: cloudflare-stream.create-live-input\n      with:\n        account_id: tools.account_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: stream-create-direct-upload\n      description: Create a direct upload URL.\n      hints:\n        readOnly: false\n      call: cloudflare-stream.create-direct-upload\n      with:\n        account_id: tools.account_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: images-list-images\n      description: List all images.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: cloudflare-images.list-images\n      with:\n        account_id: tools.account_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: images-upload-image\n\
  \      description: Upload an image.\n      hints:\n        readOnly: false\n      call: cloudflare-images.upload-image\n      with:\n        account_id: tools.account_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: images-get-image\n      description: Get image details.\n      hints:\n        readOnly: true\n      call: cloudflare-images.get-image\n      with:\n        account_id: tools.account_id\n        image_id: tools.image_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: images-delete-image\n      description: Delete an image.\n      hints:\n        destructive: true\n        idempotent: true\n      call: cloudflare-images.delete-image\n      with:\n        account_id: tools.account_id\n        image_id: tools.image_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: images-list-variants\n      description: List image variants.\n      hints:\n        readOnly: true\n      call:\
  \ cloudflare-images.list-image-variants\n      with:\n        account_id: tools.account_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: images-create-direct-upload\n      description: Create a direct upload URL for images.\n      hints:\n        readOnly: false\n      call: cloudflare-images.create-image-direct-upload\n      with:\n        account_id: tools.account_id\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/cloudflare/refs/heads/main/capabilities/media-and-content.yaml
tags:
- Cloudflare
- Media
- Video
- Images
tools:
- description: List all videos.
  hints:
    openWorld: true
    readOnly: true
  name: stream-list-videos
- description: Upload a video from URL.
  hints:
    readOnly: false
  name: stream-upload-video
- description: Get video details.
  hints:
    readOnly: true
  name: stream-get-video
- description: Delete a video.
  hints:
    destructive: true
    idempotent: true
  name: stream-delete-video
- description: List live streaming inputs.
  hints:
    readOnly: true
  name: stream-list-live-inputs
- description: Create a live streaming input.
  hints:
    readOnly: false
  name: stream-create-live-input
- description: Create a direct upload URL.
  hints:
    readOnly: false
  name: stream-create-direct-upload
- description: List all images.
  hints:
    openWorld: true
    readOnly: true
  name: images-list-images
- description: Upload an image.
  hints:
    readOnly: false
  name: images-upload-image
- description: Get image details.
  hints:
    readOnly: true
  name: images-get-image
- description: Delete an image.
  hints:
    destructive: true
    idempotent: true
  name: images-delete-image
- description: List image variants.
  hints:
    readOnly: true
  name: images-list-variants
- description: Create a direct upload URL for images.
  hints:
    readOnly: false
  name: images-create-direct-upload
---
