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
- user relationships, direct messaging, spaces, and community interaction.
- list compliance jobs
- stream user compliance events
- data management
- brand manager
- streaming
- create a new compliance job
- createComplianceJobs
- social media manager
- handles customer inquiries and issues via direct messages and replies.
- streamLikesCompliance
- data compliance, deletion tracking, and regulatory event monitoring.
- real-time data
- social monitoring, search, trending topics, and sentiment analysis.
- researcher
- customer support
- extracts insights from social data through search, streaming, and analytics.
- monitors brand mentions, sentiment, and competitive landscape.
- advertising
- labels compliance stream
- likes compliance stream
- stream labels compliance events
- get a compliance job by its id
- get a specific compliance job
- manages data pipelines, streaming ingestion, and compliance data flows.
- data analyst
- creates, schedules, and analyzes social media content across platforms.
- microblogging
- stream post compliance events in real-time
- manage user relationships, direct messages, spaces, and community interactions.
- get a compliance job by id
- manage compliance jobs, data streams, and real-time compliance monitoring.
- x api
- produces original posts, threads, and media content on x.
- getComplianceJobs
- builds and maintains communities through engagement and moderation.
- stream labels compliance events in real-time
- conducts academic or market research using x data archives.
- marketing team
- getComplianceJobsById
- data engineer
- stream likes compliance events in real-time
- manages user relationships, follows, and interaction strategies.
- manages brand presence, campaigns, and content strategy.
- create and list compliance jobs
- stream user compliance events in real-time
- content creator
- monitor conversations, search posts, analyze trends, and extract insights.
- streamPostsCompliance
- compliance
- user compliance stream
- streamUsersCompliance
- ensures data handling meets regulatory and platform compliance requirements.
- social media
- stream post compliance events
- engagement specialist
- community manager
- compliance officer
- streamLabelsCompliance
- post compliance stream
- stream likes compliance events
- content
- create, manage, and analyze posts, media, bookmarks, and lists.
- platform operations
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
