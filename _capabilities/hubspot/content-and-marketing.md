---
categories:
- content-management
consumed_apis:
- blog-posts
- blog-authors
- analytics-events
- cms-pages
- domains
- marketing-email
description: Unified workflow for marketing managers to manage blog content, authors, landing pages, site pages, domains, analytics events, and transactional email. Combines CMS and marketing APIs into a single content operations interface.
layout: capability
name: HubSpot Content And Marketing
operations:
- description: List all blog posts
  method: GET
  name: list-blog-posts
  path: /v1/blog-posts
- description: Create a blog post
  method: POST
  name: create-blog-post
  path: /v1/blog-posts
- description: Get a blog post
  method: GET
  name: get-blog-post
  path: /v1/blog-posts/{objectId}
- description: Update a blog post
  method: PATCH
  name: update-blog-post
  path: /v1/blog-posts/{objectId}
- description: Archive a blog post
  method: DELETE
  name: archive-blog-post
  path: /v1/blog-posts/{objectId}
- description: List all blog authors
  method: GET
  name: list-blog-authors
  path: /v1/blog-authors
- description: Retrieve analytics events
  method: GET
  name: list-events
  path: /v1/events
- description: List available event types
  method: GET
  name: list-event-types
  path: /v1/event-types
personas: []
provider_name: HubSpot
provider_slug: hubspot
search_terms:
- update a blog post
- get a specific blog post by id
- crm
- archive blog post
- schedule blog post
- analytics
- list blog posts
- list all blog posts in hubspot
- get blog post
- push a draft blog post to live
- get a blog post
- schedule a blog post for publication
- list all blog posts
- marketing
- event type definitions
- update blog post
- blog
- clone an existing blog post
- clone blog post
- create a new blog post
- create a new blog author
- list events
- create blog post
- get blog author
- retrieve analytics event data for crm objects
- commerce
- email marketing
- individual blog post
- get blog post revisions
- create a blog post
- list blog authors
- cms
- analytics events
- list event types
- get a blog author by id
- marketing automation
- sales
- content
- update an existing blog post
- create blog author
- archive a blog post
- blog post management
- list available event types
- get revision history for a blog post
- retrieve analytics events
- push blog post live
- list available analytics event types
- customer service
- hubspot
- list all blog authors
- get event types
- get analytics events
- operations
- blog author management
slug: content-and-marketing
source_filename: content-and-marketing.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"HubSpot Content And Marketing\"\n  description: \"Unified workflow for marketing managers to manage blog content, authors, landing pages, site pages, domains, analytics events, and transactional email. Combines CMS and marketing APIs into a single content operations interface.\"\n  tags:\n    - HubSpot\n    - Marketing\n    - Content\n    - CMS\n    - Blog\n    - Analytics\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      HUBSPOT_ACCESS_TOKEN: HUBSPOT_ACCESS_TOKEN\n\ncapability:\n  consumes:\n    - import: blog-posts\n      location: ./shared/blog-posts.yaml\n    - import: blog-authors\n      location: ./shared/blog-authors.yaml\n    - import: analytics-events\n      location: ./shared/analytics-events.yaml\n    - import: cms-pages\n      location: ./shared/cms-pages-api.yaml\n    - import: domains\n      location: ./shared/domains-api.yaml\n    - import: marketing-email\n  \
  \    location: ./shared/marketing-emal-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: content-marketing-api\n      description: \"Unified REST API for content creation, publishing, and marketing analytics.\"\n      resources:\n        - path: /v1/blog-posts\n          name: blog-posts\n          description: \"Blog post management\"\n          operations:\n            - method: GET\n              name: list-blog-posts\n              description: \"List all blog posts\"\n              call: \"blog-posts.list-blog-posts\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-blog-post\n              description: \"Create a blog post\"\n              call: \"blog-posts.create-blog-post\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/blog-posts/{objectId}\n          name: blog-post-by-id\n\
  \          description: \"Individual blog post\"\n          operations:\n            - method: GET\n              name: get-blog-post\n              description: \"Get a blog post\"\n              call: \"blog-posts.get-blog-post\"\n              with:\n                objectId: \"rest.objectId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PATCH\n              name: update-blog-post\n              description: \"Update a blog post\"\n              call: \"blog-posts.update-blog-post\"\n              with:\n                objectId: \"rest.objectId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: archive-blog-post\n              description: \"Archive a blog post\"\n              call: \"blog-posts.archive-blog-post\"\n              with:\n                objectId: \"rest.objectId\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n        - path: /v1/blog-authors\n          name: blog-authors\n          description: \"Blog author management\"\n          operations:\n            - method: GET\n              name: list-blog-authors\n              description: \"List all blog authors\"\n              call: \"blog-authors.list-blog-authors\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/events\n          name: events\n          description: \"Analytics events\"\n          operations:\n            - method: GET\n              name: list-events\n              description: \"Retrieve analytics events\"\n              call: \"analytics-events.get-event-instances\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/event-types\n          name: event-types\n          description: \"Event type definitions\"\n    \
  \      operations:\n            - method: GET\n              name: list-event-types\n              description: \"List available event types\"\n              call: \"analytics-events.get-event-types\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: content-marketing-mcp\n      transport: http\n      description: \"MCP server for AI-assisted content creation, blog management, and marketing analytics.\"\n      tools:\n        - name: list-blog-posts\n          description: \"List all blog posts in HubSpot\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"blog-posts.list-blog-posts\"\n          with:\n            limit: \"tools.limit\"\n            after: \"tools.after\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-blog-post\n          description: \"Get a specific blog post\
  \ by ID\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"blog-posts.get-blog-post\"\n          with:\n            objectId: \"tools.objectId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-blog-post\n          description: \"Create a new blog post\"\n          hints:\n            readOnly: false\n          call: \"blog-posts.create-blog-post\"\n          with:\n            name: \"tools.name\"\n            contentGroupId: \"tools.contentGroupId\"\n            postBody: \"tools.postBody\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-blog-post\n          description: \"Update an existing blog post\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"blog-posts.update-blog-post\"\n          with:\n            objectId: \"tools.objectId\"\n            name: \"tools.name\"\
  \n            postBody: \"tools.postBody\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: schedule-blog-post\n          description: \"Schedule a blog post for publication\"\n          hints:\n            readOnly: false\n          call: \"blog-posts.schedule-blog-post\"\n          with:\n            id: \"tools.id\"\n            publishDate: \"tools.publishDate\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: clone-blog-post\n          description: \"Clone an existing blog post\"\n          hints:\n            readOnly: false\n          call: \"blog-posts.clone-blog-post\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: push-blog-post-live\n          description: \"Push a draft blog post to live\"\n          hints:\n            readOnly: false\n          call: \"blog-posts.push-blog-post-live\"\
  \n          with:\n            objectId: \"tools.objectId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-blog-authors\n          description: \"List all blog authors\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"blog-authors.list-blog-authors\"\n          with:\n            limit: \"tools.limit\"\n            after: \"tools.after\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-blog-author\n          description: \"Get a blog author by ID\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"blog-authors.get-blog-author\"\n          with:\n            objectId: \"tools.objectId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-blog-author\n          description: \"Create a new blog author\"\n          hints:\n\
  \            readOnly: false\n          call: \"blog-authors.create-blog-author\"\n          with:\n            name: \"tools.name\"\n            email: \"tools.email\"\n            bio: \"tools.bio\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-analytics-events\n          description: \"Retrieve analytics event data for CRM objects\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"analytics-events.get-event-instances\"\n          with:\n            objectType: \"tools.objectType\"\n            objectId: \"tools.objectId\"\n            eventType: \"tools.eventType\"\n            occurredAfter: \"tools.occurredAfter\"\n            occurredBefore: \"tools.occurredBefore\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-event-types\n          description: \"List available analytics event types\"\n          hints:\n    \
  \        readOnly: true\n            idempotent: true\n          call: \"analytics-events.get-event-types\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: archive-blog-post\n          description: \"Archive a blog post\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"blog-posts.archive-blog-post\"\n          with:\n            objectId: \"tools.objectId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-blog-post-revisions\n          description: \"Get revision history for a blog post\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"blog-posts.get-blog-post-revisions\"\n          with:\n            objectId: \"tools.objectId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/hubspot/refs/heads/main/capabilities/content-and-marketing.yaml
tags:
- HubSpot
- Marketing
- Content
- CMS
- Blog
- Analytics
tools:
- description: List all blog posts in HubSpot
  hints:
    idempotent: true
    readOnly: true
  name: list-blog-posts
- description: Get a specific blog post by ID
  hints:
    idempotent: true
    readOnly: true
  name: get-blog-post
- description: Create a new blog post
  hints:
    readOnly: false
  name: create-blog-post
- description: Update an existing blog post
  hints:
    idempotent: true
    readOnly: false
  name: update-blog-post
- description: Schedule a blog post for publication
  hints:
    readOnly: false
  name: schedule-blog-post
- description: Clone an existing blog post
  hints:
    readOnly: false
  name: clone-blog-post
- description: Push a draft blog post to live
  hints:
    readOnly: false
  name: push-blog-post-live
- description: List all blog authors
  hints:
    idempotent: true
    readOnly: true
  name: list-blog-authors
- description: Get a blog author by ID
  hints:
    idempotent: true
    readOnly: true
  name: get-blog-author
- description: Create a new blog author
  hints:
    readOnly: false
  name: create-blog-author
- description: Retrieve analytics event data for CRM objects
  hints:
    idempotent: true
    readOnly: true
  name: get-analytics-events
- description: List available analytics event types
  hints:
    idempotent: true
    readOnly: true
  name: get-event-types
- description: Archive a blog post
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: archive-blog-post
- description: Get revision history for a blog post
  hints:
    idempotent: true
    readOnly: true
  name: get-blog-post-revisions
---
