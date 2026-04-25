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
- social media manager
- brand manager
- engagement specialist
- stream likes compliance events in real-time
- monitors brand mentions, sentiment, and competitive landscape.
- researcher
- streamLabelsCompliance
- ensures data handling meets regulatory and platform compliance requirements.
- get a compliance job by its id
- compliance
- conducts academic or market research using x data archives.
- stream labels compliance events in real-time
- data compliance, deletion tracking, and regulatory event monitoring.
- platform operations
- stream user compliance events
- create, manage, and analyze posts, media, bookmarks, and lists.
- create and list compliance jobs
- streamLikesCompliance
- stream post compliance events
- stream user compliance events in real-time
- marketing team
- extracts insights from social data through search, streaming, and analytics.
- community manager
- handles customer inquiries and issues via direct messages and replies.
- manages data pipelines, streaming ingestion, and compliance data flows.
- likes compliance stream
- user relationships, direct messaging, spaces, and community interaction.
- content
- real-time data
- streamPostsCompliance
- get a specific compliance job
- stream post compliance events in real-time
- post compliance stream
- content creator
- getComplianceJobsById
- user compliance stream
- stream labels compliance events
- manage compliance jobs, data streams, and real-time compliance monitoring.
- data engineer
- stream likes compliance events
- social monitoring, search, trending topics, and sentiment analysis.
- createComplianceJobs
- x api
- manages brand presence, campaigns, and content strategy.
- getComplianceJobs
- streamUsersCompliance
- create a new compliance job
- data management
- get a compliance job by id
- list compliance jobs
- labels compliance stream
- compliance officer
- advertising
- data analyst
- customer support
- builds and maintains communities through engagement and moderation.
- manages user relationships, follows, and interaction strategies.
- post creation, editing, media management, and content analytics.
- manage user relationships, direct messages, spaces, and community interactions.
- creates, schedules, and analyzes social media content across platforms.
- monitor conversations, search posts, analyze trends, and extract insights.
- microblogging
- social media
- produces original posts, threads, and media content on x.
- streaming
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
