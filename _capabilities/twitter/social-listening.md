---
categories:
- analytics
consumed_apis: []
description: Unified workflow for monitoring conversations, searching posts, analyzing trends, and extracting insights from X data. Used by data analysts, brand managers, and researchers.
layout: capability
name: X Social Listening and Analytics
operations:
- description: Search posts from last 7 days
  method: POST
  name: searchPostsRecent
  path: /v1/listening/search/recent
- description: Search full archive of posts
  method: POST
  name: searchPostsAll
  path: /v1/listening/search/all
- description: Get counts from last 7 days
  method: GET
  name: getPostsCountsRecent
  path: /v1/listening/counts/recent
- description: Get counts from full archive
  method: GET
  name: getPostsCountsAll
  path: /v1/listening/counts/all
- description: Get post insights for last 28 hours
  method: GET
  name: getInsights28Hr
  path: /v1/listening/insights/28hr
- description: Get historical post insights
  method: GET
  name: getInsightsHistorical
  path: /v1/listening/insights/historical
- description: Stream posts matching filter rules
  method: GET
  name: streamPostsSearch
  path: /v1/listening/streams/search
- description: Add or delete stream rules
  method: POST
  name: addSearchStreamRules
  path: /v1/listening/streams/search/rules
- description: Get current stream rules
  method: GET
  name: getSearchStreamRules
  path: /v1/listening/streams/search/rules
- description: Stream all public posts
  method: GET
  name: streamPostsFirehose
  path: /v1/listening/streams/firehose
- description: Stream 10% sample of posts
  method: GET
  name: streamPostsSample10
  path: /v1/listening/streams/sample10
- description: Retrieve users by IDs
  method: GET
  name: getUsersByIds
  path: /v1/listening/users
- description: Retrieve users by usernames
  method: GET
  name: getUsersByUsernames
  path: /v1/listening/users/by
- description: Get user followers
  method: GET
  name: getFollowers
  path: /v1/listening/users/{id}/followers
- description: Get users being followed
  method: GET
  name: getFollowing
  path: /v1/listening/users/{id}/following
personas:
- description: Extracts insights from social data through search, streaming, and analytics.
  id: data-analyst
  name: Data Analyst
- description: Monitors brand mentions, sentiment, and competitive landscape.
  id: brand-manager
  name: Brand Manager
- description: Conducts academic or market research using X data archives.
  id: researcher
  name: Researcher
provider_name: X (Twitter)
provider_slug: twitter
search_terms:
- community manager
- analytics
- data engineer
- content
- manage compliance jobs, data streams, and real-time compliance monitoring.
- get users being followed
- getFollowers
- stream posts matching filtered stream rules in real-time
- add or delete rules for the filtered search stream
- filtered search stream
- 10% sample stream
- manages user relationships, follows, and interaction strategies.
- researcher
- conducts academic or market research using x data archives.
- x api
- platform operations
- advertising
- search
- streamPostsSearch
- get recent post counts
- getUsersMe
- get historical post insights
- add or delete stream rules
- streaming
- getUsersByIds
- get counts of posts matching a query from last 7 days
- search full archive of posts
- get current stream rules
- full firehose stream
- post creation, editing, media management, and content analytics.
- search all posts
- get 28-hour post insights
- get post insights for the last 28 hours
- get following
- addSearchStreamRules
- search for posts from the last 7 days
- extracts insights from social data through search, streaming, and analytics.
- stream a 10% sample of all public posts in real-time
- get counts from last 7 days
- manage stream filter rules
- get users that a user is following
- user relationships, direct messaging, spaces, and community interaction.
- getInsightsHistorical
- get post insights for last 28 hours
- social monitoring, search, trending topics, and sentiment analysis.
- brand manager
- get all post counts
- handles customer inquiries and issues via direct messages and replies.
- get counts from full archive
- real-time data
- social listening
- searchPostsAll
- streamPostsSample10
- get user followers
- content creator
- data compliance, deletion tracking, and regulatory event monitoring.
- getFollowing
- search recent posts
- monitor conversations, search posts, analyze trends, and extract insights.
- getUsersByUsernames
- search the full archive of posts
- stream 10% sample of posts
- getUserMentions
- retrieve users by ids
- produces original posts, threads, and media content on x.
- create, manage, and analyze posts, media, bookmarks, and lists.
- social media manager
- stream all public posts
- getUserTimeline
- searchPostsRecent
- ensures data handling meets regulatory and platform compliance requirements.
- manages data pipelines, streaming ingestion, and compliance data flows.
- look up users by ids
- manages brand presence, campaigns, and content strategy.
- search posts from last 7 days
- streamPostsFirehose
- get current rules for the filtered search stream
- getPostsCountsRecent
- get posts authored by a specific user
- builds and maintains communities through engagement and moderation.
- get followers
- get counts of posts matching a query from full archive
- get posts mentioning a specific user
- trends
- data analyst
- compliance officer
- getSearchStreamRules
- marketing team
- creates, schedules, and analyzes social media content across platforms.
- look up users by usernames
- getPostsCountsAll
- retrieve multiple users by their ids
- engagement specialist
- getInsights28Hr
- microblogging
- retrieve users by usernames
- monitors brand mentions, sentiment, and competitive landscape.
- retrieve multiple users by their usernames
- retrieve the authenticated user's profile
- customer support
- manage user relationships, direct messages, spaces, and community interactions.
- stream posts matching filter rules
- social media
- get followers of a user
- stream all public posts in real-time via the firehose
slug: social-listening
source_filename: social-listening.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: X Social Listening and Analytics\n  description: Unified workflow for monitoring conversations, searching posts, analyzing trends, and extracting insights from\n    X data. Used by data analysts, brand managers, and researchers.\n  tags:\n  - X API\n  - Social Listening\n  - Analytics\n  - Search\n  - Trends\n  personas:\n  - data analysts\n  - brand managers\n  - researchers\n  created: '2026-04-17'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    X_API_BEARER_TOKEN: X_API_BEARER_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: x-posts\n    baseUri: https://api.x.com\n    description: X API v2 endpoints for posts (tweets) management.\n    authentication:\n      type: bearer\n      token: '{{X_API_BEARER_TOKEN}}'\n    resources:\n    - name: posts\n      path: /2\n      description: Create, retrieve, and delete posts.\n      operations:\n      - name: createPosts\n        method: POST\n        path: /tweets\n\
  \        description: Create a new post (tweet).\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getPostsByIds\n        method: GET\n        path: /tweets\n        description: Retrieve multiple posts by their IDs.\n        inputParameters:\n        - name: ids\n          in: query\n          type: string\n          required: true\n          description: Comma-separated list of post IDs\n        - name: tweet.fields\n          in: query\n          type: string\n          required: false\n          description: Comma-separated list of tweet fields to return\n        - name: expansions\n          in: query\n          type: string\n          required: false\n          description: Comma-separated list of expansions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletePostById\n\
  \        method: DELETE\n        path: /tweets/{id}\n        description: Delete a post by its ID.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The ID of the post to delete\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: post-analytics\n      path: /2\n      description: Retrieve analytics and insights for posts.\n      operations:\n      - name: getPostsAnalytics\n        method: GET\n        path: /tweets/{id}/analytics\n        description: Get analytics data for a specific post.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The ID of the post\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getInsights28Hr\n      \
  \  method: GET\n        path: /insights/tweets/28hr\n        description: Get post insights for the last 28 hours.\n        inputParameters:\n        - name: tweet.fields\n          in: query\n          type: string\n          required: false\n          description: Comma-separated list of tweet fields\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getInsightsHistorical\n        method: GET\n        path: /insights/tweets/historical\n        description: Get historical post insights.\n        inputParameters:\n        - name: tweet.fields\n          in: query\n          type: string\n          required: false\n          description: Comma-separated list of tweet fields\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: post-search\n      path: /2\n      description: Search for posts using queries.\n     \
  \ operations:\n      - name: searchPostsRecent\n        method: POST\n        path: /tweets/search/recent\n        description: Search for posts from the last 7 days.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: searchPostsAll\n        method: POST\n        path: /tweets/search/all\n        description: Search the full archive of posts.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: post-counts\n      path: /2\n      description: Get counts of posts matching a query.\n      operations:\n      - name: getPostsCountsRecent\n        method: GET\n        path: /tweets/counts/recent\n        description: Get counts of posts matching a query from the last 7 days.\n        inputParameters:\n        - name: query\n          in: query\n\
  \          type: string\n          required: true\n          description: Search query for matching posts\n        - name: granularity\n          in: query\n          type: string\n          required: false\n          description: Granularity of count results (minute, hour, day)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getPostsCountsAll\n        method: GET\n        path: /tweets/counts/all\n        description: Get counts of posts matching a query from the full archive.\n        inputParameters:\n        - name: query\n          in: query\n          type: string\n          required: true\n          description: Search query for matching posts\n        - name: granularity\n          in: query\n          type: string\n          required: false\n          description: Granularity of count results (minute, hour, day)\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n    - name: timelines\n      path: /2\n      description: Retrieve user timelines and mentions.\n      operations:\n      - name: getUserTimeline\n        method: GET\n        path: /users/{id}/tweets\n        description: Get posts authored by a specific user.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The user ID\n        - name: max_results\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results (1-100)\n        - name: pagination_token\n          in: query\n          type: string\n          required: false\n          description: Token for pagination\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getUserMentions\n        method: GET\n        path: /users/{id}/mentions\n   \
  \     description: Get posts mentioning a specific user.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The user ID\n        - name: max_results\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results (1-100)\n        - name: pagination_token\n          in: query\n          type: string\n          required: false\n          description: Token for pagination\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getUserHomeTimeline\n        method: GET\n        path: /users/{id}/timelines/reverse_chronological\n        description: Get the authenticated user's home timeline.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The authenticated user ID\n    \
  \    - name: max_results\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results (1-100)\n        - name: pagination_token\n          in: query\n          type: string\n          required: false\n          description: Token for pagination\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: post-engagement\n      path: /2\n      description: Get engagement data for posts.\n      operations:\n      - name: getPostsQuotePosts\n        method: GET\n        path: /tweets/{id}/quote_tweets\n        description: Get posts that quote a specific post.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The post ID\n        - name: max_results\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of\
  \ results\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getPostsRepostedBy\n        method: GET\n        path: /tweets/{id}/retweeted_by\n        description: Get users who reposted a specific post.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The post ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getPostsLikingUsers\n        method: GET\n        path: /tweets/{id}/liking_users\n        description: Get users who liked a specific post.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The post ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n    - name: post-moderation\n      path: /2\n      description: Moderate post replies.\n      operations:\n      - name: hidePostsReply\n        method: PUT\n        path: /tweets/{id}/hidden\n        description: Hide or unhide a reply to a post.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The reply post ID\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: x-streaming\n    baseUri: https://api.x.com\n    description: X API v2 streaming endpoints for real-time data access.\n    authentication:\n      type: bearer\n      token: '{{X_API_BEARER_TOKEN}}'\n    resources:\n    - name: post-streams\n      path: /2\n      description: Stream posts in real-time via firehose, sample, and filtered search.\n      operations:\n      - name: streamPostsFirehose\n\
  \        method: GET\n        path: /tweets/firehose/stream\n        description: Stream all public posts in real-time via the firehose.\n        inputParameters:\n        - name: partition\n          in: query\n          type: integer\n          required: true\n          description: The partition number\n        - name: tweet.fields\n          in: query\n          type: string\n          required: false\n          description: Comma-separated list of tweet fields\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: streamPostsFirehoseEn\n        method: GET\n        path: /tweets/firehose/stream/lang/en\n        description: Stream all public English-language posts in real-time.\n        inputParameters:\n        - name: partition\n          in: query\n          type: integer\n          required: true\n          description: The partition number\n        - name: tweet.fields\n          in: query\n\
  \          type: string\n          required: false\n          description: Comma-separated list of tweet fields\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: streamPostsSample10\n        method: GET\n        path: /tweets/sample10/stream\n        description: Stream a 10% sample of all public posts in real-time.\n        inputParameters:\n        - name: partition\n          in: query\n          type: integer\n          required: true\n          description: The partition number\n        - name: tweet.fields\n          in: query\n          type: string\n          required: false\n          description: Comma-separated list of tweet fields\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: streamPostsSample1\n        method: GET\n        path: /tweets/sample/stream\n        description: Stream a roughly\
  \ 1% sample of all public posts in real-time.\n        inputParameters:\n        - name: tweet.fields\n          in: query\n          type: string\n          required: false\n          description: Comma-separated list of tweet fields\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: streamPostsSearch\n        method: GET\n        path: /tweets/search/stream\n        description: Stream posts matching filtered stream rules in real-time.\n        inputParameters:\n        - name: tweet.fields\n          in: query\n          type: string\n          required: false\n          description: Comma-separated list of tweet fields\n        - name: expansions\n          in: query\n          type: string\n          required: false\n          description: Comma-separated list of expansions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n    - name: stream-rules\n      path: /2\n      description: Manage filtered stream rules.\n      operations:\n      - name: addSearchStreamRules\n        method: POST\n        path: /tweets/search/stream/rules\n        description: Add or delete rules for the filtered search stream.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getSearchStreamRules\n        method: GET\n        path: /tweets/search/stream/rules\n        description: Get the current rules for the filtered search stream.\n        inputParameters:\n        - name: ids\n          in: query\n          type: string\n          required: false\n          description: Comma-separated list of rule IDs to retrieve\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: compliance-streams\n      path: /2\n    \
  \  description: Stream compliance events for users, posts, likes, and labels.\n      operations:\n      - name: streamUsersCompliance\n        method: GET\n        path: /users/compliance/stream\n        description: Stream user compliance events in real-time.\n        inputParameters:\n        - name: partition\n          in: query\n          type: integer\n          required: true\n          description: The partition number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: streamPostsCompliance\n        method: GET\n        path: /tweets/compliance/stream\n        description: Stream post compliance events in real-time.\n        inputParameters:\n        - name: partition\n          in: query\n          type: integer\n          required: true\n          description: The partition number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n      - name: streamLikesFirehose\n        method: GET\n        path: /likes/firehose/stream\n        description: Stream all likes in real-time via the firehose.\n        inputParameters:\n        - name: partition\n          in: query\n          type: integer\n          required: true\n          description: The partition number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: streamLikesCompliance\n        method: GET\n        path: /likes/compliance/stream\n        description: Stream likes compliance events in real-time.\n        inputParameters:\n        - name: partition\n          in: query\n          type: integer\n          required: true\n          description: The partition number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: streamLabelsCompliance\n        method: GET\n\
  \        path: /labels/compliance/stream\n        description: Stream labels compliance events in real-time.\n        inputParameters:\n        - name: partition\n          in: query\n          type: integer\n          required: true\n          description: The partition number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: x-users\n    baseUri: https://api.x.com\n    description: X API v2 endpoints for user management, follows, blocks, and mutes.\n    authentication:\n      type: bearer\n      token: '{{X_API_BEARER_TOKEN}}'\n    resources:\n    - name: users\n      path: /2\n      description: Look up users by ID, username, or authenticated user.\n      operations:\n      - name: getUsersByIds\n        method: GET\n        path: /users\n        description: Retrieve multiple users by their IDs.\n        inputParameters:\n        - name: ids\n          in: query\n          type:\
  \ string\n          required: true\n          description: Comma-separated list of user IDs\n        - name: user.fields\n          in: query\n          type: string\n          required: false\n          description: Comma-separated list of user fields to return\n        - name: expansions\n          in: query\n          type: string\n          required: false\n          description: Comma-separated list of expansions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getUsersByUsernames\n        method: GET\n        path: /users/by\n        description: Retrieve multiple users by their usernames.\n        inputParameters:\n        - name: usernames\n          in: query\n          type: string\n          required: true\n          description: Comma-separated list of usernames\n        - name: user.fields\n          in: query\n          type: string\n          required: false\n          description:\
  \ Comma-separated list of user fields to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getUsersByUsername\n        method: GET\n        path: /users/by/username/{username}\n        description: Retrieve a single user by username.\n        inputParameters:\n        - name: username\n          in: path\n          type: string\n          required: true\n          description: The username to look up\n        - name: user.fields\n          in: query\n          type: string\n          required: false\n          description: Comma-separated list of user fields to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getUsersMe\n        method: GET\n        path: /users/me\n        description: Retrieve the authenticated user's profile.\n        inputParameters:\n        - name: user.fields\n     \
  \     in: query\n          type: string\n          required: false\n          description: Comma-separated list of user fields to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: follows\n      path: /2\n      description: Manage follow relationships.\n      operations:\n      - name: followUser\n        method: POST\n        path: /users/{id}/following\n        description: Follow a user.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The authenticated user ID\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: unfollowUser\n        method: DELETE\n        path: /users/{source_user_id}/following/{target_user_id}\n        description: Unfollow a user.\n        inputParameters:\n\
  \        - name: source_user_id\n          in: path\n          type: string\n          required: true\n          description: The authenticated user ID\n        - name: target_user_id\n          in: path\n          type: string\n          required: true\n          description: The user ID to unfollow\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getFollowers\n        method: GET\n        path: /users/{id}/followers\n        description: Get followers of a user.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The user ID\n        - name: max_results\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results (1-1000)\n        - name: pagination_token\n          in: query\n          type: string\n          required: false\n          description:\
  \ Token for pagination\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getFollowing\n        method: GET\n        path: /users/{id}/following\n        description: Get users that a user is following.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The user ID\n        - name: max_results\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results (1-1000)\n        - name: pagination_token\n          in: query\n          type: string\n          required: false\n          description: Token for pagination\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: blocks\n      path: /2\n      description: Manage block relationships.\n      operations:\n      - name:\
  \ blockUsers\n        method: POST\n        path: /users/{id}/blocking\n        description: Block a user.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The authenticated user ID\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: unblockUsers\n        method: DELETE\n        path: /users/{source_user_id}/blocking/{target_user_id}\n        description: Unblock a user.\n        inputParameters:\n        - name: source_user_id\n          in: path\n          type: string\n          required: true\n          description: The authenticated user ID\n        - name: target_user_id\n          in: path\n          type: string\n          required: true\n          description: The user ID to unblock\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n      - name: getBlockedUsers\n        method: GET\n        path: /users/{id}/blocking\n        description: Get users blocked by the authenticated user.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The authenticated user ID\n        - name: max_results\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results\n        - name: pagination_token\n          in: query\n          type: string\n          required: false\n          description: Token for pagination\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: mutes\n      path: /2\n      description: Manage mute relationships.\n      operations:\n      - name: muteUser\n        method: POST\n        path: /users/{id}/muting\n        description: Mute\
  \ a user.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The authenticated user ID\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: unmuteUser\n        method: DELETE\n        path: /users/{source_user_id}/muting/{target_user_id}\n        description: Unmute a user.\n        inputParameters:\n        - name: source_user_id\n          in: path\n          type: string\n          required: true\n          description: The authenticated user ID\n        - name: target_user_id\n          in: path\n          type: string\n          required: true\n          description: The user ID to unmute\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getMutedUsers\n        method: GET\n     \
  \   path: /users/{id}/muting\n        description: Get users muted by the authenticated user.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The authenticated user ID\n        - name: max_results\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results\n        - name: pagination_token\n          in: query\n          type: string\n          required: false\n          description: Token for pagination\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8081\n    namespace: x-listening-api\n    resources:\n    - path: /v1/listening/search/recent\n      name: search-recent\n      description: Search recent posts\n      operations:\n      - method: POST\n        name: searchPostsRecent\n        description: Search posts from\
  \ last 7 days\n        call: x-listening-api.searchPostsRecent\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/listening/search/all\n      name: search-all\n      description: Search all posts\n      operations:\n      - method: POST\n        name: searchPostsAll\n        description: Search full archive of posts\n        call: x-listening-api.searchPostsAll\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/listening/counts/recent\n      name: counts-recent\n      description: Get recent post counts\n      operations:\n      - method: GET\n        name: getPostsCountsRecent\n        description: Get counts from last 7 days\n        call: x-listening-api.getPostsCountsRecent\n        with:\n          query: rest.query\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/listening/counts/all\n      name: counts-all\n      description: Get all post counts\n      operations:\n\
  \      - method: GET\n        name: getPostsCountsAll\n        description: Get counts from full archive\n        call: x-listening-api.getPostsCountsAll\n        with:\n          query: rest.query\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/listening/insights/28hr\n      name: insights-28hr\n      description: Get 28-hour post insights\n      operations:\n      - method: GET\n        name: getInsights28Hr\n        description: Get post insights for last 28 hours\n        call: x-listening-api.getInsights28Hr\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/listening/insights/historical\n      name: insights-historical\n      description: Get historical post insights\n      operations:\n      - method: GET\n        name: getInsightsHistorical\n        description: Get historical post insights\n        call: x-listening-api.getInsightsHistorical\n        outputParameters:\n        - type: object\n \
  \         mapping: $.\n    - path: /v1/listening/streams/search\n      name: search-stream\n      description: Filtered search stream\n      operations:\n      - method: GET\n        name: streamPostsSearch\n        description: Stream posts matching filter rules\n        call: x-listening-api.streamPostsSearch\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/listening/streams/search/rules\n      name: stream-rules\n      description: Manage stream filter rules\n      operations:\n      - method: POST\n        name: addSearchStreamRules\n        description: Add or delete stream rules\n        call: x-listening-api.addSearchStreamRules\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: getSearchStreamRules\n        description: Get current stream rules\n        call: x-listening-api.getSearchStreamRules\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path:\
  \ /v1/listening/streams/firehose\n      name: firehose\n      description: Full firehose stream\n      operations:\n      - method: GET\n        name: streamPostsFirehose\n        description: Stream all public posts\n        call: x-listening-api.streamPostsFirehose\n        with:\n          partition: rest.partition\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/listening/streams/sample10\n      name: sample10\n      description: 10% sample stream\n      operations:\n      - method: GET\n        name: streamPostsSample10\n        description: Stream 10% sample of posts\n        call: x-listening-api.streamPostsSample10\n        with:\n          partition: rest.partition\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/listening/users\n      name: users\n      description: Look up users by IDs\n      operations:\n      - method: GET\n        name: getUsersByIds\n        description: Retrieve users by\
  \ IDs\n        call: x-listening-api.getUsersByIds\n        with:\n          ids: rest.ids\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/listening/users/by\n      name: users-by-usernames\n      description: Look up users by usernames\n      operations:\n      - method: GET\n        name: getUsersByUsernames\n        description: Retrieve users by usernames\n        call: x-listening-api.getUsersByUsernames\n        with:\n          usernames: rest.usernames\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/listening/users/{id}/followers\n      name: followers\n      description: Get followers\n      operations:\n      - method: GET\n        name: getFollowers\n        description: Get user followers\n        call: x-listening-api.getFollowers\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/listening/users/{id}/following\n\
  \      name: following\n      description: Get following\n      operations:\n      - method: GET\n        name: getFollowing\n        description: Get users being followed\n        call: x-listening-api.getFollowing\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9081\n    namespace: x-listening-mcp\n    transport: http\n    tools:\n    - name: searchPostsRecent\n      description: Search for posts from the last 7 days\n      hints:\n        readOnly: true\n        idempotent: true\n      call: x-listening-mcp.searchPostsRecent\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: searchPostsAll\n      description: Search the full archive of posts\n      hints:\n        readOnly: true\n        idempotent: true\n      call: x-listening-mcp.searchPostsAll\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getPostsCountsRecent\n      description:\
  \ Get counts of posts matching a query from last 7 days\n      hints:\n        readOnly: true\n        idempotent: true\n      call: x-listening-mcp.getPostsCountsRecent\n      with:\n        query: tools.query\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getPostsCountsAll\n      description: Get counts of posts matching a query from full archive\n      hints:\n        readOnly: true\n        idempotent: true\n      call: x-listening-mcp.getPostsCountsAll\n      with:\n        query: tools.query\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getInsights28Hr\n      description: Get post insights for the last 28 hours\n      hints:\n        readOnly: true\n        idempotent: true\n      call: x-listening-mcp.getInsights28Hr\n      outputParameters:\n      - type: object\n        mapping: $\n\n# --- truncated at 32 KB (35 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/twitter/refs/heads/main/capabilities/social-listening.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/twitter/refs/heads/main/capabilities/social-listening.yaml
tags:
- X API
- Social Listening
- Analytics
- Search
- Trends
tools:
- description: Search for posts from the last 7 days
  hints:
    idempotent: true
    readOnly: true
  name: searchPostsRecent
- description: Search the full archive of posts
  hints:
    idempotent: true
    readOnly: true
  name: searchPostsAll
- description: Get counts of posts matching a query from last 7 days
  hints:
    idempotent: true
    readOnly: true
  name: getPostsCountsRecent
- description: Get counts of posts matching a query from full archive
  hints:
    idempotent: true
    readOnly: true
  name: getPostsCountsAll
- description: Get post insights for the last 28 hours
  hints:
    idempotent: true
    readOnly: true
  name: getInsights28Hr
- description: Get historical post insights
  hints:
    idempotent: true
    readOnly: true
  name: getInsightsHistorical
- description: Stream posts matching filtered stream rules in real-time
  hints:
    idempotent: true
    readOnly: true
  name: streamPostsSearch
- description: Add or delete rules for the filtered search stream
  hints:
    idempotent: false
    readOnly: false
  name: addSearchStreamRules
- description: Get current rules for the filtered search stream
  hints:
    idempotent: true
    readOnly: true
  name: getSearchStreamRules
- description: Stream all public posts in real-time via the firehose
  hints:
    idempotent: true
    readOnly: true
  name: streamPostsFirehose
- description: Stream a 10% sample of all public posts in real-time
  hints:
    idempotent: true
    readOnly: true
  name: streamPostsSample10
- description: Retrieve multiple users by their IDs
  hints:
    idempotent: true
    readOnly: true
  name: getUsersByIds
- description: Retrieve multiple users by their usernames
  hints:
    idempotent: true
    readOnly: true
  name: getUsersByUsernames
- description: Retrieve the authenticated user's profile
  hints:
    idempotent: true
    readOnly: true
  name: getUsersMe
- description: Get followers of a user
  hints:
    idempotent: true
    readOnly: true
  name: getFollowers
- description: Get users that a user is following
  hints:
    idempotent: true
    readOnly: true
  name: getFollowing
- description: Get posts authored by a specific user
  hints:
    idempotent: true
    readOnly: true
  name: getUserTimeline
- description: Get posts mentioning a specific user
  hints:
    idempotent: true
    readOnly: true
  name: getUserMentions
---
