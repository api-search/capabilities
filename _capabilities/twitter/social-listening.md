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
- get recent post counts
- stream all public posts
- get current rules for the filtered search stream
- engagement specialist
- monitor conversations, search posts, analyze trends, and extract insights.
- get users that a user is following
- compliance officer
- stream 10% sample of posts
- conducts academic or market research using x data archives.
- look up users by ids
- handles customer inquiries and issues via direct messages and replies.
- search the full archive of posts
- get counts of posts matching a query from full archive
- get post insights for last 28 hours
- retrieve users by ids
- get post insights for the last 28 hours
- full firehose stream
- getPostsCountsRecent
- social media manager
- get counts from full archive
- stream a 10% sample of all public posts in real-time
- marketing team
- social monitoring, search, trending topics, and sentiment analysis.
- retrieve the authenticated user's profile
- data analyst
- real-time data
- get 28-hour post insights
- analytics
- retrieve users by usernames
- addSearchStreamRules
- get user followers
- manage compliance jobs, data streams, and real-time compliance monitoring.
- getFollowing
- getInsightsHistorical
- searchPostsAll
- getUserMentions
- researcher
- streamPostsFirehose
- get counts of posts matching a query from last 7 days
- add or delete rules for the filtered search stream
- filtered search stream
- content
- x api
- search
- customer support
- searchPostsRecent
- getSearchStreamRules
- platform operations
- 10% sample stream
- look up users by usernames
- getInsights28Hr
- manage user relationships, direct messages, spaces, and community interactions.
- getUsersMe
- microblogging
- data engineer
- get followers
- manages user relationships, follows, and interaction strategies.
- community manager
- getFollowers
- social media
- stream posts matching filter rules
- post creation, editing, media management, and content analytics.
- retrieve multiple users by their ids
- trends
- user relationships, direct messaging, spaces, and community interaction.
- streamPostsSearch
- get counts from last 7 days
- getPostsCountsAll
- creates, schedules, and analyzes social media content across platforms.
- get posts mentioning a specific user
- ensures data handling meets regulatory and platform compliance requirements.
- add or delete stream rules
- streamPostsSample10
- search full archive of posts
- get current stream rules
- manages brand presence, campaigns, and content strategy.
- manages data pipelines, streaming ingestion, and compliance data flows.
- data compliance, deletion tracking, and regulatory event monitoring.
- advertising
- search for posts from the last 7 days
- manage stream filter rules
- builds and maintains communities through engagement and moderation.
- produces original posts, threads, and media content on x.
- search posts from last 7 days
- getUsersByUsernames
- retrieve multiple users by their usernames
- search all posts
- social listening
- content creator
- create, manage, and analyze posts, media, bookmarks, and lists.
- get followers of a user
- search recent posts
- stream posts matching filtered stream rules in real-time
- getUserTimeline
- stream all public posts in real-time via the firehose
- monitors brand mentions, sentiment, and competitive landscape.
- get historical post insights
- brand manager
- getUsersByIds
- extracts insights from social data through search, streaming, and analytics.
- streaming
- get all post counts
- get posts authored by a specific user
- get following
- get users being followed
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
