---
categories:
- analytics
consumed_apis:
- x-posts
- x-streaming
- x-users
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
- full firehose stream
- retrieve users by ids
- getUsersByUsernames
- look up users by ids
- get followers
- get posts authored by a specific user
- get counts from last 7 days
- manage user relationships, direct messages, spaces, and community interactions.
- stream posts matching filter rules
- stream 10% sample of posts
- streamPostsFirehose
- getUsersMe
- creates, schedules, and analyzes social media content across platforms.
- get users that a user is following
- get current rules for the filtered search stream
- getFollowers
- microblogging
- retrieve multiple users by their usernames
- get following
- searchPostsRecent
- brand manager
- analytics
- compliance officer
- social listening
- get current stream rules
- social monitoring, search, trending topics, and sentiment analysis.
- manages brand presence, campaigns, and content strategy.
- get followers of a user
- get posts mentioning a specific user
- stream posts matching filtered stream rules in real-time
- trends
- search all posts
- add or delete rules for the filtered search stream
- manages data pipelines, streaming ingestion, and compliance data flows.
- social media
- add or delete stream rules
- 10% sample stream
- search
- get counts of posts matching a query from last 7 days
- conducts academic or market research using x data archives.
- getInsightsHistorical
- monitor conversations, search posts, analyze trends, and extract insights.
- retrieve users by usernames
- content creator
- engagement specialist
- filtered search stream
- builds and maintains communities through engagement and moderation.
- retrieve multiple users by their ids
- data compliance, deletion tracking, and regulatory event monitoring.
- manage compliance jobs, data streams, and real-time compliance monitoring.
- marketing team
- getSearchStreamRules
- get post insights for the last 28 hours
- streamPostsSample10
- customer support
- streaming
- stream a 10% sample of all public posts in real-time
- extracts insights from social data through search, streaming, and analytics.
- manages user relationships, follows, and interaction strategies.
- get post insights for last 28 hours
- search recent posts
- create, manage, and analyze posts, media, bookmarks, and lists.
- getUsersByIds
- content
- advertising
- manage stream filter rules
- getInsights28Hr
- getPostsCountsAll
- post creation, editing, media management, and content analytics.
- search the full archive of posts
- get historical post insights
- searchPostsAll
- getPostsCountsRecent
- stream all public posts
- get all post counts
- social media manager
- getUserTimeline
- streamPostsSearch
- addSearchStreamRules
- x api
- monitors brand mentions, sentiment, and competitive landscape.
- user relationships, direct messaging, spaces, and community interaction.
- stream all public posts in real-time via the firehose
- get recent post counts
- get counts from full archive
- handles customer inquiries and issues via direct messages and replies.
- produces original posts, threads, and media content on x.
- search posts from last 7 days
- getUserMentions
- get counts of posts matching a query from full archive
- data engineer
- researcher
- getFollowing
- get users being followed
- get user followers
- get 28-hour post insights
- search full archive of posts
- retrieve the authenticated user's profile
- real-time data
- ensures data handling meets regulatory and platform compliance requirements.
- search for posts from the last 7 days
- platform operations
- look up users by usernames
- community manager
- data analyst
slug: social-listening
source_filename: social-listening.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"X Social Listening and Analytics\"\n  description: \"Unified workflow for monitoring conversations, searching posts, analyzing trends, and extracting insights from X data. Used by data analysts, brand managers, and researchers.\"\n  tags:\n    - X API\n    - Social Listening\n    - Analytics\n    - Search\n    - Trends\n  personas:\n    - data analysts\n    - brand managers\n    - researchers\n  created: \"2026-04-17\"\n  modified: \"2026-04-17\"\n\nbinds:\n  - namespace: env\n    keys:\n      X_API_BEARER_TOKEN: X_API_BEARER_TOKEN\n\ncapability:\n  consumes:\n    - import: x-posts\n      location: \"./shared/posts.yaml\"\n    - import: x-streaming\n      location: \"./shared/streaming.yaml\"\n    - import: x-users\n      location: \"./shared/users.yaml\"\n\n  exposes:\n    - type: rest\n      port: 8081\n      namespace: x-listening-api\n      resources:\n        - path: /v1/listening/search/recent\n          name: search-recent\n\
  \          description: \"Search recent posts\"\n          operations:\n            - method: POST\n              name: searchPostsRecent\n              description: \"Search posts from last 7 days\"\n              call: \"x-listening-api.searchPostsRecent\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/listening/search/all\n          name: search-all\n          description: \"Search all posts\"\n          operations:\n            - method: POST\n              name: searchPostsAll\n              description: \"Search full archive of posts\"\n              call: \"x-listening-api.searchPostsAll\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/listening/counts/recent\n          name: counts-recent\n          description: \"Get recent post counts\"\n          operations:\n            - method: GET\n              name: getPostsCountsRecent\n \
  \             description: \"Get counts from last 7 days\"\n              call: \"x-listening-api.getPostsCountsRecent\"\n              with:\n                query: \"rest.query\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/listening/counts/all\n          name: counts-all\n          description: \"Get all post counts\"\n          operations:\n            - method: GET\n              name: getPostsCountsAll\n              description: \"Get counts from full archive\"\n              call: \"x-listening-api.getPostsCountsAll\"\n              with:\n                query: \"rest.query\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/listening/insights/28hr\n          name: insights-28hr\n          description: \"Get 28-hour post insights\"\n          operations:\n            - method: GET\n              name: getInsights28Hr\n             \
  \ description: \"Get post insights for last 28 hours\"\n              call: \"x-listening-api.getInsights28Hr\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/listening/insights/historical\n          name: insights-historical\n          description: \"Get historical post insights\"\n          operations:\n            - method: GET\n              name: getInsightsHistorical\n              description: \"Get historical post insights\"\n              call: \"x-listening-api.getInsightsHistorical\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/listening/streams/search\n          name: search-stream\n          description: \"Filtered search stream\"\n          operations:\n            - method: GET\n              name: streamPostsSearch\n              description: \"Stream posts matching filter rules\"\n              call: \"x-listening-api.streamPostsSearch\"\
  \n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/listening/streams/search/rules\n          name: stream-rules\n          description: \"Manage stream filter rules\"\n          operations:\n            - method: POST\n              name: addSearchStreamRules\n              description: \"Add or delete stream rules\"\n              call: \"x-listening-api.addSearchStreamRules\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: GET\n              name: getSearchStreamRules\n              description: \"Get current stream rules\"\n              call: \"x-listening-api.getSearchStreamRules\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/listening/streams/firehose\n          name: firehose\n          description: \"Full firehose stream\"\n          operations:\n            -\
  \ method: GET\n              name: streamPostsFirehose\n              description: \"Stream all public posts\"\n              call: \"x-listening-api.streamPostsFirehose\"\n              with:\n                partition: \"rest.partition\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/listening/streams/sample10\n          name: sample10\n          description: \"10% sample stream\"\n          operations:\n            - method: GET\n              name: streamPostsSample10\n              description: \"Stream 10% sample of posts\"\n              call: \"x-listening-api.streamPostsSample10\"\n              with:\n                partition: \"rest.partition\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/listening/users\n          name: users\n          description: \"Look up users by IDs\"\n          operations:\n            - method: GET\n\
  \              name: getUsersByIds\n              description: \"Retrieve users by IDs\"\n              call: \"x-listening-api.getUsersByIds\"\n              with:\n                ids: \"rest.ids\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/listening/users/by\n          name: users-by-usernames\n          description: \"Look up users by usernames\"\n          operations:\n            - method: GET\n              name: getUsersByUsernames\n              description: \"Retrieve users by usernames\"\n              call: \"x-listening-api.getUsersByUsernames\"\n              with:\n                usernames: \"rest.usernames\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/listening/users/{id}/followers\n          name: followers\n          description: \"Get followers\"\n          operations:\n            - method: GET\n              name:\
  \ getFollowers\n              description: \"Get user followers\"\n              call: \"x-listening-api.getFollowers\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/listening/users/{id}/following\n          name: following\n          description: \"Get following\"\n          operations:\n            - method: GET\n              name: getFollowing\n              description: \"Get users being followed\"\n              call: \"x-listening-api.getFollowing\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9081\n      namespace: x-listening-mcp\n      transport: http\n      tools:\n        - name: searchPostsRecent\n          description: \"Search for posts from the last 7 days\"\n          hints:\n            readOnly: true\n\
  \            idempotent: true\n          call: \"x-listening-mcp.searchPostsRecent\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: searchPostsAll\n          description: \"Search the full archive of posts\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"x-listening-mcp.searchPostsAll\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: getPostsCountsRecent\n          description: \"Get counts of posts matching a query from last 7 days\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"x-listening-mcp.getPostsCountsRecent\"\n          with:\n            query: \"tools.query\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: getPostsCountsAll\n          description: \"Get counts of posts matching a query from full archive\"\n   \
  \       hints:\n            readOnly: true\n            idempotent: true\n          call: \"x-listening-mcp.getPostsCountsAll\"\n          with:\n            query: \"tools.query\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: getInsights28Hr\n          description: \"Get post insights for the last 28 hours\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"x-listening-mcp.getInsights28Hr\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: getInsightsHistorical\n          description: \"Get historical post insights\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"x-listening-mcp.getInsightsHistorical\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: streamPostsSearch\n          description: \"Stream posts matching filtered stream\
  \ rules in real-time\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"x-listening-mcp.streamPostsSearch\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: addSearchStreamRules\n          description: \"Add or delete rules for the filtered search stream\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"x-listening-mcp.addSearchStreamRules\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: getSearchStreamRules\n          description: \"Get current rules for the filtered search stream\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"x-listening-mcp.getSearchStreamRules\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: streamPostsFirehose\n          description: \"Stream all public\
  \ posts in real-time via the firehose\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"x-listening-mcp.streamPostsFirehose\"\n          with:\n            partition: \"tools.partition\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: streamPostsSample10\n          description: \"Stream a 10% sample of all public posts in real-time\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"x-listening-mcp.streamPostsSample10\"\n          with:\n            partition: \"tools.partition\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: getUsersByIds\n          description: \"Retrieve multiple users by their IDs\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"x-listening-mcp.getUsersByIds\"\n          with:\n            ids: \"tools.ids\"\n    \
  \      outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: getUsersByUsernames\n          description: \"Retrieve multiple users by their usernames\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"x-listening-mcp.getUsersByUsernames\"\n          with:\n            usernames: \"tools.usernames\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: getUsersMe\n          description: \"Retrieve the authenticated user's profile\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"x-listening-mcp.getUsersMe\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: getFollowers\n          description: \"Get followers of a user\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"x-listening-mcp.getFollowers\"\n      \
  \    with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: getFollowing\n          description: \"Get users that a user is following\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"x-listening-mcp.getFollowing\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: getUserTimeline\n          description: \"Get posts authored by a specific user\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"x-listening-mcp.getUserTimeline\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: getUserMentions\n          description: \"Get posts mentioning a specific user\"\n          hints:\n            readOnly: true\n        \
  \    idempotent: true\n          call: \"x-listening-mcp.getUserMentions\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
