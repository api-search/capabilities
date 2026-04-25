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
- media
- stream create direct upload
- images list images
- stream list live inputs
- create a live streaming input.
- artificial intelligence
- stream create live input
- security
- list live streaming inputs.
- images list variants
- images create direct upload
- image management.
- stream upload video
- api gateway
- images get image
- ddos protection
- platform
- serverless
- cloudflare
- delete a video.
- list images
- images
- edge computing
- images upload image
- list videos
- video
- web performance
- cloud
- upload a video from url.
- stream delete video
- list all videos.
- list videos.
- list all images.
- containers
- get image details.
- get video details.
- edge
- create a direct upload url for images.
- dns
- video management.
- images delete image
- list images.
- real-time communication
- list image variants.
- stream list videos
- stream get video
- delete an image.
- ai gateway
- upload an image.
- object storage
- cdn
- create a direct upload url.
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
