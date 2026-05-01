---
categories: []
consumed_apis:
- cloudflare-stream
- cloudflare-images
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
- real-time communication
- serverless
- security
- images list variants
- list all videos.
- edge
- images
- images create direct upload
- media
- video
- cloudflare
- delete a video.
- list live streaming inputs.
- list image variants.
- dns
- edge computing
- object storage
- artificial intelligence
- get image details.
- list images
- stream create direct upload
- upload a video from url.
- video management.
- get video details.
- create a direct upload url for images.
- images list images
- stream get video
- stream upload video
- web performance
- cdn
- ai gateway
- containers
- stream delete video
- create a live streaming input.
- stream list videos
- list all images.
- list videos.
- create a direct upload url.
- list images.
- upload an image.
- delete an image.
- api gateway
- cloud
- stream create live input
- stream list live inputs
- platform
- images delete image
- image management.
- ddos protection
- list videos
- images upload image
- images get image
slug: media-and-content
source_filename: media-and-content.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Cloudflare Media and Content\"\n  description: \"Media management combining Stream video platform and Images service for uploading, processing, and delivering video and image content at scale. Used by content creators and media engineers.\"\n  tags:\n    - Cloudflare\n    - Media\n    - Video\n    - Images\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      CLOUDFLARE_API_TOKEN: CLOUDFLARE_API_TOKEN\n\ncapability:\n  consumes:\n    - import: cloudflare-stream\n      location: ./shared/stream.yaml\n    - import: cloudflare-images\n      location: ./shared/images.yaml\n\n  exposes:\n    - type: rest\n      port: 8083\n      namespace: media-content-api\n      description: \"Unified REST API for Cloudflare media and content services.\"\n      resources:\n        - path: /v1/videos\n          name: videos\n          description: \"Video management.\"\n          operations:\n      \
  \      - method: GET\n              name: list-videos\n              description: \"List videos.\"\n              call: \"cloudflare-stream.list-videos\"\n              with:\n                account_id: \"rest.account_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/images\n          name: images\n          description: \"Image management.\"\n          operations:\n            - method: GET\n              name: list-images\n              description: \"List images.\"\n              call: \"cloudflare-images.list-images\"\n              with:\n                account_id: \"rest.account_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9083\n      namespace: media-content-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Cloudflare media management.\"\n      tools:\n        - name: stream-list-videos\n\
  \          description: \"List all videos.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"cloudflare-stream.list-videos\"\n          with:\n            account_id: \"tools.account_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: stream-upload-video\n          description: \"Upload a video from URL.\"\n          hints:\n            readOnly: false\n          call: \"cloudflare-stream.upload-video\"\n          with:\n            account_id: \"tools.account_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: stream-get-video\n          description: \"Get video details.\"\n          hints:\n            readOnly: true\n          call: \"cloudflare-stream.get-video\"\n          with:\n            account_id: \"tools.account_id\"\n            video_id: \"tools.video_id\"\n          outputParameters:\n            - type: object\n\
  \              mapping: \"$.\"\n        - name: stream-delete-video\n          description: \"Delete a video.\"\n          hints:\n            destructive: true\n            idempotent: true\n          call: \"cloudflare-stream.delete-video\"\n          with:\n            account_id: \"tools.account_id\"\n            video_id: \"tools.video_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: stream-list-live-inputs\n          description: \"List live streaming inputs.\"\n          hints:\n            readOnly: true\n          call: \"cloudflare-stream.list-live-inputs\"\n          with:\n            account_id: \"tools.account_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: stream-create-live-input\n          description: \"Create a live streaming input.\"\n          hints:\n            readOnly: false\n          call: \"cloudflare-stream.create-live-input\"\n       \
  \   with:\n            account_id: \"tools.account_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: stream-create-direct-upload\n          description: \"Create a direct upload URL.\"\n          hints:\n            readOnly: false\n          call: \"cloudflare-stream.create-direct-upload\"\n          with:\n            account_id: \"tools.account_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: images-list-images\n          description: \"List all images.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"cloudflare-images.list-images\"\n          with:\n            account_id: \"tools.account_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: images-upload-image\n          description: \"Upload an image.\"\n          hints:\n            readOnly: false\n        \
  \  call: \"cloudflare-images.upload-image\"\n          with:\n            account_id: \"tools.account_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: images-get-image\n          description: \"Get image details.\"\n          hints:\n            readOnly: true\n          call: \"cloudflare-images.get-image\"\n          with:\n            account_id: \"tools.account_id\"\n            image_id: \"tools.image_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: images-delete-image\n          description: \"Delete an image.\"\n          hints:\n            destructive: true\n            idempotent: true\n          call: \"cloudflare-images.delete-image\"\n          with:\n            account_id: \"tools.account_id\"\n            image_id: \"tools.image_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: images-list-variants\n\
  \          description: \"List image variants.\"\n          hints:\n            readOnly: true\n          call: \"cloudflare-images.list-image-variants\"\n          with:\n            account_id: \"tools.account_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: images-create-direct-upload\n          description: \"Create a direct upload URL for images.\"\n          hints:\n            readOnly: false\n          call: \"cloudflare-images.create-image-direct-upload\"\n          with:\n            account_id: \"tools.account_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
