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
- real-time data
- create and list compliance jobs
- stream post compliance events
- stream likes compliance events in real-time
- marketing team
- createComplianceJobs
- customer support
- social monitoring, search, trending topics, and sentiment analysis.
- create, manage, and analyze posts, media, bookmarks, and lists.
- streamLikesCompliance
- engagement specialist
- platform operations
- compliance
- labels compliance stream
- data management
- manages brand presence, campaigns, and content strategy.
- produces original posts, threads, and media content on x.
- community manager
- manage user relationships, direct messages, spaces, and community interactions.
- post creation, editing, media management, and content analytics.
- x api
- social media
- get a specific compliance job
- manages data pipelines, streaming ingestion, and compliance data flows.
- stream user compliance events
- data engineer
- ensures data handling meets regulatory and platform compliance requirements.
- get a compliance job by its id
- getComplianceJobs
- list compliance jobs
- post compliance stream
- stream post compliance events in real-time
- extracts insights from social data through search, streaming, and analytics.
- conducts academic or market research using x data archives.
- get a compliance job by id
- advertising
- streaming
- monitors brand mentions, sentiment, and competitive landscape.
- stream likes compliance events
- data analyst
- streamUsersCompliance
- creates, schedules, and analyzes social media content across platforms.
- create a new compliance job
- compliance officer
- getComplianceJobsById
- social media manager
- user relationships, direct messaging, spaces, and community interaction.
- user compliance stream
- data compliance, deletion tracking, and regulatory event monitoring.
- likes compliance stream
- streamPostsCompliance
- builds and maintains communities through engagement and moderation.
- brand manager
- manage compliance jobs, data streams, and real-time compliance monitoring.
- content
- monitor conversations, search posts, analyze trends, and extract insights.
- handles customer inquiries and issues via direct messages and replies.
- manages user relationships, follows, and interaction strategies.
- streamLabelsCompliance
- stream labels compliance events
- content creator
- stream user compliance events in real-time
- researcher
- stream labels compliance events in real-time
- microblogging
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
