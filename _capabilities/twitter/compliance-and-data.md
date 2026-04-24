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
- data management
- researcher
- get a compliance job by id
- conducts academic or market research using x data archives.
- getComplianceJobs
- compliance officer
- user relationships, direct messaging, spaces, and community interaction.
- streamUsersCompliance
- platform operations
- real-time data
- likes compliance stream
- content creator
- data analyst
- advertising
- streamLabelsCompliance
- content
- get a compliance job by its id
- stream likes compliance events in real-time
- social monitoring, search, trending topics, and sentiment analysis.
- post compliance stream
- getComplianceJobsById
- customer support
- data engineer
- produces original posts, threads, and media content on x.
- manage user relationships, direct messages, spaces, and community interactions.
- extracts insights from social data through search, streaming, and analytics.
- stream likes compliance events
- stream labels compliance events
- manages user relationships, follows, and interaction strategies.
- data compliance, deletion tracking, and regulatory event monitoring.
- microblogging
- post creation, editing, media management, and content analytics.
- builds and maintains communities through engagement and moderation.
- monitor conversations, search posts, analyze trends, and extract insights.
- stream post compliance events
- compliance
- create a new compliance job
- stream labels compliance events in real-time
- labels compliance stream
- manage compliance jobs, data streams, and real-time compliance monitoring.
- create and list compliance jobs
- social media
- streaming
- ensures data handling meets regulatory and platform compliance requirements.
- manages data pipelines, streaming ingestion, and compliance data flows.
- marketing team
- x api
- streamPostsCompliance
- community manager
- user compliance stream
- monitors brand mentions, sentiment, and competitive landscape.
- manages brand presence, campaigns, and content strategy.
- creates, schedules, and analyzes social media content across platforms.
- social media manager
- stream user compliance events in real-time
- stream post compliance events in real-time
- stream user compliance events
- create, manage, and analyze posts, media, bookmarks, and lists.
- get a specific compliance job
- engagement specialist
- brand manager
- streamLikesCompliance
- list compliance jobs
- createComplianceJobs
- handles customer inquiries and issues via direct messages and replies.
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
