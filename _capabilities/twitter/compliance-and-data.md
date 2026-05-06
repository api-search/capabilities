---
categories:
- compliance
consumed_apis: []
description: Unified workflow for managing compliance jobs, data streams, and real-time compliance monitoring on X. Used by compliance officers, data engineers, and platform operations.
layout: capability
name: X Compliance and Data Management
operations:
- description: Create a new compliance job
  method: POST
  name: createComplianceJobs
  path: /v1/compliance/jobs
- description: List compliance jobs
  method: GET
  name: getComplianceJobs
  path: /v1/compliance/jobs
- description: Get a compliance job by ID
  method: GET
  name: getComplianceJobsById
  path: /v1/compliance/jobs/{id}
- description: Stream user compliance events
  method: GET
  name: streamUsersCompliance
  path: /v1/compliance/streams/users
- description: Stream post compliance events
  method: GET
  name: streamPostsCompliance
  path: /v1/compliance/streams/posts
- description: Stream likes compliance events
  method: GET
  name: streamLikesCompliance
  path: /v1/compliance/streams/likes
- description: Stream labels compliance events
  method: GET
  name: streamLabelsCompliance
  path: /v1/compliance/streams/labels
personas:
- description: Ensures data handling meets regulatory and platform compliance requirements.
  id: compliance-officer
  name: Compliance Officer
- description: Manages data pipelines, streaming ingestion, and compliance data flows.
  id: data-engineer
  name: Data Engineer
provider_name: X (Twitter)
provider_slug: twitter
search_terms:
- stream post compliance events in real-time
- getComplianceJobsById
- user compliance stream
- data analyst
- compliance officer
- stream likes compliance events in real-time
- community manager
- data engineer
- produces original posts, threads, and media content on x.
- content
- create, manage, and analyze posts, media, bookmarks, and lists.
- streamUsersCompliance
- social media manager
- stream post compliance events
- marketing team
- manage compliance jobs, data streams, and real-time compliance monitoring.
- creates, schedules, and analyzes social media content across platforms.
- extracts insights from social data through search, streaming, and analytics.
- create a new compliance job
- compliance
- stream user compliance events in real-time
- user relationships, direct messaging, spaces, and community interaction.
- stream labels compliance events in real-time
- social monitoring, search, trending topics, and sentiment analysis.
- stream likes compliance events
- brand manager
- manages user relationships, follows, and interaction strategies.
- createComplianceJobs
- researcher
- get a compliance job by id
- engagement specialist
- conducts academic or market research using x data archives.
- ensures data handling meets regulatory and platform compliance requirements.
- manages data pipelines, streaming ingestion, and compliance data flows.
- streamLikesCompliance
- x api
- platform operations
- data management
- handles customer inquiries and issues via direct messages and replies.
- advertising
- microblogging
- manages brand presence, campaigns, and content strategy.
- real-time data
- stream labels compliance events
- monitors brand mentions, sentiment, and competitive landscape.
- get a specific compliance job
- streamPostsCompliance
- create and list compliance jobs
- customer support
- getComplianceJobs
- manage user relationships, direct messages, spaces, and community interactions.
- list compliance jobs
- stream user compliance events
- labels compliance stream
- social media
- streamLabelsCompliance
- streaming
- builds and maintains communities through engagement and moderation.
- content creator
- data compliance, deletion tracking, and regulatory event monitoring.
- post compliance stream
- get a compliance job by its id
- monitor conversations, search posts, analyze trends, and extract insights.
- likes compliance stream
- post creation, editing, media management, and content analytics.
slug: compliance-and-data
source_filename: compliance-and-data.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: X Compliance and Data Management\n  description: Unified workflow for managing compliance jobs, data streams, and real-time compliance monitoring on X. Used\n    by compliance officers, data engineers, and platform operations.\n  tags:\n  - X API\n  - Compliance\n  - Data Management\n  - Streaming\n  personas:\n  - compliance officers\n  - data engineers\n  - platform operations\n  created: '2026-04-17'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    X_API_BEARER_TOKEN: X_API_BEARER_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: x-streaming\n    baseUri: https://api.x.com\n    description: X API v2 streaming endpoints for real-time data access.\n    authentication:\n      type: bearer\n      token: '{{X_API_BEARER_TOKEN}}'\n    resources:\n    - name: post-streams\n      path: /2\n      description: Stream posts in real-time via firehose, sample, and filtered search.\n      operations:\n      - name:\
  \ streamPostsFirehose\n        method: GET\n        path: /tweets/firehose/stream\n        description: Stream all public posts in real-time via the firehose.\n        inputParameters:\n        - name: partition\n          in: query\n          type: integer\n          required: true\n          description: The partition number\n        - name: tweet.fields\n          in: query\n          type: string\n          required: false\n          description: Comma-separated list of tweet fields\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: streamPostsFirehoseEn\n        method: GET\n        path: /tweets/firehose/stream/lang/en\n        description: Stream all public English-language posts in real-time.\n        inputParameters:\n        - name: partition\n          in: query\n          type: integer\n          required: true\n          description: The partition number\n        - name: tweet.fields\n\
  \          in: query\n          type: string\n          required: false\n          description: Comma-separated list of tweet fields\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: streamPostsSample10\n        method: GET\n        path: /tweets/sample10/stream\n        description: Stream a 10% sample of all public posts in real-time.\n        inputParameters:\n        - name: partition\n          in: query\n          type: integer\n          required: true\n          description: The partition number\n        - name: tweet.fields\n          in: query\n          type: string\n          required: false\n          description: Comma-separated list of tweet fields\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: streamPostsSample1\n        method: GET\n        path: /tweets/sample/stream\n        description:\
  \ Stream a roughly 1% sample of all public posts in real-time.\n        inputParameters:\n        - name: tweet.fields\n          in: query\n          type: string\n          required: false\n          description: Comma-separated list of tweet fields\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: streamPostsSearch\n        method: GET\n        path: /tweets/search/stream\n        description: Stream posts matching filtered stream rules in real-time.\n        inputParameters:\n        - name: tweet.fields\n          in: query\n          type: string\n          required: false\n          description: Comma-separated list of tweet fields\n        - name: expansions\n          in: query\n          type: string\n          required: false\n          description: Comma-separated list of expansions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n    - name: stream-rules\n      path: /2\n      description: Manage filtered stream rules.\n      operations:\n      - name: addSearchStreamRules\n        method: POST\n        path: /tweets/search/stream/rules\n        description: Add or delete rules for the filtered search stream.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getSearchStreamRules\n        method: GET\n        path: /tweets/search/stream/rules\n        description: Get the current rules for the filtered search stream.\n        inputParameters:\n        - name: ids\n          in: query\n          type: string\n          required: false\n          description: Comma-separated list of rule IDs to retrieve\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: compliance-streams\n    \
  \  path: /2\n      description: Stream compliance events for users, posts, likes, and labels.\n      operations:\n      - name: streamUsersCompliance\n        method: GET\n        path: /users/compliance/stream\n        description: Stream user compliance events in real-time.\n        inputParameters:\n        - name: partition\n          in: query\n          type: integer\n          required: true\n          description: The partition number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: streamPostsCompliance\n        method: GET\n        path: /tweets/compliance/stream\n        description: Stream post compliance events in real-time.\n        inputParameters:\n        - name: partition\n          in: query\n          type: integer\n          required: true\n          description: The partition number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n       \
  \   type: object\n          value: $.\n      - name: streamLikesFirehose\n        method: GET\n        path: /likes/firehose/stream\n        description: Stream all likes in real-time via the firehose.\n        inputParameters:\n        - name: partition\n          in: query\n          type: integer\n          required: true\n          description: The partition number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: streamLikesCompliance\n        method: GET\n        path: /likes/compliance/stream\n        description: Stream likes compliance events in real-time.\n        inputParameters:\n        - name: partition\n          in: query\n          type: integer\n          required: true\n          description: The partition number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: streamLabelsCompliance\n\
  \        method: GET\n        path: /labels/compliance/stream\n        description: Stream labels compliance events in real-time.\n        inputParameters:\n        - name: partition\n          in: query\n          type: integer\n          required: true\n          description: The partition number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: x-posts\n    baseUri: https://api.x.com\n    description: X API v2 endpoints for posts (tweets) management.\n    authentication:\n      type: bearer\n      token: '{{X_API_BEARER_TOKEN}}'\n    resources:\n    - name: posts\n      path: /2\n      description: Create, retrieve, and delete posts.\n      operations:\n      - name: createPosts\n        method: POST\n        path: /tweets\n        description: Create a new post (tweet).\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        -\
  \ name: result\n          type: object\n          value: $.\n      - name: getPostsByIds\n        method: GET\n        path: /tweets\n        description: Retrieve multiple posts by their IDs.\n        inputParameters:\n        - name: ids\n          in: query\n          type: string\n          required: true\n          description: Comma-separated list of post IDs\n        - name: tweet.fields\n          in: query\n          type: string\n          required: false\n          description: Comma-separated list of tweet fields to return\n        - name: expansions\n          in: query\n          type: string\n          required: false\n          description: Comma-separated list of expansions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletePostById\n        method: DELETE\n        path: /tweets/{id}\n        description: Delete a post by its ID.\n        inputParameters:\n        - name: id\n\
  \          in: path\n          type: string\n          required: true\n          description: The ID of the post to delete\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: post-analytics\n      path: /2\n      description: Retrieve analytics and insights for posts.\n      operations:\n      - name: getPostsAnalytics\n        method: GET\n        path: /tweets/{id}/analytics\n        description: Get analytics data for a specific post.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The ID of the post\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getInsights28Hr\n        method: GET\n        path: /insights/tweets/28hr\n        description: Get post insights for the last 28 hours.\n        inputParameters:\n    \
  \    - name: tweet.fields\n          in: query\n          type: string\n          required: false\n          description: Comma-separated list of tweet fields\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getInsightsHistorical\n        method: GET\n        path: /insights/tweets/historical\n        description: Get historical post insights.\n        inputParameters:\n        - name: tweet.fields\n          in: query\n          type: string\n          required: false\n          description: Comma-separated list of tweet fields\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: post-search\n      path: /2\n      description: Search for posts using queries.\n      operations:\n      - name: searchPostsRecent\n        method: POST\n        path: /tweets/search/recent\n        description: Search for posts from\
  \ the last 7 days.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: searchPostsAll\n        method: POST\n        path: /tweets/search/all\n        description: Search the full archive of posts.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: post-counts\n      path: /2\n      description: Get counts of posts matching a query.\n      operations:\n      - name: getPostsCountsRecent\n        method: GET\n        path: /tweets/counts/recent\n        description: Get counts of posts matching a query from the last 7 days.\n        inputParameters:\n        - name: query\n          in: query\n          type: string\n          required: true\n          description: Search query for matching posts\n        - name: granularity\n          in:\
  \ query\n          type: string\n          required: false\n          description: Granularity of count results (minute, hour, day)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getPostsCountsAll\n        method: GET\n        path: /tweets/counts/all\n        description: Get counts of posts matching a query from the full archive.\n        inputParameters:\n        - name: query\n          in: query\n          type: string\n          required: true\n          description: Search query for matching posts\n        - name: granularity\n          in: query\n          type: string\n          required: false\n          description: Granularity of count results (minute, hour, day)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: timelines\n      path: /2\n      description: Retrieve user timelines and mentions.\n\
  \      operations:\n      - name: getUserTimeline\n        method: GET\n        path: /users/{id}/tweets\n        description: Get posts authored by a specific user.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The user ID\n        - name: max_results\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results (1-100)\n        - name: pagination_token\n          in: query\n          type: string\n          required: false\n          description: Token for pagination\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getUserMentions\n        method: GET\n        path: /users/{id}/mentions\n        description: Get posts mentioning a specific user.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n    \
  \      required: true\n          description: The user ID\n        - name: max_results\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results (1-100)\n        - name: pagination_token\n          in: query\n          type: string\n          required: false\n          description: Token for pagination\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getUserHomeTimeline\n        method: GET\n        path: /users/{id}/timelines/reverse_chronological\n        description: Get the authenticated user's home timeline.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The authenticated user ID\n        - name: max_results\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results (1-100)\n\
  \        - name: pagination_token\n          in: query\n          type: string\n          required: false\n          description: Token for pagination\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: post-engagement\n      path: /2\n      description: Get engagement data for posts.\n      operations:\n      - name: getPostsQuotePosts\n        method: GET\n        path: /tweets/{id}/quote_tweets\n        description: Get posts that quote a specific post.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The post ID\n        - name: max_results\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getPostsRepostedBy\n\
  \        method: GET\n        path: /tweets/{id}/retweeted_by\n        description: Get users who reposted a specific post.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The post ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getPostsLikingUsers\n        method: GET\n        path: /tweets/{id}/liking_users\n        description: Get users who liked a specific post.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The post ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: post-moderation\n      path: /2\n      description: Moderate post replies.\n      operations:\n      - name: hidePostsReply\n        method: PUT\n  \
  \      path: /tweets/{id}/hidden\n        description: Hide or unhide a reply to a post.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The reply post ID\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8083\n    namespace: x-compliance-api\n    resources:\n    - path: /v1/compliance/jobs\n      name: compliance-jobs\n      description: Create and list compliance jobs\n      operations:\n      - method: POST\n        name: createComplianceJobs\n        description: Create a new compliance job\n        call: x-compliance-api.createComplianceJobs\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: getComplianceJobs\n        description: List compliance jobs\n        call: x-compliance-api.getComplianceJobs\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/compliance/jobs/{id}\n      name: compliance-job\n      description: Get a specific compliance job\n      operations:\n      - method: GET\n        name: getComplianceJobsById\n        description: Get a compliance job by ID\n        call: x-compliance-api.getComplianceJobsById\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/compliance/streams/users\n      name: users-compliance\n      description: User compliance stream\n      operations:\n      - method: GET\n        name: streamUsersCompliance\n        description: Stream user compliance events\n        call: x-compliance-api.streamUsersCompliance\n        with:\n          partition: rest.partition\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/compliance/streams/posts\n      name: posts-compliance\n      description: Post\
  \ compliance stream\n      operations:\n      - method: GET\n        name: streamPostsCompliance\n        description: Stream post compliance events\n        call: x-compliance-api.streamPostsCompliance\n        with:\n          partition: rest.partition\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/compliance/streams/likes\n      name: likes-compliance\n      description: Likes compliance stream\n      operations:\n      - method: GET\n        name: streamLikesCompliance\n        description: Stream likes compliance events\n        call: x-compliance-api.streamLikesCompliance\n        with:\n          partition: rest.partition\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/compliance/streams/labels\n      name: labels-compliance\n      description: Labels compliance stream\n      operations:\n      - method: GET\n        name: streamLabelsCompliance\n        description: Stream labels compliance events\n\
  \        call: x-compliance-api.streamLabelsCompliance\n        with:\n          partition: rest.partition\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9083\n    namespace: x-compliance-mcp\n    transport: http\n    tools:\n    - name: createComplianceJobs\n      description: Create a new compliance job\n      hints:\n        readOnly: false\n        idempotent: false\n      call: x-compliance-mcp.createComplianceJobs\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getComplianceJobs\n      description: List compliance jobs\n      hints:\n        readOnly: true\n        idempotent: true\n      call: x-compliance-mcp.getComplianceJobs\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getComplianceJobsById\n      description: Get a compliance job by its ID\n      hints:\n        readOnly: true\n        idempotent: true\n      call: x-compliance-mcp.getComplianceJobsById\n\
  \      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: streamUsersCompliance\n      description: Stream user compliance events in real-time\n      hints:\n        readOnly: true\n        idempotent: true\n      call: x-compliance-mcp.streamUsersCompliance\n      with:\n        partition: tools.partition\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: streamPostsCompliance\n      description: Stream post compliance events in real-time\n      hints:\n        readOnly: true\n        idempotent: true\n      call: x-compliance-mcp.streamPostsCompliance\n      with:\n        partition: tools.partition\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: streamLikesCompliance\n      description: Stream likes compliance events in real-time\n      hints:\n        readOnly: true\n        idempotent: true\n      call: x-compliance-mcp.streamLikesCompliance\n      with:\n     \
  \   partition: tools.partition\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: streamLabelsCompliance\n      description: Stream labels compliance events in real-time\n      hints:\n        readOnly: true\n        idempotent: true\n      call: x-compliance-mcp.streamLabelsCompliance\n      with:\n        partition: tools.partition\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/twitter/refs/heads/main/capabilities/compliance-and-data.yaml
tags:
- X API
- Compliance
- Data Management
- Streaming
tools:
- description: Create a new compliance job
  hints:
    idempotent: false
    readOnly: false
  name: createComplianceJobs
- description: List compliance jobs
  hints:
    idempotent: true
    readOnly: true
  name: getComplianceJobs
- description: Get a compliance job by its ID
  hints:
    idempotent: true
    readOnly: true
  name: getComplianceJobsById
- description: Stream user compliance events in real-time
  hints:
    idempotent: true
    readOnly: true
  name: streamUsersCompliance
- description: Stream post compliance events in real-time
  hints:
    idempotent: true
    readOnly: true
  name: streamPostsCompliance
- description: Stream likes compliance events in real-time
  hints:
    idempotent: true
    readOnly: true
  name: streamLikesCompliance
- description: Stream labels compliance events in real-time
  hints:
    idempotent: true
    readOnly: true
  name: streamLabelsCompliance
---
