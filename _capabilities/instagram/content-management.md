---
categories:
- content-management
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
- insights and performance metrics.
- get a collection of ig media objects published on the account.
- photos
- content management
- delete media
- get media children
- publish a media container.
- user media collection and container creation.
- social media
- update media
- media
- create a media container for publishing content.
- embeds instagram content on websites and applications.
- carousel album children.
- delete an instagram media object (post, story, reel, or carousel).
- user stories collection.
- comments, mentions, and community interaction.
- creates and publishes photos, videos, reels, and stories.
- instagram direct messaging.
- videos
- enable or disable comments on a media object.
- website embedding of instagram content.
- meta
- get a collection of story ig media objects on the account.
- get content publishing limit
- manages instagram direct conversations for business inquiries.
- individual media object operations.
- monitors mentions, comments, and brand sentiment on instagram.
- publishes and manages content across instagram accounts.
- publish a media container. step 2 of the publishing flow.
- create media container
- content publishing rate limit.
- tracks content performance and audience insights.
- content publishing and media management.
- get media objects within a carousel album.
- create a media container for publishing content. step 1 of the publishing flow.
- content publishing
- publishing
- check the publishing status of a media container.
- get container
- get current content publishing usage and rate limit status.
- container status check.
- instagram
- get user media
- publish media
- get media
- get fields on an instagram photo, video, story, reel, or album.
- get user stories
- get fields on an instagram media object.
- delete an instagram media object.
slug: content-management
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Instagram Content Management\"\n  description: >-\n    Unified workflow for managing Instagram content including media browsing,\n    publishing (container creation and publish), stories, carousel albums, and\n    media updates. Used by social media managers and content creators to create,\n    review, update, and delete Instagram posts, reels, stories, and carousels.\n  tags:\n    - Instagram\n    - Content Management\n    - Social Media\n    - Publishing\n    - Media\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      INSTAGRAM_ACCESS_TOKEN: INSTAGRAM_ACCESS_TOKEN\n\ncapability:\n  consumes:\n    - import: instagram-graph\n      location: ./shared/instagram-graph-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: instagram-content-api\n      description: \"Unified REST API for Instagram content management workflows.\"\n      resources:\n        - path:\
  \ /v1/users/{user_id}/media\n          name: user-media\n          description: \"User media collection and container creation.\"\n          operations:\n            - method: GET\n              name: get-user-media\n              description: \"Get a collection of IG Media objects published on the account.\"\n              call: \"instagram-graph.get-user-media\"\n              with:\n                user_id: \"rest.user_id\"\n                fields: \"rest.fields\"\n                limit: \"rest.limit\"\n                after: \"rest.after\"\n                access_token: \"rest.access_token\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-media-container\n              description: \"Create a media container for publishing content.\"\n              call: \"instagram-graph.create-media-container\"\n              with:\n                user_id: \"rest.user_id\"\n              \
  \  image_url: \"rest.image_url\"\n                video_url: \"rest.video_url\"\n                caption: \"rest.caption\"\n                media_type: \"rest.media_type\"\n                is_carousel_item: \"rest.is_carousel_item\"\n                location_id: \"rest.location_id\"\n                access_token: \"rest.access_token\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/users/{user_id}/publish\n          name: publish-media\n          description: \"Publish a media container.\"\n          operations:\n            - method: POST\n              name: publish-media\n              description: \"Publish a media container. Step 2 of the publishing flow.\"\n              call: \"instagram-graph.publish-media\"\n              with:\n                user_id: \"rest.user_id\"\n                creation_id: \"rest.creation_id\"\n                access_token: \"rest.access_token\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/users/{user_id}/stories\n          name: user-stories\n          description: \"User stories collection.\"\n          operations:\n            - method: GET\n              name: get-user-stories\n              description: \"Get a collection of story IG Media objects on the account.\"\n              call: \"instagram-graph.get-user-stories\"\n              with:\n                user_id: \"rest.user_id\"\n                fields: \"rest.fields\"\n                access_token: \"rest.access_token\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/users/{user_id}/publishing-limit\n          name: publishing-limit\n          description: \"Content publishing rate limit.\"\n          operations:\n            - method: GET\n              name: get-content-publishing-limit\n              description: \"Get current content publishing\
  \ usage and rate limit status.\"\n              call: \"instagram-graph.get-content-publishing-limit\"\n              with:\n                user_id: \"rest.user_id\"\n                fields: \"rest.fields\"\n                access_token: \"rest.access_token\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/media/{media_id}\n          name: media\n          description: \"Individual media object operations.\"\n          operations:\n            - method: GET\n              name: get-media\n              description: \"Get fields on an Instagram media object.\"\n              call: \"instagram-graph.get-media\"\n              with:\n                media_id: \"rest.media_id\"\n                fields: \"rest.fields\"\n                access_token: \"rest.access_token\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name:\
  \ update-media\n              description: \"Enable or disable comments on a media object.\"\n              call: \"instagram-graph.update-media\"\n              with:\n                media_id: \"rest.media_id\"\n                comment_enabled: \"rest.comment_enabled\"\n                access_token: \"rest.access_token\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-media\n              description: \"Delete an Instagram media object.\"\n              call: \"instagram-graph.delete-media\"\n              with:\n                media_id: \"rest.media_id\"\n                access_token: \"rest.access_token\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/media/{media_id}/children\n          name: media-children\n          description: \"Carousel album children.\"\n          operations:\n            -\
  \ method: GET\n              name: get-media-children\n              description: \"Get media objects within a carousel album.\"\n              call: \"instagram-graph.get-media-children\"\n              with:\n                media_id: \"rest.media_id\"\n                fields: \"rest.fields\"\n                access_token: \"rest.access_token\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/containers/{container_id}\n          name: container\n          description: \"Container status check.\"\n          operations:\n            - method: GET\n              name: get-container\n              description: \"Check the publishing status of a media container.\"\n              call: \"instagram-graph.get-container\"\n              with:\n                container_id: \"rest.container_id\"\n                fields: \"rest.fields\"\n                access_token: \"rest.access_token\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: instagram-content-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Instagram content management.\"\n      tools:\n        - name: get-user-media\n          description: \"Get a collection of IG Media objects published on the account.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"instagram-graph.get-user-media\"\n          with:\n            user_id: \"tools.user_id\"\n            fields: \"tools.fields\"\n            limit: \"tools.limit\"\n            after: \"tools.after\"\n            access_token: \"tools.access_token\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-user-stories\n          description: \"Get a collection of story IG Media objects on the account.\"\n          hints:\n            readOnly: true\n           \
  \ idempotent: true\n          call: \"instagram-graph.get-user-stories\"\n          with:\n            user_id: \"tools.user_id\"\n            fields: \"tools.fields\"\n            access_token: \"tools.access_token\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-media\n          description: \"Get fields on an Instagram photo, video, story, reel, or album.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"instagram-graph.get-media\"\n          with:\n            media_id: \"tools.media_id\"\n            fields: \"tools.fields\"\n            access_token: \"tools.access_token\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-media-children\n          description: \"Get media objects within a carousel album.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"instagram-graph.get-media-children\"\
  \n          with:\n            media_id: \"tools.media_id\"\n            fields: \"tools.fields\"\n            access_token: \"tools.access_token\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: update-media\n          description: \"Enable or disable comments on a media object.\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"instagram-graph.update-media\"\n          with:\n            media_id: \"tools.media_id\"\n            comment_enabled: \"tools.comment_enabled\"\n            access_token: \"tools.access_token\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: delete-media\n          description: \"Delete an Instagram media object (post, story, reel, or carousel).\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"instagram-graph.delete-media\"\
  \n          with:\n            media_id: \"tools.media_id\"\n            access_token: \"tools.access_token\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-media-container\n          description: \"Create a media container for publishing content. Step 1 of the publishing flow.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"instagram-graph.create-media-container\"\n          with:\n            user_id: \"tools.user_id\"\n            image_url: \"tools.image_url\"\n            video_url: \"tools.video_url\"\n            caption: \"tools.caption\"\n            media_type: \"tools.media_type\"\n            is_carousel_item: \"tools.is_carousel_item\"\n            location_id: \"tools.location_id\"\n            access_token: \"tools.access_token\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n   \
  \     - name: publish-media\n          description: \"Publish a media container. Step 2 of the publishing flow.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"instagram-graph.publish-media\"\n          with:\n            user_id: \"tools.user_id\"\n            creation_id: \"tools.creation_id\"\n            access_token: \"tools.access_token\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-content-publishing-limit\n          description: \"Get current content publishing usage and rate limit status.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"instagram-graph.get-content-publishing-limit\"\n          with:\n            user_id: \"tools.user_id\"\n            fields: \"tools.fields\"\n            access_token: \"tools.access_token\"\n          outputParameters:\n            - type: object\n\
  \              mapping: \"$.\"\n\n        - name: get-container\n          description: \"Check the publishing status of a media container.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"instagram-graph.get-container\"\n          with:\n            container_id: \"tools.container_id\"\n            fields: \"tools.fields\"\n            access_token: \"tools.access_token\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/instagram/refs/heads/main/capabilities/content-management.yaml
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
