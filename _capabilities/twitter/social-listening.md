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
- get current rules for the filtered search stream
- streamPostsSearch
- search posts from last 7 days
- get post insights for the last 28 hours
- create, manage, and analyze posts, media, bookmarks, and lists.
- searchPostsRecent
- handles customer inquiries and issues via direct messages and replies.
- builds and maintains communities through engagement and moderation.
- microblogging
- search full archive of posts
- get all post counts
- extracts insights from social data through search, streaming, and analytics.
- get recent post counts
- engagement specialist
- manages data pipelines, streaming ingestion, and compliance data flows.
- retrieve the authenticated user's profile
- get counts of posts matching a query from full archive
- produces original posts, threads, and media content on x.
- get users being followed
- user relationships, direct messaging, spaces, and community interaction.
- get posts mentioning a specific user
- streaming
- get users that a user is following
- post creation, editing, media management, and content analytics.
- data engineer
- manages brand presence, campaigns, and content strategy.
- search the full archive of posts
- 10% sample stream
- get historical post insights
- streamPostsSample10
- manage stream filter rules
- real-time data
- social listening
- manage compliance jobs, data streams, and real-time compliance monitoring.
- full firehose stream
- ensures data handling meets regulatory and platform compliance requirements.
- searchPostsAll
- get 28-hour post insights
- getFollowing
- trends
- get following
- retrieve users by usernames
- get current stream rules
- platform operations
- analytics
- retrieve multiple users by their usernames
- community manager
- stream 10% sample of posts
- get user followers
- getSearchStreamRules
- getUsersByUsernames
- manages user relationships, follows, and interaction strategies.
- social monitoring, search, trending topics, and sentiment analysis.
- manage user relationships, direct messages, spaces, and community interactions.
- streamPostsFirehose
- get counts of posts matching a query from last 7 days
- get counts from last 7 days
- stream posts matching filtered stream rules in real-time
- getPostsCountsRecent
- x api
- look up users by ids
- add or delete stream rules
- customer support
- search all posts
- getInsights28Hr
- data analyst
- compliance officer
- retrieve users by ids
- getUserTimeline
- stream all public posts in real-time via the firehose
- advertising
- creates, schedules, and analyzes social media content across platforms.
- getPostsCountsAll
- get counts from full archive
- get posts authored by a specific user
- monitor conversations, search posts, analyze trends, and extract insights.
- social media
- conducts academic or market research using x data archives.
- data compliance, deletion tracking, and regulatory event monitoring.
- content
- get followers
- brand manager
- search
- stream a 10% sample of all public posts in real-time
- add or delete rules for the filtered search stream
- researcher
- getUserMentions
- monitors brand mentions, sentiment, and competitive landscape.
- getUsersMe
- search for posts from the last 7 days
- get post insights for last 28 hours
- stream posts matching filter rules
- social media manager
- addSearchStreamRules
- search recent posts
- retrieve multiple users by their ids
- getFollowers
- filtered search stream
- content creator
- get followers of a user
- stream all public posts
- marketing team
- getInsightsHistorical
- getUsersByIds
- look up users by usernames
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
