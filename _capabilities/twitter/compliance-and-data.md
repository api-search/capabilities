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
- extracts insights from social data through search, streaming, and analytics.
- marketing team
- stream likes compliance events
- list compliance jobs
- create, manage, and analyze posts, media, bookmarks, and lists.
- post compliance stream
- get a specific compliance job
- streamUsersCompliance
- social media manager
- social media
- manage compliance jobs, data streams, and real-time compliance monitoring.
- builds and maintains communities through engagement and moderation.
- user compliance stream
- data management
- getComplianceJobsById
- conducts academic or market research using x data archives.
- produces original posts, threads, and media content on x.
- post creation, editing, media management, and content analytics.
- stream post compliance events in real-time
- real-time data
- content
- manages user relationships, follows, and interaction strategies.
- streamLikesCompliance
- stream user compliance events in real-time
- community manager
- create and list compliance jobs
- microblogging
- advertising
- stream likes compliance events in real-time
- create a new compliance job
- manages data pipelines, streaming ingestion, and compliance data flows.
- stream labels compliance events
- data compliance, deletion tracking, and regulatory event monitoring.
- createComplianceJobs
- ensures data handling meets regulatory and platform compliance requirements.
- getComplianceJobs
- data analyst
- data engineer
- compliance
- manage user relationships, direct messages, spaces, and community interactions.
- x api
- streaming
- platform operations
- streamPostsCompliance
- manages brand presence, campaigns, and content strategy.
- handles customer inquiries and issues via direct messages and replies.
- user relationships, direct messaging, spaces, and community interaction.
- brand manager
- engagement specialist
- labels compliance stream
- content creator
- monitors brand mentions, sentiment, and competitive landscape.
- stream post compliance events
- get a compliance job by its id
- monitor conversations, search posts, analyze trends, and extract insights.
- researcher
- customer support
- stream labels compliance events in real-time
- creates, schedules, and analyzes social media content across platforms.
- social monitoring, search, trending topics, and sentiment analysis.
- likes compliance stream
- get a compliance job by id
- streamLabelsCompliance
- stream user compliance events
- compliance officer
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
