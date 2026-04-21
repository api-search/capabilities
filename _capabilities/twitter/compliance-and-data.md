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
- post creation, editing, media management, and content analytics.
- data compliance, deletion tracking, and regulatory event monitoring.
- streamUsersCompliance
- labels compliance stream
- stream labels compliance events
- platform operations
- social media
- advertising
- brand manager
- post compliance stream
- get a specific compliance job
- stream likes compliance events in real-time
- microblogging
- handles customer inquiries and issues via direct messages and replies.
- createComplianceJobs
- compliance officer
- stream post compliance events
- user relationships, direct messaging, spaces, and community interaction.
- data management
- content
- streamLikesCompliance
- ensures data handling meets regulatory and platform compliance requirements.
- stream likes compliance events
- monitors brand mentions, sentiment, and competitive landscape.
- streamPostsCompliance
- monitor conversations, search posts, analyze trends, and extract insights.
- creates, schedules, and analyzes social media content across platforms.
- manages data pipelines, streaming ingestion, and compliance data flows.
- create and list compliance jobs
- manage compliance jobs, data streams, and real-time compliance monitoring.
- content creator
- create a new compliance job
- get a compliance job by id
- likes compliance stream
- customer support
- stream labels compliance events in real-time
- community manager
- manages brand presence, campaigns, and content strategy.
- data engineer
- stream post compliance events in real-time
- getComplianceJobs
- create, manage, and analyze posts, media, bookmarks, and lists.
- compliance
- marketing team
- x api
- streamLabelsCompliance
- engagement specialist
- produces original posts, threads, and media content on x.
- stream user compliance events in real-time
- stream user compliance events
- streaming
- manages user relationships, follows, and interaction strategies.
- real-time data
- extracts insights from social data through search, streaming, and analytics.
- user compliance stream
- conducts academic or market research using x data archives.
- data analyst
- get a compliance job by its id
- builds and maintains communities through engagement and moderation.
- getComplianceJobsById
- social monitoring, search, trending topics, and sentiment analysis.
- researcher
- manage user relationships, direct messages, spaces, and community interactions.
- social media manager
- list compliance jobs
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
