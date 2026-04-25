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
- get current rules for the filtered search stream
- filtered search stream
- creates, schedules, and analyzes social media content across platforms.
- researcher
- user relationships, direct messaging, spaces, and community interaction.
- social media
- manage compliance jobs, data streams, and real-time compliance monitoring.
- add or delete rules for the filtered search stream
- platform operations
- add or delete stream rules
- manage user relationships, direct messages, spaces, and community interactions.
- content creator
- search posts from last 7 days
- engagement specialist
- get user followers
- streamPostsSample10
- search all posts
- data engineer
- conducts academic or market research using x data archives.
- data compliance, deletion tracking, and regulatory event monitoring.
- get posts authored by a specific user
- retrieve users by usernames
- create, manage, and analyze posts, media, bookmarks, and lists.
- searchPostsAll
- getPostsCountsAll
- trends
- getUsersMe
- getFollowers
- get current stream rules
- get users being followed
- get following
- handles customer inquiries and issues via direct messages and replies.
- get posts mentioning a specific user
- analytics
- produces original posts, threads, and media content on x.
- community manager
- get 28-hour post insights
- extracts insights from social data through search, streaming, and analytics.
- monitors brand mentions, sentiment, and competitive landscape.
- get followers
- 10% sample stream
- get counts from full archive
- manages brand presence, campaigns, and content strategy.
- get post insights for last 28 hours
- social media manager
- searchPostsRecent
- getInsights28Hr
- get all post counts
- stream all public posts
- get post insights for the last 28 hours
- social listening
- manages user relationships, follows, and interaction strategies.
- streamPostsFirehose
- microblogging
- x api
- getSearchStreamRules
- streaming
- getUserMentions
- getUserTimeline
- real-time data
- marketing team
- retrieve the authenticated user's profile
- addSearchStreamRules
- retrieve multiple users by their usernames
- search
- get followers of a user
- stream posts matching filter rules
- getInsightsHistorical
- retrieve multiple users by their ids
- social monitoring, search, trending topics, and sentiment analysis.
- get recent post counts
- brand manager
- stream 10% sample of posts
- get counts of posts matching a query from full archive
- builds and maintains communities through engagement and moderation.
- manages data pipelines, streaming ingestion, and compliance data flows.
- look up users by usernames
- data analyst
- streamPostsSearch
- get counts from last 7 days
- compliance officer
- get historical post insights
- stream posts matching filtered stream rules in real-time
- search for posts from the last 7 days
- getUsersByUsernames
- get counts of posts matching a query from last 7 days
- customer support
- content
- manage stream filter rules
- look up users by ids
- ensures data handling meets regulatory and platform compliance requirements.
- stream a 10% sample of all public posts in real-time
- monitor conversations, search posts, analyze trends, and extract insights.
- get users that a user is following
- search recent posts
- post creation, editing, media management, and content analytics.
- getFollowing
- retrieve users by ids
- search the full archive of posts
- full firehose stream
- getUsersByIds
- advertising
- search full archive of posts
- stream all public posts in real-time via the firehose
- getPostsCountsRecent
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
