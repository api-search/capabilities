---
categories: []
consumed_apis: []
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
- tracks employee learning activity and completions.
- social media
- create an ad creative.
- initialize document upload
- initialize image upload.
- retrieve follower statistics.
- retrieve share statistics.
- retrieve inmail content by id.
- initialize document upload.
- create a share with company mention.
- get page statistics
- uses sales navigator for lead generation and crm sync.
- create inmail content.
- create sponsored conversation
- look up organization by id.
- get inmail content
- retrieve social action notifications.
- get follower statistics
- professional networking
- community management
- get notifications
- get sponsored conversations.
- integrates linkedin authentication and sharing into applications.
- create inmail content
- linkedin
- create a sponsored conversation.
- create post
- employee development tracking and content access.
- business
- search creatives
- job posting, recruiting, and applicant tracking.
- data portability and advertiser transparency for dma.
- retrieve page statistics.
- sales intelligence, lead management, and crm integration.
- content marketing
- create a post.
- message archiving and regulatory communications governance.
- create creative
- recruiting
- archives communications for regulatory compliance.
- initialize video upload.
- posts jobs and manages candidates through ats integrations.
- initialize video upload
- get posts
- careers
- retrieve organization follower count.
- b2b advertising, audience targeting, and campaign analytics.
- fetch multiple posts.
- marketing
- create share
- search for creatives.
- get sponsored conversations
- initialize image upload
- manages b2b ad campaigns and audience targeting on linkedin.
- authentication, sharing, and verification for consumer apps.
- get organization by id
- get follower count
- get share statistics
slug: content-and-community
source_filename: content-and-community.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: LinkedIn Content And Community\n  description: Unified workflow for content marketers to create rich ad content, manage organization pages, track engagement,\n    and monitor social actions -- combining content APIs and community management.\n  tags:\n  - LinkedIn\n  - Content Marketing\n  - Community Management\n  - Social Media\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    LINKEDIN_OAUTH_TOKEN: LINKEDIN_OAUTH_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: marketing-content\n    baseUri: https://api.linkedin.com\n    description: LinkedIn Content APIs for rich content management.\n    authentication:\n      type: bearer\n      token: '{{LINKEDIN_OAUTH_TOKEN}}'\n    resources:\n    - name: inmail-contents\n      path: /rest/inMailContents\n      description: InMail content management.\n      operations:\n      - name: create-inmail-content\n        method: POST\n        description:\
  \ Create InMail content.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: batch-get-inmail-content\n        method: GET\n        description: Batch retrieve InMail content.\n        inputParameters:\n        - name: ids\n          in: query\n          type: string\n          required: false\n          description: InMail content IDs\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: send-test-inmail\n        method: POST\n        description: Send a test InMail.\n        inputParameters:\n        - name: action\n          in: query\n          type: string\n          required: false\n          description: Action type\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: inmail-content-by-id\n      path: /rest/inMailContents/{adInMailContentId}\n\
  \      description: Individual InMail content operations.\n      operations:\n      - name: get-inmail-content\n        method: GET\n        description: Retrieve InMail content by ID.\n        inputParameters:\n        - name: adInMailContentId\n          in: path\n          type: string\n          required: true\n          description: InMail content ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-inmail-content\n        method: POST\n        description: Update InMail content.\n        inputParameters:\n        - name: adInMailContentId\n          in: path\n          type: string\n          required: true\n          description: InMail content ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: images\n      path: /images\n      description: Image upload management.\n      operations:\n    \
  \  - name: initialize-image-upload\n        method: POST\n        description: Initialize image upload.\n        inputParameters:\n        - name: action\n          in: query\n          type: string\n          required: false\n          description: Action type\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: videos\n      path: /videos\n      description: Video upload management.\n      operations:\n      - name: initialize-video-upload\n        method: POST\n        description: Initialize video upload.\n        inputParameters:\n        - name: action\n          in: query\n          type: string\n          required: false\n          description: Action type\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: posts\n      path: /posts\n      description: Post management.\n      operations:\n      - name: create-post\n\
  \        method: POST\n        description: Create document or content post.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-posts\n        method: GET\n        description: Fetch multiple posts.\n        inputParameters:\n        - name: ids\n          in: query\n          type: string\n          required: false\n          description: Post IDs\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: creatives\n      path: /creatives\n      description: Creative management.\n      operations:\n      - name: create-creative\n        method: POST\n        description: Create a dynamic spotlight or other ad creative.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: search-creatives\n        method: GET\n        description:\
  \ Search for creatives.\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: false\n          description: Query type\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: conversation-ads\n      path: /conversationAds\n      description: Conversation ad management.\n      operations:\n      - name: create-sponsored-conversation\n        method: POST\n        description: Create a sponsored conversation.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-sponsored-conversations\n        method: GET\n        description: Get multiple sponsored conversations.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: documents\n      path: /documents\n      description: Document\
  \ upload management.\n      operations:\n      - name: initialize-document-upload\n        method: POST\n        description: Initialize document upload.\n        inputParameters:\n        - name: action\n          in: query\n          type: string\n          required: false\n          description: Action type\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: marketing-community\n    baseUri: https://api.linkedin.com\n    description: LinkedIn Community Management API.\n    authentication:\n      type: bearer\n      token: '{{LINKEDIN_OAUTH_TOKEN}}'\n    resources:\n    - name: shares\n      path: /shares\n      description: Create and manage shares.\n      operations:\n      - name: create-share\n        method: POST\n        description: Create a share with a company mention.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n    - name: event-subscriptions\n      path: /eventSubscriptions\n      description: Event subscription management.\n      operations:\n      - name: get-notifications\n        method: GET\n        description: Retrieve notifications for the authenticated member's organization.\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: false\n          description: Query type\n        - name: eventType\n          in: query\n          type: string\n          required: false\n          description: Event type filter\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: follower-statistics\n      path: /organizationalEntityFollowerStatistics\n      description: Organization follower statistics.\n      operations:\n      - name: get-follower-statistics\n        method: GET\n        description: Retrieve time-bound follower statistics.\n\
  \        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: false\n          description: Query type\n        - name: organizationalEntity\n          in: query\n          type: string\n          required: false\n          description: Organization URN\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: page-statistics\n      path: /organizationPageStatistics\n      description: Organization page statistics.\n      operations:\n      - name: get-page-statistics\n        method: GET\n        description: Retrieve lifetime page statistics.\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: false\n          description: Query type\n        - name: organization\n          in: query\n          type: string\n          required: false\n          description: Organization URN\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: share-statistics\n      path: /organizationalEntityShareStatistics\n      description: Organization share statistics.\n      operations:\n      - name: get-share-statistics\n        method: GET\n        description: Retrieve time-bound share statistics.\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: false\n          description: Query type\n        - name: organizationalEntity\n          in: query\n          type: string\n          required: false\n          description: Organization URN\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organizations\n      path: /organizations\n      description: Organization lookup.\n      operations:\n      - name: find-organization-brands\n        method: GET\n        description: Find\
  \ administered organization brands by parent org.\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: false\n          description: Query type\n        - name: parent\n          in: query\n          type: string\n          required: false\n          description: Parent organization URN\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organization-by-id\n      path: /organizations/{organization_id}\n      description: Organization lookup by ID.\n      operations:\n      - name: get-organization-by-id\n        method: GET\n        description: Look up organization by ID.\n        inputParameters:\n        - name: organization_id\n          in: path\n          type: string\n          required: true\n          description: Organization ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n    - name: network-sizes\n      path: /networkSizes/urn:li:organization:{organization_id}\n      description: Organization follower count.\n      operations:\n      - name: get-follower-count\n        method: GET\n        description: Retrieve organization follower count.\n        inputParameters:\n        - name: organization_id\n          in: path\n          type: string\n          required: true\n          description: Organization ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organization-acls\n      path: /organizationAcls\n      description: Organization access controls.\n      operations:\n      - name: find-organization-access-control\n        method: GET\n        description: Find organization access control.\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: false\n          description: Query type\n\
  \        - name: organization\n          in: query\n          type: string\n          required: false\n          description: Organization URN\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: people-typeahead\n      path: /peopleTypeahead\n      description: People search within organization followers.\n      operations:\n      - name: search-followers-by-keyword\n        method: GET\n        description: Search organization followers by keyword.\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: false\n          description: Query type\n        - name: keywords\n          in: query\n          type: string\n          required: false\n          description: Search keywords\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8081\n\
  \    namespace: content-community-api\n    description: Unified REST API for LinkedIn content creation and community management.\n    resources:\n    - path: /v1/posts\n      name: posts\n      operations:\n      - method: POST\n        name: create-post\n        description: Create a post.\n        call: marketing-content.create-post\n      - method: GET\n        name: get-posts\n        description: Fetch multiple posts.\n        call: marketing-content.get-posts\n    - path: /v1/shares\n      name: shares\n      operations:\n      - method: POST\n        name: create-share\n        description: Create a share with company mention.\n        call: marketing-community.create-share\n    - path: /v1/creatives\n      name: creatives\n      operations:\n      - method: POST\n        name: create-creative\n        description: Create an ad creative.\n        call: marketing-content.create-creative\n      - method: GET\n        name: search-creatives\n        description: Search for creatives.\n\
  \        call: marketing-content.search-creatives\n    - path: /v1/inmail-contents\n      name: inmail-contents\n      operations:\n      - method: POST\n        name: create-inmail-content\n        description: Create InMail content.\n        call: marketing-content.create-inmail-content\n    - path: /v1/conversation-ads\n      name: conversation-ads\n      operations:\n      - method: POST\n        name: create-sponsored-conversation\n        description: Create a sponsored conversation.\n        call: marketing-content.create-sponsored-conversation\n      - method: GET\n        name: get-sponsored-conversations\n        description: Get sponsored conversations.\n        call: marketing-content.get-sponsored-conversations\n    - path: /v1/images\n      name: images\n      operations:\n      - method: POST\n        name: initialize-image-upload\n        description: Initialize image upload.\n        call: marketing-content.initialize-image-upload\n    - path: /v1/videos\n      name: videos\n\
  \      operations:\n      - method: POST\n        name: initialize-video-upload\n        description: Initialize video upload.\n        call: marketing-content.initialize-video-upload\n    - path: /v1/organizations/{organization_id}\n      name: organization-by-id\n      operations:\n      - method: GET\n        name: get-organization-by-id\n        description: Look up organization by ID.\n        call: marketing-community.get-organization-by-id\n    - path: /v1/follower-statistics\n      name: follower-statistics\n      operations:\n      - method: GET\n        name: get-follower-statistics\n        description: Retrieve follower statistics.\n        call: marketing-community.get-follower-statistics\n    - path: /v1/page-statistics\n      name: page-statistics\n      operations:\n      - method: GET\n        name: get-page-statistics\n        description: Retrieve page statistics.\n        call: marketing-community.get-page-statistics\n  - type: mcp\n    port: 9091\n    namespace: content-community-mcp\n\
  \    transport: http\n    description: MCP server for AI-assisted LinkedIn content and community management.\n    tools:\n    - name: create-post\n      description: Create a post.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: marketing-content.create-post\n    - name: get-posts\n      description: Fetch multiple posts.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: marketing-content.get-posts\n    - name: create-share\n      description: Create a share with company mention.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: marketing-community.create-share\n    - name: create-creative\n      description: Create an ad creative.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: marketing-content.create-creative\n    - name: search-creatives\n      description:\
  \ Search for creatives.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: marketing-content.search-creatives\n    - name: create-inmail-content\n      description: Create InMail content.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: marketing-content.create-inmail-content\n    - name: get-inmail-content\n      description: Retrieve InMail content by ID.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: marketing-content.get-inmail-content\n    - name: create-sponsored-conversation\n      description: Create a sponsored conversation.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: marketing-content.create-sponsored-conversation\n    - name: initialize-image-upload\n      description: Initialize image upload.\n      hints:\n        readOnly: false\n        destructive:\
  \ false\n        idempotent: false\n      call: marketing-content.initialize-image-upload\n    - name: initialize-video-upload\n      description: Initialize video upload.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: marketing-content.initialize-video-upload\n    - name: initialize-document-upload\n      description: Initialize document upload.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: marketing-content.initialize-document-upload\n    - name: get-organization-by-id\n      description: Look up organization by ID.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: marketing-community.get-organization-by-id\n    - name: get-follower-statistics\n      description: Retrieve follower statistics.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: marketing-community.get-follower-statistics\n\
  \    - name: get-page-statistics\n      description: Retrieve page statistics.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: marketing-community.get-page-statistics\n    - name: get-share-statistics\n      description: Retrieve share statistics.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: marketing-community.get-share-statistics\n    - name: get-follower-count\n      description: Retrieve organization follower count.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: marketing-community.get-follower-count\n    - name: get-notifications\n      description: Retrieve social action notifications.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: marketing-community.get-notifications\n"
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
