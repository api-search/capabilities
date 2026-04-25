---
consumed_apis:
- marketing-content
- marketing-community
description: Unified workflow for content marketers to create rich ad content, manage organization pages, track engagement, and monitor social actions -- combining content APIs and community management.
layout: capability
name: LinkedIn Content And Community
operations:
- description: Create a post.
  method: POST
  name: create-post
  path: /v1/posts
- description: Fetch multiple posts.
  method: GET
  name: get-posts
  path: /v1/posts
- description: Create a share with company mention.
  method: POST
  name: create-share
  path: /v1/shares
- description: Create an ad creative.
  method: POST
  name: create-creative
  path: /v1/creatives
- description: Search for creatives.
  method: GET
  name: search-creatives
  path: /v1/creatives
- description: Create InMail content.
  method: POST
  name: create-inmail-content
  path: /v1/inmail-contents
- description: Create a sponsored conversation.
  method: POST
  name: create-sponsored-conversation
  path: /v1/conversation-ads
- description: Get sponsored conversations.
  method: GET
  name: get-sponsored-conversations
  path: /v1/conversation-ads
- description: Initialize image upload.
  method: POST
  name: initialize-image-upload
  path: /v1/images
- description: Initialize video upload.
  method: POST
  name: initialize-video-upload
  path: /v1/videos
- description: Look up organization by ID.
  method: GET
  name: get-organization-by-id
  path: /v1/organizations/{organization_id}
- description: Retrieve follower statistics.
  method: GET
  name: get-follower-statistics
  path: /v1/follower-statistics
- description: Retrieve page statistics.
  method: GET
  name: get-page-statistics
  path: /v1/page-statistics
personas: []
provider_name: LinkedIn
provider_slug: linkedin
search_terms:
- initialize document upload
- community management
- initialize image upload.
- create a post.
- get organization by id
- integrates linkedin authentication and sharing into applications.
- create creative
- recruiting
- search creatives
- social media
- retrieve organization follower count.
- create post
- retrieve share statistics.
- initialize document upload.
- retrieve social action notifications.
- create sponsored conversation
- sales intelligence, lead management, and crm integration.
- fetch multiple posts.
- get notifications
- initialize image upload
- manages b2b ad campaigns and audience targeting on linkedin.
- posts jobs and manages candidates through ats integrations.
- initialize video upload.
- linkedin
- create share
- create a share with company mention.
- create an ad creative.
- b2b advertising, audience targeting, and campaign analytics.
- employee development tracking and content access.
- look up organization by id.
- careers
- content marketing
- data portability and advertiser transparency for dma.
- tracks employee learning activity and completions.
- create inmail content.
- get inmail content
- get follower count
- retrieve follower statistics.
- message archiving and regulatory communications governance.
- business
- authentication, sharing, and verification for consumer apps.
- professional networking
- job posting, recruiting, and applicant tracking.
- search for creatives.
- retrieve inmail content by id.
- get sponsored conversations
- get follower statistics
- create a sponsored conversation.
- get posts
- get share statistics
- create inmail content
- retrieve page statistics.
- initialize video upload
- get sponsored conversations.
- get page statistics
- marketing
- archives communications for regulatory compliance.
- uses sales navigator for lead generation and crm sync.
slug: content-and-community
tags:
- LinkedIn
- Content Marketing
- Community Management
- Social Media
tools:
- description: Create a post.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-post
- description: Fetch multiple posts.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-posts
- description: Create a share with company mention.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-share
- description: Create an ad creative.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-creative
- description: Search for creatives.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: search-creatives
- description: Create InMail content.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-inmail-content
- description: Retrieve InMail content by ID.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-inmail-content
- description: Create a sponsored conversation.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-sponsored-conversation
- description: Initialize image upload.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: initialize-image-upload
- description: Initialize video upload.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: initialize-video-upload
- description: Initialize document upload.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: initialize-document-upload
- description: Look up organization by ID.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-organization-by-id
- description: Retrieve follower statistics.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-follower-statistics
- description: Retrieve page statistics.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-page-statistics
- description: Retrieve share statistics.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-share-statistics
- description: Retrieve organization follower count.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-follower-count
- description: Retrieve social action notifications.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-notifications
---
