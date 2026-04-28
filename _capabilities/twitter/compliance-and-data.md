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
- labels compliance stream
- streamLikesCompliance
- get a compliance job by id
- content
- post creation, editing, media management, and content analytics.
- create and list compliance jobs
- brand manager
- data engineer
- manage user relationships, direct messages, spaces, and community interactions.
- social monitoring, search, trending topics, and sentiment analysis.
- create, manage, and analyze posts, media, bookmarks, and lists.
- manages brand presence, campaigns, and content strategy.
- data compliance, deletion tracking, and regulatory event monitoring.
- x api
- streamLabelsCompliance
- handles customer inquiries and issues via direct messages and replies.
- getComplianceJobsById
- researcher
- stream labels compliance events
- monitors brand mentions, sentiment, and competitive landscape.
- createComplianceJobs
- real-time data
- streamPostsCompliance
- builds and maintains communities through engagement and moderation.
- customer support
- manage compliance jobs, data streams, and real-time compliance monitoring.
- compliance officer
- data analyst
- stream user compliance events in real-time
- compliance
- microblogging
- stream post compliance events
- stream likes compliance events
- social media manager
- ensures data handling meets regulatory and platform compliance requirements.
- get a specific compliance job
- advertising
- getComplianceJobs
- likes compliance stream
- stream likes compliance events in real-time
- creates, schedules, and analyzes social media content across platforms.
- get a compliance job by its id
- extracts insights from social data through search, streaming, and analytics.
- stream labels compliance events in real-time
- stream user compliance events
- user compliance stream
- content creator
- engagement specialist
- manages data pipelines, streaming ingestion, and compliance data flows.
- stream post compliance events in real-time
- platform operations
- streamUsersCompliance
- produces original posts, threads, and media content on x.
- post compliance stream
- data management
- community manager
- marketing team
- user relationships, direct messaging, spaces, and community interaction.
- monitor conversations, search posts, analyze trends, and extract insights.
- create a new compliance job
- list compliance jobs
- social media
- streaming
- conducts academic or market research using x data archives.
- manages user relationships, follows, and interaction strategies.
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
