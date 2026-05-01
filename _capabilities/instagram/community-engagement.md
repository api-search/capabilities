---
api_specs:
- filename: instagram-graph-api.yaml
  format: yaml
  label: instagram-graph
  slug: instagram-graph
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/instagram/refs/heads/main/openapi/instagram-graph-api.yaml
categories: []
consumed_apis:
- instagram-graph
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
- individual comment operations.
- hide comment
- delete a comment on your media.
- get comment
- embeds instagram content on websites and applications.
- insights and performance metrics.
- search for a hashtag by name and get its id.
- monitors mentions, comments, and brand sentiment on instagram.
- meta
- manages instagram direct conversations for business inquiries.
- website embedding of instagram content.
- get hashtag top media
- reply to a comment.
- photos
- get the most popular media tagged with a specific hashtag.
- hide or unhide a comment on your media.
- get hashtag recent media
- search hashtag
- content publishing and media management.
- comments
- instagram direct messaging.
- instagram
- creates and publishes photos, videos, reels, and stories.
- social media
- create a comment on an instagram media object.
- recent media for a hashtag.
- tracks content performance and audience insights.
- replies to a comment.
- comments on a media object.
- community engagement
- get ig media objects where the user has been tagged by other users.
- delete comment
- search for hashtags.
- get replies to a comment.
- top media for a hashtag.
- get user tags
- comments, mentions, and community interaction.
- videos
- get comment replies
- get the most recently published media tagged with a specific hashtag.
- get fields on an instagram comment.
- get media comments
- media where user was tagged.
- mentions
- create comment reply
- hashtags
- publishes and manages content across instagram accounts.
- create comment
- content publishing
- get comments on an instagram media object.
slug: community-engagement
source_filename: community-engagement.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Instagram Community Engagement\"\n  description: >-\n    Unified workflow for managing Instagram community interactions including\n    comment moderation, replies, hashtag discovery, and mention tracking. Used by\n    community managers and social media teams to engage with followers, moderate\n    comments, discover trending content via hashtags, and monitor brand mentions.\n  tags:\n    - Instagram\n    - Community Engagement\n    - Social Media\n    - Comments\n    - Hashtags\n    - Mentions\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      INSTAGRAM_ACCESS_TOKEN: INSTAGRAM_ACCESS_TOKEN\n\ncapability:\n  consumes:\n    - import: instagram-graph\n      location: ./shared/instagram-graph-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8081\n      namespace: instagram-engagement-api\n      description: \"Unified REST API for Instagram community engagement workflows.\"\n\
  \      resources:\n        - path: /v1/media/{media_id}/comments\n          name: media-comments\n          description: \"Comments on a media object.\"\n          operations:\n            - method: GET\n              name: get-media-comments\n              description: \"Get comments on an Instagram media object.\"\n              call: \"instagram-graph.get-media-comments\"\n              with:\n                media_id: \"rest.media_id\"\n                fields: \"rest.fields\"\n                access_token: \"rest.access_token\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-comment\n              description: \"Create a comment on an Instagram media object.\"\n              call: \"instagram-graph.create-comment\"\n              with:\n                media_id: \"rest.media_id\"\n                message: \"rest.message\"\n                access_token: \"rest.access_token\"\n\
  \              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/comments/{comment_id}\n          name: comment\n          description: \"Individual comment operations.\"\n          operations:\n            - method: GET\n              name: get-comment\n              description: \"Get fields on an Instagram comment.\"\n              call: \"instagram-graph.get-comment\"\n              with:\n                comment_id: \"rest.comment_id\"\n                fields: \"rest.fields\"\n                access_token: \"rest.access_token\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: hide-comment\n              description: \"Hide or unhide a comment on your media.\"\n              call: \"instagram-graph.hide-comment\"\n              with:\n                comment_id: \"rest.comment_id\"\n                hide: \"rest.hide\"\n      \
  \          access_token: \"rest.access_token\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-comment\n              description: \"Delete a comment on your media.\"\n              call: \"instagram-graph.delete-comment\"\n              with:\n                comment_id: \"rest.comment_id\"\n                access_token: \"rest.access_token\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/comments/{comment_id}/replies\n          name: comment-replies\n          description: \"Replies to a comment.\"\n          operations:\n            - method: GET\n              name: get-comment-replies\n              description: \"Get replies to a comment.\"\n              call: \"instagram-graph.get-comment-replies\"\n              with:\n                comment_id: \"rest.comment_id\"\n                fields: \"\
  rest.fields\"\n                access_token: \"rest.access_token\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-comment-reply\n              description: \"Reply to a comment.\"\n              call: \"instagram-graph.create-comment-reply\"\n              with:\n                comment_id: \"rest.comment_id\"\n                message: \"rest.message\"\n                access_token: \"rest.access_token\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/hashtags/search\n          name: hashtag-search\n          description: \"Search for hashtags.\"\n          operations:\n            - method: GET\n              name: search-hashtag\n              description: \"Search for a hashtag by name and get its ID.\"\n              call: \"instagram-graph.search-hashtag\"\n              with:\n                q: \"\
  rest.q\"\n                user_id: \"rest.user_id\"\n                access_token: \"rest.access_token\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/hashtags/{hashtag_id}/top-media\n          name: hashtag-top-media\n          description: \"Top media for a hashtag.\"\n          operations:\n            - method: GET\n              name: get-hashtag-top-media\n              description: \"Get the most popular media tagged with a specific hashtag.\"\n              call: \"instagram-graph.get-hashtag-top-media\"\n              with:\n                hashtag_id: \"rest.hashtag_id\"\n                user_id: \"rest.user_id\"\n                fields: \"rest.fields\"\n                access_token: \"rest.access_token\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/hashtags/{hashtag_id}/recent-media\n          name: hashtag-recent-media\n\
  \          description: \"Recent media for a hashtag.\"\n          operations:\n            - method: GET\n              name: get-hashtag-recent-media\n              description: \"Get the most recently published media tagged with a specific hashtag.\"\n              call: \"instagram-graph.get-hashtag-recent-media\"\n              with:\n                hashtag_id: \"rest.hashtag_id\"\n                user_id: \"rest.user_id\"\n                fields: \"rest.fields\"\n                access_token: \"rest.access_token\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/users/{user_id}/tags\n          name: user-tags\n          description: \"Media where user was tagged.\"\n          operations:\n            - method: GET\n              name: get-user-tags\n              description: \"Get IG Media objects where the user has been tagged by other users.\"\n              call: \"instagram-graph.get-user-tags\"\n   \
  \           with:\n                user_id: \"rest.user_id\"\n                fields: \"rest.fields\"\n                access_token: \"rest.access_token\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9091\n      namespace: instagram-engagement-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Instagram community engagement.\"\n      tools:\n        - name: get-media-comments\n          description: \"Get comments on an Instagram media object.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"instagram-graph.get-media-comments\"\n          with:\n            media_id: \"tools.media_id\"\n            fields: \"tools.fields\"\n            access_token: \"tools.access_token\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-comment\n          description: \"Create a comment\
  \ on an Instagram media object.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"instagram-graph.create-comment\"\n          with:\n            media_id: \"tools.media_id\"\n            message: \"tools.message\"\n            access_token: \"tools.access_token\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-comment\n          description: \"Get fields on an Instagram comment.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"instagram-graph.get-comment\"\n          with:\n            comment_id: \"tools.comment_id\"\n            fields: \"tools.fields\"\n            access_token: \"tools.access_token\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: hide-comment\n          description: \"Hide or unhide a comment on your media.\"\n      \
  \    hints:\n            readOnly: false\n            idempotent: true\n          call: \"instagram-graph.hide-comment\"\n          with:\n            comment_id: \"tools.comment_id\"\n            hide: \"tools.hide\"\n            access_token: \"tools.access_token\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: delete-comment\n          description: \"Delete a comment on your media.\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"instagram-graph.delete-comment\"\n          with:\n            comment_id: \"tools.comment_id\"\n            access_token: \"tools.access_token\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-comment-replies\n          description: \"Get replies to a comment.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"\
  instagram-graph.get-comment-replies\"\n          with:\n            comment_id: \"tools.comment_id\"\n            fields: \"tools.fields\"\n            access_token: \"tools.access_token\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-comment-reply\n          description: \"Reply to a comment.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"instagram-graph.create-comment-reply\"\n          with:\n            comment_id: \"tools.comment_id\"\n            message: \"tools.message\"\n            access_token: \"tools.access_token\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: search-hashtag\n          description: \"Search for a hashtag by name and get its ID.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"instagram-graph.search-hashtag\"\
  \n          with:\n            q: \"tools.q\"\n            user_id: \"tools.user_id\"\n            access_token: \"tools.access_token\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-hashtag-top-media\n          description: \"Get the most popular media tagged with a specific hashtag.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"instagram-graph.get-hashtag-top-media\"\n          with:\n            hashtag_id: \"tools.hashtag_id\"\n            user_id: \"tools.user_id\"\n            fields: \"tools.fields\"\n            access_token: \"tools.access_token\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-hashtag-recent-media\n          description: \"Get the most recently published media tagged with a specific hashtag.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call:\
  \ \"instagram-graph.get-hashtag-recent-media\"\n          with:\n            hashtag_id: \"tools.hashtag_id\"\n            user_id: \"tools.user_id\"\n            fields: \"tools.fields\"\n            access_token: \"tools.access_token\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-user-tags\n          description: \"Get IG Media objects where the user has been tagged by other users.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"instagram-graph.get-user-tags\"\n          with:\n            user_id: \"tools.user_id\"\n            fields: \"tools.fields\"\n            access_token: \"tools.access_token\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
