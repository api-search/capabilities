---
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
- get video details.
- stream list live inputs
- cdn
- delete a video.
- stream delete video
- dns
- images upload image
- stream create live input
- edge computing
- object storage
- get image details.
- media
- ddos protection
- edge
- images get image
- stream upload video
- delete an image.
- images create direct upload
- video management.
- upload an image.
- serverless
- create a direct upload url.
- stream create direct upload
- platform
- api gateway
- list videos.
- list images
- stream get video
- list all images.
- artificial intelligence
- create a live streaming input.
- containers
- list videos
- video
- images
- cloudflare
- stream list videos
- images list images
- ai gateway
- cloud
- create a direct upload url for images.
- list live streaming inputs.
- real-time communication
- upload a video from url.
- security
- images list variants
- list all videos.
- images delete image
- list image variants.
- image management.
- list images.
- web performance
slug: media-and-content
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
