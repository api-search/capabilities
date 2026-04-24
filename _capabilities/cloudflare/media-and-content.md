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
- upload an image.
- artificial intelligence
- upload a video from url.
- list all videos.
- get image details.
- serverless
- list videos.
- create a direct upload url for images.
- images list variants
- cloud
- delete an image.
- list videos
- dns
- list all images.
- real-time communication
- images list images
- image management.
- images create direct upload
- stream list live inputs
- video
- stream create direct upload
- stream create live input
- edge
- video management.
- images delete image
- stream get video
- ai gateway
- media
- edge computing
- create a direct upload url.
- stream list videos
- create a live streaming input.
- images upload image
- images get image
- list images.
- ddos protection
- containers
- stream delete video
- api gateway
- images
- cloudflare
- list images
- cdn
- security
- stream upload video
- get video details.
- platform
- web performance
- list image variants.
- object storage
- list live streaming inputs.
- delete a video.
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
