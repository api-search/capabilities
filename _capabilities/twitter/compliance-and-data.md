---
categories:
- compliance
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
- creates, schedules, and analyzes social media content across platforms.
- stream user compliance events in real-time
- create and list compliance jobs
- streamPostsCompliance
- post creation, editing, media management, and content analytics.
- get a compliance job by its id
- manage compliance jobs, data streams, and real-time compliance monitoring.
- streaming
- user compliance stream
- compliance
- get a specific compliance job
- stream likes compliance events in real-time
- advertising
- real-time data
- handles customer inquiries and issues via direct messages and replies.
- create a new compliance job
- marketing team
- platform operations
- likes compliance stream
- stream post compliance events
- engagement specialist
- stream labels compliance events in real-time
- compliance officer
- createComplianceJobs
- getComplianceJobs
- post compliance stream
- produces original posts, threads, and media content on x.
- monitor conversations, search posts, analyze trends, and extract insights.
- data engineer
- data compliance, deletion tracking, and regulatory event monitoring.
- customer support
- data analyst
- getComplianceJobsById
- x api
- ensures data handling meets regulatory and platform compliance requirements.
- create, manage, and analyze posts, media, bookmarks, and lists.
- manages brand presence, campaigns, and content strategy.
- stream likes compliance events
- microblogging
- content
- streamLabelsCompliance
- stream labels compliance events
- streamLikesCompliance
- stream post compliance events in real-time
- social media manager
- manages user relationships, follows, and interaction strategies.
- monitors brand mentions, sentiment, and competitive landscape.
- get a compliance job by id
- labels compliance stream
- list compliance jobs
- user relationships, direct messaging, spaces, and community interaction.
- streamUsersCompliance
- builds and maintains communities through engagement and moderation.
- community manager
- extracts insights from social data through search, streaming, and analytics.
- conducts academic or market research using x data archives.
- manage user relationships, direct messages, spaces, and community interactions.
- social monitoring, search, trending topics, and sentiment analysis.
- stream user compliance events
- researcher
- data management
- social media
- content creator
- manages data pipelines, streaming ingestion, and compliance data flows.
- brand manager
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
