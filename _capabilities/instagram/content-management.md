---
consumed_apis:
- instagram-graph
description: Unified workflow for managing Instagram content including media browsing, publishing (container creation and publish), stories, carousel albums, and media updates. Used by social media managers and content creators to create, review, update, and delete Instagram posts, reels, stories, and carousels.
layout: capability
name: Instagram Content Management
operations:
- description: Get a collection of IG Media objects published on the account.
  method: GET
  name: get-user-media
  path: /v1/users/{user_id}/media
- description: Create a media container for publishing content.
  method: POST
  name: create-media-container
  path: /v1/users/{user_id}/media
- description: Publish a media container. Step 2 of the publishing flow.
  method: POST
  name: publish-media
  path: /v1/users/{user_id}/publish
- description: Get a collection of story IG Media objects on the account.
  method: GET
  name: get-user-stories
  path: /v1/users/{user_id}/stories
- description: Get current content publishing usage and rate limit status.
  method: GET
  name: get-content-publishing-limit
  path: /v1/users/{user_id}/publishing-limit
- description: Get fields on an Instagram media object.
  method: GET
  name: get-media
  path: /v1/media/{media_id}
- description: Enable or disable comments on a media object.
  method: POST
  name: update-media
  path: /v1/media/{media_id}
- description: Delete an Instagram media object.
  method: DELETE
  name: delete-media
  path: /v1/media/{media_id}
- description: Get media objects within a carousel album.
  method: GET
  name: get-media-children
  path: /v1/media/{media_id}/children
- description: Check the publishing status of a media container.
  method: GET
  name: get-container
  path: /v1/containers/{container_id}
personas: []
provider_name: Instagram
provider_slug: instagram
search_terms:
- tracks content performance and audience insights.
- publish media
- delete media
- get user stories
- get container
- get a collection of story ig media objects on the account.
- get fields on an instagram media object.
- instagram
- website embedding of instagram content.
- create a media container for publishing content.
- get content publishing limit
- create media container
- get media objects within a carousel album.
- media
- check the publishing status of a media container.
- get a collection of ig media objects published on the account.
- get user media
- photos
- content publishing and media management.
- individual media object operations.
- insights and performance metrics.
- update media
- videos
- user media collection and container creation.
- instagram direct messaging.
- manages instagram direct conversations for business inquiries.
- publish a media container.
- meta
- carousel album children.
- content publishing rate limit.
- get media children
- creates and publishes photos, videos, reels, and stories.
- delete an instagram media object (post, story, reel, or carousel).
- comments, mentions, and community interaction.
- publishing
- embeds instagram content on websites and applications.
- publish a media container. step 2 of the publishing flow.
- monitors mentions, comments, and brand sentiment on instagram.
- publishes and manages content across instagram accounts.
- social media
- enable or disable comments on a media object.
- delete an instagram media object.
- container status check.
- get media
- get fields on an instagram photo, video, story, reel, or album.
- create a media container for publishing content. step 1 of the publishing flow.
- content management
- content publishing
- user stories collection.
- get current content publishing usage and rate limit status.
slug: content-management
tags:
- Instagram
- Content Management
- Social Media
- Publishing
- Media
tools:
- description: Get a collection of IG Media objects published on the account.
  hints:
    idempotent: true
    readOnly: true
  name: get-user-media
- description: Get a collection of story IG Media objects on the account.
  hints:
    idempotent: true
    readOnly: true
  name: get-user-stories
- description: Get fields on an Instagram photo, video, story, reel, or album.
  hints:
    idempotent: true
    readOnly: true
  name: get-media
- description: Get media objects within a carousel album.
  hints:
    idempotent: true
    readOnly: true
  name: get-media-children
- description: Enable or disable comments on a media object.
  hints:
    idempotent: true
    readOnly: false
  name: update-media
- description: Delete an Instagram media object (post, story, reel, or carousel).
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-media
- description: Create a media container for publishing content. Step 1 of the publishing flow.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-media-container
- description: Publish a media container. Step 2 of the publishing flow.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: publish-media
- description: Get current content publishing usage and rate limit status.
  hints:
    idempotent: true
    readOnly: true
  name: get-content-publishing-limit
- description: Check the publishing status of a media container.
  hints:
    idempotent: true
    readOnly: true
  name: get-container
---
