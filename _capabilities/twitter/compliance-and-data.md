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
- get a compliance job by id
- data management
- stream labels compliance events in real-time
- labels compliance stream
- manage compliance jobs, data streams, and real-time compliance monitoring.
- brand manager
- data compliance, deletion tracking, and regulatory event monitoring.
- compliance
- createComplianceJobs
- compliance officer
- create a new compliance job
- user compliance stream
- stream likes compliance events
- social media manager
- marketing team
- manage user relationships, direct messages, spaces, and community interactions.
- social monitoring, search, trending topics, and sentiment analysis.
- x api
- monitors brand mentions, sentiment, and competitive landscape.
- user relationships, direct messaging, spaces, and community interaction.
- manages brand presence, campaigns, and content strategy.
- get a compliance job by its id
- customer support
- streaming
- handles customer inquiries and issues via direct messages and replies.
- produces original posts, threads, and media content on x.
- extracts insights from social data through search, streaming, and analytics.
- stream post compliance events
- likes compliance stream
- streamLikesCompliance
- list compliance jobs
- post compliance stream
- data engineer
- manages user relationships, follows, and interaction strategies.
- get a specific compliance job
- researcher
- stream user compliance events in real-time
- streamLabelsCompliance
- stream post compliance events in real-time
- creates, schedules, and analyzes social media content across platforms.
- stream user compliance events
- stream labels compliance events
- manages data pipelines, streaming ingestion, and compliance data flows.
- create, manage, and analyze posts, media, bookmarks, and lists.
- social media
- getComplianceJobs
- advertising
- content
- streamPostsCompliance
- streamUsersCompliance
- real-time data
- conducts academic or market research using x data archives.
- ensures data handling meets regulatory and platform compliance requirements.
- create and list compliance jobs
- getComplianceJobsById
- monitor conversations, search posts, analyze trends, and extract insights.
- platform operations
- post creation, editing, media management, and content analytics.
- community manager
- content creator
- microblogging
- engagement specialist
- stream likes compliance events in real-time
- builds and maintains communities through engagement and moderation.
- data analyst
slug: compliance-and-data
source_filename: compliance-and-data.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"X Compliance and Data Management\"\n  description: \"Unified workflow for managing compliance jobs, data streams, and real-time compliance monitoring on X. Used by compliance officers, data engineers, and platform operations.\"\n  tags:\n    - X API\n    - Compliance\n    - Data Management\n    - Streaming\n  personas:\n    - compliance officers\n    - data engineers\n    - platform operations\n  created: \"2026-04-17\"\n  modified: \"2026-04-17\"\n\nbinds:\n  - namespace: env\n    keys:\n      X_API_BEARER_TOKEN: X_API_BEARER_TOKEN\n\ncapability:\n  consumes:\n    - import: x-streaming\n      location: \"./shared/streaming.yaml\"\n    - import: x-posts\n      location: \"./shared/posts.yaml\"\n\n  exposes:\n    - type: rest\n      port: 8083\n      namespace: x-compliance-api\n      resources:\n        - path: /v1/compliance/jobs\n          name: compliance-jobs\n          description: \"Create and list compliance jobs\"\n   \
  \       operations:\n            - method: POST\n              name: createComplianceJobs\n              description: \"Create a new compliance job\"\n              call: \"x-compliance-api.createComplianceJobs\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: GET\n              name: getComplianceJobs\n              description: \"List compliance jobs\"\n              call: \"x-compliance-api.getComplianceJobs\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/compliance/jobs/{id}\n          name: compliance-job\n          description: \"Get a specific compliance job\"\n          operations:\n            - method: GET\n              name: getComplianceJobsById\n              description: \"Get a compliance job by ID\"\n              call: \"x-compliance-api.getComplianceJobsById\"\n              with:\n                id: \"rest.id\"\n    \
  \          outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/compliance/streams/users\n          name: users-compliance\n          description: \"User compliance stream\"\n          operations:\n            - method: GET\n              name: streamUsersCompliance\n              description: \"Stream user compliance events\"\n              call: \"x-compliance-api.streamUsersCompliance\"\n              with:\n                partition: \"rest.partition\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/compliance/streams/posts\n          name: posts-compliance\n          description: \"Post compliance stream\"\n          operations:\n            - method: GET\n              name: streamPostsCompliance\n              description: \"Stream post compliance events\"\n              call: \"x-compliance-api.streamPostsCompliance\"\n              with:\n             \
  \   partition: \"rest.partition\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/compliance/streams/likes\n          name: likes-compliance\n          description: \"Likes compliance stream\"\n          operations:\n            - method: GET\n              name: streamLikesCompliance\n              description: \"Stream likes compliance events\"\n              call: \"x-compliance-api.streamLikesCompliance\"\n              with:\n                partition: \"rest.partition\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/compliance/streams/labels\n          name: labels-compliance\n          description: \"Labels compliance stream\"\n          operations:\n            - method: GET\n              name: streamLabelsCompliance\n              description: \"Stream labels compliance events\"\n              call: \"x-compliance-api.streamLabelsCompliance\"\
  \n              with:\n                partition: \"rest.partition\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9083\n      namespace: x-compliance-mcp\n      transport: http\n      tools:\n        - name: createComplianceJobs\n          description: \"Create a new compliance job\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"x-compliance-mcp.createComplianceJobs\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: getComplianceJobs\n          description: \"List compliance jobs\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"x-compliance-mcp.getComplianceJobs\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: getComplianceJobsById\n          description: \"Get a compliance job by its ID\"\n\
  \          hints:\n            readOnly: true\n            idempotent: true\n          call: \"x-compliance-mcp.getComplianceJobsById\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: streamUsersCompliance\n          description: \"Stream user compliance events in real-time\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"x-compliance-mcp.streamUsersCompliance\"\n          with:\n            partition: \"tools.partition\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: streamPostsCompliance\n          description: \"Stream post compliance events in real-time\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"x-compliance-mcp.streamPostsCompliance\"\n          with:\n            partition: \"tools.partition\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n        - name: streamLikesCompliance\n          description: \"Stream likes compliance events in real-time\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"x-compliance-mcp.streamLikesCompliance\"\n          with:\n            partition: \"tools.partition\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: streamLabelsCompliance\n          description: \"Stream labels compliance events in real-time\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"x-compliance-mcp.streamLabelsCompliance\"\n          with:\n            partition: \"tools.partition\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/twitter/refs/heads/main/capabilities/compliance-and-data.yaml
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
