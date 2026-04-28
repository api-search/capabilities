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
- stream create live input
- delete a video.
- get image details.
- list videos.
- edge
- images
- platform
- list all images.
- images upload image
- real-time communication
- create a direct upload url.
- edge computing
- list images.
- stream upload video
- create a live streaming input.
- images get image
- upload an image.
- api gateway
- stream delete video
- list live streaming inputs.
- containers
- video management.
- stream create direct upload
- list videos
- stream list live inputs
- create a direct upload url for images.
- list images
- security
- web performance
- images create direct upload
- media
- image management.
- ai gateway
- cdn
- video
- ddos protection
- delete an image.
- artificial intelligence
- serverless
- cloudflare
- upload a video from url.
- stream list videos
- images delete image
- list all videos.
- cloud
- dns
- list image variants.
- object storage
- get video details.
- images list images
- images list variants
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
