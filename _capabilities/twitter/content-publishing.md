---
categories:
- content-management
consumed_apis: []
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
- updateLists
- community manager
- getUsersBookmarks
- data engineer
- content
- manage compliance jobs, data streams, and real-time compliance monitoring.
- get analytics for a post
- initializeMediaUpload
- upload media for posts
- create lists
- manages user relationships, follows, and interaction strategies.
- researcher
- conducts academic or market research using x data archives.
- x api
- platform operations
- initialize a chunked media upload
- posts
- advertising
- createUsersBookmark
- manage a specific post
- streaming
- post creation, editing, media management, and content analytics.
- create a new list
- get bookmarked posts for the authenticated user
- get posts from a list timeline
- upload media for posts (simple upload for small files)
- extracts insights from social data through search, streaming, and analytics.
- finalize a chunked media upload
- user relationships, direct messaging, spaces, and community interaction.
- addListsMember
- social monitoring, search, trending topics, and sentiment analysis.
- deleteUsersBookmark
- brand manager
- deleteLists
- create and retrieve posts
- handles customer inquiries and issues via direct messages and replies.
- real-time data
- get post analytics
- create a new post (tweet) on x
- initialize chunked upload
- content creator
- data compliance, deletion tracking, and regulatory event monitoring.
- monitor conversations, search posts, analyze trends, and extract insights.
- createPosts
- getPostsAnalytics
- mediaUpload
- upload media
- produces original posts, threads, and media content on x.
- create, manage, and analyze posts, media, bookmarks, and lists.
- manage list members
- social media manager
- bookmark a post
- get the members of a list
- create a new post
- finalize chunked upload
- get list posts
- getListsMembers
- update a list's name or description
- delete a post
- ensures data handling meets regulatory and platform compliance requirements.
- manages data pipelines, streaming ingestion, and compliance data flows.
- get the processing status of an uploaded media
- remove a bookmark
- manages brand presence, campaigns, and content strategy.
- create a new list on x
- finalizeMediaUpload
- media
- getPostsByIds
- retrieve multiple posts by their ids
- retrieve posts by ids
- get bookmarked posts
- getListsPosts
- builds and maintains communities through engagement and moderation.
- getListsById
- get analytics data for a specific post
- manage user bookmarks
- data analyst
- delete a post by its id
- compliance officer
- marketing
- marketing team
- publishing
- creates, schedules, and analyzes social media content across platforms.
- append a chunk to an in-progress media upload
- create or update metadata (alt text) for uploaded media
- engagement specialist
- get posts from a list's timeline
- get a list by its id
- microblogging
- getMediaUploadStatus
- monitors brand mentions, sentiment, and competitive landscape.
- appendMediaUpload
- createLists
- customer support
- manage user relationships, direct messages, spaces, and community interactions.
- social media
- add a member to a list
- createMediaMetadata
- delete a list
- deletePostById
slug: content-publishing
source_filename: content-publishing.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: X Content Publishing and Management\n  description: Unified workflow for creating, managing, and analyzing posts, media, bookmarks, and lists on X. Used by social\n    media managers, content creators, and marketing teams.\n  tags:\n  - X API\n  - Content\n  - Publishing\n  - Posts\n  - Media\n  - Marketing\n  personas:\n  - social media managers\n  - content creators\n  - marketing teams\n  created: '2026-04-17'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    X_API_BEARER_TOKEN: X_API_BEARER_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: x-posts\n    baseUri: https://api.x.com\n    description: X API v2 endpoints for posts (tweets) management.\n    authentication:\n      type: bearer\n      token: '{{X_API_BEARER_TOKEN}}'\n    resources:\n    - name: posts\n      path: /2\n      description: Create, retrieve, and delete posts.\n      operations:\n      - name: createPosts\n        method: POST\n    \
  \    path: /tweets\n        description: Create a new post (tweet).\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getPostsByIds\n        method: GET\n        path: /tweets\n        description: Retrieve multiple posts by their IDs.\n        inputParameters:\n        - name: ids\n          in: query\n          type: string\n          required: true\n          description: Comma-separated list of post IDs\n        - name: tweet.fields\n          in: query\n          type: string\n          required: false\n          description: Comma-separated list of tweet fields to return\n        - name: expansions\n          in: query\n          type: string\n          required: false\n          description: Comma-separated list of expansions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n\
  \      - name: deletePostById\n        method: DELETE\n        path: /tweets/{id}\n        description: Delete a post by its ID.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The ID of the post to delete\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: post-analytics\n      path: /2\n      description: Retrieve analytics and insights for posts.\n      operations:\n      - name: getPostsAnalytics\n        method: GET\n        path: /tweets/{id}/analytics\n        description: Get analytics data for a specific post.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The ID of the post\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      -\
  \ name: getInsights28Hr\n        method: GET\n        path: /insights/tweets/28hr\n        description: Get post insights for the last 28 hours.\n        inputParameters:\n        - name: tweet.fields\n          in: query\n          type: string\n          required: false\n          description: Comma-separated list of tweet fields\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getInsightsHistorical\n        method: GET\n        path: /insights/tweets/historical\n        description: Get historical post insights.\n        inputParameters:\n        - name: tweet.fields\n          in: query\n          type: string\n          required: false\n          description: Comma-separated list of tweet fields\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: post-search\n      path: /2\n      description: Search for\
  \ posts using queries.\n      operations:\n      - name: searchPostsRecent\n        method: POST\n        path: /tweets/search/recent\n        description: Search for posts from the last 7 days.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: searchPostsAll\n        method: POST\n        path: /tweets/search/all\n        description: Search the full archive of posts.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: post-counts\n      path: /2\n      description: Get counts of posts matching a query.\n      operations:\n      - name: getPostsCountsRecent\n        method: GET\n        path: /tweets/counts/recent\n        description: Get counts of posts matching a query from the last 7 days.\n        inputParameters:\n        - name:\
  \ query\n          in: query\n          type: string\n          required: true\n          description: Search query for matching posts\n        - name: granularity\n          in: query\n          type: string\n          required: false\n          description: Granularity of count results (minute, hour, day)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getPostsCountsAll\n        method: GET\n        path: /tweets/counts/all\n        description: Get counts of posts matching a query from the full archive.\n        inputParameters:\n        - name: query\n          in: query\n          type: string\n          required: true\n          description: Search query for matching posts\n        - name: granularity\n          in: query\n          type: string\n          required: false\n          description: Granularity of count results (minute, hour, day)\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: timelines\n      path: /2\n      description: Retrieve user timelines and mentions.\n      operations:\n      - name: getUserTimeline\n        method: GET\n        path: /users/{id}/tweets\n        description: Get posts authored by a specific user.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The user ID\n        - name: max_results\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results (1-100)\n        - name: pagination_token\n          in: query\n          type: string\n          required: false\n          description: Token for pagination\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getUserMentions\n        method: GET\n        path: /users/{id}/mentions\n\
  \        description: Get posts mentioning a specific user.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The user ID\n        - name: max_results\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results (1-100)\n        - name: pagination_token\n          in: query\n          type: string\n          required: false\n          description: Token for pagination\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getUserHomeTimeline\n        method: GET\n        path: /users/{id}/timelines/reverse_chronological\n        description: Get the authenticated user's home timeline.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The authenticated user ID\n \
  \       - name: max_results\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results (1-100)\n        - name: pagination_token\n          in: query\n          type: string\n          required: false\n          description: Token for pagination\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: post-engagement\n      path: /2\n      description: Get engagement data for posts.\n      operations:\n      - name: getPostsQuotePosts\n        method: GET\n        path: /tweets/{id}/quote_tweets\n        description: Get posts that quote a specific post.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The post ID\n        - name: max_results\n          in: query\n          type: integer\n          required: false\n          description: Maximum number\
  \ of results\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getPostsRepostedBy\n        method: GET\n        path: /tweets/{id}/retweeted_by\n        description: Get users who reposted a specific post.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The post ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getPostsLikingUsers\n        method: GET\n        path: /tweets/{id}/liking_users\n        description: Get users who liked a specific post.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The post ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n       \
  \   value: $.\n    - name: post-moderation\n      path: /2\n      description: Moderate post replies.\n      operations:\n      - name: hidePostsReply\n        method: PUT\n        path: /tweets/{id}/hidden\n        description: Hide or unhide a reply to a post.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The reply post ID\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: x-media\n    baseUri: https://api.x.com\n    description: X API endpoints for media upload and management.\n    authentication:\n      type: bearer\n      token: '{{X_API_BEARER_TOKEN}}'\n    resources:\n    - name: upload\n      path: /2\n      description: Upload media via simple or chunked upload.\n      operations:\n      - name: mediaUpload\n        method: POST\n        path:\
  \ /media/upload\n        description: Upload media (simple upload for small files).\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: initializeMediaUpload\n        method: POST\n        path: /media/upload/initialize\n        description: Initialize a chunked media upload.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: appendMediaUpload\n        method: POST\n        path: /media/upload/append\n        description: Append a chunk to an in-progress media upload.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: finalizeMediaUpload\n        method: POST\n        path: /media/upload/finalize\n        description:\
  \ Finalize a chunked media upload.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getMediaUploadStatus\n        method: GET\n        path: /media/upload/status/{media_id}\n        description: Get the processing status of an uploaded media.\n        inputParameters:\n        - name: media_id\n          in: path\n          type: string\n          required: true\n          description: The media ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: media-info\n      path: /2\n      description: Retrieve media information and analytics.\n      operations:\n      - name: getMediaByMediaKeys\n        method: GET\n        path: /media\n        description: Retrieve media by media keys.\n        inputParameters:\n        - name: media_keys\n          in: query\n          type:\
  \ string\n          required: true\n          description: Comma-separated list of media keys\n        - name: media.fields\n          in: query\n          type: string\n          required: false\n          description: Comma-separated list of media fields\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getMediaAnalytics\n        method: GET\n        path: /media/{media_id}/analytics\n        description: Get analytics for a specific media.\n        inputParameters:\n        - name: media_id\n          in: path\n          type: string\n          required: true\n          description: The media ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: media-metadata\n      path: /2\n      description: Manage media metadata and subtitles.\n      operations:\n      - name: createMediaMetadata\n        method: POST\n\
  \        path: /media/metadata/create\n        description: Create or update metadata (alt text) for uploaded media.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createMediaSubtitles\n        method: POST\n        path: /media/subtitles/create\n        description: Associate subtitles with uploaded media.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteMediaSubtitles\n        method: DELETE\n        path: /media/subtitles/delete\n        description: Remove subtitles from uploaded media.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: x-bookmarks\n    baseUri: https://api.x.com\n\
  \    description: X API v2 endpoints for bookmarks and bookmark folders.\n    authentication:\n      type: bearer\n      token: '{{X_API_BEARER_TOKEN}}'\n    resources:\n    - name: bookmarks\n      path: /2\n      description: Manage user bookmarks.\n      operations:\n      - name: getUsersBookmarks\n        method: GET\n        path: /users/{id}/bookmarks\n        description: Get bookmarked posts for the authenticated user.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The authenticated user ID\n        - name: max_results\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results\n        - name: pagination_token\n          in: query\n          type: string\n          required: false\n          description: Token for pagination\n        - name: tweet.fields\n          in: query\n          type: string\n          required: false\n\
  \          description: Comma-separated list of tweet fields\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createUsersBookmark\n        method: POST\n        path: /users/{id}/bookmarks\n        description: Bookmark a post.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The authenticated user ID\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteUsersBookmark\n        method: DELETE\n        path: /users/{id}/bookmarks/{tweet_id}\n        description: Remove a bookmark.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The authenticated user ID\n        - name: tweet_id\n       \
  \   in: path\n          type: string\n          required: true\n          description: The post ID to unbookmark\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: bookmark-folders\n      path: /2\n      description: Manage bookmark folders.\n      operations:\n      - name: getUsersBookmarkFolders\n        method: GET\n        path: /users/{id}/bookmarks/folders\n        description: Get bookmark folders for the authenticated user.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The authenticated user ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getUsersBookmarksByFolderId\n        method: GET\n        path: /users/{id}/bookmarks/folders/{folder_id}\n        description: Get bookmarked posts in a specific folder.\n\
  \        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The authenticated user ID\n        - name: folder_id\n          in: path\n          type: string\n          required: true\n          description: The bookmark folder ID\n        - name: max_results\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results\n        - name: pagination_token\n          in: query\n          type: string\n          required: false\n          description: Token for pagination\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: x-lists\n    baseUri: https://api.x.com\n    description: X API v2 endpoints for list management.\n    authentication:\n      type: bearer\n      token: '{{X_API_BEARER_TOKEN}}'\n    resources:\n    - name: lists\n      path: /2\n\
  \      description: Create, retrieve, update, and delete lists.\n      operations:\n      - name: createLists\n        method: POST\n        path: /lists\n        description: Create a new list.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getListsById\n        method: GET\n        path: /lists/{id}\n        description: Get a list by its ID.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The list ID\n        - name: list.fields\n          in: query\n          type: string\n          required: false\n          description: Comma-separated list of list fields\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateLists\n        method: PUT\n        path: /lists/{id}\n    \
  \    description: Update a list's name or description.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The list ID\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteLists\n        method: DELETE\n        path: /lists/{id}\n        description: Delete a list.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The list ID to delete\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: list-members\n      path: /2\n      description: Manage list members.\n      operations:\n      - name: getListsMembers\n        method: GET\n        path: /lists/{id}/members\n        description: Get the members\
  \ of a list.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The list ID\n        - name: max_results\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results\n        - name: pagination_token\n          in: query\n          type: string\n          required: false\n          description: Token for pagination\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: addListsMember\n        method: POST\n        path: /lists/{id}/members\n        description: Add a member to a list.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The list ID\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n      - name: removeListsMemberByUserId\n        method: DELETE\n        path: /lists/{id}/members/{user_id}\n        description: Remove a member from a list.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The list ID\n        - name: user_id\n          in: path\n          type: string\n          required: true\n          description: The user ID to remove\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: list-followers\n      path: /2\n      description: Get list followers.\n      operations:\n      - name: getListsFollowers\n        method: GET\n        path: /lists/{id}/followers\n        description: Get users who follow a list.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description:\
  \ The list ID\n        - name: max_results\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results\n        - name: pagination_token\n          in: query\n          type: string\n          required: false\n          description: Token for pagination\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: list-follows\n      path: /2\n      description: Follow and unfollow lists.\n      operations:\n      - name: followList\n        method: POST\n        path: /users/{id}/followed_lists\n        description: Follow a list.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The authenticated user ID\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n      - name: unfollowList\n        method: DELETE\n        path: /users/{id}/followed_lists/{list_id}\n        description: Unfollow a list.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The authenticated user ID\n        - name: list_id\n          in: path\n          type: string\n          required: true\n          description: The list ID to unfollow\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: list-pins\n      path: /2\n      description: Pin and unpin lists.\n      operations:\n      - name: pinList\n        method: POST\n        path: /users/{id}/pinned_lists\n        description: Pin a list.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The authenticated user ID\n        body:\n          type:\
  \ json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: unpinList\n        method: DELETE\n        path: /users/{id}/pinned_lists/{list_id}\n        description: Unpin a list.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The authenticated user ID\n        - name: list_id\n          in: path\n          type: string\n          required: true\n          description: The list ID to unpin\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: list-posts\n      path: /2\n      description: Get posts from a list timeline.\n      operations:\n      - name: getListsPosts\n        method: GET\n        path: /lists/{id}/tweets\n        description: Get posts from a list's timeline.\n        inputParameters:\n        - name: id\n\
  \          in: path\n          type: string\n          required: true\n          description: The list ID\n        - name: max_results\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results\n        - name: pagination_token\n          in: query\n          type: string\n          required: false\n          description: Token for pagination\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: user-lists\n      path: /2\n      description: Get lists associated with a user.\n      operations:\n      - name: getUserOwnedLists\n        method: GET\n        path: /users/{id}/owned_lists\n        description: Get lists owned by a user.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The user ID\n        - name: max_results\n          in: query\n     \
  \     type: integer\n          required: false\n          description: Maximum number of results\n        - name: pagination_token\n          in: query\n          type: string\n          required: false\n          description: Token for pagination\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getUserListMemberships\n        method: GET\n        path: /users/{id}/list_memberships\n        description: Get lists a user is a member of.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The user ID\n        - name: max_results\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results\n        - name: pagination_token\n          in: query\n          type: string\n          required: false\n          description: Token for pagination\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getUserFollowedLists\n        method: GET\n        path: /users/{id}/followed_lists\n        description: Get lists a user follows.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The user ID\n        - name: max_results\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results\n        - name: pagination_token\n          in: query\n          type: string\n          required: false\n          description: Token for pagination\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getUserPinnedLists\n        method: GET\n        path: /users/{id}/pinned_lists\n        description: Get lists pinned by a user.\n        inputParameters:\n\
  \        - name: id\n          in: path\n          type: string\n          required: true\n          description: The user ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: x-content-api\n    resources:\n    - path: /v1/content/posts\n      name: posts\n      description: Create and retrieve posts\n      operations:\n      - method: POST\n        name: createPosts\n        description: Create a new post\n        call: x-content-api.createPosts\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: getPostsByIds\n        description: Retrieve posts by IDs\n        call: x-content-api.getPostsByIds\n        with:\n          ids: rest.ids\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/content/posts/{id}\n      name: post\n      description: Manage a specific\
  \ post\n      operations:\n      - method: DELETE\n        name: deletePostById\n        description: Delete a post\n        call: x-content-api.deletePostById\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/content/posts/{id}/analytics\n      name: post-analytics\n      description: Get post analytics\n      operations:\n      - method: GET\n        name: getPostsAnalytics\n        description: Get analytics for a post\n        call: x-content-api.getPostsAnalytics\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/content/media/upload\n      name: media-upload\n      description: Upload media\n      operations:\n      - method: POST\n        name: mediaUpload\n        description: Upload media for posts\n        call: x-content-api.mediaUpload\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path:\
  \ /v1/content/media/upload/initialize\n      name: media-upload-init\n      description: Initialize chunked upload\n      operations:\n      - method: POST\n        name: initializeMediaUpload\n        description: Initialize a chunked media upload\n        call: x-content-api.initializeMediaUpload\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/content/media/upload/finalize\n      name: media-upload-finalize\n      description: Finalize chunked upload\n      operations:\n      - method: POST\n        name: finalizeMediaUpload\n        description: Finalize a chunked media upload\n        call: x-content-api.finalizeMediaUpload\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/content/users/{id}/bookmarks\n      name: bookmarks\n      description: Manage user bookmarks\n      operations:\n      - method: POST\n        name: createUsersBookmark\n        description: Bookmark a post\n        call: x-content-api.createUsersBookmark\n\
  \        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: getUsersBookmarks\n        description: Get bookmarked posts\n        call: x-content-api.getUsersBookmarks\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/content/lists\n      name: lists\n      description: Create lists\n      operations:\n      - method: POST\n        name: createLists\n        description: Create a new list\n        call: x-content-api.createLists\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/content/lists/{id}/members\n      name: list-members\n      description: Manage list members\n      operations:\n      - method: POST\n        name: addListsMember\n        description: Add a member to a list\n        call: x-content-api.addListsMember\n        with:\n          id: rest.id\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /v1/content/lists/{id}/posts\n      name: list-posts\n      description: Get list posts\n      operations:\n      - method: GET\n        name: getListsPosts\n        description: Get posts from a list timeline\n        call: x-content-api.getListsPosts\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9080\n    namespace: x-content-mcp\n    transport: http\n    tools:\n    - name: createPosts\n      description: Create a new post (tweet) on X\n      hints:\n        readOnly: false\n        idempotent: false\n      call: x-content-mcp.createPosts\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getPostsByIds\n      description: Retrieve multiple posts by their IDs\n    \n\n# --- truncated at 32 KB (37 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/twitter/refs/heads/main/capabilities/content-publishing.yaml\n"
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
