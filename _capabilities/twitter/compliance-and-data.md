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
- compliance officer
- create and list compliance jobs
- get a specific compliance job
- creates, schedules, and analyzes social media content across platforms.
- post creation, editing, media management, and content analytics.
- brand manager
- getComplianceJobsById
- extracts insights from social data through search, streaming, and analytics.
- manages user relationships, follows, and interaction strategies.
- post compliance stream
- getComplianceJobs
- stream user compliance events
- customer support
- labels compliance stream
- content
- social media
- stream likes compliance events
- platform operations
- stream labels compliance events
- createComplianceJobs
- streamUsersCompliance
- manages data pipelines, streaming ingestion, and compliance data flows.
- stream likes compliance events in real-time
- researcher
- data management
- get a compliance job by its id
- advertising
- streaming
- streamLikesCompliance
- stream post compliance events
- user relationships, direct messaging, spaces, and community interaction.
- streamLabelsCompliance
- manage compliance jobs, data streams, and real-time compliance monitoring.
- content creator
- streamPostsCompliance
- user compliance stream
- create, manage, and analyze posts, media, bookmarks, and lists.
- monitors brand mentions, sentiment, and competitive landscape.
- marketing team
- handles customer inquiries and issues via direct messages and replies.
- ensures data handling meets regulatory and platform compliance requirements.
- conducts academic or market research using x data archives.
- data compliance, deletion tracking, and regulatory event monitoring.
- list compliance jobs
- manages brand presence, campaigns, and content strategy.
- stream post compliance events in real-time
- social media manager
- x api
- microblogging
- engagement specialist
- stream user compliance events in real-time
- produces original posts, threads, and media content on x.
- data engineer
- get a compliance job by id
- monitor conversations, search posts, analyze trends, and extract insights.
- social monitoring, search, trending topics, and sentiment analysis.
- manage user relationships, direct messages, spaces, and community interactions.
- create a new compliance job
- compliance
- stream labels compliance events in real-time
- likes compliance stream
- community manager
- real-time data
- builds and maintains communities through engagement and moderation.
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
