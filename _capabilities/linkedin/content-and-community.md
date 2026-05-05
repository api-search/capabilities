---
categories: []
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
- look up organization by id.
- professional networking
- create an ad creative.
- search for creatives.
- initialize video upload.
- create a share with company mention.
- authentication, sharing, and verification for consumer apps.
- create inmail content.
- get page statistics
- content marketing
- retrieve social action notifications.
- archives communications for regulatory compliance.
- retrieve follower statistics.
- sales intelligence, lead management, and crm integration.
- data portability and advertiser transparency for dma.
- marketing
- get sponsored conversations
- linkedin
- community management
- employee development tracking and content access.
- get inmail content
- search creatives
- create post
- get posts
- fetch multiple posts.
- posts jobs and manages candidates through ats integrations.
- get sponsored conversations.
- create inmail content
- retrieve page statistics.
- get share statistics
- b2b advertising, audience targeting, and campaign analytics.
- initialize document upload
- create a post.
- initialize image upload
- careers
- initialize video upload
- social media
- retrieve share statistics.
- create creative
- initialize document upload.
- manages b2b ad campaigns and audience targeting on linkedin.
- job posting, recruiting, and applicant tracking.
- message archiving and regulatory communications governance.
- retrieve organization follower count.
- initialize image upload.
- get follower statistics
- recruiting
- get organization by id
- uses sales navigator for lead generation and crm sync.
- get follower count
- create sponsored conversation
- retrieve inmail content by id.
- tracks employee learning activity and completions.
- get notifications
- create a sponsored conversation.
- business
- integrates linkedin authentication and sharing into applications.
- create share
slug: content-and-community
source_filename: content-and-community.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"LinkedIn Content And Community\"\n  description: \"Unified workflow for content marketers to create rich ad content, manage organization pages, track engagement, and monitor social actions -- combining content APIs and community management.\"\n  tags:\n    - LinkedIn\n    - Content Marketing\n    - Community Management\n    - Social Media\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      LINKEDIN_OAUTH_TOKEN: LINKEDIN_OAUTH_TOKEN\n\ncapability:\n  consumes:\n    - import: marketing-content\n      location: ./shared/marketing-content.yaml\n    - import: marketing-community\n      location: ./shared/marketing-community.yaml\n\n  exposes:\n    - type: rest\n      port: 8081\n      namespace: content-community-api\n      description: \"Unified REST API for LinkedIn content creation and community management.\"\n      resources:\n        - path: /v1/posts\n          name: posts\n \
  \         operations:\n            - method: POST\n              name: create-post\n              description: \"Create a post.\"\n              call: \"marketing-content.create-post\"\n            - method: GET\n              name: get-posts\n              description: \"Fetch multiple posts.\"\n              call: \"marketing-content.get-posts\"\n        - path: /v1/shares\n          name: shares\n          operations:\n            - method: POST\n              name: create-share\n              description: \"Create a share with company mention.\"\n              call: \"marketing-community.create-share\"\n        - path: /v1/creatives\n          name: creatives\n          operations:\n            - method: POST\n              name: create-creative\n              description: \"Create an ad creative.\"\n              call: \"marketing-content.create-creative\"\n            - method: GET\n              name: search-creatives\n              description: \"Search for creatives.\"\n     \
  \         call: \"marketing-content.search-creatives\"\n        - path: /v1/inmail-contents\n          name: inmail-contents\n          operations:\n            - method: POST\n              name: create-inmail-content\n              description: \"Create InMail content.\"\n              call: \"marketing-content.create-inmail-content\"\n        - path: /v1/conversation-ads\n          name: conversation-ads\n          operations:\n            - method: POST\n              name: create-sponsored-conversation\n              description: \"Create a sponsored conversation.\"\n              call: \"marketing-content.create-sponsored-conversation\"\n            - method: GET\n              name: get-sponsored-conversations\n              description: \"Get sponsored conversations.\"\n              call: \"marketing-content.get-sponsored-conversations\"\n        - path: /v1/images\n          name: images\n          operations:\n            - method: POST\n              name: initialize-image-upload\n\
  \              description: \"Initialize image upload.\"\n              call: \"marketing-content.initialize-image-upload\"\n        - path: /v1/videos\n          name: videos\n          operations:\n            - method: POST\n              name: initialize-video-upload\n              description: \"Initialize video upload.\"\n              call: \"marketing-content.initialize-video-upload\"\n        - path: /v1/organizations/{organization_id}\n          name: organization-by-id\n          operations:\n            - method: GET\n              name: get-organization-by-id\n              description: \"Look up organization by ID.\"\n              call: \"marketing-community.get-organization-by-id\"\n        - path: /v1/follower-statistics\n          name: follower-statistics\n          operations:\n            - method: GET\n              name: get-follower-statistics\n              description: \"Retrieve follower statistics.\"\n              call: \"marketing-community.get-follower-statistics\"\
  \n        - path: /v1/page-statistics\n          name: page-statistics\n          operations:\n            - method: GET\n              name: get-page-statistics\n              description: \"Retrieve page statistics.\"\n              call: \"marketing-community.get-page-statistics\"\n\n    - type: mcp\n      port: 9091\n      namespace: content-community-mcp\n      transport: http\n      description: \"MCP server for AI-assisted LinkedIn content and community management.\"\n      tools:\n        - name: create-post\n          description: \"Create a post.\"\n          hints: { readOnly: false, destructive: false, idempotent: false }\n          call: \"marketing-content.create-post\"\n        - name: get-posts\n          description: \"Fetch multiple posts.\"\n          hints: { readOnly: true, destructive: false, idempotent: true }\n          call: \"marketing-content.get-posts\"\n        - name: create-share\n          description: \"Create a share with company mention.\"\n         \
  \ hints: { readOnly: false, destructive: false, idempotent: false }\n          call: \"marketing-community.create-share\"\n        - name: create-creative\n          description: \"Create an ad creative.\"\n          hints: { readOnly: false, destructive: false, idempotent: false }\n          call: \"marketing-content.create-creative\"\n        - name: search-creatives\n          description: \"Search for creatives.\"\n          hints: { readOnly: true, destructive: false, idempotent: true }\n          call: \"marketing-content.search-creatives\"\n        - name: create-inmail-content\n          description: \"Create InMail content.\"\n          hints: { readOnly: false, destructive: false, idempotent: false }\n          call: \"marketing-content.create-inmail-content\"\n        - name: get-inmail-content\n          description: \"Retrieve InMail content by ID.\"\n          hints: { readOnly: true, destructive: false, idempotent: true }\n          call: \"marketing-content.get-inmail-content\"\
  \n        - name: create-sponsored-conversation\n          description: \"Create a sponsored conversation.\"\n          hints: { readOnly: false, destructive: false, idempotent: false }\n          call: \"marketing-content.create-sponsored-conversation\"\n        - name: initialize-image-upload\n          description: \"Initialize image upload.\"\n          hints: { readOnly: false, destructive: false, idempotent: false }\n          call: \"marketing-content.initialize-image-upload\"\n        - name: initialize-video-upload\n          description: \"Initialize video upload.\"\n          hints: { readOnly: false, destructive: false, idempotent: false }\n          call: \"marketing-content.initialize-video-upload\"\n        - name: initialize-document-upload\n          description: \"Initialize document upload.\"\n          hints: { readOnly: false, destructive: false, idempotent: false }\n          call: \"marketing-content.initialize-document-upload\"\n        - name: get-organization-by-id\n\
  \          description: \"Look up organization by ID.\"\n          hints: { readOnly: true, destructive: false, idempotent: true }\n          call: \"marketing-community.get-organization-by-id\"\n        - name: get-follower-statistics\n          description: \"Retrieve follower statistics.\"\n          hints: { readOnly: true, destructive: false, idempotent: true }\n          call: \"marketing-community.get-follower-statistics\"\n        - name: get-page-statistics\n          description: \"Retrieve page statistics.\"\n          hints: { readOnly: true, destructive: false, idempotent: true }\n          call: \"marketing-community.get-page-statistics\"\n        - name: get-share-statistics\n          description: \"Retrieve share statistics.\"\n          hints: { readOnly: true, destructive: false, idempotent: true }\n          call: \"marketing-community.get-share-statistics\"\n        - name: get-follower-count\n          description: \"Retrieve organization follower count.\"\n     \
  \     hints: { readOnly: true, destructive: false, idempotent: true }\n          call: \"marketing-community.get-follower-count\"\n        - name: get-notifications\n          description: \"Retrieve social action notifications.\"\n          hints: { readOnly: true, destructive: false, idempotent: true }\n          call: \"marketing-community.get-notifications\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/linkedin/refs/heads/main/capabilities/content-and-community.yaml
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
