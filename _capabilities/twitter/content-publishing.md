---
categories:
- content-management
consumed_apis:
- x-posts
- x-media
- x-bookmarks
- x-lists
description: Unified workflow for creating, managing, and analyzing posts, media, bookmarks, and lists on X. Used by social media managers, content creators, and marketing teams.
layout: capability
name: X Content Publishing and Management
operations:
- description: Create a new post
  method: POST
  name: createPosts
  path: /v1/content/posts
- description: Retrieve posts by IDs
  method: GET
  name: getPostsByIds
  path: /v1/content/posts
- description: Delete a post
  method: DELETE
  name: deletePostById
  path: /v1/content/posts/{id}
- description: Get analytics for a post
  method: GET
  name: getPostsAnalytics
  path: /v1/content/posts/{id}/analytics
- description: Upload media for posts
  method: POST
  name: mediaUpload
  path: /v1/content/media/upload
- description: Initialize a chunked media upload
  method: POST
  name: initializeMediaUpload
  path: /v1/content/media/upload/initialize
- description: Finalize a chunked media upload
  method: POST
  name: finalizeMediaUpload
  path: /v1/content/media/upload/finalize
- description: Bookmark a post
  method: POST
  name: createUsersBookmark
  path: /v1/content/users/{id}/bookmarks
- description: Get bookmarked posts
  method: GET
  name: getUsersBookmarks
  path: /v1/content/users/{id}/bookmarks
- description: Create a new list
  method: POST
  name: createLists
  path: /v1/content/lists
- description: Add a member to a list
  method: POST
  name: addListsMember
  path: /v1/content/lists/{id}/members
- description: Get posts from a list timeline
  method: GET
  name: getListsPosts
  path: /v1/content/lists/{id}/posts
personas:
- description: Creates, schedules, and analyzes social media content across platforms.
  id: social-media-manager
  name: Social Media Manager
- description: Produces original posts, threads, and media content on X.
  id: content-creator
  name: Content Creator
- description: Manages brand presence, campaigns, and content strategy.
  id: marketing-team
  name: Marketing Team
provider_name: X (Twitter)
provider_slug: twitter
search_terms:
- engagement specialist
- publishing
- getUsersBookmarks
- deleteUsersBookmark
- get analytics data for a specific post
- content
- retrieve multiple posts by their ids
- ensures data handling meets regulatory and platform compliance requirements.
- upload media for posts
- social media
- createMediaMetadata
- user relationships, direct messaging, spaces, and community interaction.
- deleteLists
- marketing team
- manage user relationships, direct messages, spaces, and community interactions.
- researcher
- data analyst
- get the processing status of an uploaded media
- create a new list
- get a list by its id
- createPosts
- get bookmarked posts for the authenticated user
- manage compliance jobs, data streams, and real-time compliance monitoring.
- bookmark a post
- extracts insights from social data through search, streaming, and analytics.
- delete a post by its id
- getListsMembers
- create a new post
- getPostsAnalytics
- remove a bookmark
- retrieve posts by ids
- streaming
- getPostsByIds
- finalize chunked upload
- media
- compliance officer
- manages user relationships, follows, and interaction strategies.
- creates, schedules, and analyzes social media content across platforms.
- getListsPosts
- add a member to a list
- get list posts
- microblogging
- manage user bookmarks
- finalize a chunked media upload
- get bookmarked posts
- content creator
- customer support
- advertising
- create lists
- mediaUpload
- monitor conversations, search posts, analyze trends, and extract insights.
- create, manage, and analyze posts, media, bookmarks, and lists.
- manage list members
- community manager
- get posts from a list's timeline
- platform operations
- initialize a chunked media upload
- get post analytics
- createUsersBookmark
- social monitoring, search, trending topics, and sentiment analysis.
- marketing
- getListsById
- updateLists
- get the members of a list
- x api
- manage a specific post
- brand manager
- post creation, editing, media management, and content analytics.
- initializeMediaUpload
- social media manager
- produces original posts, threads, and media content on x.
- conducts academic or market research using x data archives.
- appendMediaUpload
- create a new list on x
- update a list's name or description
- handles customer inquiries and issues via direct messages and replies.
- manages data pipelines, streaming ingestion, and compliance data flows.
- initialize chunked upload
- get posts from a list timeline
- real-time data
- builds and maintains communities through engagement and moderation.
- delete a post
- addListsMember
- data engineer
- deletePostById
- create a new post (tweet) on x
- get analytics for a post
- delete a list
- upload media
- manages brand presence, campaigns, and content strategy.
- data compliance, deletion tracking, and regulatory event monitoring.
- createLists
- append a chunk to an in-progress media upload
- create and retrieve posts
- getMediaUploadStatus
- monitors brand mentions, sentiment, and competitive landscape.
- upload media for posts (simple upload for small files)
- posts
- create or update metadata (alt text) for uploaded media
- finalizeMediaUpload
slug: content-publishing
source_filename: content-publishing.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"X Content Publishing and Management\"\n  description: \"Unified workflow for creating, managing, and analyzing posts, media, bookmarks, and lists on X. Used by social media managers, content creators, and marketing teams.\"\n  tags:\n    - X API\n    - Content\n    - Publishing\n    - Posts\n    - Media\n    - Marketing\n  personas:\n    - social media managers\n    - content creators\n    - marketing teams\n  created: \"2026-04-17\"\n  modified: \"2026-04-17\"\n\nbinds:\n  - namespace: env\n    keys:\n      X_API_BEARER_TOKEN: X_API_BEARER_TOKEN\n\ncapability:\n  consumes:\n    - import: x-posts\n      location: \"./shared/posts.yaml\"\n    - import: x-media\n      location: \"./shared/media.yaml\"\n    - import: x-bookmarks\n      location: \"./shared/bookmarks.yaml\"\n    - import: x-lists\n      location: \"./shared/lists.yaml\"\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: x-content-api\n      resources:\n\
  \        - path: /v1/content/posts\n          name: posts\n          description: \"Create and retrieve posts\"\n          operations:\n            - method: POST\n              name: createPosts\n              description: \"Create a new post\"\n              call: \"x-content-api.createPosts\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: GET\n              name: getPostsByIds\n              description: \"Retrieve posts by IDs\"\n              call: \"x-content-api.getPostsByIds\"\n              with:\n                ids: \"rest.ids\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/content/posts/{id}\n          name: post\n          description: \"Manage a specific post\"\n          operations:\n            - method: DELETE\n              name: deletePostById\n              description: \"Delete a post\"\n              call: \"x-content-api.deletePostById\"\
  \n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/content/posts/{id}/analytics\n          name: post-analytics\n          description: \"Get post analytics\"\n          operations:\n            - method: GET\n              name: getPostsAnalytics\n              description: \"Get analytics for a post\"\n              call: \"x-content-api.getPostsAnalytics\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/content/media/upload\n          name: media-upload\n          description: \"Upload media\"\n          operations:\n            - method: POST\n              name: mediaUpload\n              description: \"Upload media for posts\"\n              call: \"x-content-api.mediaUpload\"\n              outputParameters:\n                - type:\
  \ object\n                  mapping: \"$.\"\n        - path: /v1/content/media/upload/initialize\n          name: media-upload-init\n          description: \"Initialize chunked upload\"\n          operations:\n            - method: POST\n              name: initializeMediaUpload\n              description: \"Initialize a chunked media upload\"\n              call: \"x-content-api.initializeMediaUpload\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/content/media/upload/finalize\n          name: media-upload-finalize\n          description: \"Finalize chunked upload\"\n          operations:\n            - method: POST\n              name: finalizeMediaUpload\n              description: \"Finalize a chunked media upload\"\n              call: \"x-content-api.finalizeMediaUpload\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/content/users/{id}/bookmarks\n\
  \          name: bookmarks\n          description: \"Manage user bookmarks\"\n          operations:\n            - method: POST\n              name: createUsersBookmark\n              description: \"Bookmark a post\"\n              call: \"x-content-api.createUsersBookmark\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: GET\n              name: getUsersBookmarks\n              description: \"Get bookmarked posts\"\n              call: \"x-content-api.getUsersBookmarks\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/content/lists\n          name: lists\n          description: \"Create lists\"\n          operations:\n            - method: POST\n              name: createLists\n              description: \"Create a new list\"\n     \
  \         call: \"x-content-api.createLists\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/content/lists/{id}/members\n          name: list-members\n          description: \"Manage list members\"\n          operations:\n            - method: POST\n              name: addListsMember\n              description: \"Add a member to a list\"\n              call: \"x-content-api.addListsMember\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/content/lists/{id}/posts\n          name: list-posts\n          description: \"Get list posts\"\n          operations:\n            - method: GET\n              name: getListsPosts\n              description: \"Get posts from a list timeline\"\n              call: \"x-content-api.getListsPosts\"\n              with:\n                id: \"rest.id\"\n    \
  \          outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9080\n      namespace: x-content-mcp\n      transport: http\n      tools:\n        - name: createPosts\n          description: \"Create a new post (tweet) on X\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"x-content-mcp.createPosts\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: getPostsByIds\n          description: \"Retrieve multiple posts by their IDs\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"x-content-mcp.getPostsByIds\"\n          with:\n            ids: \"tools.ids\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: deletePostById\n          description: \"Delete a post by its ID\"\n          hints:\n            readOnly: false\n      \
  \      destructive: true\n          call: \"x-content-mcp.deletePostById\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: getPostsAnalytics\n          description: \"Get analytics data for a specific post\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"x-content-mcp.getPostsAnalytics\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: mediaUpload\n          description: \"Upload media for posts (simple upload for small files)\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"x-content-mcp.mediaUpload\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: initializeMediaUpload\n          description: \"Initialize a chunked media upload\"\
  \n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"x-content-mcp.initializeMediaUpload\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: appendMediaUpload\n          description: \"Append a chunk to an in-progress media upload\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"x-content-mcp.appendMediaUpload\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: finalizeMediaUpload\n          description: \"Finalize a chunked media upload\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"x-content-mcp.finalizeMediaUpload\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: getMediaUploadStatus\n          description: \"Get the processing status of an uploaded media\"\n          hints:\n\
  \            readOnly: true\n            idempotent: true\n          call: \"x-content-mcp.getMediaUploadStatus\"\n          with:\n            media_id: \"tools.media_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: createMediaMetadata\n          description: \"Create or update metadata (alt text) for uploaded media\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"x-content-mcp.createMediaMetadata\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: createUsersBookmark\n          description: \"Bookmark a post\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"x-content-mcp.createUsersBookmark\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: getUsersBookmarks\n          description:\
  \ \"Get bookmarked posts for the authenticated user\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"x-content-mcp.getUsersBookmarks\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: deleteUsersBookmark\n          description: \"Remove a bookmark\"\n          hints:\n            readOnly: false\n            destructive: true\n          call: \"x-content-mcp.deleteUsersBookmark\"\n          with:\n            id: \"tools.id\"\n            tweet_id: \"tools.tweet_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: createLists\n          description: \"Create a new list on X\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"x-content-mcp.createLists\"\n          outputParameters:\n            - type: object\n              mapping: \"\
  $.\"\n        - name: getListsById\n          description: \"Get a list by its ID\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"x-content-mcp.getListsById\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: updateLists\n          description: \"Update a list's name or description\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"x-content-mcp.updateLists\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: addListsMember\n          description: \"Add a member to a list\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"x-content-mcp.addListsMember\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type:\
  \ object\n              mapping: \"$.\"\n        - name: getListsMembers\n          description: \"Get the members of a list\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"x-content-mcp.getListsMembers\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: getListsPosts\n          description: \"Get posts from a list's timeline\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"x-content-mcp.getListsPosts\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: deleteLists\n          description: \"Delete a list\"\n          hints:\n            readOnly: false\n            destructive: true\n          call: \"x-content-mcp.deleteLists\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/twitter/refs/heads/main/capabilities/content-publishing.yaml
tags:
- X API
- Content
- Publishing
- Posts
- Media
- Marketing
tools:
- description: Create a new post (tweet) on X
  hints:
    idempotent: false
    readOnly: false
  name: createPosts
- description: Retrieve multiple posts by their IDs
  hints:
    idempotent: true
    readOnly: true
  name: getPostsByIds
- description: Delete a post by its ID
  hints:
    destructive: true
    readOnly: false
  name: deletePostById
- description: Get analytics data for a specific post
  hints:
    idempotent: true
    readOnly: true
  name: getPostsAnalytics
- description: Upload media for posts (simple upload for small files)
  hints:
    idempotent: false
    readOnly: false
  name: mediaUpload
- description: Initialize a chunked media upload
  hints:
    idempotent: false
    readOnly: false
  name: initializeMediaUpload
- description: Append a chunk to an in-progress media upload
  hints:
    idempotent: true
    readOnly: false
  name: appendMediaUpload
- description: Finalize a chunked media upload
  hints:
    idempotent: false
    readOnly: false
  name: finalizeMediaUpload
- description: Get the processing status of an uploaded media
  hints:
    idempotent: true
    readOnly: true
  name: getMediaUploadStatus
- description: Create or update metadata (alt text) for uploaded media
  hints:
    idempotent: true
    readOnly: false
  name: createMediaMetadata
- description: Bookmark a post
  hints:
    idempotent: false
    readOnly: false
  name: createUsersBookmark
- description: Get bookmarked posts for the authenticated user
  hints:
    idempotent: true
    readOnly: true
  name: getUsersBookmarks
- description: Remove a bookmark
  hints:
    destructive: true
    readOnly: false
  name: deleteUsersBookmark
- description: Create a new list on X
  hints:
    idempotent: false
    readOnly: false
  name: createLists
- description: Get a list by its ID
  hints:
    idempotent: true
    readOnly: true
  name: getListsById
- description: Update a list's name or description
  hints:
    idempotent: true
    readOnly: false
  name: updateLists
- description: Add a member to a list
  hints:
    idempotent: false
    readOnly: false
  name: addListsMember
- description: Get the members of a list
  hints:
    idempotent: true
    readOnly: true
  name: getListsMembers
- description: Get posts from a list's timeline
  hints:
    idempotent: true
    readOnly: true
  name: getListsPosts
- description: Delete a list
  hints:
    destructive: true
    readOnly: false
  name: deleteLists
---
