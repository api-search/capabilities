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
- streamLabelsCompliance
- manage user relationships, direct messages, spaces, and community interactions.
- microblogging
- real-time data
- data engineer
- stream likes compliance events
- manages user relationships, follows, and interaction strategies.
- content creator
- data management
- community manager
- social media
- stream labels compliance events in real-time
- engagement specialist
- manage compliance jobs, data streams, and real-time compliance monitoring.
- post creation, editing, media management, and content analytics.
- monitor conversations, search posts, analyze trends, and extract insights.
- get a compliance job by its id
- stream user compliance events in real-time
- streamPostsCompliance
- create, manage, and analyze posts, media, bookmarks, and lists.
- compliance officer
- user relationships, direct messaging, spaces, and community interaction.
- researcher
- conducts academic or market research using x data archives.
- labels compliance stream
- streamUsersCompliance
- compliance
- get a compliance job by id
- creates, schedules, and analyzes social media content across platforms.
- get a specific compliance job
- user compliance stream
- monitors brand mentions, sentiment, and competitive landscape.
- stream post compliance events in real-time
- ensures data handling meets regulatory and platform compliance requirements.
- stream user compliance events
- handles customer inquiries and issues via direct messages and replies.
- brand manager
- post compliance stream
- stream post compliance events
- manages brand presence, campaigns, and content strategy.
- manages data pipelines, streaming ingestion, and compliance data flows.
- data compliance, deletion tracking, and regulatory event monitoring.
- list compliance jobs
- getComplianceJobsById
- extracts insights from social data through search, streaming, and analytics.
- advertising
- streaming
- streamLikesCompliance
- createComplianceJobs
- builds and maintains communities through engagement and moderation.
- social media manager
- produces original posts, threads, and media content on x.
- content
- getComplianceJobs
- x api
- stream likes compliance events in real-time
- create a new compliance job
- likes compliance stream
- stream labels compliance events
- customer support
- platform operations
- create and list compliance jobs
- marketing team
- social monitoring, search, trending topics, and sentiment analysis.
- data analyst
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
