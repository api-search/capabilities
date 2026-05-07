---
categories:
- content-management
consumed_apis: []
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
- social media
- content publishing rate limit.
- update media
- individual media object operations.
- get media objects within a carousel album.
- get current content publishing usage and rate limit status.
- content publishing and media management.
- comments, mentions, and community interaction.
- create media container
- instagram direct messaging.
- enable or disable comments on a media object.
- check the publishing status of a media container.
- photos
- publishing
- get media
- manages instagram direct conversations for business inquiries.
- meta
- publishes and manages content across instagram accounts.
- get fields on an instagram media object.
- website embedding of instagram content.
- embeds instagram content on websites and applications.
- get content publishing limit
- carousel album children.
- get a collection of story ig media objects on the account.
- monitors mentions, comments, and brand sentiment on instagram.
- publish a media container. step 2 of the publishing flow.
- get media children
- publish a media container.
- delete an instagram media object.
- tracks content performance and audience insights.
- get fields on an instagram photo, video, story, reel, or album.
- create a media container for publishing content. step 1 of the publishing flow.
- create a media container for publishing content.
- creates and publishes photos, videos, reels, and stories.
- container status check.
- insights and performance metrics.
- get a collection of ig media objects published on the account.
- get user media
- get container
- user stories collection.
- media
- content management
- videos
- delete media
- instagram
- user media collection and container creation.
- publish media
- content publishing
- get user stories
- delete an instagram media object (post, story, reel, or carousel).
slug: content-management
source_filename: content-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Instagram Content Management\n  description: Unified workflow for managing Instagram content including media browsing, publishing (container creation and\n    publish), stories, carousel albums, and media updates. Used by social media managers and content creators to create, review,\n    update, and delete Instagram posts, reels, stories, and carousels.\n  tags:\n  - Instagram\n  - Content Management\n  - Social Media\n  - Publishing\n  - Media\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    INSTAGRAM_ACCESS_TOKEN: INSTAGRAM_ACCESS_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: instagram-graph\n    baseUri: https://graph.facebook.com/v21.0\n    description: Instagram Graph API for managing Business and Creator accounts.\n    authentication:\n      type: bearer\n      token: '{{INSTAGRAM_ACCESS_TOKEN}}'\n    resources:\n    - name: users\n      path: /\n      description: Instagram\
  \ Business and Creator account profiles.\n      operations:\n      - name: get-user\n        method: GET\n        path: /{user_id}\n        description: Get fields and edges on an Instagram Business or Creator account.\n        inputParameters:\n        - name: user_id\n          in: path\n          type: string\n          required: true\n          description: The Instagram user ID.\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Comma-separated list of fields to return.\n        - name: access_token\n          in: query\n          type: string\n          required: true\n          description: User access token.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-business-discovery\n        method: GET\n        path: /{user_id}/business_discovery\n        description: Get data about other Instagram Business or Creator accounts.\n\
  \        inputParameters:\n        - name: user_id\n          in: path\n          type: string\n          required: true\n          description: The Instagram user ID.\n        - name: fields\n          in: query\n          type: string\n          required: true\n          description: Must include business_discovery.fields().\n        - name: access_token\n          in: query\n          type: string\n          required: true\n          description: User access token.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: media\n      path: /\n      description: Photos, videos, stories, reels, and carousels.\n      operations:\n      - name: get-user-media\n        method: GET\n        path: /{user_id}/media\n        description: Get a collection of IG Media objects published on the account.\n        inputParameters:\n        - name: user_id\n          in: path\n          type: string\n          required:\
  \ true\n          description: The Instagram user ID.\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Comma-separated list of fields.\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results per page.\n        - name: after\n          in: query\n          type: string\n          required: false\n          description: Cursor for pagination.\n        - name: access_token\n          in: query\n          type: string\n          required: true\n          description: User access token.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-user-stories\n        method: GET\n        path: /{user_id}/stories\n        description: Get a collection of story IG Media objects on the account.\n        inputParameters:\n        - name: user_id\n    \
  \      in: path\n          type: string\n          required: true\n          description: The Instagram user ID.\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Comma-separated list of fields.\n        - name: access_token\n          in: query\n          type: string\n          required: true\n          description: User access token.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-media\n        method: GET\n        path: /{media_id}\n        description: Get fields on an Instagram photo, video, story, reel, or album.\n        inputParameters:\n        - name: media_id\n          in: path\n          type: string\n          required: true\n          description: The IG Media ID.\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Comma-separated list of\
  \ fields.\n        - name: access_token\n          in: query\n          type: string\n          required: true\n          description: User access token.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-media\n        method: POST\n        path: /{media_id}\n        description: Enable or disable comments on a media object.\n        inputParameters:\n        - name: media_id\n          in: path\n          type: string\n          required: true\n          description: The IG Media ID.\n        body:\n          type: json\n          data:\n            comment_enabled: '{{tools.comment_enabled}}'\n            access_token: '{{tools.access_token}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-media\n        method: DELETE\n        path: /{media_id}\n        description: Delete an Instagram\
  \ media object (post, story, reel, or carousel).\n        inputParameters:\n        - name: media_id\n          in: path\n          type: string\n          required: true\n          description: The IG Media ID.\n        - name: access_token\n          in: query\n          type: string\n          required: true\n          description: User access token.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-media-children\n        method: GET\n        path: /{media_id}/children\n        description: Get media objects within a carousel album.\n        inputParameters:\n        - name: media_id\n          in: path\n          type: string\n          required: true\n          description: The IG Media ID.\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Comma-separated list of fields.\n        - name: access_token\n          in: query\n\
  \          type: string\n          required: true\n          description: User access token.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: publishing\n      path: /\n      description: Content creation and publishing workflow.\n      operations:\n      - name: create-media-container\n        method: POST\n        path: /{user_id}/media\n        description: Create a media container for publishing content. Step 1 of the publishing flow.\n        inputParameters:\n        - name: user_id\n          in: path\n          type: string\n          required: true\n          description: The Instagram user ID.\n        body:\n          type: json\n          data:\n            image_url: '{{tools.image_url}}'\n            video_url: '{{tools.video_url}}'\n            caption: '{{tools.caption}}'\n            media_type: '{{tools.media_type}}'\n            is_carousel_item: '{{tools.is_carousel_item}}'\n\
  \            location_id: '{{tools.location_id}}'\n            access_token: '{{tools.access_token}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: publish-media\n        method: POST\n        path: /{user_id}/media_publish\n        description: Publish a media container. Step 2 of the publishing flow.\n        inputParameters:\n        - name: user_id\n          in: path\n          type: string\n          required: true\n          description: The Instagram user ID.\n        body:\n          type: json\n          data:\n            creation_id: '{{tools.creation_id}}'\n            access_token: '{{tools.access_token}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-content-publishing-limit\n        method: GET\n        path: /{user_id}/content_publishing_limit\n        description: Get current\
  \ content publishing usage and rate limit status.\n        inputParameters:\n        - name: user_id\n          in: path\n          type: string\n          required: true\n          description: The Instagram user ID.\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Comma-separated list of fields.\n        - name: access_token\n          in: query\n          type: string\n          required: true\n          description: User access token.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-container\n        method: GET\n        path: /{container_id}\n        description: Check the publishing status of a media container.\n        inputParameters:\n        - name: container_id\n          in: path\n          type: string\n          required: true\n          description: The container ID.\n        - name: fields\n          in:\
  \ query\n          type: string\n          required: false\n          description: Comma-separated list of fields.\n        - name: access_token\n          in: query\n          type: string\n          required: true\n          description: User access token.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: comments\n      path: /\n      description: Comment management and moderation.\n      operations:\n      - name: get-media-comments\n        method: GET\n        path: /{media_id}/comments\n        description: Get comments on an Instagram media object.\n        inputParameters:\n        - name: media_id\n          in: path\n          type: string\n          required: true\n          description: The IG Media ID.\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Comma-separated list of fields.\n        - name: access_token\n\
  \          in: query\n          type: string\n          required: true\n          description: User access token.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-comment\n        method: POST\n        path: /{media_id}/comments\n        description: Create a comment on an Instagram media object.\n        inputParameters:\n        - name: media_id\n          in: path\n          type: string\n          required: true\n          description: The IG Media ID.\n        body:\n          type: json\n          data:\n            message: '{{tools.message}}'\n            access_token: '{{tools.access_token}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-comment\n        method: GET\n        path: /{comment_id}\n        description: Get fields on an Instagram comment.\n        inputParameters:\n \
  \       - name: comment_id\n          in: path\n          type: string\n          required: true\n          description: The comment ID.\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Comma-separated list of fields.\n        - name: access_token\n          in: query\n          type: string\n          required: true\n          description: User access token.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: hide-comment\n        method: POST\n        path: /{comment_id}\n        description: Hide or unhide a comment on your media.\n        inputParameters:\n        - name: comment_id\n          in: path\n          type: string\n          required: true\n          description: The comment ID.\n        body:\n          type: json\n          data:\n            hide: '{{tools.hide}}'\n            access_token: '{{tools.access_token}}'\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-comment\n        method: DELETE\n        path: /{comment_id}\n        description: Delete a comment on your media.\n        inputParameters:\n        - name: comment_id\n          in: path\n          type: string\n          required: true\n          description: The comment ID.\n        - name: access_token\n          in: query\n          type: string\n          required: true\n          description: User access token.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-comment-replies\n        method: GET\n        path: /{comment_id}/replies\n        description: Get replies to a comment.\n        inputParameters:\n        - name: comment_id\n          in: path\n          type: string\n          required: true\n          description: The comment\
  \ ID.\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Comma-separated list of fields.\n        - name: access_token\n          in: query\n          type: string\n          required: true\n          description: User access token.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-comment-reply\n        method: POST\n        path: /{comment_id}/replies\n        description: Reply to a comment.\n        inputParameters:\n        - name: comment_id\n          in: path\n          type: string\n          required: true\n          description: The comment ID.\n        body:\n          type: json\n          data:\n            message: '{{tools.message}}'\n            access_token: '{{tools.access_token}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n    - name: hashtags\n      path: /\n      description: Hashtag search and media discovery.\n      operations:\n      - name: search-hashtag\n        method: GET\n        path: /ig_hashtag_search\n        description: Search for a hashtag by name and get its ID.\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: true\n          description: 'The hashtag to search for (without #).'\n        - name: user_id\n          in: query\n          type: string\n          required: true\n          description: The ID of the user making the request.\n        - name: access_token\n          in: query\n          type: string\n          required: true\n          description: User access token.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-hashtag-top-media\n        method: GET\n        path: /{hashtag_id}/top_media\n        description: Get\
  \ the most popular media tagged with a specific hashtag.\n        inputParameters:\n        - name: hashtag_id\n          in: path\n          type: string\n          required: true\n          description: The hashtag ID.\n        - name: user_id\n          in: query\n          type: string\n          required: true\n          description: The ID of the user making the request.\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Comma-separated list of fields.\n        - name: access_token\n          in: query\n          type: string\n          required: true\n          description: User access token.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-hashtag-recent-media\n        method: GET\n        path: /{hashtag_id}/recent_media\n        description: Get the most recently published media tagged with a specific hashtag.\n\
  \        inputParameters:\n        - name: hashtag_id\n          in: path\n          type: string\n          required: true\n          description: The hashtag ID.\n        - name: user_id\n          in: query\n          type: string\n          required: true\n          description: The ID of the user making the request.\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Comma-separated list of fields.\n        - name: access_token\n          in: query\n          type: string\n          required: true\n          description: User access token.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: insights\n      path: /\n      description: Account and media level analytics.\n      operations:\n      - name: get-user-insights\n        method: GET\n        path: /{user_id}/insights\n        description: Get social interaction metrics for\
  \ the account.\n        inputParameters:\n        - name: user_id\n          in: path\n          type: string\n          required: true\n          description: The Instagram user ID.\n        - name: metric\n          in: query\n          type: string\n          required: true\n          description: Comma-separated list of metrics.\n        - name: period\n          in: query\n          type: string\n          required: true\n          description: Time period for aggregation (day, week, days_28, month, lifetime).\n        - name: since\n          in: query\n          type: integer\n          required: false\n          description: Unix timestamp for start of range.\n        - name: until\n          in: query\n          type: integer\n          required: false\n          description: Unix timestamp for end of range.\n        - name: access_token\n          in: query\n          type: string\n          required: true\n          description: User access token.\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-media-insights\n        method: GET\n        path: /{media_id}/insights\n        description: Get social interaction metrics for a media object.\n        inputParameters:\n        - name: media_id\n          in: path\n          type: string\n          required: true\n          description: The IG Media ID.\n        - name: metric\n          in: query\n          type: string\n          required: true\n          description: Comma-separated list of metrics.\n        - name: access_token\n          in: query\n          type: string\n          required: true\n          description: User access token.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: mentions\n      path: /\n      description: Content where account was mentioned.\n      operations:\n      - name: get-user-tags\n        method:\
  \ GET\n        path: /{user_id}/tags\n        description: Get IG Media objects where the user has been tagged by other users.\n        inputParameters:\n        - name: user_id\n          in: path\n          type: string\n          required: true\n          description: The Instagram user ID.\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Comma-separated list of fields.\n        - name: access_token\n          in: query\n          type: string\n          required: true\n          description: User access token.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: instagram-content-api\n    description: Unified REST API for Instagram content management workflows.\n    resources:\n    - path: /v1/users/{user_id}/media\n      name: user-media\n      description: User media collection\
  \ and container creation.\n      operations:\n      - method: GET\n        name: get-user-media\n        description: Get a collection of IG Media objects published on the account.\n        call: instagram-graph.get-user-media\n        with:\n          user_id: rest.user_id\n          fields: rest.fields\n          limit: rest.limit\n          after: rest.after\n          access_token: rest.access_token\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-media-container\n        description: Create a media container for publishing content.\n        call: instagram-graph.create-media-container\n        with:\n          user_id: rest.user_id\n          image_url: rest.image_url\n          video_url: rest.video_url\n          caption: rest.caption\n          media_type: rest.media_type\n          is_carousel_item: rest.is_carousel_item\n          location_id: rest.location_id\n          access_token: rest.access_token\n   \
  \     outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/users/{user_id}/publish\n      name: publish-media\n      description: Publish a media container.\n      operations:\n      - method: POST\n        name: publish-media\n        description: Publish a media container. Step 2 of the publishing flow.\n        call: instagram-graph.publish-media\n        with:\n          user_id: rest.user_id\n          creation_id: rest.creation_id\n          access_token: rest.access_token\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/users/{user_id}/stories\n      name: user-stories\n      description: User stories collection.\n      operations:\n      - method: GET\n        name: get-user-stories\n        description: Get a collection of story IG Media objects on the account.\n        call: instagram-graph.get-user-stories\n        with:\n          user_id: rest.user_id\n          fields: rest.fields\n          access_token:\
  \ rest.access_token\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/users/{user_id}/publishing-limit\n      name: publishing-limit\n      description: Content publishing rate limit.\n      operations:\n      - method: GET\n        name: get-content-publishing-limit\n        description: Get current content publishing usage and rate limit status.\n        call: instagram-graph.get-content-publishing-limit\n        with:\n          user_id: rest.user_id\n          fields: rest.fields\n          access_token: rest.access_token\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/media/{media_id}\n      name: media\n      description: Individual media object operations.\n      operations:\n      - method: GET\n        name: get-media\n        description: Get fields on an Instagram media object.\n        call: instagram-graph.get-media\n        with:\n          media_id: rest.media_id\n          fields: rest.fields\n\
  \          access_token: rest.access_token\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: update-media\n        description: Enable or disable comments on a media object.\n        call: instagram-graph.update-media\n        with:\n          media_id: rest.media_id\n          comment_enabled: rest.comment_enabled\n          access_token: rest.access_token\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-media\n        description: Delete an Instagram media object.\n        call: instagram-graph.delete-media\n        with:\n          media_id: rest.media_id\n          access_token: rest.access_token\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/media/{media_id}/children\n      name: media-children\n      description: Carousel album children.\n      operations:\n      - method: GET\n        name: get-media-children\n\
  \        description: Get media objects within a carousel album.\n        call: instagram-graph.get-media-children\n        with:\n          media_id: rest.media_id\n          fields: rest.fields\n          access_token: rest.access_token\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/containers/{container_id}\n      name: container\n      description: Container status check.\n      operations:\n      - method: GET\n        name: get-container\n        description: Check the publishing status of a media container.\n        call: instagram-graph.get-container\n        with:\n          container_id: rest.container_id\n          fields: rest.fields\n          access_token: rest.access_token\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: instagram-content-mcp\n    transport: http\n    description: MCP server for AI-assisted Instagram content management.\n    tools:\n    - name:\
  \ get-user-media\n      description: Get a collection of IG Media objects published on the account.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: instagram-graph.get-user-media\n      with:\n        user_id: tools.user_id\n        fields: tools.fields\n        limit: tools.limit\n        after: tools.after\n        access_token: tools.access_token\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-user-stories\n      description: Get a collection of story IG Media objects on the account.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: instagram-graph.get-user-stories\n      with:\n        user_id: tools.user_id\n        fields: tools.fields\n        access_token: tools.access_token\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-media\n      description: Get fields on an Instagram photo, video, story, reel, or album.\n      hints:\n        readOnly: true\n\
  \        idempotent: true\n      call: instagram-graph.get-media\n      with:\n        media_id: tools.media_id\n        fields: tools.fields\n        access_token: tools.access_token\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-media-children\n      description: Get media objects within a carousel album.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: instagram-graph.get-media-children\n      with:\n        media_id: tools.media_id\n        fields: tools.fields\n        access_token: tools.access_token\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-media\n      description: Enable or disable comments on a media object.\n      hints:\n        readOnly: false\n        idempotent: true\n      call: instagram-graph.update-media\n      with:\n        media_id: tools.media_id\n        comment_enabled: tools.comment_enabled\n        access_token: tools.access_token\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: delete-media\n      description: Delete an Instagram media object (post, story, reel, or carousel).\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: instagram-graph.delete-media\n      with:\n        media_id: tools.media_id\n        access_token: tools.access_token\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-media-container\n      description: Create a media container for publishing content. Step 1 of the publishing flow.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: instagram-graph.create-media-container\n      with:\n        user_id: tools.user_id\n        image_url: tools.image_url\n        video_url: tools.video_url\n        caption: tools.caption\n        media_type: tools.media_type\n        is_carousel_item: tools.is_carousel_item\n        location_id: tools.location_id\n\
  \        access_token: tools.access_token\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: publish-media\n      description: Publish a media container. Step 2 of the publishing flow.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: instagram-graph.publish-media\n      with:\n        user_id: tools.user_id\n        creation_id: tools.creation_id\n        access_token: tools.access_token\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-content-publishing-limit\n      description: Get current content publishing usage and rate limit status.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: instagram-graph.get-content-publishing-limit\n      with:\n        user_id: tools.user_id\n        fields: tools.fields\n        access_token: tools.access_token\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-container\n\
  \      description: Check the publishing status of a media container.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: instagram-graph.get-container\n      with:\n        container_id: tools.container_id\n        fields: tools.fields\n        access_token: tools.access_token\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
