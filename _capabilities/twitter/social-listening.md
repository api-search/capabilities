---
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
- get post insights for the last 28 hours
- engagement specialist
- researcher
- filtered search stream
- search recent posts
- retrieve the authenticated user's profile
- add or delete stream rules
- data compliance, deletion tracking, and regulatory event monitoring.
- get post insights for last 28 hours
- create, manage, and analyze posts, media, bookmarks, and lists.
- getFollowing
- getUsersMe
- getUserMentions
- manages data pipelines, streaming ingestion, and compliance data flows.
- search all posts
- trends
- getSearchStreamRules
- stream posts matching filtered stream rules in real-time
- stream a 10% sample of all public posts in real-time
- data engineer
- get counts of posts matching a query from full archive
- manages brand presence, campaigns, and content strategy.
- x api
- retrieve users by usernames
- searchPostsRecent
- getUserTimeline
- get recent post counts
- monitor conversations, search posts, analyze trends, and extract insights.
- microblogging
- produces original posts, threads, and media content on x.
- streaming
- brand manager
- get users being followed
- search for posts from the last 7 days
- getFollowers
- stream all public posts
- getInsightsHistorical
- search
- get counts from last 7 days
- get 28-hour post insights
- platform operations
- get users that a user is following
- real-time data
- get following
- manage compliance jobs, data streams, and real-time compliance monitoring.
- advertising
- get followers
- full firehose stream
- streamPostsSearch
- manage user relationships, direct messages, spaces, and community interactions.
- stream posts matching filter rules
- getInsights28Hr
- retrieve multiple users by their ids
- getUsersByIds
- streamPostsSample10
- social media
- stream all public posts in real-time via the firehose
- get posts mentioning a specific user
- get counts from full archive
- streamPostsFirehose
- social listening
- 10% sample stream
- search full archive of posts
- get current rules for the filtered search stream
- get counts of posts matching a query from last 7 days
- marketing team
- searchPostsAll
- community manager
- retrieve multiple users by their usernames
- content creator
- look up users by usernames
- get current stream rules
- get user followers
- add or delete rules for the filtered search stream
- data analyst
- customer support
- builds and maintains communities through engagement and moderation.
- analytics
- creates, schedules, and analyzes social media content across platforms.
- retrieve users by ids
- manages user relationships, follows, and interaction strategies.
- social media manager
- monitors brand mentions, sentiment, and competitive landscape.
- get historical post insights
- ensures data handling meets regulatory and platform compliance requirements.
- get all post counts
- getPostsCountsRecent
- search the full archive of posts
- conducts academic or market research using x data archives.
- handles customer inquiries and issues via direct messages and replies.
- extracts insights from social data through search, streaming, and analytics.
- user relationships, direct messaging, spaces, and community interaction.
- content
- search posts from last 7 days
- get followers of a user
- getUsersByUsernames
- social monitoring, search, trending topics, and sentiment analysis.
- addSearchStreamRules
- stream 10% sample of posts
- look up users by ids
- compliance officer
- post creation, editing, media management, and content analytics.
- getPostsCountsAll
- manage stream filter rules
- get posts authored by a specific user
slug: social-listening
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
