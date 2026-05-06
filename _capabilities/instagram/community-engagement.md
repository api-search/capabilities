---
categories: []
consumed_apis: []
description: Unified workflow for managing Instagram community interactions including comment moderation, replies, hashtag discovery, and mention tracking. Used by community managers and social media teams to engage with followers, moderate comments, discover trending content via hashtags, and monitor brand mentions.
layout: capability
name: Instagram Community Engagement
operations:
- description: Get comments on an Instagram media object.
  method: GET
  name: get-media-comments
  path: /v1/media/{media_id}/comments
- description: Create a comment on an Instagram media object.
  method: POST
  name: create-comment
  path: /v1/media/{media_id}/comments
- description: Get fields on an Instagram comment.
  method: GET
  name: get-comment
  path: /v1/comments/{comment_id}
- description: Hide or unhide a comment on your media.
  method: POST
  name: hide-comment
  path: /v1/comments/{comment_id}
- description: Delete a comment on your media.
  method: DELETE
  name: delete-comment
  path: /v1/comments/{comment_id}
- description: Get replies to a comment.
  method: GET
  name: get-comment-replies
  path: /v1/comments/{comment_id}/replies
- description: Reply to a comment.
  method: POST
  name: create-comment-reply
  path: /v1/comments/{comment_id}/replies
- description: Search for a hashtag by name and get its ID.
  method: GET
  name: search-hashtag
  path: /v1/hashtags/search
- description: Get the most popular media tagged with a specific hashtag.
  method: GET
  name: get-hashtag-top-media
  path: /v1/hashtags/{hashtag_id}/top-media
- description: Get the most recently published media tagged with a specific hashtag.
  method: GET
  name: get-hashtag-recent-media
  path: /v1/hashtags/{hashtag_id}/recent-media
- description: Get IG Media objects where the user has been tagged by other users.
  method: GET
  name: get-user-tags
  path: /v1/users/{user_id}/tags
personas: []
provider_name: Instagram
provider_slug: instagram
search_terms:
- get the most popular media tagged with a specific hashtag.
- photos
- meta
- get comment replies
- delete a comment on your media.
- delete comment
- create comment reply
- hide comment
- comments, mentions, and community interaction.
- create a comment on an instagram media object.
- mentions
- hashtags
- replies to a comment.
- community engagement
- videos
- content publishing and media management.
- comments
- search for a hashtag by name and get its id.
- publishes and manages content across instagram accounts.
- get the most recently published media tagged with a specific hashtag.
- comments on a media object.
- get replies to a comment.
- search for hashtags.
- get comment
- reply to a comment.
- get user tags
- search hashtag
- get fields on an instagram comment.
- get hashtag top media
- recent media for a hashtag.
- embeds instagram content on websites and applications.
- get comments on an instagram media object.
- tracks content performance and audience insights.
- individual comment operations.
- media where user was tagged.
- manages instagram direct conversations for business inquiries.
- monitors mentions, comments, and brand sentiment on instagram.
- top media for a hashtag.
- hide or unhide a comment on your media.
- instagram direct messaging.
- social media
- get media comments
- get hashtag recent media
- website embedding of instagram content.
- create comment
- creates and publishes photos, videos, reels, and stories.
- insights and performance metrics.
- content publishing
- instagram
- get ig media objects where the user has been tagged by other users.
slug: community-engagement
source_filename: community-engagement.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Instagram Community Engagement\n  description: Unified workflow for managing Instagram community interactions including comment moderation, replies, hashtag\n    discovery, and mention tracking. Used by community managers and social media teams to engage with followers, moderate\n    comments, discover trending content via hashtags, and monitor brand mentions.\n  tags:\n  - Instagram\n  - Community Engagement\n  - Social Media\n  - Comments\n  - Hashtags\n  - Mentions\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    INSTAGRAM_ACCESS_TOKEN: INSTAGRAM_ACCESS_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: instagram-graph\n    baseUri: https://graph.facebook.com/v21.0\n    description: Instagram Graph API for managing Business and Creator accounts.\n    authentication:\n      type: bearer\n      token: '{{INSTAGRAM_ACCESS_TOKEN}}'\n    resources:\n    - name: users\n      path: /\n\
  \      description: Instagram Business and Creator account profiles.\n      operations:\n      - name: get-user\n        method: GET\n        path: /{user_id}\n        description: Get fields and edges on an Instagram Business or Creator account.\n        inputParameters:\n        - name: user_id\n          in: path\n          type: string\n          required: true\n          description: The Instagram user ID.\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Comma-separated list of fields to return.\n        - name: access_token\n          in: query\n          type: string\n          required: true\n          description: User access token.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-business-discovery\n        method: GET\n        path: /{user_id}/business_discovery\n        description: Get data about other Instagram\
  \ Business or Creator accounts.\n        inputParameters:\n        - name: user_id\n          in: path\n          type: string\n          required: true\n          description: The Instagram user ID.\n        - name: fields\n          in: query\n          type: string\n          required: true\n          description: Must include business_discovery.fields().\n        - name: access_token\n          in: query\n          type: string\n          required: true\n          description: User access token.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: media\n      path: /\n      description: Photos, videos, stories, reels, and carousels.\n      operations:\n      - name: get-user-media\n        method: GET\n        path: /{user_id}/media\n        description: Get a collection of IG Media objects published on the account.\n        inputParameters:\n        - name: user_id\n          in: path\n       \
  \   type: string\n          required: true\n          description: The Instagram user ID.\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Comma-separated list of fields.\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results per page.\n        - name: after\n          in: query\n          type: string\n          required: false\n          description: Cursor for pagination.\n        - name: access_token\n          in: query\n          type: string\n          required: true\n          description: User access token.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-user-stories\n        method: GET\n        path: /{user_id}/stories\n        description: Get a collection of story IG Media objects on the account.\n        inputParameters:\n\
  \        - name: user_id\n          in: path\n          type: string\n          required: true\n          description: The Instagram user ID.\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Comma-separated list of fields.\n        - name: access_token\n          in: query\n          type: string\n          required: true\n          description: User access token.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-media\n        method: GET\n        path: /{media_id}\n        description: Get fields on an Instagram photo, video, story, reel, or album.\n        inputParameters:\n        - name: media_id\n          in: path\n          type: string\n          required: true\n          description: The IG Media ID.\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description:\
  \ Comma-separated list of fields.\n        - name: access_token\n          in: query\n          type: string\n          required: true\n          description: User access token.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-media\n        method: POST\n        path: /{media_id}\n        description: Enable or disable comments on a media object.\n        inputParameters:\n        - name: media_id\n          in: path\n          type: string\n          required: true\n          description: The IG Media ID.\n        body:\n          type: json\n          data:\n            comment_enabled: '{{tools.comment_enabled}}'\n            access_token: '{{tools.access_token}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-media\n        method: DELETE\n        path: /{media_id}\n        description:\
  \ Delete an Instagram media object (post, story, reel, or carousel).\n        inputParameters:\n        - name: media_id\n          in: path\n          type: string\n          required: true\n          description: The IG Media ID.\n        - name: access_token\n          in: query\n          type: string\n          required: true\n          description: User access token.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-media-children\n        method: GET\n        path: /{media_id}/children\n        description: Get media objects within a carousel album.\n        inputParameters:\n        - name: media_id\n          in: path\n          type: string\n          required: true\n          description: The IG Media ID.\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Comma-separated list of fields.\n        - name: access_token\n\
  \          in: query\n          type: string\n          required: true\n          description: User access token.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: publishing\n      path: /\n      description: Content creation and publishing workflow.\n      operations:\n      - name: create-media-container\n        method: POST\n        path: /{user_id}/media\n        description: Create a media container for publishing content. Step 1 of the publishing flow.\n        inputParameters:\n        - name: user_id\n          in: path\n          type: string\n          required: true\n          description: The Instagram user ID.\n        body:\n          type: json\n          data:\n            image_url: '{{tools.image_url}}'\n            video_url: '{{tools.video_url}}'\n            caption: '{{tools.caption}}'\n            media_type: '{{tools.media_type}}'\n            is_carousel_item: '{{tools.is_carousel_item}}'\n\
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
  \ GET\n        path: /{user_id}/tags\n        description: Get IG Media objects where the user has been tagged by other users.\n        inputParameters:\n        - name: user_id\n          in: path\n          type: string\n          required: true\n          description: The Instagram user ID.\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Comma-separated list of fields.\n        - name: access_token\n          in: query\n          type: string\n          required: true\n          description: User access token.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8081\n    namespace: instagram-engagement-api\n    description: Unified REST API for Instagram community engagement workflows.\n    resources:\n    - path: /v1/media/{media_id}/comments\n      name: media-comments\n      description: Comments\
  \ on a media object.\n      operations:\n      - method: GET\n        name: get-media-comments\n        description: Get comments on an Instagram media object.\n        call: instagram-graph.get-media-comments\n        with:\n          media_id: rest.media_id\n          fields: rest.fields\n          access_token: rest.access_token\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-comment\n        description: Create a comment on an Instagram media object.\n        call: instagram-graph.create-comment\n        with:\n          media_id: rest.media_id\n          message: rest.message\n          access_token: rest.access_token\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/comments/{comment_id}\n      name: comment\n      description: Individual comment operations.\n      operations:\n      - method: GET\n        name: get-comment\n        description: Get fields on an Instagram\
  \ comment.\n        call: instagram-graph.get-comment\n        with:\n          comment_id: rest.comment_id\n          fields: rest.fields\n          access_token: rest.access_token\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: hide-comment\n        description: Hide or unhide a comment on your media.\n        call: instagram-graph.hide-comment\n        with:\n          comment_id: rest.comment_id\n          hide: rest.hide\n          access_token: rest.access_token\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-comment\n        description: Delete a comment on your media.\n        call: instagram-graph.delete-comment\n        with:\n          comment_id: rest.comment_id\n          access_token: rest.access_token\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/comments/{comment_id}/replies\n      name: comment-replies\n\
  \      description: Replies to a comment.\n      operations:\n      - method: GET\n        name: get-comment-replies\n        description: Get replies to a comment.\n        call: instagram-graph.get-comment-replies\n        with:\n          comment_id: rest.comment_id\n          fields: rest.fields\n          access_token: rest.access_token\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-comment-reply\n        description: Reply to a comment.\n        call: instagram-graph.create-comment-reply\n        with:\n          comment_id: rest.comment_id\n          message: rest.message\n          access_token: rest.access_token\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/hashtags/search\n      name: hashtag-search\n      description: Search for hashtags.\n      operations:\n      - method: GET\n        name: search-hashtag\n        description: Search for a hashtag by name and\
  \ get its ID.\n        call: instagram-graph.search-hashtag\n        with:\n          q: rest.q\n          user_id: rest.user_id\n          access_token: rest.access_token\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/hashtags/{hashtag_id}/top-media\n      name: hashtag-top-media\n      description: Top media for a hashtag.\n      operations:\n      - method: GET\n        name: get-hashtag-top-media\n        description: Get the most popular media tagged with a specific hashtag.\n        call: instagram-graph.get-hashtag-top-media\n        with:\n          hashtag_id: rest.hashtag_id\n          user_id: rest.user_id\n          fields: rest.fields\n          access_token: rest.access_token\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/hashtags/{hashtag_id}/recent-media\n      name: hashtag-recent-media\n      description: Recent media for a hashtag.\n      operations:\n      - method: GET\n       \
  \ name: get-hashtag-recent-media\n        description: Get the most recently published media tagged with a specific hashtag.\n        call: instagram-graph.get-hashtag-recent-media\n        with:\n          hashtag_id: rest.hashtag_id\n          user_id: rest.user_id\n          fields: rest.fields\n          access_token: rest.access_token\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/users/{user_id}/tags\n      name: user-tags\n      description: Media where user was tagged.\n      operations:\n      - method: GET\n        name: get-user-tags\n        description: Get IG Media objects where the user has been tagged by other users.\n        call: instagram-graph.get-user-tags\n        with:\n          user_id: rest.user_id\n          fields: rest.fields\n          access_token: rest.access_token\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9091\n    namespace: instagram-engagement-mcp\n\
  \    transport: http\n    description: MCP server for AI-assisted Instagram community engagement.\n    tools:\n    - name: get-media-comments\n      description: Get comments on an Instagram media object.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: instagram-graph.get-media-comments\n      with:\n        media_id: tools.media_id\n        fields: tools.fields\n        access_token: tools.access_token\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-comment\n      description: Create a comment on an Instagram media object.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: instagram-graph.create-comment\n      with:\n        media_id: tools.media_id\n        message: tools.message\n        access_token: tools.access_token\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-comment\n      description: Get fields on an Instagram comment.\n\
  \      hints:\n        readOnly: true\n        idempotent: true\n      call: instagram-graph.get-comment\n      with:\n        comment_id: tools.comment_id\n        fields: tools.fields\n        access_token: tools.access_token\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: hide-comment\n      description: Hide or unhide a comment on your media.\n      hints:\n        readOnly: false\n        idempotent: true\n      call: instagram-graph.hide-comment\n      with:\n        comment_id: tools.comment_id\n        hide: tools.hide\n        access_token: tools.access_token\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-comment\n      description: Delete a comment on your media.\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: instagram-graph.delete-comment\n      with:\n        comment_id: tools.comment_id\n        access_token: tools.access_token\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: get-comment-replies\n      description: Get replies to a comment.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: instagram-graph.get-comment-replies\n      with:\n        comment_id: tools.comment_id\n        fields: tools.fields\n        access_token: tools.access_token\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-comment-reply\n      description: Reply to a comment.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: instagram-graph.create-comment-reply\n      with:\n        comment_id: tools.comment_id\n        message: tools.message\n        access_token: tools.access_token\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-hashtag\n      description: Search for a hashtag by name and get its ID.\n      hints:\n        readOnly: true\n        idempotent: true\n    \
  \  call: instagram-graph.search-hashtag\n      with:\n        q: tools.q\n        user_id: tools.user_id\n        access_token: tools.access_token\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-hashtag-top-media\n      description: Get the most popular media tagged with a specific hashtag.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: instagram-graph.get-hashtag-top-media\n      with:\n        hashtag_id: tools.hashtag_id\n        user_id: tools.user_id\n        fields: tools.fields\n        access_token: tools.access_token\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-hashtag-recent-media\n      description: Get the most recently published media tagged with a specific hashtag.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: instagram-graph.get-hashtag-recent-media\n      with:\n        hashtag_id: tools.hashtag_id\n        user_id: tools.user_id\n  \
  \      fields: tools.fields\n        access_token: tools.access_token\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-user-tags\n      description: Get IG Media objects where the user has been tagged by other users.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: instagram-graph.get-user-tags\n      with:\n        user_id: tools.user_id\n        fields: tools.fields\n        access_token: tools.access_token\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/instagram/refs/heads/main/capabilities/community-engagement.yaml
tags:
- Instagram
- Community Engagement
- Social Media
- Comments
- Hashtags
- Mentions
tools:
- description: Get comments on an Instagram media object.
  hints:
    idempotent: true
    readOnly: true
  name: get-media-comments
- description: Create a comment on an Instagram media object.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-comment
- description: Get fields on an Instagram comment.
  hints:
    idempotent: true
    readOnly: true
  name: get-comment
- description: Hide or unhide a comment on your media.
  hints:
    idempotent: true
    readOnly: false
  name: hide-comment
- description: Delete a comment on your media.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-comment
- description: Get replies to a comment.
  hints:
    idempotent: true
    readOnly: true
  name: get-comment-replies
- description: Reply to a comment.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-comment-reply
- description: Search for a hashtag by name and get its ID.
  hints:
    idempotent: true
    readOnly: true
  name: search-hashtag
- description: Get the most popular media tagged with a specific hashtag.
  hints:
    idempotent: true
    readOnly: true
  name: get-hashtag-top-media
- description: Get the most recently published media tagged with a specific hashtag.
  hints:
    idempotent: true
    readOnly: true
  name: get-hashtag-recent-media
- description: Get IG Media objects where the user has been tagged by other users.
  hints:
    idempotent: true
    readOnly: true
  name: get-user-tags
---
