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
- list image variants.
- edge computing
- object storage
- cloud
- create a live streaming input.
- list all videos.
- list images.
- stream upload video
- image management.
- containers
- real-time communication
- delete an image.
- list images
- get image details.
- ai gateway
- dns
- stream delete video
- video management.
- images get image
- list live streaming inputs.
- get video details.
- images create direct upload
- security
- platform
- upload a video from url.
- delete a video.
- cloudflare
- stream list live inputs
- create a direct upload url.
- stream list videos
- stream create direct upload
- edge
- images delete image
- list videos
- list all images.
- api gateway
- images list variants
- cdn
- ddos protection
- video
- upload an image.
- media
- serverless
- artificial intelligence
- stream create live input
- images
- web performance
- images list images
- create a direct upload url for images.
- list videos.
- images upload image
- stream get video
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
