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
- real-time data
- searchPostsAll
- getUsersByIds
- social monitoring, search, trending topics, and sentiment analysis.
- getInsightsHistorical
- search recent posts
- community manager
- post creation, editing, media management, and content analytics.
- retrieve users by usernames
- get current stream rules
- manage stream filter rules
- getUserMentions
- conducts academic or market research using x data archives.
- stream posts matching filtered stream rules in real-time
- streaming
- monitors brand mentions, sentiment, and competitive landscape.
- retrieve the authenticated user's profile
- data analyst
- creates, schedules, and analyzes social media content across platforms.
- social media manager
- getFollowers
- data compliance, deletion tracking, and regulatory event monitoring.
- getUsersMe
- get post insights for the last 28 hours
- get posts authored by a specific user
- stream posts matching filter rules
- get followers of a user
- manages user relationships, follows, and interaction strategies.
- get counts from full archive
- add or delete rules for the filtered search stream
- content creator
- search
- search posts from last 7 days
- stream 10% sample of posts
- get counts from last 7 days
- stream a 10% sample of all public posts in real-time
- getSearchStreamRules
- engagement specialist
- produces original posts, threads, and media content on x.
- search full archive of posts
- manages data pipelines, streaming ingestion, and compliance data flows.
- stream all public posts in real-time via the firehose
- search the full archive of posts
- get following
- search for posts from the last 7 days
- stream all public posts
- retrieve users by ids
- addSearchStreamRules
- get 28-hour post insights
- brand manager
- get current rules for the filtered search stream
- researcher
- search all posts
- streamPostsFirehose
- get recent post counts
- retrieve multiple users by their usernames
- marketing team
- streamPostsSample10
- create, manage, and analyze posts, media, bookmarks, and lists.
- streamPostsSearch
- retrieve multiple users by their ids
- manages brand presence, campaigns, and content strategy.
- searchPostsRecent
- x api
- analytics
- extracts insights from social data through search, streaming, and analytics.
- getFollowing
- advertising
- getUserTimeline
- getPostsCountsRecent
- filtered search stream
- user relationships, direct messaging, spaces, and community interaction.
- builds and maintains communities through engagement and moderation.
- manage compliance jobs, data streams, and real-time compliance monitoring.
- content
- handles customer inquiries and issues via direct messages and replies.
- trends
- get post insights for last 28 hours
- get counts of posts matching a query from last 7 days
- full firehose stream
- customer support
- getUsersByUsernames
- platform operations
- add or delete stream rules
- look up users by ids
- manage user relationships, direct messages, spaces, and community interactions.
- social media
- data engineer
- 10% sample stream
- get followers
- ensures data handling meets regulatory and platform compliance requirements.
- look up users by usernames
- social listening
- get users that a user is following
- get historical post insights
- get user followers
- compliance officer
- get users being followed
- get counts of posts matching a query from full archive
- get posts mentioning a specific user
- monitor conversations, search posts, analyze trends, and extract insights.
- getPostsCountsAll
- get all post counts
- getInsights28Hr
- microblogging
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
