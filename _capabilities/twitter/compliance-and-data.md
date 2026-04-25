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
- data analyst
- likes compliance stream
- get a compliance job by id
- x api
- getComplianceJobs
- researcher
- compliance officer
- creates, schedules, and analyzes social media content across platforms.
- handles customer inquiries and issues via direct messages and replies.
- stream post compliance events
- user relationships, direct messaging, spaces, and community interaction.
- social media
- stream post compliance events in real-time
- manage compliance jobs, data streams, and real-time compliance monitoring.
- produces original posts, threads, and media content on x.
- getComplianceJobsById
- customer support
- stream labels compliance events
- stream likes compliance events
- streaming
- platform operations
- content
- ensures data handling meets regulatory and platform compliance requirements.
- community manager
- real-time data
- marketing team
- monitor conversations, search posts, analyze trends, and extract insights.
- manage user relationships, direct messages, spaces, and community interactions.
- streamLabelsCompliance
- stream likes compliance events in real-time
- content creator
- extracts insights from social data through search, streaming, and analytics.
- engagement specialist
- monitors brand mentions, sentiment, and competitive landscape.
- stream user compliance events
- get a specific compliance job
- manages brand presence, campaigns, and content strategy.
- streamLikesCompliance
- social media manager
- post creation, editing, media management, and content analytics.
- data engineer
- conducts academic or market research using x data archives.
- social monitoring, search, trending topics, and sentiment analysis.
- post compliance stream
- streamUsersCompliance
- createComplianceJobs
- data management
- data compliance, deletion tracking, and regulatory event monitoring.
- user compliance stream
- brand manager
- create, manage, and analyze posts, media, bookmarks, and lists.
- advertising
- stream user compliance events in real-time
- create a new compliance job
- stream labels compliance events in real-time
- manages user relationships, follows, and interaction strategies.
- list compliance jobs
- streamPostsCompliance
- get a compliance job by its id
- builds and maintains communities through engagement and moderation.
- microblogging
- manages data pipelines, streaming ingestion, and compliance data flows.
- create and list compliance jobs
- labels compliance stream
- compliance
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
