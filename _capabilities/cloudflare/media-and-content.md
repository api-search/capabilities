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
- web performance
- video management.
- stream get video
- images
- list images.
- list all videos.
- images create direct upload
- cloudflare
- create a direct upload url for images.
- api gateway
- ai gateway
- stream create direct upload
- edge computing
- image management.
- containers
- create a direct upload url.
- list all images.
- get image details.
- images delete image
- stream list live inputs
- ddos protection
- list image variants.
- real-time communication
- stream create live input
- platform
- edge
- upload an image.
- stream list videos
- video
- list live streaming inputs.
- delete an image.
- object storage
- security
- upload a video from url.
- get video details.
- cdn
- serverless
- images get image
- list videos
- delete a video.
- stream upload video
- create a live streaming input.
- stream delete video
- images list variants
- cloud
- media
- images list images
- list images
- dns
- images upload image
- artificial intelligence
- list videos.
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
