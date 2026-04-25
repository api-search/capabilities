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
- images create direct upload
- get image details.
- list videos.
- list images
- stream delete video
- images
- images delete image
- create a direct upload url.
- stream list live inputs
- stream create live input
- edge
- real-time communication
- containers
- images list variants
- list all images.
- list image variants.
- list images.
- images upload image
- image management.
- images list images
- ai gateway
- serverless
- list videos
- delete a video.
- security
- api gateway
- artificial intelligence
- get video details.
- stream get video
- video
- upload a video from url.
- stream upload video
- platform
- list live streaming inputs.
- list all videos.
- create a direct upload url for images.
- ddos protection
- stream create direct upload
- cloudflare
- create a live streaming input.
- video management.
- delete an image.
- dns
- media
- stream list videos
- upload an image.
- cdn
- images get image
- cloud
- object storage
- web performance
- edge computing
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
