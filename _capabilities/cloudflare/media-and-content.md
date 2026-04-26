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
- stream create live input
- create a direct upload url.
- list image variants.
- get video details.
- stream get video
- serverless
- list images
- list videos.
- cloud
- web performance
- images
- ai gateway
- get image details.
- stream upload video
- images delete image
- dns
- edge computing
- stream list videos
- cdn
- platform
- ddos protection
- upload a video from url.
- artificial intelligence
- edge
- video
- images create direct upload
- api gateway
- create a live streaming input.
- containers
- stream list live inputs
- stream create direct upload
- security
- real-time communication
- list videos
- delete a video.
- upload an image.
- create a direct upload url for images.
- video management.
- object storage
- list all images.
- list images.
- cloudflare
- media
- list live streaming inputs.
- list all videos.
- image management.
- images get image
- delete an image.
- images upload image
- images list images
- images list variants
- stream delete video
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
