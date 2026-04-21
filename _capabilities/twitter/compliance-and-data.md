---
consumed_apis:
- x-streaming
- x-posts
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
- createComplianceJobs
- creates, schedules, and analyzes social media content across platforms.
- stream labels compliance events in real-time
- produces original posts, threads, and media content on x.
- x api
- likes compliance stream
- stream user compliance events
- manage user relationships, direct messages, spaces, and community interactions.
- data engineer
- stream post compliance events
- researcher
- create a new compliance job
- platform operations
- social media manager
- content creator
- getComplianceJobs
- microblogging
- social monitoring, search, trending topics, and sentiment analysis.
- data compliance, deletion tracking, and regulatory event monitoring.
- data management
- manages data pipelines, streaming ingestion, and compliance data flows.
- social media
- streamLikesCompliance
- stream labels compliance events
- manage compliance jobs, data streams, and real-time compliance monitoring.
- brand manager
- stream likes compliance events
- streamLabelsCompliance
- list compliance jobs
- user compliance stream
- stream user compliance events in real-time
- stream likes compliance events in real-time
- data analyst
- extracts insights from social data through search, streaming, and analytics.
- compliance
- get a compliance job by its id
- marketing team
- community manager
- manages user relationships, follows, and interaction strategies.
- getComplianceJobsById
- advertising
- post compliance stream
- monitors brand mentions, sentiment, and competitive landscape.
- conducts academic or market research using x data archives.
- labels compliance stream
- stream post compliance events in real-time
- customer support
- compliance officer
- handles customer inquiries and issues via direct messages and replies.
- real-time data
- builds and maintains communities through engagement and moderation.
- post creation, editing, media management, and content analytics.
- monitor conversations, search posts, analyze trends, and extract insights.
- ensures data handling meets regulatory and platform compliance requirements.
- user relationships, direct messaging, spaces, and community interaction.
- content
- create and list compliance jobs
- streamUsersCompliance
- streaming
- get a compliance job by id
- create, manage, and analyze posts, media, bookmarks, and lists.
- streamPostsCompliance
- engagement specialist
- manages brand presence, campaigns, and content strategy.
- get a specific compliance job
slug: compliance-and-data
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
