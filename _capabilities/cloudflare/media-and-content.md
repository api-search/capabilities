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
- stream create direct upload
- stream create live input
- containers
- images list variants
- api gateway
- stream list videos
- list videos.
- object storage
- list images.
- stream delete video
- real-time communication
- list images
- list live streaming inputs.
- edge computing
- dns
- cdn
- upload a video from url.
- images create direct upload
- upload an image.
- get video details.
- edge
- images delete image
- video management.
- image management.
- create a direct upload url.
- ddos protection
- images upload image
- video
- list all images.
- ai gateway
- list image variants.
- cloud
- images list images
- stream upload video
- web performance
- create a direct upload url for images.
- delete a video.
- serverless
- media
- images get image
- artificial intelligence
- stream get video
- create a live streaming input.
- cloudflare
- platform
- get image details.
- delete an image.
- list all videos.
- images
- list videos
- security
- stream list live inputs
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
